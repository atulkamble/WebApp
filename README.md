# Test WebApp on Azure

Prerequisites:
- Azure account 
-.NET SDK (https://dotnet.microsoft.com/en-us/download).
- Visual Studio Code (https://code.visualstudio.com/Download)
- C# Extension (https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)
- Azure App Service Extension. (https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azureappservice)

Commands:
dotnet new console
dotnet run
dotnet new mvc -o MyMVCapp
code -r MyMVCapp
dotnet dev-certs https --trust
dotnet run
dotnet publish -c Release -o ./bin/Publish
