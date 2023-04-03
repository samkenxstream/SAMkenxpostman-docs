---
title: "Postman API authentication"
updated: 2022-02-17
search_keyword: "postman-api-key, collection-access-key, postman-api"
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Postman API authentication"
    url: "/docs/developer/postman-api/authentication/"
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Videos"
  - type: link
    name: "Intro to the Postman API | Postman Level Up"
    url: "https://www.youtube.com/watch?v=iEtsp6o4AJg"
  - type: link
    name: "User Info from the Postman API | Postman Level Up"
    url: "https://www.youtube.com/watch?v=k2bvdqxDcsU"
  - type: subtitle
    name: "Blog posts"
  - type: link
    name: "Filtering and Sorting APIs Using the Postman API"
    url: "https://blog.postman.com/filtering-and-sorting-apis-using-the-postman-api/"
  - type: link
    name: "Introducing an API to Access Mock Server Call Logs"
    url: "https://blog.postman.com/introducing-an-api-to-access-mock-server-call-logs/"
  - type: link
    name: "Introducing APIs to Access and Manage Server-Level Responses on a Mock Server"
    url: "https://blog.postman.com/apis-to-access-manage-server-level-responses-mock-server/"
  - type: subtitle
    name: "Public workspaces"
  - type: link
    name: "Postman API collection"
    url:  "https://www.postman.com/postman/workspace/postman-public-workspace/collection/12959542-c8142d51-e97c-46b6-bd77-52bb66712c9a?ctx=documentation"
  - type: link
    name: "Postman API definition"
    url:  "https://www.postman.com/postman/workspace/postman-public-workspace/api/72a32ca3-f06a-4e83-a933-2821a0e6616f/definition/d429098b-1789-4c62-b77b-cf02024aba53?view=documentation"
  - type: subtitle
    name: "Next steps"
  - type: link
    name: "Continuous Integration"
    url: "/docs/running-collections/using-newman-cli/continuous-integration/"
---

The use of the Postman API requires authentication.

## Contents

* [Generate a Postman API key](#generate-a-postman-api-key)
* [Generate a collection access key](#generate-a-collection-access-key)

## Generate a Postman API key

You need a valid Postman API key to send requests to the Postman API.

1. Open your [**API Keys** page](https://go.postman.co/settings/me/api-keys). Select your avatar in the Postman header, then select **Settings**. Then select **API keys**.

2. If you do not have a key you will be prompted to create one. Select **Generate API Key**.

   <img alt="Generate API Key" src="https://assets.postman.com/postman-docs/v10/no-api-keys-generate-v10.jpg" width="600px"/>

3. Enter a name for your key and select **Generate API Key**.

4. Copy your key.

    <img src="https://assets.postman.com/postman-docs/v10/copy-your-api-key-v10.jpg" alt="Copy your API key" width="600px"/>

Once you generate your API keys you can manage them in your workspace. Select the more actions icon <img alt="More actions icon" src="https://assets.postman.com/postman-docs/icon-more-actions-v9.jpg#icon" width="16px"> next to a key to regenerate, rename, or delete it.

<img src="https://assets.postman.com/postman-docs/v10/api-keys-regenerate-rename-delete-v10.jpg" alt="View your API keys"/>

Use **API key settings** to specify expiration periods for your keys.

<img src="https://assets.postman.com/postman-docs/v10/postman-api-key-settings-v10.jpg" width="600px" alt="API key settings"/>

### Use your Postman API key

After you have a Postman API key, you must authenticate your requests to the Postman API by sending your API Key in the `X-Api-Key` header of every request you make.

You can also send the key as an `apikey` URL query parameter. An API key sent as part of the header has a higher priority in case you send the key using both request header and query parameter.

Your API Key provides access to any Postman data you have permissions for.

You can store your API key in a [variable](/docs/sending-requests/variables/). If you name it `postman_api_key`, the Postman API collection will use it automatically.

## Generate a collection access key

With a collection access key, you can securely grant other users read-only access to a single collection. Your [API Keys page](https://go.postman.co/settings/me/api-keys) has a list of all the collection access keys you have generated, and includes information about which collection the key belongs to and when it was generated.

You will generate a new collection access key every time you share a collection using the Postman API. To learn more, see [Sharing using the Postman API](/docs/collaborating-in-postman/sharing/#sharing-using-the-postman-api).

To revoke a collection access key, select **Delete**.

<img alt="Deleting collection access keys" src="https://assets.postman.com/postman-docs/v10/collection-access-keys-v10.jpg"/>
