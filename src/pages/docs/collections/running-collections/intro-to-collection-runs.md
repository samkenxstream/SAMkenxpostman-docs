---
title: "Using the Collection Runner"
updated: 2023-03-15
search_keyword: "postman.setNextRequest, setNextRequest"
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Sending requests"
    url: "/docs/sending-requests/requests/"
  - type: link
    name: "Grouping requests in collections"
    url: "/docs/sending-requests/intro-to-collections/"
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Videos"
  - type: link
    name: "Log Response Data in Collection Runs | Postman Level Up"
    url: "https://youtu.be/UreV_7fHKiU"
  - type: link
    name: "Intro to Postman | Run a Collection"
    url: "https://youtu.be/8UR1NzuT7jg"
  - type: dynamic_blog
    name: "Blog posts"
    blog_tag: "collections"
  - type: subtitle
    name: "Case Studies"
  - type: link
    name: "Lightspeed uses a collection runner to improve testing and QA times"
    url: "https://www.postman.com/case-studies/lightspeed-commerce/"
  - type: link
    name: "iQmetrix uses a collection runner to automate tasks in other systems"
    url: "https://www.postman.com/case-studies/iqmetrix/"
---

The _Collection Runner_ enables you to run a collection's requests in a specified sequence. It logs your request [test results](/docs/writing-scripts/test-scripts/) and can use [scripts](/docs/writing-scripts/intro-to-scripts/) to pass data between requests and alter the request workflow.

You can configure the Collection Runner to meet your development needs. You can run collections using a specific environment, and can pass data files into a run. Collection runs enable you to automate your API testing, and you can schedule runs to run in the Postman cloud with the [Collection Runner](/docs/collections/running-collections/scheduling-collection-runs/) or with [monitors](/docs/collections/running-collections/scheduling-collection-runs-monitors/). You can also integrate collection runs with your CI/CD pipeline using [the Postman CLI](/docs/postman-cli/postman-cli-overview/), a Postman tool that enables you to run and test collections directly from the command line.

## Contents

