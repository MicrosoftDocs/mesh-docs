---
title: Cloud scripting release notes
description: Review the release notes for Cloud Scripting for Mesh.
author: typride
ms.author: vinnietieto
ms.date: 9/27/2023
ms.topic: Guide
keywords: Microsoft Mesh, scripting, cloud scripting, visual scripting, coding, troubleshooting, problems
---

# Cloud Scripting Release Notes

## Release 27 Sept 2023
### Versions
|Component|Version|
|-|-|
| MeshApps Dom .NET SDK        |9.23124.8|
| MeshApp CLI tool             |1.0.2309.2301|
 
### Features
- Added support for mesh interactables.  Travel to TravelPoints and TravelPointGroups, replace your TouchSensors with MeshInteractables, and use AvatarAnchor and AvatarTether for higher quality moving platform support.

- The `Microsoft.MeshApps.Dom` `Vector2f`, `Vector3f`, `Vector4f` and `Matrix4f` have been replaced with their `System.Numerics` equivalents, namely `Vector2`, `Vector3`, `Vector4` and `Matrix4x4`.

- The Unity `MeshApp` component has been renamed to `MeshCloudScripting`. As well, its default parent game object name is now `Mesh Cloud Scripting`. Select **GameObject** > **Mesh Toolkit** > **Set-up Cloud Scripting** on the menu bar to add a `Mesh Cloud Scripting` component to your scene. 

### Bug Fixes

### Upgrade instructions
- When upgrading the mesh toolkit package, you should remove the reference to the old package, and them make the following renames:
  - Copy the contents of `Assets/MeshApps` into `Assets/MeshToolkit`
    - Rename the moved file `mesh_apps_manager_settings.asset` to `mesh_cloud_scripting_settings.asset` (and accompanying .meta file)
    - Rename the moved file `MeshAppPublishSettings.asset` to `mesh_cloud_scripting_publish_settings.asset` (and accompanying .meta file)
    - Rename the moved file `MeshAppPublishSettings.json` to `mesh_cloud_scripting_publish_settings.json` (and accompanying .meta file)
  - Rename the `Assets/.MeshApps` folder to `Assets/.MeshCloudScripting`
    - For every mesh cloud script within that folder, update the manifest file name from `meshapp.manifest.json` to `mesh.cloudscripting.manifest.json`
- Once these renames are made, add the new mesh toolkit package reference, and make the following fixes to the project:

  - Any TouchSensor in your Unity scenes and prefabs will no longer resolve and must be removed.  You should add MeshInteractableSetup to any node that you want to listen for Select events on.  Replace the usage of TouchSensorNode in your code with InteractableNode, and use the Selected event instead of the Clicked event.

  - The Avatar.TeleportTo methods has been replaced with Avatar.TravelTo(TravelPointNode|TravelPointGroupNode).  Place TravelPointGroup and TravelPoint in your scene to indicate the desired destination, facing and other travel properties.

  - The Avatar.AttachToMovingPlatform method has been removed.  Attachment to and detachment from moving platforms is now automatically handled using AvatarAnchor, and requires no scripting.

  - The `Microsoft.MeshApps.Dom` namespace has been renamed to `Microsoft.Mesh.CloudScripting` - update all references in Mesh cloud scripts.

  - Replace all occurences of `Vector2f`, `Vector3f`, `Vector4f` and `Matrix4f` originally in the `Microsoft.MeshApps.Dom` namespace with their `System.Numerics` equivalents, namely `Vector2`, `Vector3`, `Vector4` and `Matrix4x4`.

  - The `Application` class and its implementations have been made internal. Replace `Application` by `IApplication` and `CloudApplication` by `ICloudApplication` in your code.

  - The `Application.User` has been removed. As well, `Avatar.MovingPlatformChanged`, `Node.ClientActiveStateChanged`, `User.IsSuperUser` and `SceneNode.MessageDisplayed` have also been removed.

  - The `Application.Logger` property has been removed. You can use Dependency Injection and capture an additional `ILogger` at the same location where you capture the `Application` object.

  - Rename `UserStateChangedEventArgs` to `ParticipantStateChangedEventArgs`. Replace the `UserStateChanged` event in `CloudApplication` with `ParticipantStateChanged`. The type delegate associated with this event was also renamed from `UserStateChangedEventHandler` to `ParticipantStateChangedEventHandler`, so you'll need to update your code accordingly.

  - Rename `DomObject` to `CloudObject`. Rename `DomObjectCreated` to  `CloudObjectCreated`. Rename `DomObjectDisposed` to `CloudObjectDisposed`. Rename `DomObjectPropertyChanged` to `CloudObjectPropertyChanged`.

  - Rename `User` to `Participant`. `Node.SetActiveForUser(s)` to `SetActiveForParticipant(s)`. Rename `Node.GetActiveForUser` to `GetActiveForParticipant`. Rename `Node.GetActiveInHierarchyForUser` to `GetActiveInHierarchyForParticipant`. Rename `SceneNode.GetAvatarForUser` to `GetAvatarForParticipant`.

  - Rename `Avatar.TravelTo` to `TravelToUri`.

  - The `TimeStamp` type has been removed in favor of just using the `long` and `System.DateTime` built-ins.

  - The `Matrix3d`, `Matrix3f`, `Matrix4d` and `Vector2d`, `Vector3d`, `Vector4d` types have been removed. 

  - The `DomObject` property accessors have been refactored to go through a string-based indexer. Property getters should be refactored to `(<property_type>)cloudObject[<property_name>]`. Property setters should be refactored to `cloudObject[<property_name>].SetValue()`.

  - The `AddCloudMeshApplication` method has been renamed to `AddCloudScriptingApplication`.

  - In the `appsettings.Development.json` file replace `Microsoft.MeshApps` property names to `Microsoft.Mesh.CloudScripting`. The same change should be applied to `appsettings.Production.json` file.

  - In the `Directory.Packages.props` file update the following values PackageReference `Microsoft.MeshApps.Dom.NET` should point now to `Microsoft.Mesh.CloudScripting`.

## Release 31 Aug 2023
### Versions
|Component|Version|
|-|-|
| MeshApps Dom .NET SDK        |7.23113.1|
| MeshApp CLI tool             |1.0.2308.2801|

