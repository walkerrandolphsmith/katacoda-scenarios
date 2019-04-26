Configure the SDK with your information

## Task

The SDK makes asynchronous requests to the VersionOne system and therefore performs AJAX requests. The SDK does not require any specific ajax library to be used but instead affords extension points to use your own ajax mechanism. Two popular options are available out of the box including jQuery ajax and Axios.

In this scenario we will use axios.

`const axios = require('axios');`{{execute}}

## Task

Include the sdk and configure it to use the axios ajax library

`const v1sdk = require('v1sdk');`{{execute}}

Using the sdk with commonjs in Node.js is slightly different than using `import` statements, but for the former run:

`const sdk = v1sdk.default;`{{execute}}
`const axiosConnector = v1sdk.axiosConnector;`{{execute}}
`const axiosConnectedSdk = axiosConnector(axios)(sdk);`{{execute}}

## Task

Configure the v1sdk to connect to your VersionOne instance by:

`const v1 = axiosConnectedSdk('V1Host', 'V1Instance', 443, true).withCreds('v1User', 'v1Password');`{{execute}}
