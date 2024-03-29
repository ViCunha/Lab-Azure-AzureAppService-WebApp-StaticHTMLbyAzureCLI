
### Overview

Create a static HTML web app by using Azure Cloud Shell. In this exercise, you'll deploy a basic HTML+CSS site to Azure App Service by using the Azure CLI az webapp up command. You'll then update the code and redeploy it by using the same command.

_Azure Cloud Shell_

_This module requires a sandbox to complete. A sandbox gives you access to Azure resources. Your Azure subscription will not be charged. The sandbox may only be used to complete training on Microsoft Learn. Use for any other reason is prohibited, and may result in permanent loss of access to the sandbox. Microsoft provides this lab experience and related content for educational purposes. All presented information is owned by Microsoft and intended solely for learning about the covered products and services in this Microsoft Learn module._

### Environment

- Microsoft Azure Portal
  - Valid Subscription
  - Sandbox

### Actions

Prepare the environment
  - Activate the Azure Sandbox

Prepare the code
- Create a new directory

```azurecli
mkdir htmlapp
cd htmlapp
```
- Clone a Git repository
```azurecli
git clone https://github.com/Azure-Samples/html-docs-hello-world.git
```

- Set the session variables
```azurecli
resourceGroup=$(az group list --query "[].{id:name}" -o tsv)
appName=az204app$RANDOM
```

Create Azure App Service and deploy a static HTML page to it
- Create Azure App Service and deploy a static HTML page to it # version 01
```azurecli
cd html-docs-hello-world
az webapp up -g $resourceGroup -n $appName --html
```
  
- Create Azure App Service and deploy a static HTML page to it # version 02
```azurecli
code index.html // change the content and save
az webapp up -g $resourceGroup -n $appName --html
```

Present the result
  - Navigate to https://az204app30586.azurewebsites.net/

```powershell
curl https://az204app30586.azurewebsites.net/
```

### Media
![image](https://github.com/ViCunha/Lab-Azure-AzureAppService-WebApp-StaticHTMLbyAzureCLI/assets/65992033/721f7368-09b3-4d9b-b023-03e14da10a0b)
---
![image](https://github.com/ViCunha/Lab-Azure-AzureAppService-WebApp-StaticHTMLbyAzureCLI/assets/65992033/a3aff692-911b-454c-a5fd-070c96398409)


### References

- [Create a static HTML web app by using Azure Cloud Shell | Microsoft Learn](https://learn.microsoft.com/en-us/training/modules/introduction-to-azure-app-service/7-create-html-web-app)
