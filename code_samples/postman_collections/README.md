# Postman Collection

# About

This collection allows developers to test APIs through [Postman](https://www.postman.com/) application.

# Prerequisites

* Postman desktop or web application
* Valid subscription to Schneider Electric API product

## Usage
 
* [Import collection](#import-collection)
* [Configure variables](#configure-variables)
* [Execute](#execute)


## Import collection

Import `EcoStruxure-Compliance.postman_collection.json` to postman. Refer to [postman documentation to import a collection](https://learning.postman.com/docs/getting-started/importing-and-exporting-data/#importing-data-into-postman).

## Configure variables

Provision is provided at collection level to configure variables which are used across the postman requests.

![Postman Variables](/static/images/postman-variables.png)

| Variables|Comments|
|----------|--------|
|client_id|Client ID from API subscription. Go to Developer Portal for credentials.|
|client_secret|client secret from API subscription. Go to Developer Portal for credentials.|
|token_server|The server URL to generate access token. Use this to point to different environments. Default is UAT sandbox env `https://se-exchange-uat-sandbox.apigee.net/ecostruxure/v1`|
|api_server|The server URL for APIs. Use this to point to different environments. Default is UAT sandbox env `[https://se-exchange-uat-sandbox.apigee.net/openesx/v1](https://se-exchange-uat-sandbox.apigee.net/openesx/v1)`|
|access_token|This will auto populated on execution of `token` request|
 
## Execute

Follow the steps for end to end flow.

1. [Generate access token](#generate-access-token)
2. [Invoke APIs](#invoke-apis)

### Generate access token

Execute `Token` request to genearate access_token using client_credentials grant_type. On successful execution the access token will be automatically populated to collection variable for further API calls.

![Access token](/static/images/access-token-request.png)

### Invoke APIs

Once the token is generated, use one of the following to try out APIs required for compliance use case.

* Search aasset by QR code
* Get Asset by asset id
* Get asset hierarchy
