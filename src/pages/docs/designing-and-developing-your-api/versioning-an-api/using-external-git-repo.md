---
title: 'Using a remote Git repository'
updated: 2023-03-15
search_keyword: "whitelist, whitelist IP"
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "API version control overview"
    url: "/docs/designing-and-developing-your-api/versioning-an-api/versioning-an-api-overview/"
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Videos"
  - type: link
    name: "Git Workflows in Postman | The Exploratory"
    url: "https://youtu.be/cB7mCuYeuAU"
  - type: link
    name: "Integrating GitLab in Postman's API Builder"
    url: "https://youtu.be/ecAQv9gZEKk"
  - type: link
    name: "API Versioning in Postman using Bitbucket"
    url: "https://youtu.be/SO_88TQ2dkE"
  - type: subtitle
    name: "Blog posts"
  - type: link
    name: "Announcing Postman’s Redesigned API Builder with Native Git Support"
    url: "https://blog.postman.com/announcing-postmans-redesigned-api-builder-with-native-git-support/"
  - type: link
    name: "Better Practices for Git Version Control in Postman"
    url: "https://blog.postman.com/better-practices-for-git-version-control-in-postman/"
  - type: link
    name: "Syncing Your Specs with Collections"
    url: "https://blog.postman.com/latest-updates-to-syncing-your-specs-with-collections/"
  - type: section
    name: "Next steps"
  - type: link
    name: "Reports overview"
    url: "/docs/reports/reports-overview/"
  - type: link
    name: "Validating elements against schema"
    url: "/docs/designing-and-developing-your-api/developing-an-api/validating-elements-against-schema/"
---

