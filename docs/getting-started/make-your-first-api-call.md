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
   
