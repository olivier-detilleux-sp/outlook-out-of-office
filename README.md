# outlook-out-of-office
This SaaS Connector gets the Outlook out of Office Status through Graph API.

## Pre requisites
First, you need to create an Azure Active Directory App Registration and grant below API permissions in Microsoft Graph API

|API / Permissions name|Type|
|---|---|
|Directory.Read.All|Application|
|MailboxSettings.Read|Application|
|User.Read|Delegated|

Then, you need a client secret for this app and find your tenant Id

## Install the connector
Please refer to the https://developer.sailpoint.com/idn/tools/cli/connectors#upload-connector documentation to initialize an environment then upload the connector zip file.

## Configure a new Source
Create a new source using the new connector type.
Configure the source with your clientId, clientSecret and tenantId. In order to get only the mail enabled users, you can add a filter. For instance, to get only Business Essentials licensed users, I use this filter : `assignedLicenses/any(u:u/skuId eq 3b555118-da6a-4418-894f-7df1e2096870)`
