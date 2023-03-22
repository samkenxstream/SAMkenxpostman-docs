---
title: 'Importing and exporting data'
updated: 2022-06-03
contextual_links:
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Videos"
  - type: link
    name: "How to Import and Export Data in Postman"
    url: "https://youtu.be/sCWwOzhUMXE"
  - type: link
    name: "Postman | How to Connect to Your Git Repository"
    url: "https://youtu.be/8jJHXLVYOh0"
  - type: link
    name: "Integrating GitLab in Postman's API Builder"
    url: "https://youtu.be/ecAQv9gZEKk"
  - type: link
    name: "Generate a Collection From a Specification | Postman Level Up"
    url: "https://youtu.be/gljWt9tDKOY"
  - type: subtitle
    name: "Blog posts"
  - type: link
    name: "Postman Essentials: Exploring the Collection Format"
    url: "https://blog.postman.com/postman-essentials-exploring-the-collection-format/"
  - type: link
    name: "Latest Updates to Syncing Your Specs with Collections"
    url: "https://blog.postman.com/latest-updates-to-syncing-your-specs-with-collections/"
  - type: link
    name: "Postman Supports WSDL"
    url: "https://blog.postman.com/postman-now-supports-wsdl/"
  - type: subtitle
    name: "Next steps"
  - type: link
    name: "Using the API Builder"
    url: "/docs/designing-and-developing-your-api/the-api-workflow/"

warning: false
---

Postman can import and export Postman data, including collections, environments, data dumps, and globals. Postman can also import non-Postman data in the form of API schemas to help you consolidate your API development workflow.

## Contents