### Features
- Updated package and samples for Unity 2022.3.7f1.
- Moved to a per-environment deployment configuration workflow. The deployment configuration is associated with environment and configured from the MeshUploader UI now. See the Getting Started guide for the latest workflow.

### Bug Fixes

### Upgrade instructions
- To use the global deployment configuration previously set in the project setting in Unity Editor, select the enviorment and scene in the MeshUploader "Update Enviroment" Tab, select the "Modify Deployment Configs" tickbox and subsquently select the "Use Legacy Configs From Assets" option. This should apply the legacy global deployment configuration to the environment and scene.

**_Upgrade the Mesh App C# project_**

Rename WebViewNode to WebSlateNode

## Release 10 Aug 2023
 
### Versions
|Component|Version|
|-|-|
| MeshApps Dom .NET SDK        |6.23101.6|
| MeshApp CLI tool             |1.0.2307.2401|
 
### Features

### Bug Fixes
- Fixed a bug where scaling a deployed MeshApp's App Service resource horizontally to more than one instance causes the MeshApp to become unreachable.
- Fixed "No implementation of IHostEnvironmentStatistics was found. Load shedding will not work yet." Unity Warnings.

### Upgrade instructions

## Release 20 Jul 2023
 
### Versions
|Component|Version|
|-|-|
| MeshApps Dom .NET SDK        |6.23093.6|
| MeshApp CLI tool             |1.0.2307.701|
 
### Features
- The authentication mode is now exposed in the Mesh Scripts deployment configuration in Unity (**Edit** > **Project settings** > **Mesh Uploader Settings** > **Extensions** > **MeshApp Cloud Host tool** > **Deployment Configuration** >**Mode**). As auth is now enabled on the MeshApp server by default, it would expect you to send an auth token from whichever client you're connecting from. You can set the auth mode from the Mesh Uploader Settings located in your Unity project's settings. The **Dev** option is recommended for MeshApps in active development.
- Removed support for deploying MeshApps to the following Azure regions:
  - centraluseuap
  - eastus2euap
  - germanynorth
  - westcentralus
  - westindia
  
    > ![NOTE]
    > These regions aren't currently supported because deploying the MeshApp's Application Insights Azure resource isn't supported in those locations.

### Bug Fixes
- Fixed a bug where `meshapp.manifest.json` is being locked by another process bug during deployment.
- Fixed a bug where Unity's `Reload Assemblies` process was being held up by the initialization of telemetry.

### Upgrade instructions

## Release 29 Jun 2023

### Versions
|Component|Version|
|-|-|
| MeshApps Dom .NET SDK        |5.23083.4|
| MeshApp CLI Tool             |1.0.2306.1402|

### Features
- The serialized scene file `scene.json` has been replaced by `scene.map` to reflect the change in file format from JSON to binary.
- Updated Unity target to 2021.3.21f1

### Bug Fixes
- Fixed an issue with the Mesh Scripts Cloudhost uploader extension that would redeploy even if the version appeared to be identical.
- Fixed a null reference exception bug in DomBinding functions. 

### Upgrade instructions

**_Upgrade the Unity project_**

- Navigate to the **MeshApp** component and then press `Serialize Scene` to serialize the scene graph through the new file format.

**_Upgrade the Mesh App C# project_**

- Open the `.csproj` file of your application, find the block that copies the `scene.json` and update it to read:
```xml
    <EmbeddedResource Include="scene.map" CopyToOutputDirectory="PreserveNewest" />
```

- Remove the `scene.json` file.

## Release 08 Jun 2023
 
### Versions
|Component|Version|
|-|-|
| MeshApps Dom .NET SDK        |4.2307.1|
| MeshApp CLI Tool             |1.0.2305.2502|

### Features
### Bug Fixes
- MeshApp Connected / Disconnected UI Toasts are now hidden in MeshBrowser.
- Fixed Mesh Scripts Cloud Host Uploader Extension sometimes hanging trying to install Cloud Host to Unity project.
- Fixed Mesh Scripts Cloud Host Uploader Extension installing cloud host and performing checks when an environment without a meshapp was being published.

### Upgrade instructions
- This release contains a breaking change. Any deployed meshapps will need to be re-deployed and published. This will be done automatically by re-publishing the template.

## Release 18 May 2023

### Versions
| Component                    | Version       |
| ---------------------------- | ------------- |
| MeshApps Dom .NET SDK        | 1.0.20        |

### Features
- Nuget package dependencies of the Mesh App are now managed automatically.
- **New sample**: WebView Showcase. A scene dedicated to showcasing WebViews in MeshApps. This is based on the WebView functionality we currently provide in MeshApps. This does not include loading  HTML or any kind of synchronization of the Web content.
- Authentication on the Mesh App is no longer being enabled/disabled with the CLI tool `--auth-provider` option. Use the `--mode` option instead. It refers to the mode in which the app is being used. **Allowed Values**: dev, prod. [**Default Value**: `dev`]. 
  > **Note**: `"dev"` disables authentication and is recommended for the local development workflow, while `"prod"` has authentication enabled.
- Integrate meshapp deployment and publishing into the Mesh Uploader.

### Bug Fixes
- Fixed WebView intermittent navigation failure.

### Upgrade instructions

**_Remove old tools_**

- Make sure the old version of `MeshApp.CLI.Tool` is uninstalled.
```cmd
dotnet tool uninstall MeshApp.CLI.Tool --global
```

**_Upgrade the Unity project_**

- Use the Unity Package Manager to remove the old 'com.microsoft.mesh.toolkit.authoring' package.
- Use the Unity Package Manager to install the updated toolkit package from the `Packages` folder.
This step will also automatically install the Mesh apps NuGet packages.
- Add your Azure MeshApps Subcription ID to the project settings (**Edit > Project Settings -> Mesh Uploader Settings -> Extensions -> MeshApp CloudHost Tool**)

**_Rename the Application Insights Azure Resource_**

The MeshApp.CLI tool from the 23.5 release creates the application insights resource in the EastUS region by default. Upgrading to newer versions will cause a breaking change if your default deployment location wasn't previously set to EastUS. To avoid this:

