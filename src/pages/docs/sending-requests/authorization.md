---
title: "Authorizing requests"
order: 22
page_id: "authorization"
updated: 2022-12-12
search_keyword: "WWW-Authenticate, x-www-form-urlencoded"
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Sending your first request"
    url: "/docs/getting-started/sending-the-first-request/"
  - type: link
    name: "Requests"
    url: "/docs/sending-requests/requests/"
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Videos"
  - type: link
    name: "Intro to Postman | Authorize a Request"
    url: "https://youtu.be/7t9AB9Opprs"
  - type: link
    name: "How to Use JWT Authorization"
    url: "https://youtu.be/dLxCpd3IGys"
  - type: link
    name: "Automatically Refresh OAuth2.0 Access Tokens | Postman Level Up"
    url: "https://www.youtube.com/watch?v=FAhs9TBK-xU"
  - type: subtitle
    name: "Blog posts"
  - type: link
    name: "OAuth 2.0 just got easier: introducing token refresh and ID token support"
    url: "https://blog.postman.com/oauth-2-0-token-refresh-and-id-token-support/"
  - type: subtitle
    name: "Case Studies"
  - type: link
    name: "Intuit uses Postman's authentication protocols"
    url: "https://www.postman.com/case-studies/intuit/"
  - type: subtitle
    name: "Next steps"
  - type: link
    name: "Troubleshooting your Requests"
    url: "/docs/sending-requests/troubleshooting-api-requests/"

warning: false

---

APIs use authorization to ensure that client requests access data securely. This can involve authenticating the sender of a request and confirming that they have permission to access or manipulate the relevant data. If you're building an API, you can choose from a variety of auth models. If you're integrating a third-party API, the required authorization will be specified by the API provider.

You can pass auth details along with any request you send in Postman. Auth data can be included in the header, body, or as parameters to a request. If you enter your auth details in the __Authorization__ tab, Postman will automatically populate the relevant parts of the request for your chosen auth type. You can use variables and collections to define authorization details more safely and efficiently, enabling you to reuse the same information in multiple places.

## Contents