* [Importing data into Postman](#importing-data-into-postman)

    * [Importing Postman data](#importing-postman-data)

    * [Converting Postman collections from v1 to v2](#converting-postman-collections-from-v1-to-v2)

    * [Importing API specifications](#importing-api-specifications)

    * [Importing from GitHub repositories](#importing-from-github-repositories)

    * [Importing from Bitbucket repositories](#importing-from-bitbucket-repositories)

    * [Importing from GitLab repositories](#importing-from-gitlab-repositories)

    * [Importing from Azure DevOps repositories](#importing-from-azure-devops-repositories)

* [Exporting Postman data](#exporting-postman-data)

    * [Exporting collections](#exporting-collections)

    * [Exporting environments](#exporting-environments)

    * [Exporting data dumps](#exporting-data-dumps)

## Importing data into Postman

You can import collections, API specifications, and data files directly into Postman.

To import your data into Postman, select **Import** in the upper left. The **Import** modal opens.

![Import data into Postman](https://assets.postman.com/postman-docs/v10/import-export-import-ui-v10-3.jpg)

You can import your data from files, folders, links, raw text, or code repositories.

### Importing with cURL commands

You can use cURL commands to import data.

1. Select **Import** in the left navigation menu. The **Import** modal opens.
1. Paste your cURL command into the input field at the top. Postman creates and opens a request automatically.

    > You can also paste cURL commands into a request's URL field.

### Importing Postman data

You can import Postman data you exported earlier, including collections, environments, data dumps, and globals.

1. Select **Import** in the left navigation menu.
1. Do one of the following:
    * Select your file or folder, or drag it into the **Import** modal.
    * Paste your raw text or URL into the input field.
    * Select a button to import from a [GitHub](#importing-from-github-repositories), [Bitbucket](#importing-from-bitbucket-repositories), or [GitLab](#importing-from-gitlab-repositories) code repository.
    * Select **Other Sources** to import an [Azure](#importing-from-azure-devops-repositories) code repository, or to [import an API from Amazon API Gateway or Azure API Management](/docs/designing-and-developing-your-api/importing-an-api/).
    Postman will automatically recognize Postman data, confirming the name, format, and what the file will import as.
   ![Import collection and environment](https://assets.postman.com/postman-docs/v10/import-elements-v10.jpg)
1. If you are importing multiple files, select the files you want to import and select **Import** to bring your data into Postman.

    > If you are importing a single file, Postman automatically imports it when you select it.

### Converting Postman collections from v1 to v2

Postman no longer supports the collection v1 format and will return an error if you import a collection in this format. You can convert your collection's format from v1 to v2 to import it into Postman.

To convert your collection's format from v1 to v2, do the following:

1. In the terminal of your choice, enter the following command to install the Postman Collection Transformer.

   ```bash
   sudo npm install -g postman-collection-transformer
   ```

1. Convert an individual Postman Collection from v1 to v2 by entering this command:

   ```bash
   postman-collection-transformer convert -i <path to the input Postman Collection file> -o <path to the downloaded Postman file> -j 1.0.0 -p 2.0.0 -P
   ```

The resulting collection will download to your target file path in v2 format.

You can retrieve a list of convert options by running the command with the ``-h`` flag:

   ```bash
   postman-collection-transformer convert -h
   ```

See the [Postman Collection Transformer](https://github.com/postmanlabs/postman-collection-transformer) for more information on the collection conversion.

### Importing API specifications

To import your API specifications into Postman, see [Importing an API](/docs/designing-and-developing-your-api/importing-an-api/).

### Importing from GitHub repositories

You can import files from local or remote repositories.

To import from a local GitHub repository:

1. In Postman, select **Import** to open the **Import** modal.

1. On your computer, drag and drop folders or files into the **Import** modal.

1. Choose to import your API as a **Postman Collection** or as **OpenAPI 3.0 with a Postman Collection**.

1. If you're importing an API definition with multiple files, select the files you want to import into Postman, then select **Import**.

   ![Confirm import from GitHub](https://assets.postman.com/postman-docs/v10/import-export-github-files-confirm-1-v10.jpg)

To import data from a remote GitHub repository:

> You must sign in to a [Postman account](/docs/getting-started/postman-account/#signing-up-for-a-postman-account) to use this feature.

1. In Postman, select **Import** then select the **GitHub** button.

1. Confirm or sign in to your GitHub account and authorize **postmanlabs** to access your repositories if necessary.

1. In Postman, select your GitHub organization, repository, and branch, then select **Continue**.

1. Choose to import your API as a **Postman Collection** or as **OpenAPI 3.0 with a Postman Collection**.

1. If you're importing an API definition with multiple files, select the files you want to import into Postman, then select **Import**.

### Importing from Bitbucket repositories

You can import files from local or remote repositories.

To import from a local Bitbucket repository:

1. In Postman, select **Import** to open the **Import** modal.

1. On your computer, drag and drop folders or files into the **Import** modal.

1. Choose to import your API as a **Postman Collection** or as **OpenAPI 3.0 with a Postman Collection**.

1. If you're importing an API definition with multiple files, select the files you want to import into Postman, then select **Import**.

   ![Confirm import from GitHub](https://assets.postman.com/postman-docs/v10/import-export-github-files-confirm-1-v10.jpg)

To import data from a remote Bitbucket repository:

> You must sign in to a [Postman account](/docs/getting-started/postman-account/#signing-up-for-a-postman-account) to use this feature.

1. In Postman, select **Import** then select the **Bitbucket** button.

1. Confirm or sign in to your Bitbucket account and authorize **postmanlabs** to access your repositories if necessary.

1. In Postman, select your Bitbucket workspace, repository, and branch, then select **Continue**.

1. Choose to import your API as a **Postman Collection** or as **OpenAPI 3.0 with a Postman Collection**.

1. If your repository has an API definition with multiple files, select the files you want to import into Postman, then select **Import**.

### Importing from GitLab repositories

You can import files from local or remote repositories.

To import from a local GitLab repository:

1. In Postman, select **Import** to open the **Import** modal.

1. On your computer, drag and drop folders or files into the **Import** modal.

1. Choose to import your API as a **Postman Collection** or as **OpenAPI 3.0 with a Postman Collection**.

1. If you're importing an API definition with multiple files, select the files you want to import into Postman, then select **Import**.

   ![Confirm import from GitHub](https://assets.postman.com/postman-docs/v10/import-export-github-files-confirm-1-v10.jpg)

To import data from a remote GitLab repository:

> You must sign in to a [Postman account](/docs/getting-started/postman-account/#signing-up-for-a-postman-account) to use this feature.

1. In Postman, select **Import** then select the **GitLab** button.

1. Confirm or sign in to your GitLab account and authorize **postmanlabs** to access your repositories if necessary.

1. In Postman, select your GitLab organization, project, and branch, then select **Continue**.

1. Choose to import your API as a **Postman Collection** or as **OpenAPI 3.0 with a Postman Collection**.

1. If your repository has an API definition with multiple files, select the files you want to import into Postman, then select **Import**.

### Importing from Azure DevOps repositories

You can import files from local or remote repositories.

To import from a local Azure DevOps repository:

1. In Postman, select **Import** to open the **Import** modal.

1. On your computer, drag and drop folders or files into the **Import** modal.

1. Choose to import your API as a **Postman Collection** or as **OpenAPI 3.0 with a Postman Collection**.

1. If you're importing an API definition with multiple files, select the files you want to import into Postman, then select **Import**.

   ![Confirm import from GitHub](https://assets.postman.com/postman-docs/v10/import-export-github-files-confirm-1-v10.jpg)

To import data from a remote Azure DevOps repository:

> You must sign in to a [Postman account](/docs/getting-started/postman-account/#signing-up-for-a-postman-account) to use this feature.

1. In Postman, select **Import > Other Sources > Azure**.

1. Confirm or sign in to your Azure DevOps account and authorize **postmanlabs** to access your repositories if necessary.

1. In Postman, select your Azure DevOps workspace, repository, and branch, then select **Continue**.

1. Choose to import your API as a **Postman Collection** or as **OpenAPI 3.0 with a Postman Collection**.

1. If your repository has an API definition with multiple files, select the files you want to import into Postman, then select **Import**.

## Exporting Postman data

You can export your Postman data, including collections, environments, data dumps, and globals, as JSON files. You can import these files back into any Postman instance, or use them with [Newman](/docs/collections/using-newman-cli/command-line-integration-with-newman/), Postman's command-line collection runner.

### Exporting collections

1. Select the more actions icon <img alt="More actions icon" src="https://assets.postman.com/postman-docs/icon-more-actions-v9.jpg#icon" width="16px"> next to the collection, then select **Export**.

   <img alt="Export collection" src="https://assets.postman.com/postman-docs/export-collection-v9.1.jpg" width="350px" />

1. Select the format you'd like your collection to export as.

   > Learn more about Postman's [collection format](https://learning.postman.com/collection-format/getting-started/overview/).

1. Select **Export** to download your newly generated JSON file.

### Exporting environments

You can also export your environments from Postman.

1. Select **Environments** from the sidebar.
1. Select an environment to export.
1. In the workbench, select the more actions icon <img alt="More actions icon" src="https://assets.postman.com/postman-docs/icon-more-actions-v9.jpg#icon" width="16px">, then select **Export** to download your newly generated JSON file.

### Exporting data dumps

You can export a data dump of all your collections, environments, globals, and header presets in Postman.

> You can export individual collections and environments from the Scratch Pad. You can't make bulk data exports of all collections and environments at once.

1. Select the settings icon <img alt="Settings icon" src="https://assets.postman.com/postman-docs/icon-settings-v9.jpg#icon" width="16px"> in the header, then select **Settings**.

1. Select the **Data** tab, then **Export Data** to start your request for the data dump.

1. Select **Export Data** to confirm the data types you need to export.

1. Select **Request Data Export** to submit the request.

   ![Export data dump](https://assets.postman.com/postman-docs/import-export-data-dump-request-confirm.jpg)

The [Export page](http://go.postman.co/me/export) shows information about your export request, including the file size, the date the export expires, and the statuses of your requested data exports. Possible statuses are:

* **Scheduled** - The export request is placed.
* **Transferring** - The data transfer process has started.
* **Transferred** - The data transfer process has completed.
* **Zipping** - The process of zipping the file has started.
* **Zipped** - The file is zipped.
* **Download** - The zipped file is ready to download.

When the export is ready, you will receive an email with link to download a zipped file with the data dump. You can also download the file from the Export page using **Download**.
