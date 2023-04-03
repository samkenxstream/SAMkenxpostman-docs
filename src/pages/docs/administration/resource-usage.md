---
title: "About resource usage"
updated: 2023-02-06
contextual_links:
  - type: section
    name: "Additional resources"
  - type: link
    name: "Postman Plans and Pricing"
    url: "https://www.postman.com/pricing/"
  - type: link
    name: "Resource Usage dashboard"
    url: "https://go.postman.co/billing/add-ons/overview"
---

Postman provides you with a specified number of resources you can use each month, depending on your [Postman plan](https://www.postman.com/pricing/). Monthly resources include calls to the Postman API, requests made by monitors and scheduled collection runs, mock server requests, and Cloud Agent requests. Your Postman plan also has other limits, such as the number of integrations you can create, the number of custom domains, and storage for uploaded images.

To find out what the resource limits are for your plan, go to the [Postman Plans and Pricing page](https://www.postman.com/pricing/). To view the resources you are using, go to your [Resource Usage dashboard](https://go.postman.co/billing/add-ons/overview). You can view how close you are to your limits and when your monthly limits will reset. If you need more resources, you can [purchase an add-on](/docs/administration/billing/#purchasing-add-ons) or [upgrade your plan](/docs/administration/billing/#team-and-plan-changes).

Refer to the following sections to understand what happens when your resource usage reaches the limits set by your Postman plan.

## Contents

* [Mock server usage](#mock-server-usage)
* [Monitoring usage](#monitoring-usage)
* [Collection runs usage](#collection-runs-usage)
* [Custom domains](#custom-domains)
* [Storage usage](#storage-usage)
* [Postman API usage](#postman-api-usage)
* [Integrations](#integrations)
* [Cloud Agent usage](#cloud-agent-usage)

## Mock server usage

Your [Postman plan](https://www.postman.com/pricing/) gives you a limited number of requests that can be sent to your [Postman mock servers](/docs/designing-and-developing-your-api/mocking-data/setting-up-mock/) each month. Requests to all of your mock servers count toward this same limit. After the limit is reached, you will get a `Usage limit reached` error message when sending a request to one of your mock servers.

![Mock server usage error](https://assets.postman.com/postman-docs/v10/usage-error-mocks-v10.jpg)

To make more requests to your mock servers before your monthly limit resets, you can [enable pay-as-you-go](/docs/administration/billing/#managing-add-ons), [purchase an add-on](/docs/administration/billing/#purchasing-add-ons), or [upgrade your plan](/docs/administration/billing/#team-and-plan-changes).

## Monitoring usage

Your [Postman plan](https://www.postman.com/pricing/) gives you a limited number of requests that can be run by your [Postman Monitors](/docs/monitoring-your-api/setting-up-monitor/) each month. Requests run by your [scheduled collection runs](/docs/collections/running-collections/scheduling-collection-runs/) count toward this same limit. After the limit is reached, you will get a notification by email and in the Postman app letting you know that you've reached the usage limit for monitors.

<img alt="Monitors usage error" src="https://assets.postman.com/postman-docs/v10/usage-error-monitors-v10.jpg" width="361px"/>

Once you've reached your usage limit, your monitors and scheduled collection runs will no longer run on their configured schedules and can't be run manually. To resume running your monitors and scheduled collection runs before your monthly limit resets, you can [enable pay-as-you-go](/docs/administration/billing/#managing-add-ons), [purchase an add-on](/docs/administration/billing/#purchasing-add-ons), or [upgrade your plan](/docs/administration/billing/#team-and-plan-changes).

> Learn more about [viewing and managing your monitor usage](/docs/monitoring-your-api/monitor-usage/).

## Collection runs usage

Your [Postman plan](https://www.postman.com/pricing/) gives you a limited number of [collection runs](/docs/collections/running-collections/intro-to-collection-runs/) you can use each month. This limit applies to collections that you run in a workspace or the Scratch Pad using the **Run manually** option. This limit doesn't apply to [scheduled collection runs](/docs/collections/running-collections/scheduling-collection-runs/) in the Postman cloud. A collection run with multiple iterations counts as a single run.

You can check your manual collection run usage on the [Resource Usage dashboard](https://go.postman.co/billing/add-ons/overview). Also, a message will display in the Collection Runner when you're approaching your usage limit.

<img alt="Collection runner usage error" src="https://assets.postman.com/postman-docs/v10/usage-error-collection-runner-v10-12.jpg" width="504px"/>

Once you've reached your usage limit, you will no longer be able to run your collections using the **Run manually** option. To resume running collections before your monthly limit resets, you can [upgrade your plan](/docs/administration/billing/#team-and-plan-changes), [schedule collection runs](/docs/collections/running-collections/scheduling-collection-runs/) in the Postman cloud, or run collections using the [Postman CLI](/docs/postman-cli/postman-cli-run-collection/) or [Newman](/docs/collections/using-newman-cli/command-line-integration-with-newman/).

> Requests run in the Postman cloud by your [scheduled collection runs](/docs/collections/running-collections/scheduling-collection-runs/) count toward your [monitoring usage](#monitoring-usage). Scheduled collection runs don't count toward your collection runs usage.

## Custom domains

Postman paid [plans](https://www.postman.com/pricing/) give you a limited number of [custom domains](/docs/publishing-your-api/custom-doc-domains/) you can use when publishing API documentation. After the limit is reached, you won't be able to add a new custom domain.

![Custom domains limit reached](https://assets.postman.com/postman-docs/v10/usage-error-custom-domains-v10.jpg)

To add a new custom domain, delete one of your existing custom domains, [purchase an add-on](/docs/administration/billing/#purchasing-add-ons), or [upgrade your plan](/docs/administration/billing/#team-and-plan-changes).

## Storage usage

Your [Postman plan](https://www.postman.com/pricing/) gives you a limited amount of storage for [uploaded images](/docs/publishing-your-api/authoring-your-documentation/#uploading-an-image) in your API documentation. You will get an error message if you try to upload an image that would exceed your storage limit.

<img alt="Storage usage error" src="https://assets.postman.com/postman-docs/v10/usage-error-upload-v10.jpg" width="305px"/>

To upgrade your available storage, contact [Postman support](https://www.postman.com/support/).

> Learn more about [image storage limits](/docs/publishing-your-api/authoring-your-documentation/#image-storage-limits) for API documentation.

## Postman API usage

Your [Postman plan](https://www.postman.com/pricing/) gives you a limited number of requests that can be sent to the [Postman API](/docs/developer/postman-api/intro-api/) each month. After the limit is reached, you will get a `Service limit exhausted` error message when sending a request to the Postman API.

![Postman API usage error](https://assets.postman.com/postman-docs/v10/usage-error-api-v10.jpg)

To make more requests to the Postman API before your monthly limit resets, you can [upgrade your plan](/docs/administration/billing/#team-and-plan-changes).

## Integrations

Your [Postman plan](https://www.postman.com/pricing/) gives you a limited number of [integrations](/docs/integrations/intro-integrations/) for connecting Postman to third-party tools you use for API development. After the limit is reached, you won't be able to add a new integration. You will get a notification in the Postman app when attempting to add a new integration.

<img alt="Integrations limit reached" src="https://assets.postman.com/postman-docs/v10/usage-error-integrations-v10.jpg" width="361px"/>

To add a new integration, delete one of your existing integrations or [upgrade your plan](/docs/administration/billing/#team-and-plan-changes).

## Cloud Agent usage

The [Postman Cloud Agent](/docs/getting-started/about-postman-agent/#the-postman-cloud-agent) enables you to send requests from the [Postman web app](/docs/getting-started/installation-and-updates/#using-the-postman-web-app) without encountering cross-origin resource sharing (CORS) limitations. Your [Postman plan](https://www.postman.com/pricing/) gives you a limited number of requests that can be sent using the Cloud Agent each month. After the limit is reached, you will get a `Cloud Agent Error` message when sending a request from the Postman web app using the Cloud Agent.

![Cloud Agent usage error](https://assets.postman.com/postman-docs/v10/usage-error-cloud-agent-v10.jpg)

To continue sending requests from the Postman web app before your monthly limit resets, [upgrade your plan](/docs/administration/billing/#team-and-plan-changes) or switch to the Postman Desktop Agent. In the error message, select **Use Postman's Desktop Agent**. If you haven't already installed the Desktop Agent, you'll be prompted to download it.

> Learn more about [installing and using the Postman Desktop Agent](/docs/getting-started/about-postman-agent/#the-postman-desktop-agent).