- In the Azure Portal, navigate to the resource group containing your Mesh Apps resources.
- Rename the Application Insights resource. For example, `ai-ma-f5546cdbff0f490a-we` can be renamed to `ai-ma-f5546cdbff0f490a-eu`. **eu** here represents EastUS.
    
    **Note**: After renaming the resource, the previous logs data will not show within the newly renamed resource. This data will still be available under the old resource name.

**_Upgrade the Mesh App C# project_**

- Use the **Open Application Folder** button on the MeshApp component to locate your C# project folder.

- Open the `.csproj` file of your application and remove this block with Package References which are related to Mesh Apps (including reference to MeshApps package). These dependencies will now be inherited automatically from `Directory.Packages.props` file, which will be auto-generated and maintained by Mesh Toolkit
```xml
    <PackageReference Include="Microsoft.ApplicationInsights.WorkerService" Version="2.21.0" />
    <PackageReference Include="Microsoft.Extensions.Logging" Version="[6.0,7.0)" />
    <PackageReference Include="CommandLineParser" Version="2.8.0" />
    <PackageReference Include="System.Drawing.Common" Version="4.7.2" />
    <PackageReference Include="Microsoft.MeshApps.Dom.NET" Version="0.2.455" />
```

- Open `nuget.config` file in the same directory and remove package source for local Mesh Apps, e.g.
```xml
    <add key="MeshApps" value="../../../../Packages" />
```

**_Redeploy and Republish Mesh App_**

- On the Unity menu bar, select **Edit --> Project Settings --> Mesh Uploader Settings --> Extensions --> MeshApp Cloudhost Tool**, and then select the **Force deployment** option.
- The Mesh Toolkit Environment publishing step now handles deploying and publishing Mesh Apps. Republish your Environment to redeploy and republish your Mesh App.

## Release 20 Apr 2023

### Versions

| Component                    | Version       |
| ---------------------------- | ------------- |
| MeshApps Dom .NET SDK        | 0.2.455       |
| MeshApps Common .NET library | 0.2.436       |
| MeshApp CLI tool             | 1.0.2304.603  |

### Features
- WebView node: add a WebView to your Mesh app and set its URI.
- The Cloud app wrapper implementation has been simplified.

### Upgrade instructions

**_Upgrade the Unity project_**

- Use the Unity Package Manager to install the updated toolkit package from the `Packages` folder.

**_Upgrade the Mesh App C# project_**

- Use the **Open Application Folder** button on the MeshApp component to locate your C# project folder.

- Remove the `Options.cs` file.

