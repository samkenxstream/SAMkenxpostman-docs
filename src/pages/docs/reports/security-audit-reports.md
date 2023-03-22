---
title: "Token Scanner report"
updated: 2023-01-11
warning: false
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Token Scanner"
    url: "/docs/administration/token-scanner/"
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Blog posts"
  - type: link
    name: "Introducing New Postman Reports for Enterprises"
    url: "https://blog.postman.com/introducing-new-postman-reports-for-enterprises/"
---

The **Token Scanner** report provides metrics including an overview of your total collections scanned, collections with exposed tokens, total exposed tokens, and separate visualizations of exposed tokens by type and over time. This report consolidates the findings of the Postman Token Scanner from your public documentation. Learn more about the Postman [Token Scanner](/docs/api-security/token-scanner/).

The Token Scanner report provides the following information for the past 30 days:

* **Published documentation scanned** - The number of published documentation sets that were reviewed by the Token Scanner.
* **Published documentation with exposed tokens** - The number of published documentation sets that have an exposed token.
* **Total exposed tokens** - The number of tokens that are exposed across all published documentation sets.
* **Exposed tokens by type** - The number of exposed tokens by type.
* **Exposed tokens over time** - The number of tokens that were exposed each day.

For more details, select some data in one of the charts. This opens the **Drill Down** pane, which contains links to the collections that contain exposed tokens, when the collection was scanned, and who published the collection.
