---
title: "Running collections overview"
updated: 2022-11-09
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Using the Collection Runner"
    url: "/docs/collections/running-collections/intro-to-collection-runs/"
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Videos"
  - type: link
    name: "API Monitoring | The Exploratory"
    url: "https://youtu.be/tDQzY1Hn2LY"
  - type: dynamic_blog
    name: "Blog posts"
    blog_tag: "monitors"

warning: false

---

In Postman, a [collection](/docs/getting-started/creating-the-first-collection/) can be a group of saved [requests](/docs/getting-started/sending-the-first-request/), a [workflow](/docs/collections/running-collections/building-workflows/), or a [test suite](/docs/writing-scripts/test-scripts/). You might run a collection to send requests to your new API's endpoints, to retrieve data from a data source, or to test an API's functionality. Postman enables you to run collections in several ways:

* You can [run collections manually](/docs/collections/running-collections/intro-to-collection-runs/), with the Collection Runner. This is useful when you're sending a small number of requests and you don't need to repeat them many times.
* You can run collections frequently in an automated way by scheduling collection runs or by setting up monitors. [Scheduled collection runs](/docs/collections/running-collections/scheduling-collection-runs) are useful for automating testing, and [monitors](/docs/collections/running-collections/scheduling-collection-runs-monitors) are useful for checking performance, availability, and reliability.
* You can automate collection runs in your CI/CD with the [Postman CLI](/docs/postman-cli/postman-cli-overview/) or [Newman](/docs/collections/using-newman-cli/command-line-integration-with-newman/).
* You can use [webhooks](/docs/collections/running-collections/collection-webhooks/) to trigger collection runs at certain times or when a specific event happens in your application.
