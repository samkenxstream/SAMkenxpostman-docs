---
title: "Partner Workspaces"
updated: 2023-03-02
contextual_links:
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Videos"
  - type: link
    name: "Partner Workspaces for Enterprise"
    url: "https://youtu.be/gT55ui8UOHw"
  - type: subtitle
    name: "Blog posts"
  - type: link
    name: "Introducing Partner Workspaces: An Exclusive Space to Collaborate with Your API Partners"
    url: "https://blog.postman.com/introducing-partner-workspaces/"
---

> **[Partner Workspaces are available on Postman Enterprise plans.](https://www.postman.com/pricing)**

Partner Workspaces enable you to collaborate with external partners directly in Postman. You can use Partner Workspaces to help your partners consume your team's APIs and work together on API projects. With Partner Workspaces, you can build a single source of truth and integrate your partner projects into your Postman team, setting the foundation for an efficient and productive partnership.

## Contents

* [Creating a Partner Workspace](#creating-a-partner-workspace)
* [Setting up a Partner Workspace](#setting-up-a-partner-workspace)
    * [Moving elements to a Partner Workspace](#moving-elements-to-a-partner-workspace)
* [Inviting collaborators to a Partner Workspace](#inviting-collaborators-to-a-partner-workspace)
* [Viewing workspaces a partner can access](#viewing-workspaces-a-partner-can-access)
* [Collaborating in a Partner Workspace](#collaborating-in-a-partner-workspace)
    * [Collaborating as a team member](#collaborating-as-a-team-member)
    * [Collaborating as a partner](#collaborating-as-a-partner)
* [Managing a Partner Workspace](#managing-a-partner-workspace)
    * [Managing users and roles](#managing-users-and-roles)
    * [Managing workspace elements](#managing-workspace-elements)
    * [Editing workspace details](#editing-workspace-details)
* [Removing elements from a Partner Workspace](#removing-elements-from-a-partner-workspace)
* [Removing partners from a Partner Workspace](#removing-partners-from-a-partner-workspace)
* [Deleting a Partner Workspace](#deleting-a-partner-workspace)

## Creating a Partner Workspace

1. Select **Workspaces** from the header, then select **Create Workspace**.

    <img alt="Workspace menu" src="https://assets.postman.com/postman-docs/workspace-switcher-v9.19.jpg" width="300px"/>

1. Define a workspace **Name** and **Summary**.
1. Under **Visibility**, select **Partner**.
1. Select **Create workspace**.

    <img alt="Create Partner Workspace" src="https://assets.postman.com/postman-docs/v10/create-partner-workspace-v10.jpg" width="400px"/>

Anyone with permissions to create workspaces can request to create a Partner Workspace, but it must be approved by a [Partner Manager](#managing-users-and-roles). If you're not a [Super Admin](/docs/collaborating-in-postman/roles-and-permissions/#team-roles) or Partner Manager, you must submit your request for approval. You can also add an optional note to your request. The workspace's visibility will be set to [private](/docs/collaborating-in-postman/using-workspaces/managing-workspaces/#changing-workspace-visibility) until your request is approved. Postman will notify you when a Partner Manager reviews your request and approves or denies it.

<img alt="Create Partner Workspace approval" src="https://assets.postman.com/postman-docs/v10/partner-workspaces-visibility-request-v10.jpg" width="450px" />

To convert an existing workspace to a Partner Workspace, do the following:

1. Open the workspace. In the **Overview** tab, select **Workspace Settings** in the upper right.
1. Under **Visibility**, select **Partner**.
1. Select **Update**.

Anyone with permissions to change workspace visibility can request to convert a workspace into a Partner Workspace, but it must be approved by a [Partner Manager](#managing-users-and-roles). If you're not a [Super Admin](/docs/collaborating-in-postman/roles-and-permissions/#team-roles) or Partner Manager, Postman will mention this and you can add an optional note to your request. Postman will notify you when a Partner Manager reviews your request and approves or denies it.

> When a workspace is converted to a Partner Workspace, Postman sends in-app and email notifications to all workspace members.

## Setting up a Partner Workspace

Before sharing a Partner Workspace with external collaborators, you can set your partnership up for success by moving or forking relevant elements into it.

### Moving elements to a Partner Workspace

You must be an Editor on an API, collection, or environment, the Workspace Admin, Partner Manager, or a Super Admin to move an element to a Partner Workspace.

To move an element to a Partner Workspace, do the following:

1. In the sidebar, select the element you want to move. Then select the more actions icon <img alt="More actions icon" src="https://assets.postman.com/postman-docs/icon-more-actions-v9.jpg#icon" width="16px"> > **Move**.

1. Use the search bar to find the workspace you'd like to move the element to, or filter by workspace visibility by selecting the filter icon <img alt="Filter icon" src="https://assets.postman.com/postman-docs/icon-filter.jpg#icon" width="16px">.

    > You can move elements to Partner Workspaces that you have access to.

1. Select the workspace, then select **Move** (**Collection**, **API**, or **Environment**).

    <img alt="Move element Partner Workspace" src="https://assets.postman.com/postman-docs/v10/move-collection-to-partner-workspace-v10.jpg" width="400px"/>

Note that items related to what you're moving, such as monitors and mock servers, won't move with the element automatically. For more information, see [Moving elements to team workspaces](/docs/collaborating-in-postman/working-with-your-team/collaborating-in-team-workspaces/#moving-elements-to-team-workspaces).

If you'd like to keep certain elements in other workspaces, you can [fork them into Partner Workspaces](/docs/collaborating-in-postman/using-version-control/forking-entities/#creating-a-fork) to help [keep them up to date](/docs/collaborating-in-postman/using-version-control/forking-entities/#pulling-updates-from-a-parent-element) with any changes to the parent element.

## Inviting collaborators to a Partner Workspace

Workspace Admins, Partner Managers, and Partner Leads can invite partners to Partner Workspaces. Your team can invite three partners assigned the Workspace Editor role at no extra cost. To purchase more partner licenses, contact your Postman Account Manager or [contact Postman's sales team](mailto:sales@postman.com). A paid seat is consumed when a partner is assigned the Workspace Editor role in at least one Partner Workspace. Assigning a partner the Workspace Viewer role doesn't consume paid seats.

> For more information on partner roles, see [Partner roles](/docs/collaborating-in-postman/roles-and-permissions/#partner-roles).

To invite partners to a Partner Workspace, do the following:

1. Open the workspace, select <img alt="Workspace settings icon" src="https://assets.postman.com/postman-docs/v10/icon-sliders-v10.jpg#icon" width="24px"> **Workspace Settings** in the workspace's **Overview** tab, and then select **Invite**.

    > You can also select **Invite** in the Postman header.

1. (Workspace Admins and Partner Managers only) Select **Partners**, then **Continue**.
1. Enter the name, email, or group name of the partners.
1. Set their [workspace role](/docs/collaborating-in-postman/roles-and-permissions/#workspace-roles).

    > Your team must have [available seats](/docs/administration/billing/#changing-your-plan) or [Auto-Flex enabled](/docs/administration/billing/#using-auto-flex) to invite a partner as a Workspace Editor. Otherwise, the partner will be assigned the Workspace Viewer role. Assigning a partner the Workspace Viewer role doesn't consume paid seats.

1. (Workspace Admins and Partner Managers only) Select **Make them Partner Lead** if you'd like them to also be able to manage and invite partners within the workspace.
1. Select **Invite Partners**.

Partner invites must be accepted by the email address you provided when you invited the individual. If a partner would like to use a different email address, or if an invite was mistakenly sent, you can [revoke the invite](/docs/administration/managing-your-team/managing-your-team/#managing-invites) and send a new one.

> Partners will sign in to your team with a Postman username and password, even if your team is restricted to signing in with [SSO](/docs/administration/sso/intro-sso/).

Workspace Admins and Partner Managers can invite team members to Partner Workspaces.

To invite team members to a Partner Workspace, do the following:

1. Open the workspace, select <img alt="Workspace settings icon" src="https://assets.postman.com/postman-docs/v10/icon-sliders-v10.jpg#icon" width="24px"> **Workspace Settings** in the workspace's **Overview** tab, and then select **Invite**.

    > You can also select **Invite** in the Postman header.

1. Select **Team members**, then **Continue**.
1. Enter the name, email, or group name of the team members.
1. Set their [workspace role](/docs/collaborating-in-postman/roles-and-permissions/#workspace-roles).
1. Select **Send Invites**.

## Viewing workspaces a partner can access

A [Partner Manager](#managing-users-and-roles) can view the Partner Workspaces a partner can access, and the Workspace role they're assigned in each workspace. Go to your [team dashboard](https://go.postman.co/settings/team/members), and select **View workspaces** next to a partner. Select a Partner Workspace name to open the workspace in a new tab.

<img alt="View partner workspaces and roles" src="https://assets.postman.com/postman-docs/v10/view-partner-workspaces-and-roles-v10-2.jpg" width="800px"/>

## Collaborating in a Partner Workspace

The collaborative experience that Partner Workspaces offer depends on your role and status as a team member or external partner.

### Collaborating as a team member

Partner Workspaces are only visible to invited team members, similar to [private workspaces](/docs/collaborating-in-postman/using-workspaces/creating-workspaces/). Once invited, you can access Partner Workspaces as you would access any other workspace. To open one, select **Workspaces** in the Postman header, then select the Partner Workspace.

Within a Partner Workspace, team members can have different workspace roles: Admin, Editor, and Viewer. To learn more, see [Workspace roles](/docs/collaborating-in-postman/roles-and-permissions/#workspace-roles).

Users can also be assigned the team-level Partner Manager role. Partner Managers can view all Partner Workspaces within an organization, and can control their settings, visibility, and partner invites. To learn more, see [Managing users and roles](#managing-users-and-roles).

### Collaborating as a partner

When an external partner is invited to a Partner Workspace by a team they're working with, they only have access to that Partner Workspace and can't access any other workspaces or resources within the team. Partners don't have personal or team workspaces within the team they're partnering with.

Within a Partner Workspace, partners with the Workspace Editor role can [import and export](/docs/getting-started/importing-and-exporting-data/) elements. They can also [fork elements](/docs/collaborating-in-postman/using-version-control/forking-entities/) within the same Partner Workspace or to another Partner Workspace within the same team. They can't fork elements outside the team.

Within a Partner Workspace, partners with the Workspace Viewer role can [fork elements](/docs/collaborating-in-postman/using-version-control/forking-entities/) to another Partner Workspace within the same team where they're assigned the Workspace Editor role. They can't fork elements outside the team. Also, they can't export workspace resources.

At the team level, all external partners are automatically assigned the Partner role. At the workspace level, all partners are assigned [Workspace Editor or Viewer](/docs/collaborating-in-postman/roles-and-permissions/#workspace-roles) roles when invited to a Partner Workspace. Partners can also be assigned the Partner Lead role, which enables them to invite other individuals from their organization to the Partner Workspace.

> To learn more about partner roles and permissions, see [Partner Roles](/docs/collaborating-in-postman/roles-and-permissions/#partner-roles).

## Managing a Partner Workspace

Workspace Admins and Partner Managers manage workspace settings, users, and roles within a Partner Workspace. Partner Leads also manage users and roles of partners in Partner Workspaces.

### Managing users and roles

You can assign partner roles based on the functions users and partners require. You can [assign](/docs/administration/managing-your-team/managing-your-team/) partner roles at the team level:

* **Partner Manager** (Internal) - Manages all Partner Workspaces within an organization. Controls Partner Workspace settings and visibility, and can send invites to partners.
* **Partner** (External) - All partners are automatically granted the Partner role at the team level. Partners can only access the Partner Workspaces they've been invited to.

You can also [assign](/docs/collaborating-in-postman/using-workspaces/managing-workspaces/#managing-workspace-roles) partner roles at the workspace level:

* **Partner Lead** (External) - Can invite other partners from their organization to join a Partner Workspace.

All partners are assigned the Workspace Editor or Viewer roles when invited to a Partner Workspace.

To learn more about partner roles, see [Partner roles](/docs/collaborating-in-postman/roles-and-permissions/#partner-roles).

### Managing workspace elements

To move elements to a Partner Workspace, see [Moving elements to a Partner Workspace](#moving-elements-to-a-partner-workspace).

To remove elements from a Partner Workspace, see [Removing elements from a Partner Workspace](#removing-elements-from-a-partner-workspace).

### Editing workspace details

Workspace Admins and Partner Managers can edit Partner Workspace details. On the workspace's Overview tab, select the workspace name, summary, or description to edit it. You can add Markdown to the description—select **Save** when you're done.

## Removing elements from a Partner Workspace

You must be an Editor on an API, collection, or environment, the Workspace Admin, Partner Manager, or a Super Admin to remove an element from a Partner Workspace.

To remove an element by moving it to another workspace, do the following:

1. In the sidebar, select the element you want to move, then select the more actions icon <img alt="More actions icon" src="https://assets.postman.com/postman-docs/icon-more-actions-v9.jpg#icon" width="16px"> > **Move**.

1. Use the search bar to find the workspace you'd like to move the element to, or filter by workspace visibility by selecting the filter icon <img alt="Filter icon" src="https://assets.postman.com/postman-docs/icon-filter.jpg#icon" width="16px">.

    > You can only move elements to workspaces that you have access to.

1. Select the workspace, then **Move** (**Collection**, **API**, or **Environment**).

It's not recommended, but you can choose to delete an element entirely. To do so, select the element in the sidebar, then select the more actions icon <img alt="More actions icon" src="https://assets.postman.com/postman-docs/icon-more-actions-v9.jpg#icon" width="16px"> > **Delete**.

> Deleted APIs and environments aren't recoverable. You can recover collections smaller than 30 MB for up to 90 days on an Enterprise plan. To do so, select <img alt="Delete icon" src="https://assets.postman.com/postman-docs/icon-delete-v9.jpg#icon" width="12px"> **Trash** from the Postman footer.

## Removing partners from a Partner Workspace

You can remove partners from individual Partner Workspaces. To remove a partner from a Partner Workspace, see [Managing workspace roles](/docs/collaborating-in-postman/using-workspaces/managing-workspaces/#managing-workspace-roles).

You can remove partners from a team. Removing a partner from a team removes them from all Partner Workspaces. Also, if you remove the last Admin from the team, users assigned the Partner Manager role will be assigned the Admin role. To remove a partner from a team, see [Removing team members](/docs/administration/managing-your-team/managing-your-team/#removing-team-members).

## Deleting a Partner Workspace

Workspace Admins and Partner Managers can delete Partner Workspaces.

1. On the workspace's **Overview** tab, select **Workspace Settings**.
1. [Change the visibility of the workspace](/docs/collaborating-in-postman/using-workspaces/managing-workspaces/#changing-workspace-visibility) to **Private**.
1. Select **Remove all partners**, then select **Update**.
1. Select **Delete Workspace**.

> Postman notifies all workspace members in-app and by email when you delete a Partner Workspace.