- Rename your `UserApp` class to `App` and refactor it to implement [IHostedService](https://learn.microsoft.com/en-us/dotnet/api/microsoft.extensions.hosting.ihostedservice). For more resources about hosted services please make sure to also read [this article](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/host/hosted-services).

- Rename the `CloudApp.cs` file to `Program.cs` and replace its contents with:

```csharp
using Microsoft.ApplicationInsights.Channel;
using Microsoft.MeshApps;
using Microsoft.MeshApps.Common;

// Configure the host builder
var hostBuilder = Host.CreateDefaultBuilder(args)
    .ConfigureServices((hostBuilderContext, services) =>
    {
        var hostingEnv = hostBuilderContext.HostingEnvironment;
        var isUnityLocalDev = hostingEnv.IsUnityLocalDevelopment();
        var useAppInsights = isUnityLocalDev;

        services
            .AddCloudMeshApplication()
            .AddHostedService<App>()
            .AddLogging(loggingBuilder =>
            {
                if (!useAppInsights)
                {
                    loggingBuilder
                        .AddJsonConsole();
                }
            });

        if (useAppInsights)
        {
            // Create the telemetry channel
            if (isUnityLocalDev)
            {
                services.AddSingleton<ITelemetryChannel>(
                    new InMemoryChannel()
                    {
                        DeveloperMode = true,
                    });
            }

            services
                .AddApplicationInsightsTelemetryWorkerService();
        }
    });

// Build the host
using IHost host = hostBuilder.Build();

// Run the host
host.Run();
```

## Release 06 Apr 2023

### Versions

| Component                    | Version        |
| ---------------------------- | -------------- |
| MeshApps Dom .NET SDK        | 0.2.427        |
| MeshApps Common .NET library | 0.2.416        |
| MeshApp CLI tool             | 1.0.2303.2801  |

### Features

- Made Unity MeshApp inspector more clear about certain options. "Internal Settings" is now a drop-down called "Developer Settings". "Run Hub Automatically" was renamed to "Run Local MeshApp Server".
  - Disabling "Run Local MeshApp Server" now shows the endpoint URL that the client will connect to.  It uses the appEndpoint property, set in meshapp.manifest.json by the `meshapp publish` command, and will display a warning box if the property isn't available.
  - Disabling "Run Local MeshApp Server" now disables "Enable Application Debugging", and explains why this functionality is not available.
- Added connection information to the MeshApp Unity component, indicating whether it is connecting to a local instance or a cloud endpoint.

- The Cloud app has been refactored to an [IHostedService](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/host/hosted-services).

- Added support for [Application Insights](https://learn.microsoft.com/en-us/azure/azure-monitor/app/asp-net-core?tabs=netcorenew%2Cnetcore6). Cloud apps are now by default emitting telemetry through Application Insights.

- The log severity levels for the Cloud app are no longer configurable through the Unity editor. They are now controlled through the `appsettings.json` set of configuration files, as described [here](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/logging/?view=aspnetcore-7.0#configure-logging). When run locally from Unity, the app will use the `appsettings.UnityLocalDev.json` configuration file. Because the app logs using Application Insights, the log severity needs to be configured as described [here](https://learn.microsoft.com/en-us/azure/azure-monitor/app/asp-net-core?tabs=netcorenew%2Cnetcore6#how-do-i-customize-ilogger-logs-collection).

- Added support for shared physics
  - Added `RigidBodyNode` that alows to change physics properties of a rigid body
  - Added support for `Bounciness` and `Friction` to geometry nodes

- Partial support for authentication: We're plugging in auth to make it possible to identify your users across several sessions. Authentication is disabled by default and it can be enabled by publishing a MeshApp with the command `meshapp deploy -m prod`. No extra implementation is required from your standpoint, as the auth flow is entirely implicit.

### Upgrade instructions

**_Upgrade the Unity project_**

1. Use the Unity Package Manager to install the updated toolkit and authoring packages from the `Packages` folder.

2. Add the PlaymodeSetup prefab to your scene if it's not already present. Use the **GameObject** > **Mesh Toolkit** > **Add Playmode Setup** option to create it.

**_Upgrade the Mesh App C# project_**

- Use the **Open Application Folder** button on the MeshApp component to locate your C# project folder.

- Open the csproj file in a text editor. Change the `Project Sdk` to `Microsoft.NET.Sdk.Web`.

- Find the `ItemGroup` where `meshapp.manifest.json` is copied to the output folder. Add the following new resources to be copied as well:

```xml
<None Update="appsettings.json">
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
</None>
<None Update="appsettings.Development.json">
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
</None>
<None Update="appsettings.Production.json">
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
</None>
<None Update="appsettings.UnityLocalDev.json">
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
</None>
```

- Find the `ItemGroup` that adds the `PackageReference`s and 

    1. add the following new references:

    ```xml
    <PackageReference Include="Microsoft.ApplicationInsights.WorkerService" Version="2.21.0" />
    <PackageReference Include="System.Drawing.Common" Version="4.7.2" />
    ```

    2. remove the following references:

    ```xml
    <PackageReference Include="Microsoft.Extensions.Hosting" Version="[6.0.1,7.0)" />
    <PackageReference Include="Microsoft.Extensions.Logging.Console" Version="[6.0,7.0)" />
    ```

- Create an `appsettings.json` file in your C# project folder with the following contents:

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Information"
        },
        "Console": {
            "LogLevel": {
                "Default": "Error"
            },
            "FormatterName": "json"
        },
        "ApplicationInsights": {
            "LogLevel": {
                "Default": "Information"
            }
        }
    }
}
```

- Create an `appsettings.Development.json` file in your C# project folder with the following contents:

```json
{
    "ApplicationInsights": {
        "EnableQuickPulseMetricStream": false,
        "EnableAzureInstanceMetadataTelemetryModule": false,
        "EnableAppServicesHeartbeatTelemetryModule": false
    },
    "Logging": {
        "LogLevel": {
            "Default": "Debug",
            "MeshApps": "Debug",
            "Microsoft.MeshApps": "Debug"
        },
        "Console": {
            "LogLevel": {
                "Default": "Debug",
                "MeshApps": "Debug",
                "Microsoft.MeshApps": "Debug"
            },
            "FormatterName": "json"
        },
        "ApplicationInsights": {
            "LogLevel": {
                "Default": "Debug",
                "MeshApps": "Debug",
                "Microsoft.MeshApps": "Debug"
            }
        }
    }
}
```

- Create an `appsettings.Production.json` file in your C# project folder with the following contents:

```json
{
    "ApplicationInsights": {
        "EnableQuickPulseMetricStream": false,
        "EnableAzureInstanceMetadataTelemetryModule": false,
        "EnableAppServicesHeartbeatTelemetryModule": false
    },
    "Logging": {
        "LogLevel": {
            "Default": "Information",
            "MeshApps": "Information",
            "Microsoft.MeshApps": "Information"
        },
        "Console": {
            "LogLevel": {
                "Default": "Information",
                "MeshApps": "Information",
                "Microsoft.MeshApps": "Information"
            },
            "FormatterName": "json"
        },
        "ApplicationInsights": {
            "LogLevel": {
                "Default": "Information",
                "MeshApps": "Information",
                "Microsoft.MeshApps": "Information"
            }
        }
    }
}
```

- Create an `appsettings.UnityLocalDev.json` file in your C# project folder with the following contents:

```json
{
    "ApplicationInsights": {
        "DeveloperMode": true,
        "EnableQuickPulseMetricStream": false,
        "EnableAzureInstanceMetadataTelemetryModule": false,
        "EnableAppServicesHeartbeatTelemetryModule": false
    },
    "Logging": {
        "LogLevel": {
            "Default": "Information",
            "MeshApps": "Information",
            "Microsoft.MeshApps": "Information"
        },
        "ApplicationInsights": {
            "LogLevel": {
                "Default": "Information",
                "MeshApps": "Information",
                "Microsoft.MeshApps": "Information"
            }
        }
    }
}
```

- Open the `Options.cs` file and remove the following:

```csharp
public const LogLevel DefaultLogLevel = LogLevel.Debug;
public const LogLevel DefaultSdkLogLevel = LogLevel.Debug;

[Option('l', "logLevel", Required = false, HelpText = "Minimum app log level.", Default = DefaultLogLevel)]
public LogLevel LogLevel { get; set; } = DefaultLogLevel;

