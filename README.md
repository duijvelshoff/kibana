# Kibana

## Prerequisites

### Elasticscearch Engine

Kibana gives you insight in your Elasticsearch data, uses Elasticsearch as it's mandatory backed application.
 
- Elasticsearch Url => *The Url must be including the port (i.e. https://elastic.tada.red:9200/).*
- Elasticsearch Username => Kibana Service Account
- Elasticsearch Password => Kibana Service Account Password

*More details on the Elasticsearch will come later or [contact me](http://t.me/nduijvelshoff)*

### App Registration

A App Registration is a Azure AD entry that allows you to authenticate with Azure AD against your Application.

#### Create App Registration

1. Login to your **Azure Account** through the [current portal](https://portal.azure.com/).
2. Select **Active Directory** from the left pane.
3. Now click on **App Registrations** in the Manage column.
4. To create click on **New application registration**.
5. As name you can fill in: *"Kibana"*, the type must be : *"WebApp/API"* and the Sign-on URL must be: *"https://{siteName}.azurewebsites.net/oauth2/callback"*.

*NOTE: {siteName} will be generated when you start the Azure Deployment, therefor it's recommended to start the deployment and then copy the generated "siteName" value.*

#### Get Service Client Id

1. Login to your **Azure Account** through the [current portal](https://portal.azure.com/).
2. Select **Active Directory** from the left pane.
3. Now click on **App Registrations** in the Manage column.
4. Open your registered app by clicking on the name (i.e. "Kibana").
5. The value of *Application ID* is your *Client Id* in the wizard.

#### Create a Client Secret

1. Login to your **Azure Account** through the [current portal](https://portal.azure.com/).
2. Select **Active Directory** from the left pane.
3. Now click on **App Registrations** in the Manage column.
4. Open your registered app by clicking on the name (i.e. "Kibana").
5. Click on **settings** to open the settings panel.
6. Now click on **Keys** in the API Access column.
7. Give the new key a description, select a duration and hit **Save**, after saving the Client Secret will show up in the value column. *Save that for later, You will not be able to retrieve the key later so you will want to copy it now.*

#### Add Permissions

1. Login to your **Azure Account** through the [current portal](https://portal.azure.com/).
2. Select **Active Directory** from the left pane.
3. Now click on **App Registrations** in the Manage column.
4. Open your registered app by clicking on the name (i.e. "Kibana").
5. Click on **settings** to open the settings panel.
6. Now click on **Required permissions** in the API Access column.
7. If "Microsoft Graph" is not in the list, click on **Add** and select the "Microsoft Graph" API, else open "Microsoft Graph".
8. Select "Read all groups" and "Read user mail" within the "Delegated Premissions" column and click on **Done** or **Save**.
9. Since the right "Read all groups" requires *Admin Consent*, click on **Grant Premissions** and confirm by clicking **Yes**.

## Installation on Azure

When all the Prerequisites are completed you can start the deployment, by just clicking this button:
[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://surlt.xyz/2S3HhE9)