* [Configuring a collection run](#configuring-a-collection-run)
* [Debugging run results](#debugging-run-results)
* [Sharing collection runs](#sharing-collection-runs)
* [Automating collection runs](#automating-collection-runs)
* [Next steps](#next-steps)

## Configuring a collection run

1. Select **Collections** in the sidebar and select the collection you want to run.
1. On the overview tab, select <img alt="Runner icon" src="https://assets.postman.com/postman-docs/icon-runner-v9.jpg#icon" width="16px"> **Run**.

    <img alt="Select Run from the collection overview" src="https://assets.postman.com/postman-docs/v10/collection-runner-button.jpg" width="350px"/>

    > You can also select <img alt="Runner icon" src="https://assets.postman.com/postman-docs/icon-runner-v9.jpg#icon" width="16px"> __Runner__ from the Postman footer and drag a collection from __Collections__ or __History__ in the sidebar.

1. Select **Run manually**.
    > You can also [schedule runs](/docs/collections/running-collections/scheduling-collection-runs/) and [automate runs with the CLI](/docs/postman-cli/postman-cli-run-collection/).

1. If you want your collection to run with an environment, select it using the environment selector at the top right of Postman. You can also select __Environments__ in the sidebar, then select the environment you want to use.

1. Choose any configuration options:

    * **Iterations** - The number of iterations for your collection run. You can also run collections multiple times with different data sets to [build workflows](/docs/collections/running-collections/building-workflows/).
    * **Delay** - An interval delay in milliseconds between each request.
    * **Data** - A [data file](/docs/collections/running-collections/working-with-data-files/) for the collection run.
    * **Persist responses for a session** - Log the response headers and bodies so you can review them after running the collection. For large collections, persisting responses may affect performance.

    > Request and response details are persisted locally during your current Postman session and aren't saved permanently. Signing out of Postman, signing into another device with the same account, or refreshing your browser will end your session and remove the logged data.

    * **Advanced settings**
      * **Keep variable values** - Persist the variables used in the run, so that any variables updated by the run will remain changed after it completes. If you don't persist variables, changes aren't saved after the run completes. _Note that persisting variables in the collection run will update the current value only._
      * **Run collection without using stored cookies** - If your requests use cookies, you can optionally deactivate them for a collection run.
      * **Save cookies after collection run** - Save the cookies used in this session to the cookie manager. Any values changed by requests during the run will remain after it completes.

1. By default, your requests run in the sequence they're listed in the collection. If you need to change the order of execution, select and drag a request to its new location in the order. You can also remove an individual request from the run by clearing the checkbox next to its name.

    > You can alter the flow of execution from your request scripts using `setNextRequest` to [create workflows](/docs/collections/running-collections/building-workflows/).

1. When you've completed your configuration, select **Run (collection name)**.

![Collection Runner configuration](https://assets.postman.com/postman-docs/v10/collection-run-configuration-v10-12.jpg)

> Your [Postman plan](https://www.postman.com/pricing/) gives you a limited number of collection runs you can use each month. This limit applies to collections that you run in a workspace or the Scratch Pad using the **Run manually** option. This limit doesn't apply to [scheduled collection runs](/docs/collections/running-collections/scheduling-collection-runs/) in the Postman cloud. A collection run with multiple iterations counts as a single run.
>
> A message will display in the Collection Runner when you're approaching your usage limit. Learn more about [resource usage](/docs/administration/resource-usage/) in Postman.

## Debugging run results

When running collections manually, Postman displays the results of your request executions and test results in real time. You can view the source of the collection run, selected environment, number of iterations, total duration, number of tests, and average response time.

![Collection Runner results](https://assets.postman.com/postman-docs/v10/collection-run-results-v10-12a.jpg)

To learn more about what happened during the collection run, do any of the following:

* Select a request to view details about the request. You can view general information about the request and the request headers and body. You can also view the response headers and body if you selected the **Persist responses for a session** option when [configuring the collection run](#configuring-a-collection-run).

* Select the name of a request to open the request in a new tab. You can view any test scripts or select **Send** to send the request again.

* Select the **Passed**, **Failed**, or **Skipped** tabs to filter the results by test status. To show all requests, select the **All Tests** tab. If any tests in a request script fail during a collection run, the whole request fails.

* If your collection run included more than one iteration, select an iteration number to jump to the results of a specific iteration.

* Select **View all runs** to view a list of past runs. Learn more about [viewing run history](#viewing-run-history).

* Select **View Summary** to view a summary of the collection run, including test results. To return to the full results, select **View Results**.

![Collection Runner summary](https://assets.postman.com/postman-docs/v10/collection-run-summary-v10-12.jpg)

## Viewing run history

Each collection has a **Runs** tab, which displays past and scheduled collection runs. The **Runs** tab also shows test counts and metrics like duration and average response times.

![Collection Run History tab](https://assets.postman.com/postman-docs/v10/collection-run-tab-v10.jpg)

The **Runs** tab includes two more tabs: **Past runs** and **Scheduled runs**.

### The Past runs tab

The **Past runs** tab has controls to select how many collection runs to view, and limit the displayed runs to those from selected users, of a selected status, and either from the Collection Runner or the Postman CLI.

The following are displayed for each collection run:

* A checkbox for each run and an option to select all runs.
    * Select one or more collection runs and select **Delete** to remove them.
* The start time of the collection run.
* The run source, duration, all tests, passed tests, failed tests, skipped tests, and the average response time. Select any of these items to sort the table by that item. Select again to change the sort order.

Hover over an item to show the following controls:

* **View report** - Select to open the full results for the collection run. Learn more about [debugging run results](#debugging-run-results).
* **Share** - Select to share the results with another team member. This provides a link you can give to other team members so they can view details of this run. Note that this doesn't work in personal workspaces.

## The Scheduled runs tab

The **Scheduled runs** tab shows all the scheduled runs for the current collection. The following are displayed for each scheduled run:

* The upcoming run's scheduled time
* The name of the scheduled run
* The environment associated with the scheduled run (if any)

Hover over an item to show the following controls:

* **View** - Select to open a page detailing the scheduled collection run's latest results.
* The **more actions icon** <img alt="More actions icon" src="https://assets.postman.com/postman-docs/icon-more-actions-v9.jpg#icon" width="16px"> - Select to [pause, resume, edit, or delete](/docs/collections/running-collections/scheduling-collection-runs/#pausing-or-resuming-a-scheduled-run) the schedule.

## Sharing collection runs

You can share collection run results with others by exporting the results from the Collection Runner.

> The **Export Results** button is available in the Postman desktop app but not in the web version. <!-- TODO: Add procedure for sharing results in web version-->

To export a collection run, do the following:

1. Open the collection run in the __Runner__. You can also access the collection run using __History__ in the sidebar if you don't have the run open.
1. Select __Export Results__ at the top right to download the run.
1. Choose a location to save your downloaded collection run, then select **Save**.

## Automating collection runs

In addition to running collections manually, the Collection Runner enables you to [schedule collections](/docs/collections/running-collections/scheduling-collection-runs/) to run automatically at specified times in the Postman cloud. You can also use collection runs in conjunction with other Postman utilities to build automation into your API projects.

* [The Postman CLI](/docs/postman-cli/postman-cli-overview/) command-line interface enables you to run collections and build them into your development pipeline, responding to test outcomes to support your API performance.
* The [Newman](/docs/collections/using-newman-cli/command-line-integration-with-newman/) interface also enables you to run collections from the command line.
* Adding a [monitor](/docs/monitoring-your-api/intro-monitors/) to your collection lets you schedule collection runs and stay informed of any issues.
* You can also set up a [collection webhook](/docs/collections/running-collections/collection-webhooks/) to trigger a collection run at a specific time with your own custom payload.

## Next steps

Use the Collection Runner fundamentals you've learned to extend its functionality with workflows.

* To learn how to use scripts to build workflows with conditional sequences for running the requests in your collections, visit [Building request workflows](/docs/collections/running-collections/building-workflows/).
