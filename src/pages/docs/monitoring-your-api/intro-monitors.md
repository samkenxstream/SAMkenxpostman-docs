---
title: "Monitoring your APIs"
updated: 2023-03-20
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Grouping requests in collections"
    url: "/docs/sending-requests/intro-to-collections/"
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Videos"
  - type: link
    name: "API Monitoring | The Exploratory"
    url: "https://youtu.be/tDQzY1Hn2LY"
  - type: link
    name: "API Lifecycle, Part 2: Monitor and Deploy an API | Postman Intergalactic"
    url: "https://youtu.be/voAUfBx8fnE"
  - type: subtitle
    name: "Blog posts"
  - type: link
    name: "Integrated API Monitoring in Postman"
    url: "https://blog.postman.com/integrated-api-monitoring-in-postman/"
  - type: link
    name: "Shifting Left with Postman"
    url: "https://blog.postman.com/shifting-left-with-postman/"
  - type: subtitle
    name: "Case Studies"
  - type: link
    name: "Hathway uses monitors to identify issues with integrations"
    url: "https://www.postman.com/case-studies/hathway/"
  - type: link
    name: "Momentive tracks production API performance with monitors"
    url: "https://www.postman.com/case-studies/momentive/"
  - type: subtitle
    name: "Public workspaces"
  - type: link
    name: "Postman API Monitoring Examples"
    url:  "https://www.postman.com/postman/workspace/e348c5a0-2965-44cc-87ed-7b316516f38d"
---

Postman Monitors give you continuous visibility into the health and performance of your APIs. Collection-based monitors enable you to run API test scripts, chain together multiple requests, and validate critical API flows.

Once the monitor is running you’ll be alerted to any test failures, so you can identify and address issues before your API’s consumers are affected.

## Contents

* [Collection-based monitors](#collection-based-monitors)
* [Monitor use cases](#monitor-use-cases)
* [Comparing monitors and collection runs](#comparing-monitors-and-collection-runs)
* [Next steps](#next-steps)

## Collection-based monitors

A collection-based monitor runs a series of requests from the Postman cloud on a schedule you set. When creating a monitor, you choose a [collection](/docs/sending-requests/intro-to-collections/) with the requests you want to run. These can be basic requests that indicate whether an endpoint is up and reachable. More complex collections can make use of [chained requests](https://www.youtube.com/watch?v=shYn3Ys3ygE), [test scripts](/docs/writing-scripts/test-scripts/), and [environment variables](/docs/sending-requests/managing-environments/) to validate API responses and functionality.

You can configure your monitors to run as often as you would like, depending on your [Postman plan](https://www.postman.com/pricing/). For paid plans, monitors can be scheduled to run as often as every five minutes. For free plans, monitors can be scheduled to run as often as every hour. If you are on a Postman paid plan, you can even specify which region of the world you’d like to run the collection from.

Get alerted by email if a test fails or errors occur, or [set up integrations](/docs/integrations/intro-integrations/) to be notified over Slack and other channels. All results are recorded on the monitor’s dashboard, so you can view past results or inspect trends over time.

Learn how to [set up a collection-based monitor](/docs/monitoring-your-api/setting-up-monitor/).

## Monitor use cases

Because they run Postman requests and scripts, collection-based monitors can be used to monitor APIs in a variety of ways. Here are some things you can do with collection-based monitors:

* **Check API health and performance** - Ensure the API is up and running in production and other environments.
* **Validate API response structure and data** - Ensure the API is functioning according to specifications.
* **Test complex, multi-step workflows** - Ensure that critical API flows and edge cases are working as expected.
* **Run tests in multiple environments and regions** - Ensure your APIs are working everywhere. (Running monitors in multiple regions requires a paid Postman plan.)
* **Monitor the security of your endpoints** - Continuously test APIs for known security vulnerabilities.
* **Visualize results on the monitor dashboard** - Get better visibility into API performance over time and identify trends.

> For more examples of monitors in action, visit the [Postman API Monitoring Examples public workspace](https://www.postman.com/postman/workspace/postman-api-monitoring-examples/overview) to find example collections for some common monitoring use cases. You can collaborate on the collections in the workspace by [creating a fork](/docs/collaborating-in-postman/using-version-control/forking-entities/#creating-a-fork), or customize the collections for your team's use by [exporting and importing them into your team workspace](/docs/getting-started/importing-and-exporting-data/#exporting-collections).

## Comparing monitors and collection runs

You can also schedule collection runs using the Collection Runner. Monitors are typically used to schedule runs when you want to set up alerts like triggering on-call upon failure. Choose the Collection Runner to schedule runs for automating API tests and other use cases. Learn more about [Scheduling collection runs](/docs/collections/running-collections/scheduling-collection-runs/).

Because scheduled collection runs and monitors run in the cloud, there are some differences compared to manually sending requests and running collections in Postman. To learn more, see the [Monitoring FAQs](/docs/monitoring-your-api/faqs-monitors/#can-i-upload-data-files-or-attach-files-to-a-monitor).

## Next steps

To learn how to set up a new collection-based monitor, go to [Setting up a collection-based monitor](/docs/monitoring-your-api/setting-up-monitor/).
