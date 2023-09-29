---
title: Cloud scripting troubleshooting
description: Learn how to troubleshoot certain issues with Cloud Scripting for Mesh.
author: typride
ms.author: vinnietieto
ms.date: 8/28/2023
ms.topic: Guide
keywords: Microsoft Mesh, scripting, cloud scripting, visual scripting, coding, troubleshooting, problems
---

# Cloud Scripting Troubleshooting

## Toolkit Uploader Extension

### Environment Upload Failed

If a Mesh App stage during the Uploader process failed and the error shown is "Check the logs for more information", make sure Info logs are being shown in the Unity console.Currently some errors are shown as info logs. This will be improved in a future release.

### Mesh App Package Installation Failed
1. If you encounter errors related to package installation or dotnet tool installation (`The tool package could not be restored` or `Verify your unity package integrity`), verify that you don't have non-valid package sources in your global nuget config (under `c:\users\UserName\AppData\Roaming\nuget\nuget.config` or default nuget config directory which is configured on the machine)
2. If you encounter `package is already installed` error when starting Play Mode, exiting Play Mode and starting it again should mitigate that
3. Verify access rights on directory `Assets\.MeshApps\.Packages`

### Mesh App Deploy & Publish Fails Due to Incorrect Azure Account being used.
If you use multiple Azure accounts for deploying and publishing to multiple tenants, you will need to logout between environment publishing runs.
1. Use the Toolkit Uploader with the Mesh Scripts extension to deploy and publish the first environment.
2. Open a command line and run `az logout` to log out of the cached Azure account.
3. Use the Toolkit Uploader again to deploy and publish the next environment, expecting a popup asking you to log-in to your Azure account.

## After running `meshapp publish`, nothing happens
This error has been identified to be a build error.
1. Use `Ctrl + C` to exit the command's execution.
2. Rerun the command with the dotnet verbosity flag: `meshapp publish -v normal`. If logs still aren't informative enough to debug, increase the verbosity to `detailed` or `diagnostic`.
3. If build errors occurred, resolve them by doing the following:
   1. Open the csproj file for your Mesh App, then clean the project, and then rebuild it.
   2. Rerun the `meshapp publish` command.

## After pressing play in Unity, nothing happens

