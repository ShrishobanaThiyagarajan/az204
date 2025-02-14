# az204 Lab 1
Lab 01: Build a Web Application on Azure Platform as a Service (PaaS) Offering

This lab guides you through building a backend API and a front-end web application using Azure Storage, Azure App Service, and Azure CLI.

📌 Lab Instructions: AZ-204 Lab 01 - Build a Web Application on Azure PaaS
Exercise 1: Build a Backend API Using Azure Storage and Web Apps

Step 1: Open the Azure Portal

Open Microsoft Edge.

Navigate to Azure Portal.

Sign in with your credentials.

Step 2: Create a Storage Account

Go to Storage Accounts in the Azure Portal.

Click + Create and fill in:

Resource Group: ManagedPlatform

Storage Account Name: imgstor[unique-name]

Region: East US

Performance: Standard

Redundancy: Locally-redundant storage (LRS)

Click Review + Create, then Create.

Once deployed, navigate to Access keys, reveal the connection string, and copy it for later use.

Step 3: Upload a Sample Blob

Navigate to Containers under the storage account.

Create a new container named images.

Upload grilledcheese.jpg from F:\Allfiles\Labs\01\Starter\Images.

Step 4: Create a Web App

Go to Create a resource → Web App.

Configure:

Resource Group: ManagedPlatform

App Name: imgapi[unique-name]

Runtime Stack: .NET 8 (LTS)

OS: Windows

Pricing Plan: Standard S1

Click Review + Create, then Create.

Once deployed, copy the Default domain URL.

Step 5: Configure Environment Variables

Go to Settings → Environment Variables.

Add:

Name: StorageConnectionString

Value: Paste the copied storage connection string.

Click Apply.

Step 6: Deploy an ASP.NET Web API

Open Visual Studio Code and load F:\Allfiles\Labs\01\Starter\API.

Open the terminal and run:

az login
az webapp list --resource-group ManagedPlatform
cd F:\Allfiles\Labs\01\Starter\API
az webapp deployment source config-zip --resource-group ManagedPlatform --src api.zip --name <name-of-your-api-app>

In Azure Portal, navigate to the deployed Web App and click Browse to test.
Exercise 2: Build a Front-End Web Application Using Azure Web Apps

Step 1: Create a Web App for the Frontend

Go to Create a resource → Web App.

Configure:

Resource Group: ManagedPlatform

App Name: imgweb[unique-name]

Runtime Stack: .NET 8 (LTS)

OS: Windows

Pricing Plan: Standard S1

Click Review + Create, then Create.

Step 2: Deploy the Frontend Web Application

Open Visual Studio Code and load F:\Allfiles\Labs\01\Starter\Frontend.

Open appsettings.json and update the API base URL.

Open the terminal and run:

az login
cd F:\Allfiles\Labs\01\Starter\Frontend
az webapp deployment source config-zip --resource-group ManagedPlatform --src frontend.zip --name <name-of-your-web-app>

Step 3: Test the Web Application

Go to Azure Portal → ManagedPlatform → imgweb[unique-name].

Click Browse to verify the frontend.

Review & Summary

✅ Created a backend API using Azure Storage and Web Apps.✅ Configured App Service environment variables.✅ Deployed the API using Azure CLI and Kudu zip deployment.✅ Created a frontend web app and deployed it to Azure.✅ Verified communication between frontend and backend services.

For detailed instructions, refer to the official lab guide: AZ-204 Lab 01.