[Option("sdkLogLevel", Required = false, HelpText = "Minimum SDK log level.", Default = DefaultSdkLogLevel)]
public LogLevel SdkLogLevel { get; set; } = DefaultSdkLogLevel;
```

- Still in `Options.cs`, add the following:

```csharp
[Option("environment", Required = false, HelpText = "Environment override")]
public string Environment { get; set; } = string.Empty;
```

- Open the `CloudApp.cs` file and replace the contents of the main namespace with:

```csharp
    using System;
    using System.Diagnostics;
    using System.Threading;
    using System.Threading.Tasks;
    using CommandLine;
    using Microsoft.ApplicationInsights.Channel;
    using Microsoft.Extensions.Logging;
    using Microsoft.MeshApps;
    using Microsoft.MeshApps.Common;
    using Microsoft.MeshApps.Dom;

    public partial class CloudApp : IHostedService
    {
        private const string SceneFilePath = "./scene.json";
        private readonly ILogger _logger;
        private readonly CloudApplication _app;
        private readonly Options _options;
        private readonly CancellationTokenSource _cancelApp = new();
        private readonly IHostApplicationLifetime _appLifetime;

        private ApplicationWorkDispatcher? _appWorkDispatcher;
        private Task? _appTask;
        private bool _disposedValue = false;
        private UserApp? _userApp;

        public CloudApp(
            Options options,
            ILogger<CloudApp> logger,
            IHostApplicationLifetime appLifetime,
            CloudApplication app)
        {
            _app = app;
            _logger = logger;
            _options = options;
            _appLifetime = appLifetime;

            // Route Debug.WriteLine and Trace.WriteLine to the logger
            if (!Debugger.IsAttached)
            {
                LoggerTraceListener.AddDebugListener(_logger);
                LoggerTraceListener.AddTraceListener(_logger);
            }

            _app.Configuration.Connection.Endpoint = options.Endpoint;
        }

        public static async Task<int> Main(string[] args)
        {
            Options? options = null;
            Parser.Default
                .ParseArguments<Options>(args)
                .WithParsed(o =>
                {
                    options = o;
                });

            if (options == null)
            {
                await Console.Error.WriteLineAsync("Invalid command line arguments");
                return -1;
            }

            if (options.Debug)
            {
                Debugger.Launch();
            }

            // Configure the host builder
            var hostBuilder = Host.CreateDefaultBuilder(args)
                .ConfigureServices((hostBuilderContext, services) =>
                {
                    var hostingEnv = hostBuilderContext.HostingEnvironment;
                    var isUnityLocalDev = hostingEnv.IsUnityLocalDevelopment();
                    var useAppInsights = isUnityLocalDev;

                    services
                        .AddSingleton(options)
                        .AddCloudMeshApplication()
                        .AddHostedService<CloudApp>()
                        .AddLogging(loggingBuilder =>
                        {
                            if (!useAppInsights)
                            {
                                loggingBuilder
                                    .AddJsonConsole();
                            }
                        });

                    if (useAppInsights)
                    {
                        // Create the telemetry channel
                        if (isUnityLocalDev)
                        {
                            services.AddSingleton<ITelemetryChannel>(
                                new InMemoryChannel()
                                {
                                    DeveloperMode = true,
                                });
                        }

                        services
                            .AddApplicationInsightsTelemetryWorkerService();
                    }
                });

            // Build the host
            using IHost host = hostBuilder.Build();

            if (!File.Exists(SceneFilePath))
            {
                var loggerFactory = host.Services.GetRequiredService<ILoggerFactory>();
                var logger = loggerFactory.CreateLogger<CloudApp>();
                Log.PathNotFound(logger, SceneFilePath);
                return -2;
            }

            // Run the host
            await host.RunAsync();

            return 0;
        }

        public async Task StartAsync(CancellationToken cancellationToken)
        {
            var sceneChecksum = ChecksumHelper.ComputeChecksums(new[] { SceneFilePath });
            _app.Configuration.Connection.AssetsVersion = sceneChecksum;

            var endpoint = _app.Configuration.Connection.Endpoint;
            _app.Disconnected += HandleAppDisconnected;
            _app.Stopped += HandleAppStopped;

            // Start the app
            _appWorkDispatcher = new ApplicationWorkDispatcher(_app, _logger);
            Log.RunAsyncStep(_logger, "Starting", endpoint);
            await _app.StartAsync(cancellationToken);

            // Connect the app to the cloud host
            Log.RunAsyncStep(_logger, "Connecting", endpoint);
            await _app.ConnectAsync(cancellationToken);

            Log.RunAsyncStep(_logger, "Activated", endpoint);
            _appTask = ExecuteAsync(_cancelApp.Token);
        }

        private async Task ExecuteAsync(CancellationToken token)
        {
            // Register the user-defined types
            using var typesReg = _app.RegisterDomTypes();

            // Load the scene
            LoadScene();

            // Create user app and activate the logic
            _userApp = new UserApp(_app, _logger);
            _userApp.Activate();

            // Run the app logic until we're disconnected
            await _userApp.RunAsync(token);
        }

        public async Task StopAsync(CancellationToken cancellationToken)
        {
            // Wait for the app to complete
            _cancelApp.Cancel();
            if (_appTask != null)
            {
                await _appTask;
                _appTask = null;
            }

            Log.RunAsyncStep(_logger, "Disconnected", _options.Endpoint);
            if (_userApp != null)
            {
                _userApp.Deactivate();
                _userApp = null;
            }

            Log.RunAsyncStep(_logger, "Deactivated", _options.Endpoint);

            // We're disconnected. Stop the app completely
            try
            {
                _app.Disconnected -= HandleAppDisconnected;
                await _app.StopAsync(cancellationToken);
            }
            catch (Exception e)
            {
                Log.StoppedWithError(_logger, e);
            }

            _app.Stopped -= HandleAppStopped;

            if (_appWorkDispatcher != null)
            {
                await _appWorkDispatcher.DispatchTask;
                _appWorkDispatcher = null;
            }

            Log.RunAsyncStep(_logger, "Stopped", _options.Endpoint);
        }

        private void HandleAppDisconnected(object sender, ApplicationDisconnectedEventArgs args)
        {
            _appLifetime.StopApplication();

            try
            {
                args.RethrowException();
            }
            catch (Exception e)
            {
                Log.DisconnectedWithError(_logger, e);
            }
        }

        private void HandleAppStopped(object sender, ApplicationStoppedEventArgs args)
        {
            _appLifetime.StopApplication();

            try
            {
                args.RethrowException();
            }
            catch (Exception e)
            {
                Log.StoppedWithError(_logger, e);
            }
        }

        private void LoadScene()
        {
            try
            {
                Log.LoadingScene(_logger, SceneFilePath);

                var fileContents = File.ReadAllText(SceneFilePath);
                _app.Deserialize(fileContents);
            }
            catch (Exception e)
            {
                Log.FailedToLoadScene(_logger, e);
            }
        }

        protected virtual void Dispose(bool disposing)
        {
            if (!_disposedValue)
            {
                if (disposing)
                {
                    // Dispose the Cloud app
                    try
                    {
                        _app.Dispose();
                    }
                    catch (Exception e)
                    {
                        Log.RuntimeError(_logger, e);
                    }
                }

                _disposedValue = true;
            }
        }

        public void Dispose()
        {
            Dispose(disposing: true);
            GC.SuppressFinalize(this);
        }

        private static partial class Log
        {
            [LoggerMessage(
                EventId = 0,
                Level = Microsoft.Extensions.Logging.LogLevel.Warning,
                EventName = "CloudApp.FailedToLoadScene",
                Message = "Failed to load scene")]
            public static partial void FailedToLoadScene(ILogger logger, Exception ex);

            [LoggerMessage(
                EventId = 1,
                Level = Microsoft.Extensions.Logging.LogLevel.Information,
                EventName = "CloudApp.LoadingScene",
                Message = "Loading scene {sceneFilePath}")]
            public static partial void LoadingScene(ILogger logger, string sceneFilePath);

            [LoggerMessage(
                EventId = 2,
                Level = Microsoft.Extensions.Logging.LogLevel.Error,
                EventName = "CloudApp.PathNotFound",
                Message = "File path not found {filePath}")]
            public static partial void PathNotFound(ILogger logger, string filePath);

            [LoggerMessage(
                EventId = 3,
                Level = Microsoft.Extensions.Logging.LogLevel.Error,
                EventName = "CloudApp.RuntimeError",
                Message = "Exceptions during the app")]
            public static partial void RuntimeError(ILogger logger, Exception ex);

            [LoggerMessage(
                EventId = 4,
                Level = Microsoft.Extensions.Logging.LogLevel.Information,
                EventName = "CloudApp.RunAsync",
                Message = "{step} {endpoint}")]
            public static partial void RunAsyncStep(ILogger logger, string step, string endpoint);

            [LoggerMessage(
                EventId = 5,
                Level = Microsoft.Extensions.Logging.LogLevel.Warning,
                EventName = "CloudApp.StoppedWithError",
                Message = "Mesh application stopped with exception")]
            public static partial void StoppedWithError(ILogger logger, Exception ex);

            [LoggerMessage(
                EventId = 6,
                Level = Microsoft.Extensions.Logging.LogLevel.Warning,
                EventName = "CloudApp.DisconnectedWithError",
                Message = "Mesh application disconnected with exception")]
            public static partial void DisconnectedWithError(ILogger logger, Exception ex);
        }
    }
