---
title: "Live Collection settings"
updated: 2023-03-15
---

You can configure Live Collections settings such as update preference or status from the right sidebar in Postman. You can configure data redaction and data truncation settings only within the instrumentation code in your service.

> **Note:** Review the request and responses in a Live Collection within a sandbox or non-production environment to ensure that sensitive data is not sent to Postman. We recommend you to deploy on Production only after enabling data truncation and redaction rules to prevent any sensitive data from being sent to Postman.

## Contents

* [Live Collections configuration options](#live-collections-configuration-options)
* [Truncating and redacting sensitive data](#truncating-and-redacting-sensitive-data)

## Live Collections configuration options

To view Live Collections configuration options, select a collection, and then select the Live Collections icon <img alt="Live collections icon" src="https://assets.postman.com/postman-docs/v10/icon-live-collections.jpg#icon" width="16px"> in the right sidebar. You can also hover over the Live Collections icon <img alt="Live collections icon" src="https://assets.postman.com/postman-docs/v10/icon-live-collections.jpg#icon" width="16px"> next to the collection name, then select **Live settings**.

<img alt="Live Collections settings page" src="https://assets.postman.com/postman-docs/v10/live-collections-settings-page.jpg" width="350px">

The following configuration options are available:

* Select **Status** to turn data collection on or off for the Live Collection. Turning off data collection ensures that the Postman SDK does not send any data to the Postman cloud. This will also stop detecting any changes to the request, and stop automatic or manual updates to the collection.

* Select how updates are performed. You can choose whether changes to a Live Collection are automatically updated, or if changes must be reviewed before updating. For more information, see [Updating Live Collections](/docs/collections/live-collections/update-live-collections/).
* Select **Save Changes** to apply changes.

## Truncating and redacting sensitive data

You can configure data redaction and truncation settings for your application. This ensures that sensitive data does not reach Postman.

### Data truncation

Data truncation removes the fields from the request and response body. This will result in only the field types being sent.

To enable data truncation, add the `truncateData` option to the code in your application and set it to `true`. This is enabled by default. For example:

```json
truncateData: true
```

The following example shows response body values truncated:

<img alt="Live Collections data truncation" src="https://assets.postman.com/postman-docs/v10/live-collections-data-truncation.jpg" width="350px">

### Data redaction

Data redaction removes sensitive data from the request header, response header, request body, response body and query params. The data redaction rules obfuscate values for the fields matched by the regular expression.

To enable data redaction, add the `redactSensitiveData` option in your code and specify the regular expression to match and obfuscate the data. For example:

```json
redactSensitiveData: {
	enable: true,
	rules: {
		api_key: '\\b\\w{32}\\b',
		email_rule: '([a-zA-Z0-9_\\-\\.]+)@([a-zA-Z0-9_\\-\\.]+)\\.([a-zA-Z]{2,5})',
		bearerToken: '[bB]earer ([a-zA-Z]+[0-9]|[0-9]+[a-zA-Z]])[a-zA-Z0-9/+_.-]{15,1000}(?![a-zA-Z0-9/+.-])',
	}
}
```

The following example shows the `authorization` header value redacted:

<img alt="Live Collections data truncation" src="https://assets.postman.com/postman-docs/v10/live-collection-data-redaction-example.jpg" />
