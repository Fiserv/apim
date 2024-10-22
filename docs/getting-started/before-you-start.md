

## Before You Start

Before you start integration, it is important to sign in on the Fiserv Developer Studio to test the APIM Consumer onboarding and Monetization APIs in the Mock server. You may choose to test APIs using the Third-party API Testing Tools of your choice. 

<!-- theme: info -->
> ### Note for Developers 
>
> To get access to a dedicated test environment, optional and ancillary services, including dedicated technical services, upgrade to a paid Developer Studio subscription plan <a href="https://appmarket.fiservapps.com/fintech" > here</a>.



## Register on Fiserv Developer Studio

This section describes the process to create an account on Fiserv Developer Studio and generating access token.

### Creating an Account

Perform the following steps to create an account on Fiserv Developer Studio:
1.	From the top-right corner of the screen, click **Create account**
2.	Populate the required fields and click **Next**
3.	Follow the instructions on the screen to set up your account
4.	Sign in to your Fiserv Developer Studio account once it is activated

## Creating a APIM Self service Workspace

Workspaces are dedicated spaces for developers to obtain API key, API secret and product related details.
Perform the following steps to create a workspace on Fiserv Developer Studio:

a.	Sign in to your Fiserv Developer Studio account

b.	From the top-right corner of the screen, click Workspaces. My Workspace page displays.

>  Note for Developers 
>
> All previously created workspaces are listed on the My workspaces page

a.	To create a new workspace, click the Add a new workspace button or click the Create a new workspace card. Create a workspace dialog box displays

b.	Enter workspace name and description.

c.	From the Product drop-down list, select APIM Consumer Onboarding and Monetization and click Create. A new workspace is created and three tabs of your workspace, namely Summary, Credentials and Settings are visible.

>  Note for Developers 
>
> Currently, only one workspace can be created for APIM Consumer Onboarding and Monetization

Every workspace has following three sections:


* **Summary**: Displays workspace details and list of activities performed on the workspace
* **Credentials**: Lists all active API keys. From this section, you can view or download the following details of an API key:
  * Product name: _Name of the product, for example, APIM Consumer Onboarding and Monetization Workspace       
  * API key: _Alphanumeric value of the API key. API key is used as username while generating the access token_
  * API secret: _Alphanumeric value of the API secret. API secret is used as password while generating the access token_
  * Host URL: _Host URL path to send API requests_
* **Settings**: Used to modify or delete the workspace


## Generating Access Token

### URL

``POST https://connect-uat.fiservapis.com/fts-apim/jwt/v1/token/generate``

### Authorization

From the authirization select Basic Auth and provide:

``Username= **API key** and Password= **API secret**``

![Postman-Authorization](https://raw.githubusercontent.com/Fiserv/apim/develop/assets/images/Postman-Authorization-screenshot.png)

### Request Body

From the Body tab, select the **x-www-form-urlencoded** radio button and enter the following key-value pair:

``grant_type = client_credentials``

![Postman-OauthRequestBody](https://raw.githubusercontent.com/Fiserv/apim/develop/assets/images/Postman-OauthRequestBody-screenshot.png)

### Response

|     Field Name      |     Description                                          |     Type      |
|---------------------|----------------------------------------------------------|---------------|
|   ``access_token``    |     Generated access token   value                       |     string    |
|``expires_in``       | <p>Time in milliseconds until the generated token is valid.</p> <p>**Note:** Once generated, the access token is valid for approximately 15 minutes. You can reuse the access token until it expires. </p> | number        |
|    ``token_type``   |     Type of access token                                 |     string    |

**Sample Response**
```
{
    "access_token": "e9XBKU1l81s3NvsAKcwJVImrFAbr",
    "expires_in": "899",
    "token_type": "Bearer"
}
```

![AccessToken-Response](https://raw.githubusercontent.com/Fiserv/apim/develop/assets/images/AccessToken-Response-screenshot.png)
