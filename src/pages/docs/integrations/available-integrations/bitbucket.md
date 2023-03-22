---
title: "Bitbucket"
order: 164.1
updated: 2021-09-15
page_id: "bitbucket"
warning: false
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Grouping requests in collections"
    url: "/docs/sending-requests/intro-to-collections/"
  - type: section
    name: "Next steps"
  - type: link
    name: "Custom Webhooks"
    url: "/docs/integrations/webhooks/"
  - type: link
    name: "Slack Integration"
    url: "/docs/integrations/available-integrations/slack/"
---

You can back up your team's Postman Collections with Postman's Bitbucket integration.

## Contents

* [API sync with Bitbucket](#api-sync-with-bitbucket)
* [Backing up collections on Bitbucket](#backing-up-collections-on-bitbucket)

    * [Configuring a Bitbucket integration](#configuring-a-bitbucket-integration)

## API sync with Bitbucket

With Postman v10, you can connect a Bitbucket repository to an API in the API Builder. Once connected, you can sync your API's definition and associated collections between Postman and Bitbucket. You can switch branches, pull changes from the repository, and push changes to the repository, all from within Postman. To learn more about syncing your API with Bitbucket, see [Using a remote Git repository](/docs/designing-and-developing-your-api/versioning-an-api/using-external-git-repo/).

## Backing up collections on Bitbucket

You can back up your Postman Collections to your Bitbucket repository. Once the integration is configured, any changes to your collection in Postman will also appear in Bitbucket.

### Configuring a Bitbucket integration

From the **[Home](https://go.postman.co/home)** page select **[Integrations](https://go.postman.co/integrations)**.

<img alt="Home page and integrations" src="https://assets.postman.com/postman-docs/v10/home-integrations-v10.jpg" width="390px">

Search and select **Bitbucket**.

![Bitbucket search page](https://assets.postman.com/postman-docs/bitbucket-search-bb.jpg)

Select **Add Integration**.

![Bitbucket details page](https://assets.postman.com/postman-docs/bitbucket-add-integration-bb.jpg)

Enter your Bitbucket authentication and select **Authenticate and Proceed**.

> App passwords are different from account passwords. Learn [how to create an app password in Bitbucket](https://support.atlassian.com/bitbucket-cloud/docs/app-passwords/).

![Bitbucket creation](https://assets.postman.com/postman-docs/bitbucket-create-bb.jpg)

Select your collection to back up, the repository you'd like to back it up to, and designate the directory, filename, and branch. Select **Add Integration**.

![Bitbucket configuration](https://assets.postman.com/postman-docs/bitbucket-configure-bb.jpg)

Your new integration appears in a list along with previously created integrations.

![Configured integrations](https://assets.postman.com/postman-docs/bitbucket-add-integration-bb.jpg)

To confirm this integration, go to your [Bitbucket dashboard](https://bitbucket.org/dashboard/overview) > **Repositories**. Select your repository, then select **Commits**.

![Bitbucket commits list](https://assets.postman.com/postman-docs/bitbucket-commits.jpg)

You can select a commit to view your stored collection in JSON format.

![Bitbucket collection](https://assets.postman.com/postman-docs/bitbucket-collection.jpg)

> **You can view your configured integrations on the [Browse Integrations](https://go.postman.co/integrations/browse) page.** You can also view integrations that have been configured for a collection by opening the collection and selecting the information icon <img alt="Information icon" src="https://assets.postman.com/postman-docs/icon-information-v9-5.jpg#icon" width="16px"> in the right sidebar. Learn more about [viewing or editing integrations](/docs/integrations/intro-integrations/#viewing-or-editing-integrations).
