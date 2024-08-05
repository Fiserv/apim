# Before You Start
<!-- theme: info -->
Before you start integration, you need to  register on the Fiserv Developer Studio. 
## Register on Fiserv Developer Studio
This section describes the process to create an account on Fiserv Developer Studio and generating access token.

### Creating an Account

Perform the following steps to create an account on Fiserv Developer Studio:
1.	From the top-right corner of the screen, click **Create account**
2.	Populate the required fields and click **Next**
3.	Follow the instructions on the screen to set up your account
4.	Sign in to your Fiserv Developer Studio account once it is activated


## Generating Access Token
### URL

``POST https://connect-dev.fiservapis.com/fts/apim/consumer-management/v1/token/generate ``

### Authorization
From the authirization select Basic Auth and provide:

``Username= **API key** and Password= **API secret**``

![Postman-Authorization-screenshot](https://raw.githubusercontent.com/Fiserv/apim/develop/assets/images/Postman-Authorization-screenshot.png)



### Request Body

From the Body tab, select the **x-www-form-urlencoded** radio button and enter the following key-value pair:

``grant_type = client_credentials``



![Postman-OauthRequestBody-screenshot](https://raw.githubusercontent.com/Fiserv/apim/develop/assets/images/Postman-OauthRequestBody-screenshot.png)

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

![AccessToken-Response](https://raw.githubusercontent.com/Fiserv/apim/develop/assets/images/AccessToken-Response-screenshot.png)
   