> **[GitHub Enterprise Server, GitLab Self-Managed, and Azure DevOps Server (hosted on-premises) integrations are available on Postman Enterprise plans.](https://www.postman.com/pricing)**

You can connect a GitHub, Bitbucket, GitLab, or Azure DevOps repository to your API to sync your API definition and collections between Postman and the repository.

After connecting, you can push and pull changes between Postman and branches in the remote repository. When it's time to release, you can publish an API version to make your changes available to consumers.

## Contents

* [Connecting to a repository overview](#connecting-to-a-repository-overview)
* [Connecting to a cloud-hosted repository](#connecting-to-a-cloud-hosted-repository)
* [Connecting to an on-premises repository](#connecting-to-an-on-premises-repository)
* [Managing connected accounts for remote repositories](#managing-connected-accounts-for-remote-repositories)
* [Connecting more than one API to the same repository](#connecting-more-than-one-api-to-the-same-repository)
* [Disconnecting a remote repository](#disconnecting-a-remote-repository)
* [Next steps](#next-steps)

## Connecting to a repository overview

You can connect an API in Postman to your remote Git-based repository. This enables you to sync changes between the repository and Postman. You can connect to a [cloud-hosted repository](#connecting-to-a-cloud-hosted-repository) or to an [on-premises repository](#connecting-to-an-on-premises-repository).

Keep in mind the following when connecting to a repository:

* **The user account used for authentication requires full access to repositories.** To contribute to the API, each user must authenticate with their own account.

* **You can connect one or more APIs to a remote repository.** You can keep your APIs separate in the repository using folders or branches. Learn more about [connecting more than one API to the same repository](#connecting-more-than-one-api-to-the-same-repository).

* **For Azure DevOps connections, make sure to enable third-party application access for your organization.** If you don't enable third-party access, Postman won't be able to connect to your repository. In Azure DevOps, go to your [organization settings](https://docs.microsoft.com/en-us/azure/devops/organizations/accounts/change-application-access-policies?view=azure-devops), select **Policies**, and turn on the toggle next to **Third-party application access via OAuth**. (Enabling third-party access isn't required for connecting to an Azure DevOps Server repository hosted on-premises.)

* **For GitHub connections, there's a limit of ten auth tokens per user per application imposed by GitHub.** If you create more than ten connections with the same user, tokens beyond this limit will be revoked in the order that they were created. Teams can use other Postman accounts to create more than ten integrations.

## Connecting to a cloud-hosted repository

You can connect to a GitHub, Bitbucket, GitLab, or Azure DevOps repository hosted in the cloud.

1. Select **APIs** in the sidebar and select an API.
1. Under **Connect repository**, select **Connect** and select the type of repository you want to connect to.
1. A browser tab opens asking you to sign in to your repository. Follow the onscreen instructions. When you're finished, close the browser tab and return to Postman.
1. On the **Connect your repository** page, enter the **Organization** or **Workspace** and the **Repository** where the API will be stored. (For GitLab, enter the **Group** and **Project** for your API.)
1. Select the **Initial branch** for the API. Any changes you make in Postman are stored in the initial active branch. (You can switch to another branch to make it the active branch at any time.)
1. Select an **API schema directory** and **Collection directory** where the API definition and collections will be stored in the repository. Keep in mind the following:

    * If you leave these fields blank, a `postman/schemas` or `postman/collections` directory will be created in the root of the repository.
    * If you select a directory that already has an API definition, you will be asked which definition to use in Postman the first time you pull changes.
    * The collection directory can't be a parent or the child of the schema directory.

1. Select **Connect Repository**.

> Postman stores your authorized accounts so you can use them to connect to other repositories and services. Learn more about [managing connected accounts for remote repositories](#managing-connected-accounts-for-remote-repositories).

<img alt="Connecting to a cloud-hosted repo" src="https://assets.postman.com/postman-docs/v10/api-builder-remote-repo-v10-12.jpg" width ="562px"/>

## Connecting to an on-premises repository

If you are on a [Postman Enterprise plan](https://www.postman.com/pricing), you can connect to a Git repository hosted on-premises. To connect to a [GitHub Enterprise Server or GitLab Self-Managed](#connecting-to-github-enterprise-server-or-gitlab-self-managed), create a new installed app in Postman. To connect to [Azure DevOps server](#connecting-to-azure-devops-server), use a personal access token.

> **Use the [Postman desktop app](/docs/getting-started/installation-and-updates/) to connect to GitHub Enterprise Server, GitLab Self-Managed, or Azure DevOps Server.** You can't use the [Postman web app](/docs/getting-started/installation-and-updates/#using-the-postman-web-app) to connect to an on-premises GitHub repository.

### Connecting to GitHub Enterprise Server or GitLab Self-Managed

To connect to a repository hosted in GitHub Enterprise Server or GitLab Self-Managed, [create an installed app](#creating-an-installed-app) in Postman. To complete this process, you'll also need to create an OAuth app in GitHub Enterprise Server or GitLab Self-Managed. You need to complete this process once for a domain URL. After you create the installed app, anyone on the team can use it to [connect to repositories using the same domain URL](#connecting-an-api-using-an-installed-app).

#### Creating an installed app

[Installed apps](/docs/integrations/installed-apps/) streamline the process of adding integrations by enabling all members of a team to use the same stored authorization details. To create an installed app, you must have the [Team Admin role](/docs/collaborating-in-postman/roles-and-permissions/#team-roles).

To create an installed app for GitHub Enterprise Server or GitLab Self-Managed, do the following:

1. In Postman, open [Team Settings](https://go.postman.co/settings/team/general) by selecting **Team > Team Settings**.
1. Select **Installed apps**.
1. Select the repository provider you want to add an installed app for (**GitHub Enterprise Server** or **GitLab Self-Managed**).
1. Enter a **Name** to help you recognize the installed app later.
1. Enter the domain URL of your repository. Format the domain URL as follows:

    * **GitHub Enterprise Server** - Use the base URL of your Git server, for example: `https://my-github-server.example.com`
    * **GitLab Self-Managed** - Use the base URL of your Git server, for example: `https://gitlab.example.com`

1. Create an OAuth app by following the instructions for your Git provider ([GitHub Enterprise Server](https://go.pstmn.io/github-oauth-app-setup) or [GitLab Self-Managed](https://go.pstmn.io/GitLab-OAuth-app-setup)).

    * For **Homepage URL** enter: `https://www.postman.com`
    * For **Authorization callback URL** or **Redirect URI**, enter the authorization callback URL provided in Postman: `https://integration-oauth.pstmn.io/v1/api-git-callback.html`

1. After registering the OAuth app, copy the app's **Client ID** and **Client secret** and enter them in Postman.
1. Select **Save** to finish creating the installed app.

<img alt="Creating an installed app" src="https://assets.postman.com/postman-docs/v10/api-builder-add-installed-app-v10-12b.jpg" width ="562px"/>

#### Connecting an API using an installed app

After you [create an installed app](#creating-an-installed-app), any API editor on the team can use it to connect an API to GitHub Enterprise Server or GitLab Self-Managed.

To connect an API using an installed app, do the following:

1. Select **APIs** in the sidebar and select an API.
1. Under **Connect repository**, select **Connect** and select **GitHub Enterprise Server** or **GitLab Self-Managed**.
1. Select the authorized domain of your repository and select **Authenticate**.

    <img alt="Using an installed app" src="https://assets.postman.com/postman-docs/v10/api-builder-use-installed-app-v10-12.jpg" width ="556px"/>

1. A browser tab opens asking you to sign in to your repository. Follow the onscreen instructions. When you're finished, close the browser tab and return to Postman.
1. For GitHub, enter the **Organization** and the **Repository** where the API will be stored. For GitLab, enter the **Group** and **Project** for your API.
1. Select the **Initial branch** for the API. Any changes you make in Postman are stored in the initial active branch. (You can switch to another branch to make it the active branch at any time.)
1. Select an **API schema directory** and **Collection directory** where API the definition and collections will be stored in the repository. Keep in mind the following:

    * If you leave these fields blank, a `postman/schemas` or `postman/collections` directory will be created in the root of the repository.
    * If you select a directory that already has an API definition, you will be asked which definition to use in Postman the first time you pull changes.
    * The collection directory can't be a parent or the child of the schema directory.

1. Select **Connect Repository**.

### Connecting to Azure DevOps Server

To connect an API to a repository hosted in Azure DevOps Server, use a personal access token.

1. Select **APIs** in the sidebar and select an API.
1. Under **Connect repository**, select **Connect** and select **Azure DevOps Server**.
1. Enter the **Domain URL** of your repository. You can enter a new domain or select a domain you've used before from the list. Use the name and port of your Git server along with the collection, for example: `https://my-azure-server:8080/my-collection`
1. Enter a **Personal access token** to access the repository. Ensure that the token has the required permissions as specified on the **Connect your repository** page.
1. Select **Next**.

    <img alt="Using a personal access token" src="https://assets.postman.com/postman-docs/v10/api-builder-use-access-token-v10-12.jpg" width ="564px"/>

1. Enter the **Organization** and the **Repository** where the API will be stored.
1. Select the **Initial branch** for the API. Any changes you make in Postman are stored in the initial active branch. (You can switch to another branch to make it the active branch at any time.)
1. Select an **API schema directory** and **Collection directory** where the API definition and collections will be stored in the repository. Keep in mind the following:

    * If you leave these fields blank, a `postman/schemas` or `postman/collections` directory will be created in the root of the repository.
    * If you select a directory that already has an API definition, you will be asked which definition to use in Postman the first time you pull changes.
    * The collection directory can't be a parent or the child of the schema directory.

1. Select **Connect Repository**.

> Postman stores your authorized accounts so you can use them to connect to other repositories and services. Learn more about [managing connected accounts for remote repositories](#managing-connected-accounts-for-remote-repositories).

## Managing connected accounts for remote repositories

After you connect an API to a remote repository, other editors of the API must authenticate to be able to contribute to the API. Postman will prompt editors to authenticate the next time they open the API.

Postman stores the accounts you've authorized with. After connecting to one repository, you can connect to other repositories that use the same Git provider without having to re-authenticate.<!-- You can also connect to the provider's other services. For example, if you connect to a GitHub repository, you can connect to [GitHub Actions](/docs/integrations/available-integrations/ci-integrations/github-actions/) without having to authenticate again. -->

To manage services you've authorized with, select the settings icon <img alt="Settings icon" src="https://assets.postman.com/postman-docs/icon-settings-v9.jpg#icon" width="16px"> in the header, select **Settings**, and select the **Connected accounts** tab. Learn more about [managing connected accounts](/docs/getting-started/settings/#connected-accounts).

## Connecting more than one API to the same repository

You can connect more than one API in Postman to the same Git repository. For each API, follow the steps in [Connecting to a repository](#connecting-to-a-repository) to set up the Git integration.

It's important to make sure your APIs remain separated in the repository to avoid changes from one API getting applied to another API. You can separate your APIs in the repository using either folders or branches.

### Separating APIs with folders

You can keep your APIs separate by using a different folder for each API in the repository. For example, if you have an `emails` API and an `sms` API, you could have the following folder structure for the `main` branch in your repository:

* `/emails/postman/schemas` - Schemas for the `emails` API
* `/emails/postman/collections` - Collections for the `emails` API
* `/sms/postman/schemas` - Schemas for the `sms` API
* `/sms/postman/collections` - Collections for the `sms` API

Make sure to select the correct folders for your API's schema and collections when [connecting the API to the repository](#connecting-to-a-repository).

> The collection directory can't be a parent or the child of the schema directory.

### Separating APIs with branches

You can keep your APIs separate by using a different branch for each API in the repository. For example, if you have a `notifications-v1` API and a `notifications-v2` API, you could have the following branch and folder structure in your repository:

* `notifications-v1` branch
    * `/postman/schemas` - Schemas for the `notifications-v1` API
    * `/postman/collections` - Collections for the `notifications-v1` API
* `notifications-v2` branch
    * `/postman/schemas` - Schemas for the `notifications-v2` API
    * `/postman/collections` - Collections for the `notifications-v2` API

You must use a unique combination of branch and folder for each API you [connect to the repository](#connecting-to-a-repository). For example, if you connect one API to the `/postman/schemas` folder on the `notifications-v1` branch, you can't connect another API to the same folder on the same branch. You must use a different branch or a different schema folder.

> As you work on your APIs, you can switch branches and push or pull changes for any branch. To keep your APIs separate, always make sure you are on the correct branch before pushing or pulling changes.

## Disconnecting a remote repository

After you disconnect a remote repository, you can no longer sync changes between Postman and the repository.

1. Select **APIs** in the sidebar and select an API.
1. Select the source control icon <img alt="Git branch icon" src="https://assets.postman.com/postman-docs/icon-source-control.jpg#icon" width="16px"/> in the right sidebar.
1. In the **Source Control** pane, select the more actions icon <img alt="More actions icon" src="https://assets.postman.com/postman-docs/icon-more-actions-v9.jpg#icon" width="16px"> and select **Disconnect repository from Postman**.
1. Enter the name of the API to confirm, then select **Disconnect**.

## Next steps

After you've connected a remote repository to your API, you can:

* Work with branches, push and pull changes, and resolve conflicts. Learn more about [managing changes using Git](/docs/designing-and-developing-your-api/versioning-an-api/managing-git-changes/).
* Publish an API version to a workspace or the Private API Network. Learn more about [publishing an API version](/docs/designing-and-developing-your-api/versioning-an-api/api-versions/).
