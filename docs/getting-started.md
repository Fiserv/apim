<!-- 
type: tab 
titles: Before You Start, Know Our Standard API Structure, Make Your First API Call
-->
# Getting Started
APIM Consumer onboarding and Monetization center offers Fiserv developers access to seamlessly integrate with self-service APIs that perform consumer onboarding onto APIM and Ping IDPs, Product, Subscription and Reports management.

## Before You Start
<!-- theme: info -->
Before you start integration, it is important to sign in on the Fiserv Developer Studio to test the APIM Consumer onboarding and Monetization APIs in the Mock server. You may choose to test APIs using the Third-party API Testing Tools of your choice. 

## Register on Fiserv Developer Studio

This section describes the process to create an account on Fiserv Developer Studio and generating access token.

### Creating an Account

Perform the following steps to create an account on Fiserv Developer Studio:
1.	From the top-right corner of the screen, click **Create account**
2.	Populate the required fields and click **Next**
3.	Follow the instructions on the screen to set up your account
4.	Sign in to your Fiserv Developer Studio account once it is activated

## Creating a APIM Consumer Onboarding and Monetization Workspace
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

**Sample Response**
```
{
    "access_token": "e9XBKU1l81s3NvsAKcwJVImrFAbr",
    "expires_in": "899",
    "token_type": "Bearer"
}
```

![AccessToken-Response](https://raw.githubusercontent.com/Fiserv/apim/develop/assets/images/AccessToken-Response-screenshot.png)

<a href="#tab-know_our_standard_api_structure" >Next - Know Our Standard API Structure</a> 

<!-- type: tab -->

# Know Our Standard API Structure 

This section describes a standard structure of request and response message of APIM APIs. 

## Request Message

All API requests must contain the following components:

*	[API Method](#api-method)
* [Request URL](#request-url)
* [Access Token](#access-token)
*	[Request Body](#request-body)
	
### API Method

API methods are  GET, POST or PUT

### Request URL
  

Request URL is formed by appending Host URL,Base path and API path. 

<!-- theme: info -->
> **Request URL = Host URL + Base path + API path**

### Access Token

API key and API secret are required to generate an access token. 

To generate an access token, refer to the [Generating Access Token](?path=docs/getting-started/before-you-start.md#generating-access-token) section.

### Request Body

The request body of an API changes based on the type of transaction being processed. Request body contains the detailed information that is required to perform a particular transaction.


**Request Payload** 

sample request payload for **Create a consumer** API request.

```
{
    "firstName": "abc",
    "lastName": "abc",
    "userName": "abc11@fiserv.com",
    "email": "abc1@fiserv.com",
    "billingType": "POSTPAID",
    "company": "cars",
    "category": "abc-a123-tysd",
    "phone": "1234567890",
    "status": "active",
    "legalName": "abcd",
    "address": {
        "address1": "Test",
        "city": "Atlanta",
        "state": "GA",
        "zip": "30090",
        "country": "USA"
    },
    "attributes":[
        {
            "name": "AllOWED_IP_RANGES",
            "value": "10.234.0.0/90"
        },
        {
            "name": "IDP",
            "value": "apigee"
        }
    ]
}
```



### Response Payload
The response payload  returned details of the requested API in JSON format. 

Sample response payload for **Create a consumer** API request.

```
{
    "email": "abc1@fiserv.com",
    "firstName": "abc",
    "lastName": "abc",
    "userName": "abc11@fiserv.com",
    "attributes": [
        {
            "name": "ALLOWED_IP_RANGES",
            "value": "10.234.0.0/90"
        },
        {
            "name": "IDP",
            "value": "apigee"
        },
        {
            "name": "MINT_DEVELOPER_ADDRESS",
            "value": "{\"address1\":\"Test\",\"city\":\"Atlanta\",\"state\":\"GA\",\"zip\":\"30090\",\"country\":\"USA\"}"
        },
        {
            "name": "MINT_BILLING_TYPE",
            "value": "POSTPAID"
        },
        {
            "name": "COMPANY",
            "value": "cars"
        },
        {
            "name": "MINT_DEVELOPER_CATEGORY",
            "value": "abc-a123-tysd"
        },
        {
            "name": "MINT_DEVELOPER_PHONE",
            "value": "1234567890"
        },
        {
            "name": "MINT_DEVELOPER_LEGAL_NAME",
            "value": "abc abc"
        }
    ],
    "developerId": "abc-a123-tysd",
    "organizationName": "prj-fisv-n-apigeee4aa22a1",
    "status": "active",
    "createdAt": "1722800823899",
    "lastModifiedAt": "1722800823899"
}
```

[Next - Make Your First API Call](#tab-make_your_first_api_call)

<!-- type: tab -->

# Make Your First API Call

This section describes how to make API call  API and getting a response payload using  testing tools such as Postman,thunder Client and others.
## Prerequisites
To make an API call, you need:
- Fiserv Dev Studio user account  
- need to download postman collection
- import postman collection in to postman app
- Get API_key and API_secret

  
### Generating an Access Token
To generate an access token, refer to the [Generating Access Token](?path=docs/getting-started/before-you-start.md#generating-access-token) section.

### Make an API call 

To  make an API call using Postman application:
1. Download postman collection from Resources

![Download-PostmanCollection](https://github.com/Fiserv/apim/blob/develop/assets/images/Download-PostmanCollection-screenshot.png)

2. Open a web or desktop application of Postman.
3. Import postman collection to Postman app:

![Import postman collection-screenshot](https://raw.githubusercontent.com/Fiserv/apim/develop/assets/images/Import-PostmanCollection-screenshot.png)

4. Select collection from the list

5. Select the API and under the Authentication tab, select Auth Type as Bearer Token and insert access token in the Token box

![Bearer Token-screenshot](https://raw.githubusercontent.com/Fiserv/apim/develop/assets/images/Bearer-Token-screenshot.png)


6.	Insert the request-payload under the Body tab. Make sure that the raw radio button is activated and the text format is set to JSON for POST AND PUT API methode:

![API-RequestBody-screenshot](https://raw.githubusercontent.com/Fiserv/apim/develop/assets/images/API-RequestBody-screenshot.png)

 <!-- theme: info -->
    > #### Note
    >
    > You can use request-payload from Postman collection document and you may modify.
7.	Modify the field values in JSON code that you want to test POST and PUT API method
8.	Click Send. API response is generated in the Response section
   
   