```

## Release 16 Mar 2023

### Versions

| Component                    | Version       |
| ---------------------------- | ------------- |
| MeshApp .NET SDK             | 0.2.393       |
| MeshApp Common .NET          | 0.2.385       |
| MeshApp CLI tool             | 1.0.2303.701  |

### Features
- Removed `Endpoint` setting from mesh app component - the endpoint specified in `meshapp.manifest.json` will be used (which is populated during the `meshapp publish` step)
- Exposed a persistent user identifier to the SDK - This replaces the unsigned integer `User.Identifier` with a string
- Added `User.ConnectedEventId` that exposes the event / space id that the user has connected from.
- Added support for moving platforms.  The new `StartMovingWithPlatform` and `StopMovingWithPlatform` methods on the avatar class can be used to control the avatar motion.
- Exposed the meshapp & meshapp SDK log levels. The levels are in sync for the app and service.

### Bug Fixes
- Fixed client hang when trace logs enabled on cloud app
- Fixed issue that barrier bounds on Mesh App component can't be changed

### Upgrade instructions

> **Note**: Mesh apps published with older versions of the SDK won't function in the current version of the Mesh app. When the Mesh app is updated from the Windows or Quest store, or when using the web browser, you must perform the following steps to update and republish your project.

**_Upgrade the Unity project_**

1. Use the Unity Package Manager to install the updated packages from the `Packages` folder:

   - Mesh Common Unity Package
   - Mesh Toolkit Uploader Package
   - Mesh Scripting Package

1. Confirm that the versions shown in Package Manager match the versions in this release.

1. Make sure that all game objects, which have `TouchSensor` components and corresponding colliders, have **Default** layer assigned to them (Also see `NavMesh` layer issue in [Known Issues](Known_Issues.md#known-issues))

**_Upgrade the Mesh App C# project_**

1. Use the **Open Application Folder** button on the MeshApp component to locate your C# project folder.

1. Open the csproj file in a text editor, and then change the version of Microsoft.MeshApps.Dom.NET to `*`. Example: `<PackageReference Include="Microsoft.MeshApps.Dom.NET" Version="*" />`

1. Open the `nuget.config` file, and then change the local package path to the Packages folder for this distribution.

1. Make necessary adjustments where `Avatar.User.Identifier` field is used - its type has changed from `uint` to `string` 

**_Upgrade the Mesh App CLI tool_**

1. Use the command `dotnet tool update MeshApp.CLI.Tool --add-source "Package folder path" --global --prerelease` to update the MeshApp CLI tool. The path provided should be the Packages folder from this distribution.

1. Confirm that the version reported matches the one listed above.

1. After updating the Unity project, the C# project and the CLI tool:
   1. Redeploy your application using `meshapp deploy` and following the [normal instructions](Mesh_Scripting_Getting_Started_Guide.md#deploy-the-applications-infrastructure-publish-the-application-and-interactive-world-template) so the cloudhost image gets updated.
   1. Republish your application using `meshapp publish` using the [normal instructions](Mesh_Scripting_Getting_Started_Guide.md#deploy-the-applications-infrastructure-publish-the-application-and-interactive-world-template).
   1. Reupload the environment template using the [normal instructions](Mesh_Scripting_Getting_Started_Guide.md#deploy-the-applications-infrastructure-publish-the-application-and-interactive-world-template).


## Release 23 Feb 2023

### Versions

| Component                    | Version       |
| ---------------------------- | ------------- |
| MeshApp .NET SDK             | 0.2.352       |
| MeshApp CLI tool             | 1.0.2302.101  |
| Mesh Toolkit Unity Package   | 1.24.0        |
| Mesh Common Unity Package    | 0.0.81        |
| Mesh Scripting Unity Package | 0.2.352       |

### Features

- Added UI notifications for Mesh app connected / disconnected.

- The display name of users connected to the cloud app can now be inspected through the User.DisplayName string property.

- The new `Avatar` class represents user presence in the scene
  - `TeleportTo` method allows app to teleport avatars to a given location in the scene
  - `TravelTo` method allows app to instruct avatars to travel to another space or event by supplying a URI to it

- Added the `ShowMessageToUser[s]` method to CloudApplication that enables app to display a screen space message for a given set of users.

- Added support for trigger volumes to geometry nodes
  - `IsTrigger` controls whether a geometry is a trigger or not. This is set on the collider in Unity and cannot be changed at runtime. If a geometry node is a trigger:
    - `Entered` events are generated whenever avatars start overlapping with the given geometry
    - `Exited` events are generated whenever avatars stop overlapping with the given geometry

- The Mesh App CLI tool's `publish` command has been split into two separate commands.
  - `meshapp deploy`: This provisions all the resources needed by the Mesh app to azure.
    > **Note: This command only needs to be run once except to make some changes to the infrastructure. Examples of this are updating to a new release, changing the Mesh app's authProvider, or deploying the Mesh app to different resource group.**
  - `meshapp publish`: This uploads the Mesh app to Azure and restarts the application.
    > **Note: This command needs to be run whenever changes are made to the Mesh app.**
  - Authentication on Mesh apps can be optionally enabled.
    > **Note**: Enabling auth for **new** Mesh apps requires supplying the `-a Mesh` parameter to the Mesh App CLI `deploy` command. **Connecting to a Mesh app from Unity will fail if Auth is enabled.**

- The handshake logic for establishing the connection between the client, cloud app, and service has been changed to ensure that the versions of the MeshApp SDK used by either side of the connection are compatible with each other.

- The following `CloudApplication` methods have been removed: `CreateTransformNode`, `CreateBoxGeometryNode`, `CreateSphereGeometryNode`, `CreateCapsuleGeometryNode`, `CreatePointLightNode`, `CreateSpotLightNode`, `CreateDirectionalLightNode`, and `CreateTouchSensorNode`. Use the generic `CloudApplication.Create<TNodeType>` instead.

### Upgrade instructions

> **Note**: Mesh apps published with older versions of the SDK won't function in the current version of the Mesh app. When the Mesh app is updated from the Windows or Quest store, or when using the web browser, you must perform the following steps to update and republish your project.

**_Upgrade the Unity project_**

1. Use the Unity Package Manager to install the updated packages from the `Packages` folder:

   - Mesh Common Unity Package
   - Mesh Toolkit Uploader Package
   - Mesh Scripting Package

1. Confirm that the versions shown in Package Manager match the versions in this release.

**_Upgrade the Mesh App C# project_**

1. Use the **Open Application Folder** button on the MeshApp component to locate your C# project folder.

1. Open the csproj file in a text editor, and then change the version of Microsoft.MeshApps.Dom.NET to `*`. Example: `<PackageReference Include="Microsoft.MeshApps.Dom.NET" Version="*" />`

1. Open the `nuget.config` file, and then change the local package path to the Packages folder for this distribution.

1. Open the `CloudApp.cs` file and delete the line:

```cs
builder.Services.AddCloudLogging();
```

1. Replace any invocation of `CloudApplication.CreateXxx` with `CloudApplication.Create<Xxx>`, where `Xxx` is one of: `TransformNode`, `BoxGeometryNode`, `SphereGeometryNode`, `CapsuleGeometryNode`, `PointLightNode`, `SpotLightNode`, `DirectionalLightNode`, or `TouchSensorNode`.

**_Upgrade the Mesh App CLI tool_**

1. Use the command `dotnet tool update MeshApp.CLI.Tool --add-source "Package folder path" --global --prerelease` to update the MeshApp CLI tool. The path provided should be the Packages folder from this distribution.

1. Confirm that the version reported matches the one listed above.

1. After updating the Unity project, the C# project and the CLI tool:
   1. Redeploy your application using `meshapp deploy` and following the [normal instructions](Mesh_Scripting_Getting_Started_Guide.md#deploy-the-applications-infrastructure-publish-the-application-and-interactive-world-template) so the cloudhost image gets updated.
   1. Republish your application using `meshapp publish` using the [normal instructions](Mesh_Scripting_Getting_Started_Guide.md#deploy-the-applications-infrastructure-publish-the-application-and-interactive-world-template).
   1. Reupload the environment template using the [normal instructions](Mesh_Scripting_Getting_Started_Guide.md#deploy-the-applications-infrastructure-publish-the-application-and-interactive-world-template).

## Release 08 Dec 2022

### Versions

| Component                    | Version      |
| ---------------------------- | ------------ |
| MeshApp .NET SDK             | 0.2.246      |
| MeshApp CLI tool             | 1.0.2212.202 |
| Mesh Toolkit Unity Package   | 1.19.0       |
| Mesh Common Unity Package    | 0.0.66       |
| Mesh Scripting Unity Package | 0.2.246      |

### Features

- Text node: Control text content and styling from your mesh app.

- Unique Azure resource names: The Azure resources associated with your application will be based on the "appId" property found in the meshapp.manifest.json file. This enables you to publish different versions of the same project or samples without conflict. **Note**: this feature will cause your Azure resources and app endpoint URI to change. Follow the upgrade instructions below to remove the old resources and publish new ones.

- Simplified logging control: Use the `Default` setting for routine development and the `Diagnostic` setting to collect additional data when reporting issues.

- New sample: Block Builder. Build structures using blocks in a Minecraft-styled environment.

- New sample: Piano. Marvel at a MIDI-driven animated player piano, or record your own tunes.

- New sample: Table Football. Challenge three other players to a classic game of tabletop football.

### Bug Fixes

- The Node.IsActive property is fixed, including support for per-user visibility.

- Application logging using the ILogger, Console.WriteLine, or Debug.WriteLine should now be visible in Unity without special configuration.

- Resolved an issue where certain characters could create errors when used in animation names and properties.

### Upgrade instructions

> **Note**: Mesh apps published with older versions of the SDK won't function in the current version of the Mesh app. When the Mesh app is updated from the Windows or Quest store, or when using the web browser, you must perform the following steps to update and republish your project.

**_Upgrade the Unity project_**

1. Use the Unity Package Manager to install the updated Mesh Toolkit Uploader Package from Packages\com.microsoft.mesh_toolkit_uploader-1.19.0.tgz.

1. Use the Unity Package Manager to install the updated Mesh Scripting Unity Package from Packages\com.microsoft.mesh.meshapps.unityruntime-0.2.246.tgz.

1. Confirm that the versions shown in Package Manager match the versions listed above.

**_Upgrade the Mesh App C# project_**

1. Use the **Open Application Folder** button on the MeshApp component to locate your C# project folder.

1. Open the csproj file in a text editor, and then change the version of Microsoft.MeshApps.Dom.NET to 0.2.246. Example: `<PackageReference Include="Microsoft.MeshApps.Dom.NET" Version="0.2.246" />`

1. Also in the csproj file, add the following XML below the scene.json node, within the same ItemGroup.

```xml
<None Update="meshapp.manifest.json">
      <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
    </None>
