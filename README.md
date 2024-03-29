Overview

Create a static HTML web app by using Azure Cloud Shell. In this exercise, you'll deploy a basic HTML+CSS site to Azure App Service by using the Azure CLI az webapp up command. You'll then update the code and redeploy it by using the same command.

Azure Cloud Shell

This module requires a sandbox to complete. A sandbox gives you access to Azure resources. Your Azure subscription will not be charged. The sandbox may only be used to complete training on Microsoft Learn. Use for any other reason is prohibited, and may result in permanent loss of access to the sandbox.

Microsoft provides this lab experience and related content for educational purposes. All presented information is owned by Microsoft and intended solely for learning about the covered products and services in this Microsoft Learn module.


General Evaluation 

  


Key Aspects

Item 01

Environment

Microsoft Azure Portal

Valid Subscription

Sandbox

Actions

Prepare the environment

Activate the Azure Sandbox



Prepare the code

Create a new directory

mkdir htmlapp
cd htmlapp

Clone a Git repository

git clone https://github.com/Azure-Samples/html-docs-hello-world.git

Set the session variables

resourceGroup=$(az group list --query "[].{id:name}" -o tsv)
appName=az204app$RANDOM





Create Azure App Service and deploy a static HTML page to it

Create Azure App Service and deploy a static HTML page to it # version 01

cd html-docs-hello-world
az webapp up -g $resourceGroup -n $appName --html

Create Azure App Service and deploy a static HTML page to it # version 02

code index.html // change the content and save
az webapp up -g $resourceGroup -n $appName --html





Media







Additional information 

Bacon ipsum dolor amet shoulder burgdoggen shankle pastrami fatback porchetta chislic meatloaf buffalo tongue. Pancetta tenderloin biltong, porchetta hamburger brisket doner chicken tri-tip kevin t-bone


References

Create a static HTML web app by using Azure Cloud Shell | Microsoft Learn



To-Do

Description ()
