# Know Our Standard API Structure 

This section describes a standard structure of request and response message of APIM APIs. 

## Request Message

All API requests must contain the following components:

*	[API Method](#api-method)
* [Request URL](#request-url)
* [Access Token](#access-token)
*	[Request Authorization](#request-authorization)
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

### Request Authorization

From the Authentication tab, select the Type value as Bearer Token and insert access token in the Token box
  

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