```

1. Open the `nuget.config` file, and then change the local package path to the Packages folder for this distribution.

1. Replace the content of `CloudApp.cs` and `Options.cs` with the files found in this distribution at `Updates\CloudApp.cs` and `Updates\Options.cs`.

1. Replace any instances of `ILogger<CloudApp>` in UserApp.cs or your other code files with just `ILogger`.

1. Open the meshapp.manifest.json file in a text editor and then add an `entryPoint` attribute. Its value will be the project name with a .DLL file extension. Example for FeatureShowcase:

```json
{
  "name": "FeatureShowcase",
  "language": "C#",
  "entryPoint": "FeatureShowcase.dll"
}
```

_Important_: note the capitalization of entryPoint.

**_Upgrade the Mesh App CLI tool_**

1. Use the command `dotnet tool update MeshApp.CLI.Tool --add-source "Package folder path" --global --prerelease` to update the MeshApp CLI tool. The path provided should be the Packages folder from this distribution.

1. Confirm that the version reported matches the one listed above.

1. After updating the Unity project, the C# project and the CLI tool:
   1. In the Azure portal, delete any resources previously associated with your Mesh app. If you created a resource group for a specific app, you can delete that. Otherwise, search for resources that start with the name of your app and delete them.
   1. Republish your application using `meshapp publish` using the [normal instructions](Mesh_Scripting_Getting_Started_Guide.md#deploy-the-application-and-interactive-world-template). You'll note that the app endpoint URI and Azure resource names are now unique values. These are based on the "appId" value found in your app's meshapp.manifest.json file.
   1. Upload a new environment template using the [normal instructions](Mesh_Scripting_Getting_Started_Guide.md#deploy-the-application-and-interactive-world-template). Note that reusing an existing template might lead to errors.

## Archived - Release 08 Nov 2022

### Versions

| Component                    | Version       |
| ---------------------------- | ------------- |
| MeshApp .NET SDK             | 0.2.225       |
| MeshApp CLI tool             | 1.0.2211.1101 |
| Mesh Toolkit Unity Package   | 1.16.0        |
| Mesh Common Unity Package    | 0.0.66        |
| Mesh Scripting Unity Package | 0.2.225       |

### Features

- Publish to a specific resource group. Reduce the required Azure permissions for publishing by using the new `-g` argument to the `meshapp publish` command to target a resource group created by your subscription administrator.
- Per-user Node.IsActive. Nodes can now be enabled or disabled for specific users using the `Node.SetActiveForUsers` method.
- Writable Parent property. Move nodes around the scene graph by setting the Parent property, which replaces the Add/RemoveChildren methods.
- Quest 2 support added. The Quest 2 build of the Mesh app will now be able to connect to your Mesh apps.

### Bug Fixes

- Scene serialization improvements. Scene serialization is more automatic and less error prone.
- Removal of generated animation classes. Animations no longer create generated types in the Unity project. Generated types remain in the MeshApp project where they're useful.
- Server logging fixes. Application logging and diagnostic messages are now visible in App Service logs.

### Upgrade instructions

> **Note**: Mesh apps published with older versions of the SDK won't function in the current version of the Mesh app. When the Mesh app is updated from the Windows or Quest store, or when using the web browser, you must perform the following steps to update and republish your project.

**_Upgrade the Unity project_**

1. Install Unity 2021.3.5f1 and update your project.

1. Use the Unity Package Manager to install the updated Mesh Toolkit Uploader Package from Packages\com.microsoft.mesh_toolkit_uploader-1.16.0.tgz.

1. In Unity on the menu bar, select "Mesh Toolkit | Configure Project Settings".

1. Use the Unity Package Manager to install the updated Mesh Common Unity Package from Packages\com.microsoft.mesh.common-0.0.66.tgz.

1. Use the Unity Package Manager to install the updated Mesh Scripting Unity Package from Packages\com.microsoft.mesh.meshapps.unityruntime-0.2.225.tgz.

1. Confirm that the versions shown in Package Manager match the versions listed above.

**_Upgrade the Mesh App C# project_**

1. Use the **Open Application Folder** button on the MeshApp component to locate your C# project folder.

1. Open the csproj file in a text editor, and then change the version of Microsoft.MeshApps.Dom.NET to 0.2.225. Remove the `-release` tag if present. Example: `<PackageReference Include="Microsoft.MeshApps.Dom.NET" Version="0.2.225" />`

1. Open the `nuget.config` file, and then change the local package path to the Packages folder for this distribution.

1. Replace the content of `CloudApp.cs` with the file found in this distribution at `Updates\CloudApp.cs`.

1. Add the following function to `UserApp.cs`:

```c#
    public async Task RunAsync(CancellationToken token)
    {
        // Create a task that completes when the app is canceled
        var appDone = new TaskCompletionSource(TaskCreationOptions.RunContinuationsAsynchronously);
        token.Register(() => appDone.SetResult());

        if (token.IsCancellationRequested)
        {
            return;
        }

        await appDone.Task;
    }
```

**_Upgrade the Mesh App CLI tool_**

1. Use the command `dotnet tool update MeshApp.CLI.Tool --add-source "Package folder path" --global` to update the MeshApp CLI tool. The path provided should be the Packages folder from this distribution.

1. Confirm that the version reported matches the one listed above.

1. After updating the Unity project, the C# project and the CLI tool, republish your application and reupload your environment template using the [normal instructions](Mesh_Scripting_Getting_Started_Guide.md#deploy-the-application-and-interactive-world-template). Be aware that the command line arguments to the MeshApp tool have changed.

## Archived - Release 26 Oct 2022

### Features

- First version of Mesh Scripting

### Versions

| Component                    | Version         |
| ---------------------------- | --------------- |
| MeshApp .NET SDK             | 0.2.203-release |
| MeshApp CLI tool             | 1.0.2210.504    |
| Mesh Toolkit Unity Package   | 1.11.1          |
| Mesh Common Unity Package    | 0.0.6           |
| Mesh Scripting Unity Package | 0.2.203-release |
