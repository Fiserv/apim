# Make Your First API Call

This section describes how to make API call  API and getting a response payload using  testing tools such as Postman,thunder Client and others.
## Prerequisites
To make an API call, you need:
- Fiserv Dev Studio user account  
- need to download postman collection
- import postman collection in to postman app
- Get API_key and APIt_secret

  
### Generating an Access Token
### URL

``POST https://connect-dev.fiservapis.com/fts/apim/consumer-management/v1/token/generate ``

### Authorization
From the authirization select Basic Auth and provide:

``Username= **API key** and Password= **API secret**``

[Postman-Authorization-screenshot.png](https://raw.githubusercontent.com/Fiserv/apim/develop/assets/images/Postman-Authorization-screenshot.png
)


### Request Body

From the Body tab, select the **x-www-form-urlencoded** radio button and enter the following key-value pair:

``grant_type = client_credentials``



[Postman-OauthRequestBody-screenshot](https://raw.githubusercontent.com/Fiserv/apim/develop/assets/images/Postman-OauthRequestBody-screenshot.png)

### Response

**Sample Response**
```
{
    "api_product_list": "[FTS-APIM-APIHub-Product]",
    "api_product_list_json": [
        "FTS-APIM-APIHub-Product"
    ],
    "organization_name": "prj-fisv-n-apigeee4aa22a1",
    "token_type": "BearerToken",
    "issued_at": "1722795870202",
    "client_id": "zTB234Hoth3er7LXVT6p87erwgZAqjLefhIY",
    "access_token": "CrhZibY1t4eRXONuY8KmUqF6hyeA",
    "application_name": "db2f77f0-9a22-42f6-9451-546149841313",
    "scope": "",
    "expires_in": "899",
    "status": "approved"
}
```
[AccessToken-Response](https://raw.githubusercontent.com/Fiserv/apim/develop/assets/images/AccessToken-Response-screenshot.png)

To  make an API call using Postman application:
1. Open a web or desktop application of Postman.
2.	Create a new HTTP request
3.	Set the API method to POST, GET OR PUT
4.	Insert the request URL
5.	Under the Authentication tab, select the Type value as Bearer Token and insert access token in the Token box

[Bearer Token-screenshot](https://raw.githubusercontent.com/Fiserv/apim/develop/assets/images/assets/images/Bearer Token-screenshot.png)

6.	Insert the request-payload under the Body tab. Make sure that the raw radio button is activated and the text format is set to JSON for POST AND PUT API methode:

[API-RequestBody-screenshot](https://raw.githubusercontent.com/Fiserv/apim/assets/images/API-RequestBody-screenshot.png)

 <!-- theme: info -->
    > #### Note
    >
    > Default request-payload can be copied from the API Explorer document and you may modify certain fields as mentioned in the documentation.
7.	Modify the field values in JSON code that you want to test POST AND PUT API methode
8.	Click Send. API response is generated in the Response section
   