1. Check Unity logs for any errors. In particular, if your Mesh App code has a compile error, you'll see "Mesh App build failed" in your error log. In this case, open the csproj file for your Mesh App and fix the errors (if you build from Visual Studio, it'll show you the errors more conveniently in the build output).
2. If there are other errors, review this document for additional troubleshooting information on particular errors.
3. If there are no errors, there might be runtime errors in your Mesh App code. Attach to your application with the debugger and inspect the output for any errors.
4. If nothing helps, [report a bug](#how-to-report-bugs).

## When joining an event in the Mesh app, the app doesn't play

1. Ensure that the scene plays as expected when you preview it locally.
2. Ensure that the deployed environment matches the scene.map used by the Mesh App. To learn more about how this happens, see [the Mesh Scripting Getting Started Guide](Mesh_Scripting_Getting_Started_Guide.md#serialize-scene). TBD
    1. In the Unity project, navigate to the **MeshApp** component and then press `Serialize Scene` to force scenegraph serialization.
    2. Re-upload your environment with the Mesh Uploader.
    3. Re-deploy your Mesh App with the [CLI tool](Mesh_Scripting_Getting_Started_Guide.md#deploy-application-and-interactive-world-template).
3. Test your local Unity version [against the deployed app](Mesh_Scripting_Getting_Started_Guide.md#connect-to-deployed-application-from-unity).
   - Check the logs in Unity for any errors if not working.
4. You may need to manually restart the Mesh App to ensure that it's running correctly. From the root of the project, run `meshapp restart`, and then wait for the process to complete.
5. If nothing helps, [report a bug](#how-to-report-bugs).
   -Inspect [Mesh app logs](#how-to-collect-logs), and include relevant information where possible in your bug report.

## Clicks aren't received
Mesh Scripting
1. The TouchSensor will watch for clicks on any colliders on the same game object or any of its children. Ensure that colliders are in place.
2. It's possible that your Mesh app is sending messages at too high a frequency for the system to handle.  In this case,  your click might actually be received but, due to a large backlog of messages, it takes a long time for the result to be propagated back to the client. Try temporarily disabling your high frequency update code to see if this fixes the problem.  If it does, consider moving to drive Unity Animators instead of updating properties from your Mesh App.
3. If nothing helps, [report a bug](#how-to-report-bugs).

## Unity freezes after you press Play
If you switch focus from Unity to another app while Unity is playing, the Mesh App continues to run, submitting messages to the message queue. When you switch focus back to Unity, it pauses until it completely drains the queue. If the mesh app is making lots of frequent state changes and/or you've switched focus away from Unity for a long time, Unity can freeze for some time while this happens.

## How to collect logs
### Collecting Unity logs
Before reporting an issue, set the Verbosity to Diagnostic.

![Diagnostic Log Configuration](../../../media/mesh-scripting/troubleshooting/configure_diagnostic_unity_logging.png)

Reproduce the issue, and then send the Unity logs. You can find the log file using the Unity menu, which is stored by default at `%LOCALAPPDATA%\Unity\Editor\Editor.log`.

![Collect Unity Logs](../../../media/mesh-scripting/troubleshooting/collect_unity_logs.png)

### Collecting client logs from the Mesh app
Configure the PC client logs by creating a file on the Desktop named "startup_settings.json" with the following content:
```
{
  "use_startup_settings": true,
  "log_groups": [
    { "name": "MeshAppManager", "level": "Debug" },
    { "name": "MeshAppClientSDK", "level": "Debug" },
    { "name": "MeshAppUnityRuntime", "level": "Debug" }
  ]
}
```

Reproduce the issue, and then send the Unity logs. Mesh app logs can be found at `%USERPROFILE%\AppData\LocalLow\Microsoft Corporation\Microsoft Mesh\player.log`

Logs can also be automatically collected and reported with an issue by using the "Feedback to Microsoft" feature; however, for this release, we recommend that you manually report to the Teams channel.

### Collecting server logs
#### **A. Log Stream**
To see logs from the app, in the **Monitoring** section of the AppService resource, click the **Log Stream** menu to see logs from the container, as shown in the image below.

![Log Stream Select](../../../media/mesh-scripting/troubleshooting/log_stream_select.png 'Log Stream Select')

If you prefer, you can tail these same logs from your local machine by running the following command in your terminal:

```az webapp log tail --name <APP_SERVICE_NAME> --resource-group <RESOURCE_GROUP_NAME>```

You can also download log files from the hosted app service by going to the Advanced Tools (Kudu). 

![Kudu](../../../media/mesh-scripting/troubleshooting/kudu.png 'Kudu')

Under **Development Tools” >> Advanced Tools >> Go**. The SCM website opens and you can download the Docker logs as a zip file, as shown below.

<!-- Is there supposed to be an image here? -->

#### **B. Azure Monitor**
Alternatively, using Azure Monitor, you could write KQL (Kusto Query Language) queries to pick out logs that you're particularly interested in from events, time ranges and more. This would be automatically set up for you if you checked the "Enable App Monitoring" box during deployment. If not, see the [manual setup for Azure Monitor](#manual-setup-for-azure-monitor-optional) section to configure Azure Monitor for your deployment.

To use this, in the **Monitoring** section of the navigation pane, select **Logs**. 

![AppService Monitoring](../../../media/mesh-scripting/troubleshooting/appservice_monitoring.png 'AppService Monitoring')

In the query Monitoring pane, you can select the logs you’re interested in. At the time of writing, we have “AppServiceConsoleLogs”, “AppServiceHTTPLogs”, “AppServiceAppLogs” and “AppServicePlatformLogs”. To view the logs from the Docker container, you may find the logs in “AppServiceAppLogs” and/or “AppServiceConsoleLogs” more useful.

![Azure Monitoring Pane](../../../media/mesh-scripting/troubleshooting/azure_monitoring_pane.png 'Azure Monitoring Pane')

In the textbox provided on the right-hand side of the **Tables** menu, type in the following KQL query:

```
AppServiceConsoleLogs
| extend newLog = iif(
ResultDescription has ": Orleans.LifecycleSubject"
or ResultDescription has ": Orleans.Runtime.Catalog"
or ResultDescription has ": Microsoft.Hosting.Lifetime"
or ResultDescription has ": Microsoft.MeshApps.Dom.CloudApplication"
or ResultDescription has ": Microsoft.SceneAppService.Launcher.MeshAppInstance"
or ResultDescription has ": Microsoft.SceneAppService.Core.NamedPipesMeshAppSessionGrain"
or ResultDescription has ": Microsoft.MeshApps.Cloud.Middleware.CloudMeshAppHub"
or ResultDescription has "UNOBSERVED EXCEPTION:"
or ResultDescription has ": Microsoft.SceneAppService.SceneAppHub"
or ResultDescription has ": Microsoft.SceneAppService.Core.NamedPipesMeshAppSessionGrain"
or ResultDescription has ": Microsoft.SceneAppService.Launcher.MeshAppInstanceFactory"
or ResultDescription has ": Microsoft.ClientChannel.Hosting.ProcessLifecycleLoggers"
or ResultDescription has ": Microsoft.MeshApps.Services.ApplicationWorkDispatcher"
or ResultDescription has ": Microsoft.MeshApps.Services.MeshAppHostedService"
or ResultDescription has ": Microsoft.SceneAppService.Launcher.MeshAppPreparationService"
or ResultDescription has ": Microsoft.MeshApps.Cloud.Middleware.MeshAppProcessFactory"
or ResultDescription has ": Microsoft.ClientChannel.Resources.ClientLinkGrain"
, 1, 0)
| sort by TimeGenerated asc
| extend logId = row_cumsum(newLog) 
| summarize ResultDescription=make_list(ResultDescription), TimeGenerated=min(TimeGenerated) by logId
| extend ResultDescription = strcat_array(ResultDescription, "")
| sort by TimeGenerated desc
| project TimeGenerated, ResultDescription
| where not (ResultDescription has "Broadcasting data of size")
```

![Azure Monitoring Input Field](../../../media/mesh-scripting/troubleshooting/azure_monitoring_input_field.png 'Azure Monitoring Input Field')

Export data to csv.

![Azure Monitoring Export](../../../media/mesh-scripting/troubleshooting/azure_monitoring_export_csv.png 'Azure Monitoring Export')

##### **Manual Setup for Azure Monitor (Optional)**

Skip if you checked "Enable App Monitoring" during deployment.

A Log Analytics workspace is required for this setup. If you don't have an existing workspace, follow the official [guide](https://learn.microsoft.com/en-us/azure/azure-monitor/logs/quick-create-workspace?tabs=azure-portal).

1. Open Azure Portal and navigate to the AppService resource in which your MeshApp is running.
2. Click the "Monitoring" tab and scroll to the bottom of the page. Click the "Configure Azure Monitor" button

    ![AppService Monitoring Tab](../../../media/mesh-scripting/troubleshooting/appservice_monitoring_tab.png 'AppService Monitoring Tab')

3. Click the link "+ Add diagnostic setting" to set the log categories that would be sent to your chosen workspace.

    ![Diagnostic Settings](../../../media/mesh-scripting/troubleshooting/diagnostic_settings.png 'Diagnostic Settings')

4. In the prompt, fill the "Diagnostic setting name" field, select the log categories you are interested in (ex. App Service Console Logs, App Service Application Logs, etc), check the box to "Send to Log Analytics workspace" and then, select your preferred existing Log Analytics workspace.

    ![Create Diagnostic Setting](../../../media/mesh-scripting/troubleshooting/create_diagnostic_settings.png 'Create Diagnostic Setting')

5. Finally, enable Application Insights from the App Service page. This would ensure logs are propagated to the Log Analytics workspace.
![Enable App Insights](../../../media/mesh-scripting/troubleshooting/appservice_enable_insights_link.png 'Enable App Insights')

6. Fill the form, and be sure to point it to the same workspace in which your Diagnostic Setting was created.

    ![App Insights Form](../../../media/mesh-scripting/troubleshooting/appservice_app_insights_form.png 'App Insights Form')

7. Restart your AppService and wait a couple of minutes. You should now be able to query logs in Azure Monitor as described in the section [Azure Monitor](#b-azure-monitor).

## How to report bugs

1. [Gather](#how-to-collect-logs) all the logs available.
1. Report through the appropriate channel on Teams.

## Next steps

> [!div class="nextstepaction"]
> [Cloud scripting known issues](cloud-scripting-known-issues.md)