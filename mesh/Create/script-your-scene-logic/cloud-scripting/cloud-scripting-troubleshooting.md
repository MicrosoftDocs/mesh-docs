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

### Environment Upload Failed

If a Mesh Cloud Scripting stage during the Uploader process failed and the error shown is "Check the logs for more information", make sure Info logs are being shown in the Unity console.Currently some errors are shown as info logs. This will be improved in a future release.

### Mesh Cloud Scripting Package Installation Failed
1. If you encounter errors related to package installation or dotnet tool installation (`The tool package could not be restored` or `Verify your unity package integrity`), verify that you don't have non-valid package sources in your global nuget config (under `c:\users\UserName\AppData\Roaming\nuget\nuget.config` or default nuget config directory which is configured on the machine)
1. If you encounter `package is already installed` error when starting Play Mode, exiting Play Mode and starting it again should mitigate that
1. Verify access rights on directory `Assets\.MeshCloudScripting\.Packages`


### After pressing play in Unity, nothing happens

1. Check Unity logs for any errors. In particular, if your Mesh Cloud Scripting code has a compile error, you'll see "Cloud Scripting build failed" in your error log. In this case, open the csproj file for your Mesh Cloud Scripting and fix the errors (if you build from Visual Studio, it'll show you the errors more conveniently in the build output).
1. If there are other errors, review this document for additional troubleshooting information on particular errors.
1. If there are no errors, there might be runtime errors in your Mesh Cloud Scripting code. Attach to your application with the debugger and inspect the output for any errors.
1. If nothing helps, [report a bug](#how-to-report-issues).

### When joining an event in the Microsoft Mesh application, the Mesh Cloud Scripting doesn't work

1. Ensure that the scene plays as expected when you preview it locally in Unity.
2. Ensure that the deployed environment matches the scene.map used by the Mesh App. To learn more about how this happens, see [the Mesh Scripting Getting Started Guide](Mesh_Scripting_Getting_Started_Guide.md#serialize-scene). TBD
    1. In the Unity project, navigate to the **Mesh Cloud Scripting** component and then press `Serialize Scene` to force scene graph serialization.
    1. Re-upload your environment with the Mesh Uploader.
1. Test your local Unity version [against the deployed app](cloud-scripting-getting-started.md#connect-to-the-cloud-scripting-service-from-unity).
   - Check the logs in Unity for any errors if not working.
1. If nothing helps, [report a bug](#how-to-report-issues).
   - Inspect [Mesh Cloud Scripting logs](#how-to-collect-logs), and include relevant information where possible in your bug report.

### Clicks aren't received
Mesh Scripting
1. It's possible that your Mesh Cloud Scripting Service is sending messages at too high a frequency for the system to handle.  In this case, your click might actually be received but, due to a large backlog of messages, it takes a long time for the result to be propagated back to the client. Try temporarily disabling your high frequency update code to see if this fixes the problem. If it does, consider moving to drive Unity Animators instead of updating properties from Mesh Cloud Scripting.
1. If nothing helps, [report a bug](#how-to-report-issues).

### Unity freezes after you press Play
If you switch focus from Unity to another app while Unity is playing, the Mesh Cloud Scripting Service continues to run, submitting messages to the message queue. When you switch focus back to Unity, it pauses until it completely drains the queue. If the Mesh Cloud Scripting Service is making lots of frequent state changes and/or you've switched focus away from Unity for a long time, Unity can freeze for some time while this happens.

## How to collect logs
### Collecting Unity logs
Before reporting an issue, set the Verbosity to Diagnostic.

![Diagnostic Log Configuration](../../media/mesh-scripting/troubleshooting/configure_diagnostic_unity_logging.png)

Reproduce the issue, and then send the Unity logs. You can find the log file using the Unity menu, which is stored by default at `%LOCALAPPDATA%\Unity\Editor\Editor.log`.

![Collect Unity Logs](../../media/mesh-scripting/troubleshooting/collect_unity_logs.png)

### Collecting client logs from the Microsoft Mesh application
Configure the PC client logs by creating a file on the Desktop named "startup_settings.json" with the following content:
```
{
  "use_startup_settings": true,
  "log_groups": [
    { "name": "CloudScriptingClientSDK", "level": "Debug" },
    { "name": "CloudScriptingUnityRuntime", "level": "Debug" }
  ]
}
```

Reproduce the issue, and then share the Unity logs. Microsoft Mesh application logs can be found at `%USERPROFILE%\AppData\LocalLow\Microsoft Corporation\Microsoft Mesh\player.log`

### Collecting server logs
#### **A. Log Stream**
To see logs from the Mesh Cloud Scripting Service, in the **Monitoring** section of the AppService resource, click the **Log Stream** menu to see logs from the container, as shown in the image below.

![Log Stream Select](../../media/mesh-scripting/troubleshooting/log_stream_select.png 'Log Stream Select')

If you prefer, you can tail these same logs from your local machine by running the following command in your terminal:

```az webapp log tail --name <APP_SERVICE_NAME> --resource-group <RESOURCE_GROUP_NAME>```

You can also download log files from the hosted app service by going to the Advanced Tools (Kudu). 

![Kudu](../../media/mesh-scripting/troubleshooting/kudu.png 'Kudu')

Under **Development Tools” >> Advanced Tools >> Go**. The SCM website opens and you can download the Docker logs as a zip file, as shown below.

<!-- Is there supposed to be an image here? -->

#### **B. Azure Monitor**
Alternatively, using Azure Monitor, you could write KQL (Kusto Query Language) queries to pick out logs that you're particularly interested in from events, time ranges and more. This would be automatically set up for you if you checked the "Enable App Monitoring" box during deployment. If not, see the [manual setup for Azure Monitor](#manual-setup-for-azure-monitor-optional) section to configure Azure Monitor for your deployment.

To use this, in the **Monitoring** section of the navigation pane, select **Logs**. 

![AppService Monitoring](../../media/mesh-scripting/troubleshooting/appservice_monitoring.png 'AppService Monitoring')

In the query Monitoring pane, you can select the logs you’re interested in. At the time of writing, we have “AppServiceConsoleLogs”, “AppServiceHTTPLogs”, “AppServiceAppLogs” and “AppServicePlatformLogs”. To view the logs from the Docker container, you may find the logs in “AppServiceAppLogs” and/or “AppServiceConsoleLogs” more useful.

![Azure Monitoring Pane](../../media/mesh-scripting/troubleshooting/azure_monitoring_pane.png 'Azure Monitoring Pane')

##### **Manual Setup for Azure Monitor (Optional)**

Skip if you checked "Enable App Monitoring" during deployment.

A Log Analytics workspace is required for this setup. If you don't have an existing workspace, follow the official [guide](https://learn.microsoft.com/en-us/azure/azure-monitor/logs/quick-create-workspace?tabs=azure-portal).

1. Open Azure Portal and navigate to the AppService resource in which your Mesh Cloud Scripting Service is running.
2. Click the "Monitoring" tab and scroll to the bottom of the page. Click the "Configure Azure Monitor" button

    ![AppService Monitoring Tab](../../media/mesh-scripting/troubleshooting/appservice_monitoring_tab.png 'AppService Monitoring Tab')

3. Click the link "+ Add diagnostic setting" to set the log categories that would be sent to your chosen workspace.

    ![Diagnostic Settings](../../media/mesh-scripting/troubleshooting/diagnostic_settings.png 'Diagnostic Settings')

4. In the prompt, fill the "Diagnostic setting name" field, select the log categories you are interested in (ex. App Service Console Logs, App Service Application Logs, etc), check the box to "Send to Log Analytics workspace" and then, select your preferred existing Log Analytics workspace.

    ![Create Diagnostic Setting](../../media/mesh-scripting/troubleshooting/create_diagnostic_settings.png 'Create Diagnostic Setting')

5. Finally, enable Application Insights from the App Service page. This would ensure logs are propagated to the Log Analytics workspace.
![Enable App Insights](../../media/mesh-scripting/troubleshooting/appservice_enable_insights_link.png 'Enable App Insights')

6. Fill the form, and be sure to point it to the same workspace in which your Diagnostic Setting was created.

    ![App Insights Form](../../media/mesh-scripting/troubleshooting/appservice_app_insights_form.png 'App Insights Form')

7. Restart your AppService and wait a couple of minutes. You should now be able to query logs in Azure Monitor as described in the section [Azure Monitor](#b-azure-monitor).

## How to report issues

1. [Collect](#how-to-collect-logs) all the logs available.
1. Follow [feedback](../../Resources/feedback.md) guidance.

## Next steps

> [!div class="nextstepaction"]
> [visual scripting](visual-scripting.md)