---
title: 'Managing and sharing APIs'
updated: 2023-02-15
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "API development overview"
    url: "/docs/designing-and-developing-your-api/the-api-workflow/"
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Videos"
  - type: link
    name: "Working With Your Team in Postman | The Exploratory"
    url: "https://youtu.be/5lscUV-Exac"
  - type: section
    name: "Next steps"
  - type: link
    name: "Using API version control"
    url: "/docs/designing-and-developing-your-api/versioning-an-api/"
  - type: link
    name: "Reports overview"
    url: "/docs/reports/reports-overview/"
---

When you [define your APIs](/docs/designing-and-developing-your-api/the-api-workflow/) in Postman using the API Builder, each API is associated with a workspace. You can share access to your APIs, discuss them in comments, and view schema activity.

## Contents

* [Sharing APIs](#sharing-apis)
* [Collaborating on APIs](#collaborating-on-apis)
* [Watching APIs](#watching-apis)
* [Commenting on APIs](#commenting-on-apis)
* [Using the Changelog](#using-the-changelog)

## Sharing APIs

You can share your APIs with collaborators by navigating to the API you want to share in the sidebar. Select it, then select the more actions icon <img alt="More actions icon" src="https://assets.postman.com/postman-docs/icon-more-actions-v9.jpg#icon" width="16px"> > **Share**.

<img alt="Share API" src="https://assets.postman.com/postman-docs/share-api-9.4.jpg"/>

For more details, see [Sharing Postman elements](/docs/collaborating-in-postman/sharing/#sharing-postman-elements).

## Collaborating on APIs

You can move APIs to shared workspaces to collaborate with your team.

> You must be an Editor on an API or the Workspace Admin to move the API to another workspace. To learn more about roles and permissions, see [Defining roles](/docs/collaborating-in-postman/roles-and-permissions/).

In the sidebar, select the API you want to share, then select the more actions icon <img alt="More actions icon" src="https://assets.postman.com/postman-docs/icon-more-actions-v9.jpg#icon" width="16px"> > **Move**.

Use the search bar to find the workspace you'd like to move the API to, or filter by workspace visibility by selecting the filter icon <img alt="Filter icon" src="https://assets.postman.com/postman-docs/icon-filter.jpg#icon" width="16px">.

You can move APIs to personal, private, team, and public workspaces that you have access to. Shared private, team, and public workspaces enable you to collaborate with others.

> You can't move APIs from team, private, or public workspaces to a personal workspace.

<!-- -->

> Refer to [Roles and permissions](/docs/collaborating-in-postman/roles-and-permissions/) for information on workspace access control within your team.

Select the workspace, then select **Move API**. Any collections in the API will move with the API to the new workspace.

<img alt="Move API" src="https://assets.postman.com/postman-docs/move-api-v9.1.jpg" width="400px"/>

## Watching APIs

The watch option enables you to receive an email or in-app notification when a team member belonging to the same workspace modifies the API. For example, you'll receive a notification when a team member updates the API's definition, adds an element to the API, or adds a comment to the API.

Select __Watch__ to start watching the API.

<img src="https://assets.postman.com/postman-docs/v10/watch-api-v10.jpg" alt="Watch Option" width="249px"/>

For more information about the changes to the API, select the notifications icon <img alt="Notifications icon" src="https://assets.postman.com/postman-docs/icon-notification-bell-v9.jpg#icon" width="18px"> in the Postman header.

You will also receive an email with the information regarding who made the change, what the change was, and when it was made.

> You won't receive notifications for changes that you made.

## Commenting on APIs

You can discuss your APIs with collaborators in Postman, keeping the conversation in context and available to other stakeholders.

API producers ([Editor role](/docs/collaborating-in-postman/roles-and-permissions/#api-roles)) can add comments to an API. API consumers ([Viewer role](/docs/collaborating-in-postman/roles-and-permissions/#api-roles)) can't add comments to an API and won't see comments made by API producers. However, API consumers can comment on [published versions](#commenting-on-published-apis) of an API.

To comment on an API, do the following:

1. Select an API in the sidebar.
1. Select the comment icon <img alt="Comments icon" src="https://assets.postman.com/postman-docs/icon-comments-v9.jpg#icon" width="18px"> in the right sidebar.
1. Enter your comment and select **Add Comment**.

<img alt="Commenting on an API" src="https://assets.postman.com/postman-docs/v10/api-builder-add-comment-v10-10.jpg" width="443px" />

> You can also add comments to collections you've added to your API and to requests and folders in that collection. Learn more about [commenting on a collection](/docs/collaborating-in-postman/working-with-your-team/discussing-your-work/#commenting-on-a-collection).

To leave an inline comment on an API definition, do the following:

1. Select an API in the sidebar to expand it.
1. Select **Definition** under the API, then select the definition file you want to comment on.
1. Switch to comment mode by selecting the comment icon <img alt="Comments icon" src="https://assets.postman.com/postman-docs/icon-comments-v9.jpg#icon" width="18px"> in the editor pane.
1. Highlight part of the definition, enter your comment, and select **Add Comment**.

<img alt="Adding an inline comment" src="https://assets.postman.com/postman-docs/v10/api-builder-comment-mode-v10-10.jpg" />

> To make sure you're viewing the latest comments, select the refresh icon <img alt="Refresh icon" src="https://assets.postman.com/postman-docs/icon-refresh-v9-5.jpg#icon" width="14px"> in the comment box.

### Formatting API comments

You can use Markdown in your comments. Check out the [Markdown Cheatsheet on GitHub](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) for tips on formatting.

To mention a collaborator in a comment, type `@` followed by their name, then choose the person from the auto-suggested list. When you mention a user in a comment, Postman sends them a notification.

### Editing, deleting, or linking to an API comment

To manage API comments, select an API or a definition file in the sidebar, then select the comment icon <img alt="Comments icon" src="https://assets.postman.com/postman-docs/icon-comments-v9.jpg#icon" width="18px"> in the right sidebar.

Hover over the comment you want to manage and do one of the following:

* Select the anchor icon <img alt="Link icon" src="https://assets.postman.com/postman-docs/icon-workspace-link-v9.jpg#icon" width="18px"> to get a direct link to the comment.
* Select the edit icon <img alt="Edit icon" src="https://assets.postman.com/postman-docs/documentation-edit-icon-v8-10.jpg#icon" width="18px"> to edit the comment.
* Select the delete icon <img alt="Delete icon" src="https://assets.postman.com/postman-docs/icon-delete-v9.jpg#icon" width="12px"> to delete the comment.

<img alt="Managing an API comment" src="https://assets.postman.com/postman-docs/v10/api-builder-manage-comment-v10-10.jpg" width="443px" />

> If you have the Admin role for the workspace, you can delete comments made by any contributor, but you can't edit comments made by others.

### Replying to an API comment

To reply to an API comment, select an API or a definition file in the sidebar, then select the comment icon <img alt="Comments icon" src="https://assets.postman.com/postman-docs/icon-comments-v9.jpg#icon" width="18px"> in the right sidebar. Select **Add comment** on the comment you want to reply to. Enter your reply and select **Add comment**.

<img alt="Replying to an API comment" src="https://assets.postman.com/postman-docs/v10/api-builder-reply-comment-v10-10.jpg" width="443px" />

### Resolving API comments

You can resolve inline comments for an API definition after the comments have been addressed. Open a definition file and switch to comment mode by selecting the comment icon <img alt="Comments icon" src="https://assets.postman.com/postman-docs/icon-comments-v9.jpg#icon" width="18px"> in the editor pane. Select **Resolve** to resolve a comment and any associated replies.

<img alt="Resolving an API comment" src="https://assets.postman.com/postman-docs/v10/api-builder-resolve-comment-v10-10.jpg" width="443px" />

> You can't undo resolving a comment, but you can view resolved comments by selecting the filter icon <img alt="Filter icon" src="https://assets.postman.com/postman-docs/icon-filter.jpg#icon" width="16px"> in the comments pane.

### Commenting on published APIs

You can [publish your API](/docs/designing-and-developing-your-api/versioning-an-api/api-versions/) to share the current state of your API with consumers. Keep in mind the following when publishing an API:

* When you publish an API version, comments made by API producers aren't published with the API.
* API consumers can't add comments to an API, but they can add comments to a published API version.

### Commenting on Git-linked APIs

You can [connect a Git repository](/docs/designing-and-developing-your-api/versioning-an-api/using-external-git-repo/) to your API to sync your API between Postman and the repository. Keep in mind the following differences when commenting on Git-linked APIs:

* Comments are associated with a branch. If you add a comment while working on one branch, those comments won't be visible when you [switch to another branch](/docs/designing-and-developing-your-api/versioning-an-api/managing-git-changes/#switching-branches).
* You must [commit and push changes](/docs/designing-and-developing-your-api/versioning-an-api/managing-git-changes/#committing-and-pushing-changes) on a branch before you can add a new comment on that branch. (You can reply to an existing comment without committing and pushing changes.)
* When you [merge a branch](/docs/designing-and-developing-your-api/versioning-an-api/managing-git-changes/#creating-a-pull-request), comments remain on the branch being merged and aren't merged to the target branch.

## Using the Changelog

You can view a history of changes to your API schemas and all linked collections. To access the Changelog, open an API, then select the changelog icon <img alt="Changelog icon" src="https://assets.postman.com/postman-docs/icon-changelog.jpg" width="25px" style="vertical-align:middle;margin-bottom:0px"> in the right sidebar.

> If you connect your API to a Git repository, the changelog is replaced by the **Source Control** pane. Learn more about [API version control](/docs/designing-and-developing-your-api/versioning-an-api/versioning-an-api-overview/).

The Changelog shows a list of changes made to the schema and associated elements. Select each entry for more details.

<img src="https://assets.postman.com/postman-docs/v10/api-builder-changelog-v10.jpg" alt="API Builder changelog" width="443px" />