* [Specifying authorization details](#specifying-authorization-details)
* [Inheriting auth](#inheriting-authorization)
* [Authorization types](#authorization-types)
    * [No auth](#no-auth)
    * [API key](#api-key)
    * [Bearer token](#bearer-token)
    * [JWT bearer](#jwt-bearer)
    * [Basic auth](#basic-auth)
    * [Digest auth](#digest-auth)
    * [OAuth 1.0](#oauth-10)
    * [OAuth 2.0](#oauth-20)
        * [Authorization code](#authorization-code)
        * [Authorization code (with PKCE)](#authorization-code-with-pkce)
        * [Implicit](#implicit)
        * [Password credentials](#password-credentials)
        * [Client credentials](#client-credentials)
        * [Requesting an OAuth 2.0 token](#requesting-an-oauth-20-token)
        * [Refreshing an OAuth 2.0 token](#refreshing-an-oauth-20-token)
        * [Sharing an OAuth 2.0 token](#sharing-an-oauth-20-access-token)
        * [Changing the OAuth 2.0 token type](#changing-the-oauth-20-token-type)
    * [Hawk authentication](#hawk-authentication)
    * [AWS Signature](#aws-signature)
    * [NTLM authentication](#ntlm-authentication)
    * [Akamai EdgeGrid](#akamai-edgegrid)
* [Syncing cookies](#syncing-cookies)
* [Troubleshooting](#troubleshooting)

## Specifying authorization details

With a request open in Postman, use the __Authorization__ tab to select an auth type, then complete the relevant details for your selected type. The correct data values will be determined by your API at the server side. If you're using a third party API, refer to the provider's documentation for any required auth details.

![Authorization tab](https://assets.postman.com/postman-docs/authorization-tab-v9.jpg)

> You can use these auth types with Newman and monitors as well as in Postman.

When you select a type from the **Type** dropdown list, Postman will indicate which parts of the request your details will be included in, for example the header, body, URL, or query parameters. Postman adds your auth details to the relevant parts of the request when you select or enter them, so you can preview how your data will be sent before you run the request.

Your auth data will appear in the relevant parts of the request, for example in the __Headers__ tab. To show headers that were added automatically, select __hidden__.

<img alt="Hidden Headers" src="https://assets.postman.com/postman-docs/hidden-headers-v9.jpg" width="400px"/>

Hover over a header to get information about where it was added. To change an auth header, return to the __Authorization__ tab and update your configuration.

> You can't override headers added by your __Authorization__ selections directly in the __Headers__ tab. If you need different auth headers from those autogenerated by Postman, alter your setup in __Authorization__, or remove your auth setup and add headers manually.

Your request auth can use environment, collection, and global [variables](/docs/sending-requests/variables/). Postman doesn't save header data or query parameters to avoid exposing sensitive data such as API keys.

You can inspect a raw dump of the entire request including auth data in the Postman Console after you send it.

## Inheriting authorization

If you group your requests in [collections](/docs/sending-requests/intro-to-collections/) and folders, you can specify auth details to reuse throughout a group.

By default, requests inside the collection or folder will inherit auth from the parent, which means that they'll use the same auth that you've specified at the folder or collection level. To change this for an individual request, make a different selection in the request __Authorization__ tab.

## Authorization types

Select a type from the **Type** dropdown list on the **Authorization** tab. You can choose an authorization type on requests, collections, or folders.

### No auth

Postman won't send authorization details with a request unless you specify an auth type. If your request doesn't require authorization, select __No Auth__ from the __Authorization__ tab __Type__ dropdown list.

### API key

With API key auth, you send a key-value pair to the API either in the request headers or query parameters. In the request __Authorization__ tab, select __API Key__ from the __Type__ list. Enter your key name and value, and select either __Header__ or __Query Params__ from the __Add to__ dropdown list. You can store your values in variables for extra security.

[![API Key Auth](https://assets.postman.com/postman-docs/api-key-auth-selection-v9.jpg)](https://assets.postman.com/postman-docs/api-key-auth-selection-v9.jpg)

Postman will append the relevant information to your request __Headers__ or the URL query string.

### Bearer token

Bearer tokens enable requests to authenticate using an access key, such as a JSON Web Token (JWT). The token is a text string, included in the request header. In the request __Authorization__ tab, select __Bearer Token__ from the __Type__ dropdown list. In the __Token__ field, enter your API key value. For added security, store it in a variable and reference the variable by name.

Postman will append the token value to the text `Bearer` in the required format to the request Authorization header as follows:

```shell
Bearer <Your API key>
```

> If a custom prefix is needed, use an [API Key](#api-key) with a key of __Authorization__.

### JWT bearer

Postman also supports generating JWT bearer tokens to authorize requests. You can enter a payload in an editor, and JWT tokens are generated and added to the request. In the request __Authorization__ tab, select __JWT Bearer__ from the __Type__ dropdown list.

* **Add JWT token to** -  Select **Request Header** or **Query Param** to specify how the JWT token will be added to your request.
* **Algorithm** - Select an algorithm to use for the JWT token. Supported algorithms include:

    * **HS** - HMAC with SHA
    * **RS** - RSA (RSASSA-PKCS1-v1_5) with SHA
    * **ES** - ECDSA with SHA
    * **PS** - RSA (RSASSA-PSS) with SHA

* **Secret** - The secret that’s used with the HMAC-SHA algorithm.
* **Secret Base64 encoded** - If the secret is encoded in the base-64 format.
* **Private key** - The private key for signing the token for RS, ES, and PS algorithms. Select **Select file** to upload a private key in PKCS #8 format.

* **Payload** - Enter the payload data for your JWT token, in JSON format.

In the Advanced configuration section, you can also configure the following items. If you don't configure them, they are generated automatically.

* **Header prefix** - An optional prefix to use at the start of headers. This header prefix is part of the request and not a part of JWT.

* **Headers** - Any custom headers you also want to send in the JWT token. Headers pertaining to the selected algorithm are automatically added.

### Basic auth

Basic authentication involves sending a verified username and password with your request. In the request __Authorization__ tab, select __Basic Auth__ from the __Type__ dropdown list.

Enter your API username and password in the __Username__ and __Password__ fields. For extra security, store these in variables.

In the request __Headers__, the Authorization header passes the API a Base64 encoded string representing your username and password values, appended to the text `Basic` as follows:

```shell
Basic <Base64 encoded username and password>
```

### Digest auth

With Digest auth, the client sends a first request to the API, and the server responds with a few details, including a number that can be used only once (a _nonce_), a realm value, and a `401` unauthorized response. You then send back an encrypted array of data including a username and password combined with the data received from the server in the first request. The server uses the passed data to generate an encrypted string and compares it against what you sent to authenticate your request.

In the __Authorization__ tab for a request, select __Digest Auth__ from the __Type__ dropdown list. Postman will present fields for both stages of authentication request. It will autocomplete the fields for the second request in the **Advanced** section using data returned from the server by the first request. To enable Postman to automate the flow, enter __Username__ and __Password__ values (or variables) and these will be sent with the second request.

> If you don't want Postman to automatically extract the data, select **Yes, disable retrying the request** in the left column. If you do this, you will need to complete the advanced fields and run each request manually.

Setting the fields in the **Advanced** section is optional. Postman will populate them automatically when your first request runs.

* **Realm** - A string specified by the server in the `WWW-Authenticate` response header.
* **Nonce** - A unique string specified by the server in the `WWW-Authenticate` response header.
* **Algorithm** - A string that indicates a pair of algorithms used to produce the digest and a checksum. Postman supports `MD5` and `SHA` algorithms.
* **qop** - The quality of protection applied to the message. The value must be one of the options specified by the server in the `WWW-Authenticate` response header.
* **Nonce Count** - The hexadecimal count of the number of requests (including the current request) that the client has sent with the nonce value in this request.
* **Client Nonce** - An opaque quoted string value provided by the client, used by both client and server to avoid chosen plaintext attacks, to provide mutual authentication, and to provide some message integrity protection.
* **Opaque** - A string of data specified by the server in the `WWW-Authenticate` response header, which will be used unchanged with URIs in the same protection space.

### OAuth 1.0

OAuth 1.0 enables client applications to access data provided by a third-party API. For example, as a user of a service, you can grant another application access to your data with that service without exposing details like your username and password. Accessing user data with OAuth 1.0 involves a few requests back and forth between client application, user, and service provider.

OAuth 1.0 is sometimes referred to as "two-legged" (auth only between client and server) or "three-legged" (where a client requests data for a user of a third-party service). An example OAuth 1.0 flow could run as follows:

* To request user data with a third-party service, a consumer (client application) requests an access token using credentials such as a key and secret.
* The service provider issues an initial token (that doesn't provide access to user data) and the consumer requests authorization from the user.
* When the user grants auth, the consumer makes a request to exchange the temporary token for an access token, passing verification from the user auth.
* The service provider returns the access token and the consumer can then make requests to the service provider to access the user's data.

> Postman supports [OAuth Core 1.0 Revision A](https://oauth.net/core/1.0a/).

To use OAuth 1.0, do the following:

1. In the __Authorization__ tab for a request, select __OAuth 1.0__ from the __Type__ dropdown list.

1. Select a __Signature Method__ from the dropdown list. This will determine which parameters to include with your request. Postman supports `HMAC-SHA1`, `HMAC-SHA256`, `HMAC-SHA512`, `RSA-SHA1`, `RSA-SHA256`, `RSA-SHA512`, and `PLAINTEXT`.

   * If your server requires an `HMAC` or `PLAINTEXT` signature, Postman will provide __Consumer Key__, __Consumer Secret__, __Access Token__, and __Token Secret__ fields.
   * If you're using an `RSA` signature, Postman will present __Consumer Key__, __Access Token__, and __Private Key__ inputs.

1. You can optionally set advanced details—otherwise Postman will try to autocomplete these.

1. You can include the auth details either in the request headers or in the body / URL. Select one from the **Add authorization to** dropdown list. Open the __Headers__ or __Body__ tab if you want to check how the details will be included with the request.

If you send the OAuth 1.0 data in the headers, an Authorization header sending your key and secret values is appended to the string `OAuth` together with additional comma-separated required details.

> Postman will append the OAuth 1.0 information to the request __Headers__ when you have completed all required fields in your __Authorization__ setup.

If you send the OAuth 1.0 data in the body and URL, the data is added either in the request __Body__ or __Parameters__ depending on the request method.

If the request method is `POST` or `PUT`, and if the request body type is `x-www-form-urlencoded`, Postman will add the authorization parameters to the request body. Otherwise, for example in a `GET` request, your key and secret data will be passed in the URL query parameters.

The OAuth 1.0 auth parameter values are as follows:

* **Signature Method** - The method your API uses to authenticate requests.
* **Consumer Key** - A value used to identify a consumer with the service provider.
* **Consumer Secret** - A value used by the consumer to establish ownership of the key. (For `HMAC` and `PLAINTEXT` signing methods.)
* **Access Token** - A value representing the consumer's permission to access the user's data.
* **Token Secret** - A value used by the consumer to establish ownership of a given token. (For `HMAC` and `PLAINTEXT` signing methods.)
* **Private Key** - A private key to generate the auth signature. (For `RSA` signing methods.)
* Advanced Parameters:
    * **Callback URL** - URL service provider will redirect to following user authorization. (Required if your server uses OAuth 1.0 Revision A.)
    * **Verifier** - Verification code from service provider after user auth.
    * **Time Stamp** - The timestamp the server uses to prevent replay attacks outside the time window.
    * **Nonce** - A random string generated by the client.
    * **Version** - The version of the OAuth authentication protocol (1.0).
    * **Realm** - A string specified by the server in the `WWW-Authenticate` response header.
    * **Include body hash** - Hash for integrity check with request bodies _other than_ `application/x-www-form-urlencoded`. (Deactivated when you're using callback URL / verifier.)

> If your server implementation of OAuth 1.0 requires it, select __Add empty parameters to signature__.
>
> You can also select the checkbox to __Encode the parameters in the authorization header__ for your request.

### OAuth 2.0

With OAuth 2.0, you first retrieve an access token for the API, then use that token to authenticate future requests. Accessing data with OAuth 2.0 varies greatly between API service providers, but typically involves a few requests back and forth between client application, user, and API.

An example OAuth 2.0 flow could run as follows:

* A client application makes a request for the user to authorize access to their data.
* If the user grants access, the application then requests an access token from the service provider, passing the access grant from the user and authentication details to identify the client.
* The service provider validates these details and returns an access token.
* The client uses the access token to request the user data with the service provider.

To use OAuth 2.0, do the following:

1. In the __Authorization__ tab for a request, select __OAuth 2.0__ from the __Type__ dropdown list. Specify if you want pass the auth details in the request URL or headers.

   > By default Postman will append the access token to `Bearer` in the Authorization header for your request, but if your server implementation requires a different prefix, you can specify it in the __Header Prefix__ field.

1. To request an access token, fill out the fields in the __Configure New Token__ section, and select __Get New Access Token__. You can save both the token and the details to generate a token with your request or collection.

   > Once you have a token value generated and added, it will appear in the request __Headers__.

1. Enter the details for your client application, and any auth details from the service provider. This allows you to replicate your application auth flow inside Postman to test authenticated requests.

   > You can share token credentials with your team by selecting the sync token icon <img alt="Syncing icon" src="https://assets.postman.com/postman-docs/icon-syncing-v9.jpg#icon" width="16px"> next to an available token. By default Postman won't sync your token in case you don't want to share it.

1. Postman will prompt you to supply specific details depending on the OAuth 2.0 __grant__ type, which can be [Authorization code](#authorization-code), [Implicit](#implicit), [Password credentials](#password-credentials), or [Client credentials](#client-credentials).

#### Authorization code

Authorization code grant type requires the user to authenticate with the provider—an authorization code is then sent back to the client app, extracted, and exchanged with the provider for an access token to authenticate later requests.

To use authorization code grant type, enter a __Callback URL__ for your client application (which needs to be registered with the API provider), together with various details provided by the API service including __Auth URL__, __Access Token URL__, __Client ID__, and __Client Secret__.

> You can enter your auth details in the web browser, instead of in Postman, if you prefer, by selecting __Authorize using browser__.

#### Authorization code (with PKCE)

You can use PKCE (Proof Key for Code Exchange) with OAuth 2.0. When you select __Authorization Code (With PKCE)__ two more fields will become available for __Code Challenge Method__ and __Code Verifier__. You can opt to use `SHA-256` or `Plain` algorithms to generate the code challenge. The verifier is an optional 43-128 character string to connect the authorization request to the token request.

> __Authorization code (With PKCE)__ grant type coupled with __Authorize using browser__ is recommended to prevent auth code interception attacks.

#### Implicit

Implicit grant type returns an access token to the client without requiring the extra auth code step (and is therefore less secure).

To use implicit grant type with your requests in Postman, enter a __Callback URL__ you have registered with the API provider, the provider __Auth URL__, and a __Client ID__ for the app you have registered.

> You can enter your auth details in the web browser, instead of in Postman, if you prefer, by selecting __Authorize using browser__.

#### Password credentials

OAuth 2.0 Password grant type involves sending username and password directly from the client and is therefore not recommended if you're dealing with third-party data.

To use password grant type, enter your API provider's __Access Token URL__, together with the __Username__ and __Password__. In some cases you will also need to provide a client ID and secret.

#### Client credentials

Client credentials grant type is typically not used to access user data but instead for data associated with the client application.

Enter the provider's __Access Token URL__, together with the __Client ID__ and __Client Secret__ for your registered application.

#### Requesting an OAuth 2.0 token

The full list of parameters to request a new access token is as follows, depending on your grant type.

On the **Configuration Options** tab:

* **Token Name** - The name you want to use for the token.
* **Grant Type** - A dropdown list of options. This will depend on the API service provider requirements.
* **Callback URL** - The client application callback URL to redirect to after auth. This must be registered with the API provider. If not provided, Postman will use a default empty URL and try to extract the code or access token from it. If this doesn't work for your API, you can use the following URL: `https://oauth.pstmn.io/v1/browser-callback`
    * **Authorize using browser** - You can enter your credentials in your web browser, instead of the pop-up that appears in Postman by default when you use the __Authorization code__ or __Implicit__ grant type. Select this checkbox to set the __Callback URL__ to return to Postman. If you opt to authorize using the browser, make sure pop-ups are deactivated for the callback URL, otherwise it won't work.
* **Auth URL** - The endpoint for the API provider authorization server, to retrieve the auth code.
* **Access Token URL** - The provider's authentication server, to exchange an authorization code for an access token.
* **Client ID** - The ID for your client application registered with the API provider.
* **Client Secret** - The client secret given to you by the API provider.
* **Scope** - The scope of access you are requesting, which may include multiple space-separated values.
* **State** - An opaque value to prevent cross-site request forgery.
* **Client Authentication** - Send a Basic Auth request in the header, or client credentials in the request body. After upgrading to a new version, change the value here to avoid problems with client authentication.

On the **Advanced Options** tab:

* **Resource** - A URI that indicates the resource or target service where the token is intended to be used.
* **Audience** - A URI that indicates the target audience or service where the token is intended to be used.

When your config is complete, select __Get New Access Token__.

> When you use __Authorization code__ or __Implicit__ grant type, you will be prompted to supply your credentials to retrieve an access token to use in later requests. By default Postman will display a pop-up browser when you select __Request Token__. You can instead choose to authenticate using your system's default web browser. Select __Authorize using browser__ and the __Callback URL__ will autofill to return to Postman when you have completed auth in the browser, so that your requests can use the token returned on successful authentication.

A token from the API includes its details, together with the expiry, and optionally a refresh token you can use to retrieve a new access token when your current one expires. Select __Use Token__ to select the returned value.

Any successfully retrieved tokens will be listed in the request __Available Tokens__ dropdown list. Select one to send with your request. Select __Manage Tokens__ in the dropdown list to view more details or delete your tokens.

If authentication fails or times out, Postman will display an error message. You can check the error details in the console, __Retry__ to try authentication again, or edit your auth details before continuing.

> Deleting a token in Postman doesn't revoke access. Only the server that issues the token can revoke it.

#### Refreshing an OAuth 2.0 token

Before an OAuth 2.0 token generated in Postman expires, Postman automatically refreshes it in the background before you send a request that uses it. The refreshed access token is updated in any requests that it's used in. Auto-refreshing is the default behavior.

To turn this feature off or on, select **Auto-refresh access token**. To manually refresh a token, select **Refresh**. The token's expiration time displays if the token expires within the next day.

Auto-refresh is available when a refresh token is present. If no refresh token is present, the **Auto-refresh access token** toggle and the manual **Refresh** option aren't available. To check if a refresh token is present, select **Manage Tokens** in the **Token** dropdown list. If a refresh token is not present, check with the authorization service. Postman can't refresh the access tokens without the refresh token.

<img alt="Auto-refresh an OAuth 2.0 access token" src="https://assets.postman.com/postman-docs/v10/authorization-oauth2-auto-refresh-v10.jpg" width="500px"/>

> You can use auto-refresh when manually sending the request. Auto-refresh isn't used for scheduled runs or monitors for the same collection.

#### Sharing an OAuth 2.0 access token

To enable other Postman users to view and use an OAuth 2.0 access token, select **Share access token**.

<img alt="Share an OAuth 2.0 access token" src="https://assets.postman.com/postman-docs/v10/authorization-oauth2-share-v10.jpg" width="500px"/>

To revoke other users' access to a synced token, do the following:

1. Turn **Share access token** off.
1. Select **Remove Synced Token**.

After you revoke access, other users with access to the request won't be able to see or use the token.

#### Changing the OAuth 2.0 token type

Postman supports using access tokens or ID tokens for OAuth 2.0 authorization. An _access token_ enables an OAuth client to make calls to an API. An _ID token_ contains information about the authenticated user. This information can be used by an OAuth client to customize their experience.

If an ID token is present, you can select the token type (**Access token** or **ID token**) in the **Use Token Type** dropdown list. If no ID token is present, this dropdown list isn't available. To check if an ID token is present, select **Manage Tokens** in the **Token** dropdown list.

<img alt="Change the OAuth 2.0 token type" src="https://assets.postman.com/postman-docs/v10/authorization-oauth2-token-type-v10.jpg" width="500px"/>

### Hawk authentication

Hawk authentication enables you to authorize requests using partial cryptographic verification.

To use Hawk authentication, do the following:

1. In the __Authorization__ tab for a request, select __Hawk Authentication__ from the __Type__ dropdown list.

1. Enter your details in the __Hawk Auth ID__, __Hawk Auth Key__, and __Algorithm__ fields. You can optionally set advanced details, but Postman will try to generate values for them if necessary.

> When the required details are complete in the __Authorization__ tab for your request, Postman will add them to the __Headers__.

The Hawk Authentication parameters are as follows:

* **Hawk Auth ID** - Your API authentication ID value.
* **Hawk Auth Key** - Your API authentication key value.
* **Algorithm** - The hash algorithm used to create the message authentication code (MAC).
* Advanced parameters:
    * **User** - The username.
    * **Nonce** - A random string generated by the client.
    * **ext** - Any application-specific information to be sent with the request.
    * **app** - The binding between credentials and the application to prevent an attacker using credentials issued to someone else.
    * **dlg** - The ID of the application the credentials were issued to.
    * **Timestamp** - Timestamp the server uses to prevent replay attacks outside the time window.

### AWS Signature

AWS is the authorization workflow for Amazon Web Services requests. AWS uses a custom HTTP scheme based on a keyed-HMAC (Hash Message Authentication Code) for authentication.

The official AWS Signature documentation provides more detail:

* [Signing and Authenticating REST Requests](https://docs.aws.amazon.com/AmazonS3/latest/userguide/RESTAuthentication.html)
* [Use Postman to Call an API](https://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-call-api.html)

To use AWS Signature, do the following:

1. In the __Authorization__ tab for a request, select __AWS Signature__ from the __Type__ dropdown list.

1. Select the location where Postman will append your AWS auth details using the __Add authorization data to__ dropdown list, choosing the request headers or URL.

    * If you select __Request Headers__, Postman will add `Authorization` and `X-Amz-` prefixed fields in the __Headers__ tab.
    * If you select __Request URL__, Postman will add the auth details in __Params__ with keys prefixed `X-Amz-`.

1. Enter your access key and secret values directly in the fields. For extra security, you can use [secret variables](/docs/sending-requests/variables/#variable-types) for these values.

1. You can optionally set advanced fields, but Postman will autogenerate these if necessary.

The AWS Signature parameters are as follows:

* **AWS Region** - The region receiving the request (defaults to `us-east-1`).
* **Service Name** - The service receiving the request.
* **Session Token** - Required only when using temporary security credentials.

### NTLM authentication

Windows Challenge/Response (NTLM) is the authorization flow for the Windows operating system and for standalone systems.

To use NTLM authentication, do the following:

1. In the __Authorization__ tab for a request, select __NTLM Authentication__ from the __Type__ dropdown list.

1. Enter your __Username__ and __Password__ for NTLM access (use variables to avoid entering the values directly). You can optionally specify advanced parameters, but Postman will try to autocomplete these if necessary. By default your request will run a second time after extracting data received from the first. You can turn off this behavior by selecting the checkbox.

Advanced parameters for NTLM auth are as follows:

* **Domain** - The domain or host to authenticate against.
* **Workstation** - The hostname of the PC.

### Akamai EdgeGrid

Akamai EdgeGrid is an authorization helper developed and used by Akamai.

To use Akamai EdgeGrid, do the following:

1. In the __Authorization__ tab for a request, select __Akamai EdgeGrid__ from the __Type__ dropdown list.

1. Enter your __Access Token__, __Client Token__, and __Client Secret__, using variables for extra security—you will receive these details when you register a client application with Akamai.

> When the required details are complete in the __Authorization__ tab for your request, Postman will add them to the __Headers__.

For information on obtaining your credentials, see [Akamai Developer - Authorize your Client](https://techdocs.akamai.com/developer/docs/set-up-authentication-credentials).

## Syncing cookies

If you have session cookies in your browser, you can sync them to Postman using the Interceptor. See [Interceptor extension](/docs/sending-requests/capturing-request-data/interceptor/) and [Cookies](/docs/sending-requests/cookies/) for more detail.

## Troubleshooting

If you're having issues getting a request to authenticate and run successfully, review the tips in [troubleshooting API requests](/docs/sending-requests/troubleshooting-api-requests/). If you still have auth problems, check out the [authentication tag](https://community.postman.com/tags/authentication) on the Postman forum.
