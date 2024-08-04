# Make Your First API Call

This section describes how to make API call  API and getting a response payload using  testing tools such as Postman,thunder Client and others.
## Prerequisites
To make an API call, you need:
- Fiserv Dev Studio user account  
- need to download postman collection
- import postman collection in to postman app
- API_key
- APIt_secret

  
### Generating an Access Token
### URL

``POST https://connect-dev.fiservapis.com/fts/apim/consumer-management/v1/token/generate ``

### Authorization
From the authirization select Basic Auth and providr Username= **API key** and Password= **API secret**

[Postman-Authorization-screenshot.png](https://raw.githubusercontent.com/Fiserv/apim/develop/assets/images/Postman-Authorization-screenshot.png
)


### Request Body

From the Body tab, select the **x-www-form-urlencoded** radio button and enter the following key-value pair:

``grant_type = client_credentials``
