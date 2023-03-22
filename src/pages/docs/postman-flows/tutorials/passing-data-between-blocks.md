---
title: "Passing data between blocks"
updated: 2023-01-18
warning: false
contextual_links:
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Blog posts"
  - type: link
    name: "Postman Flows is now more powerful and user-friendly"
    url: "https://blog.postman.com/postman-flows-is-now-more-powerful-and-user-friendly/"
---

Postman Flows can get data with [API requests](/docs/getting-started/sending-the-first-request/) or directly from the **Start** block. This tutorial shows examples of Postman Flows getting data using both methods and passing data between blocks.

## Contents

* [Getting data and passing it between blocks](#getting-data-and-passing-it-between-blocks)
    * [Getting data with an API request](#getting-data-with-an-api-request)
    * [Getting data from the Start block](#getting-data-from-the-start-block)
* [Passing specfied data between blocks](#passing-specified-data-between-blocks)

## Getting data and passing it between blocks

These examples get response data with [API requests](/docs/getting-started/sending-the-first-request/) from existing collections in your workspace and from data pasted into the **Start** block. In these examples, the entire response is passed between blocks.

### Getting data with an API request

In this example, the **Send Request** block gets data using a collection's GET request. The **Send Request** block then passes all the data to a **Log** block.

1. [Create a collection](/docs/getting-started/creating-the-first-collection/) named `Random User Collection` and add a GET request with this URL: `https://randomuser.me/api/`.

1. Select **Send**.

    ![Select Send](https://assets.postman.com/postman-docs/v10/flow-get-request-v10.jpg)

1. Select **Save**.

1. [Create a new flow](/docs/postman-flows/flows-intro/building-your-first-flow/) and connect a **Send Request** block to the **Start** block.

    ![Create a flow and add a Send Request block](https://assets.postman.com/postman-docs/v10/flow-data-send-request-v10.jpg)

1. In the **Send Request** block, select **Add request > Random User Collection > New Request**. Each time the flow executes, it will get data using the GET request from the Random User Collection request you created earlier.

    ![Select Add request](https://assets.postman.com/postman-docs/v10/flow-select-data-v10.jpg)

1. Connect a **Log** block to the **Send Request** block's **Success** port.

    ![Add a Log block](https://assets.postman.com/postman-docs/v10/flow-add-log-block-2-v10.jpg)

1. Select **Console** then select **Run**. The **Log** block sends the entire response to the console, including request headers, response headers, and the response body.

### Getting data from the Start block

In this example, the flow gets data from the **Start** block and passes it to an **Evaluate** block. The **Evaluate** block passes the entire response to the **Log** block in a variable.

1. [Create a new flow](/docs/postman-flows/flows-intro/building-your-first-flow/) and select the gear icon <img alt="Gear icon" src="https://assets.postman.com/postman-docs/icon-settings-v9.jpg#icon" width="16px"> in the **Start** block.

    ![Select the gear icon](https://assets.postman.com/postman-docs/v10/flow-start-configure-1-v10.jpg)

1. Select **Enter Incoming Data** and paste in the sample data below. The flow will use this data every time it executes.

   ``` json
   {
      "results": [
         {
               "gender": "female",
               "name": {
                  "title": "Miss",
                  "first": "Astrid",
                  "last": "Klingenberg"
               },
               "location": {
                  "street": {
                     "number": 2547,
                     "name": "Lyseskrenten"
                  },
                  "city": "Tvedestrand",
                  "state": "Oppland",
                  "country": "Norway",
                  "postcode": "6523",
                  "coordinates": {
                     "latitude": "44.5909",
                     "longitude": "130.7502"
                  },
                  "timezone": {
                     "offset": "+9:00",
                     "description": "Tokyo, Seoul, Osaka, Sapporo, Yakutsk"
                  }
               },
               "email": "astrid.klingenberg@example.com",
               "login": {
                  "uuid": "263e48e9-1d6d-4d18-9458-27b1b7bad1b9",
                  "username": "lazycat514",
                  "password": "francois",
                  "salt": "YAY2fGhq",
                  "md5": "0ed2300b7aad0843267d658db0f22f2a",
                  "sha1": "57ef1b1c5cac06feb6712ac863b7c9d6292e400e",
                  "sha256": "5312eee0d8693e522aa62814fb49fb3239bad5326ca0f37011a97704978a4add"
               },
               "dob": {
                  "date": "1984-03-11T08:50:14.752Z",
                  "age": 38
               },
               "registered": {
                  "date": "2003-09-27T19:45:20.432Z",
                  "age": 19
               },
               "phone": "57680755",
               "cell": "96350131",
               "id": {
                  "name": "FN",
                  "value": "11038429851"
               },
               "picture": {
                  "large": "https://randomuser.me/api/portraits/women/68.jpg",
                  "medium": "https://randomuser.me/api/portraits/med/women/68.jpg",
                  "thumbnail": "https://randomuser.me/api/portraits/thumb/women/68.jpg"
               },
               "nat": "NO"
         }
      ],
      "info": {
         "seed": "4be1e2e93f6d34ba",
         "results": 1,
         "page": 1,
         "version": "1.4"
      }
   }
   ```

1. Select the **Language** dropdown list and select **JSON**.

    ![Select JSON](https://assets.postman.com/postman-docs/v10/flow-passing-data-start-1-v10.jpg)

1. Connect an **Evaluate** block to the **Start** block.
1. In the **Evaluate** block, select **key** and enter `body`. This assigns all the data received from the **Start** block to the variable `body`.

    ![Add variable body](https://assets.postman.com/postman-docs/v10/flow-body-v10.jpg)

1. In the **Evaluate** block, select **Enter FQL query** and enter `body`. This sends all the data in the `body` variable to the **Evaluate** block's output.
1. Connect a **Log** block to the **Evaluate** block.

    ![Connect a Log block](https://assets.postman.com/postman-docs/v10/flow-body-log-v10.jpg)

1. Select **Console** then select **Run**. The flow gets the data from the **Start** block, routes it to the **Evaluate** block, and passes the entire response to the **Log** block, which displays the data in the console.

## Passing specified data between blocks

You can extract specific values from response data in a number of ways using variables and [Flows Query Language (FQL)](/docs/postman-flows/flows-query-language/introduction-to-fql/). The example below uses FQL in an **Evaluate** block to get the `country` field value from sample response data in the **Start** block.

1. [Create a new flow](/docs/postman-flows/flows-intro/building-your-first-flow/) and select the gear icon <img alt="Gear icon" src="https://assets.postman.com/postman-docs/icon-settings-v9.jpg#icon" width="16px"> in the **Start** block.

    ![Select the gear icon](https://assets.postman.com/postman-docs/v10/flow-start-configure-v10.jpg)

1. Select **Enter Incoming Data** and paste in the sample data below. The flow will use this data every time it executes.

   ``` json
   {
      "results": [
         {
               "gender": "female",
               "name": {
                  "title": "Miss",
                  "first": "Astrid",
                  "last": "Klingenberg"
               },
               "location": {
                  "street": {
                     "number": 2547,
                     "name": "Lyseskrenten"
                  },
                  "city": "Tvedestrand",
                  "state": "Oppland",
                  "country": "Norway",
                  "postcode": "6523",
                  "coordinates": {
                     "latitude": "44.5909",
                     "longitude": "130.7502"
                  },
                  "timezone": {
                     "offset": "+9:00",
                     "description": "Tokyo, Seoul, Osaka, Sapporo, Yakutsk"
                  }
               },
               "email": "astrid.klingenberg@example.com",
               "login": {
                  "uuid": "263e48e9-1d6d-4d18-9458-27b1b7bad1b9",
                  "username": "lazycat514",
                  "password": "francois",
                  "salt": "YAY2fGhq",
                  "md5": "0ed2300b7aad0843267d658db0f22f2a",
                  "sha1": "57ef1b1c5cac06feb6712ac863b7c9d6292e400e",
                  "sha256": "5312eee0d8693e522aa62814fb49fb3239bad5326ca0f37011a97704978a4add"
               },
               "dob": {
                  "date": "1984-03-11T08:50:14.752Z",
                  "age": 38
               },
               "registered": {
                  "date": "2003-09-27T19:45:20.432Z",
                  "age": 19
               },
               "phone": "57680755",
               "cell": "96350131",
               "id": {
                  "name": "FN",
                  "value": "11038429851"
               },
               "picture": {
                  "large": "https://randomuser.me/api/portraits/women/68.jpg",
                  "medium": "https://randomuser.me/api/portraits/med/women/68.jpg",
                  "thumbnail": "https://randomuser.me/api/portraits/thumb/women/68.jpg"
               },
               "nat": "NO"
         }
      ],
      "info": {
         "seed": "4be1e2e93f6d34ba",
         "results": 1,
         "page": 1,
         "version": "1.4"
      }
   }
   ```

1. Select the **Language** dropdown list and select **JSON**.

    ![Select JSON](https://assets.postman.com/postman-docs/v10/flow-passing-data-start-1-v10.jpg)

1. Connect an **Evaluate** block to the **Start** block.
1. In the **Evaluate** block, select **key** and enter `body`. This assigns all the data received from the **Start** block to the variable `body`.

    ![Add variable body](https://assets.postman.com/postman-docs/v10/flow-body-v10.jpg)

1. In the **Evaluate** block, select **Enter FQL query** and enter `body.results.location.country`. This navigates the response data with [FQL](/docs/postman-flows/flows-query-language/introduction-to-fql/) and extracts the value for the `country` field.
1. Connect a **Log** block to the **Evaluate** block.

    ![Add a Log block](https://assets.postman.com/postman-docs/v10/flow-add-log-block-data-v10.jpg)

1. Select **Console**.
1. Select **Run**. The **Start** block sends its data to the **Evaluate** block. The FQL in the **Evaluate** block gets the value of the `country` field (`"Norway"`) in the response data and sends it to the **Log** block. `"Norway"` appears in the console.

    ![Open the console and select Run](https://assets.postman.com/postman-docs/v10/flow-console-country-1-v10.jpg)
