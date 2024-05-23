azure openai denis video

Create an Azure OpenAI resource

1. Go to the Azure portal and log in.
1. In the Search box at the top, type "azure openai".
1. In the drop-down box that appears, under **Services**, select **Azure OpenAI**.
1. On the next page, click the **Create** button.
<finish creation of resource>
1. Go to Azure OpenAI Studio.
1. Create a new deployment for the model gpt-35-turbo.
1. Go back to the resource.
1. Navigate to Resource Management > Keys and Endpoints.
1. Copy (both?) keys and the endpoint and save for later. Later, we paste one key but it's not clear which one to copy.
1. Open appsettings.UnityLocalDev and paste in the endpoint (API_URI) and key (API_KEY).
1. "As soon as you deploy your cloud application, navigate to Settings > Environment variables and add AZURE_OPENAI_API_KEY and AZURE_OPENAI_API_URI. 



In the video, Denis says "create an Azure OpenAI resource" but it's not clear to me how to do that or if I even can with my account. 

================

1. In the **Project** folder, navigate to **Assets** > **MeshCloudScripting** and then drag **4 - GlobeWithCloudScripting** and **5 - AIAssistant** to the **Hierarchy** an place them as child objects to **Mesh Cloud Scripting**.

    ![__________________________________](../../../media/mesh-201/077-drag-prefabs.png)




1. Note that at the bottom of the file, there's a comment with a placeholder for a package reference.

    ![__________________________________](../../../media/mesh-201/088-extra-pkg-reference.png)

1. Delete the placeholder *PackageReference* element and replace it with the line below:

   	`<PackageReference Include="Azure.AI.OpenAI" Version="1.0.0-beta.15" />`


  "WEATHER_API_URI": "http://api.weatherapi.com/v1/current.json?key=",
  "WEATHER_API_KEY": "79c5e04f3cab4b268c6165002240403",
  "AZURE_OPENAI_API_URI": "https://mesh201-weather.openai.azure.com/",
  "AZURE_OPENAI_API_KEY": "78ad3e771f404ac2b761fe2602e2313a"
}
