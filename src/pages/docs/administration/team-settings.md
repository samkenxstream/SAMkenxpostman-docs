---
title: "Configuring team settings"
order: 125
updated: 2021-12-01
page_id: "team_settings"
warning: false
contextual_links:
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Videos"
  - type: link
    name: "Checklist for a Great Team Profile | Postman Level Up"
    url: "https://youtu.be/Ud_rq-VwO4s"
  - type: subtitle
    name: "Blog posts"
  - type: link
    name: "Increase API adoption with improved team profiles"
    url: "https://blog.postman.com/increase-api-adoption-with-improved-team-profiles/"
  - type: link
    name: "Get More Out of Postman by Collaborating with Your Team"
    url: "https://blog.postman.com/get-more-out-of-postman-by-collaborating-with-your-team/"
  - type: section
    name: "Next steps"
  - type: link
    name: "Working with your team"
    url: "/docs/collaborating-in-postman/working-with-your-team/collaboration-overview/"
  - type: link
    name: "Managing your team"
    url: "/docs/administration/managing-your-team/managing-your-team/"

---

Your [Team Settings](https://go.postman.co/settings/team/general) enable you to manage items such as your team's profile, discoverability, custom domains, billing details, authentication, and active invite links.

## Contents

* [Accessing team settings](#accessing-team-settings)
* [Managing your team profile](#managing-your-team-profile)
    * [Editing your team profile](#editing-your-team-profile)
    * [Making your team profile public](#making-your-team-profile-public)
* [Making your team discoverable](#making-your-team-discoverable)
* [Adding custom domains](#adding-custom-domains)
* [Updating billing details](#updating-billing-details)
* [Editing authentication methods](#editing-authentication-methods)
* [Understanding roles and permissions](#understanding-roles-and-permissions)

## Accessing team settings

You can access team settings by selecting **Team** in the header, then selecting **Team Settings**.

<img alt="Team menu with Team Settings selected" src="https://assets.postman.com/postman-docs/team-settings-menu-selected.jpg" width="350px"/>

## Managing your team profile

Your team profile gives you a way to share important information about your team with other Postman users. The profile brings together all your team's public resources in one place, and can serve as a developer portal for your API's consumers.

Your team profile includes:

* A short summary about your team and the work you do
* Social media links like your GitHub profile
* A list containing links to your team members' profiles
* A **Team Description** section
* A **Highlights** section with pinned elements
* Links to all your team's public collections, APIs, workspaces, and flows

<img alt="Example of a filled-in team profile" src="https://assets.postman.com/postman-docs/v10/team-settings-overview-v10.1.jpg" width="800px"/>

### Editing your team profile

When you select **Team Settings**, you will be automatically directed to your **Team profile**. Next, select **View team profile**. Here, you can edit your team's summary, description, highlights, and more.

<img alt="Edit your team profile" src="https://assets.postman.com/postman-docs/v10/team-settings-edit-profile-v10.jpg" width="700px"/>

* **Team summary** - Select **Add Team Summary**. Use this space to add a summary about your team and the work you do, up to 140 characters. To edit your team summary, hover over the section and select the edit icon <img alt="Edit icon" src="https://assets.postman.com/postman-docs/documentation-edit-icon-v8-10.jpg#icon" width="18px">.
* **Social links** - Select **Add Social Links**. You can add a link to your website and links to social media accounts. To edit these links, hover over the section and select the edit icon <img alt="Edit icon" src="https://assets.postman.com/postman-docs/documentation-edit-icon-v8-10.jpg#icon" width="18px">.
* **Members** - To manage your team members, hover over this section and select **Manage**.
* **About your team** - Select **Add Team Description**. To update your team description, hover over the section and select the edit icon <img alt="Edit icon" src="https://assets.postman.com/postman-docs/documentation-edit-icon-v8-10.jpg#icon" width="18px">. The editor supports Markdown, or you can use the built-in text formatting tools.
* **Highlights** - This section lets you show off your team's work to other Postman users. If you don't choose any elements to pin to this section, Postman displays the most popular elements that you've worked on. To update the highlighted elements, hover over the section and select the edit icon <img alt="Edit icon" src="https://assets.postman.com/postman-docs/documentation-edit-icon-v8-10.jpg#icon" width="18px">. Add or remove the desired elements, then select **Save**.

#### Customizing your team's branding

You can also add a **team logo**, **cover photo**, and **favicon** to establish your team identity and ensure consistent branding.

To add these assets, do the following:

1. In **Team settings**, select **Team profile**.
1. To add a team logo and cover photo, hover over the desired section and select the edit icon <img alt="Edit icon" src="https://assets.postman.com/postman-docs/documentation-edit-icon-v8-10.jpg#icon" width="18px">, then upload the image you want to use.
1. To add a favicon, select **Upload** under the **Favicon** section.

<img alt="Customize your team's branding" src="https://assets.postman.com/postman-docs/v10/team-settings-customize-branding-v10.jpg" width="500px"/>

Keep the following in mind when you upload a logo, cover photo, or favicon:

* Logos and cover photos must be 500 KB or less in size and must be in **.jpg**, **.jpeg**, or **.png** format.
* Logos must have a 1:1 aspect ratio (height:width), and cover photos must have a 1:7.5 aspect ratio. If your image has a different aspect ratio, Postman prompts you to select a part of your image to display.
* Favicons must be in **.ico** format, no larger than 32x32 pixels, and 500 KB or less in size. Your favicon appears on the browser tab of your team's published documentation site.

### Making your team profile public

If you enable your team's public profile, your team will be visible on Postman's [API Network](/docs/collaborating-in-postman/adding-private-network/), along with any [APIs](/docs/collaborating-in-postman/adding-private-network/#adding-apis), [collections](/docs/publishing-your-api/publishing-your-docs/), and [workspaces](/docs/collaborating-in-postman/using-workspaces/public-workspaces/) your team has published.

A public team profile encourages other users to collaborate with you in a public workspace, enables you to ask for contributions and gather feedback, and increases your API's discovery in search results. A public team profile also shows up on the [Public API Network](https://www.postman.com/explore).

To make your [team profile](https://go.postman.co/settings/team/general) public, do the following:

1. In **Team settings**, select **Team profile**.
1. Select **Make team profile public** to set the profile to public.

<img alt="Make your team profile public" src="https://assets.postman.com/postman-docs/v10/team-settings-make-profile-public-v10.jpg" width="300px"/>

## Making your team discoverable

You can select **Team Discovery** from the left-hand menu to view your options for making your team discoverable to other Postman users with email addresses from your team's domain.

See [Team Discovery](/docs/collaborating-in-postman/working-with-your-team/enabling-team-discovery/) for more information on this feature and the admin and user experience it provides.

## Adding custom domains

Select **Custom Domains** from the left-hand menu to add, update, or remove custom domains for your API documentation.

Visit [Using custom domains](/docs/publishing-your-api/custom-doc-domains/) for information on adding, verifying, troubleshooting, and publishing to custom domains.

<img alt="Custom domains dashboard" src="https://assets.postman.com/postman-docs/dashboard-view-custom-domains-v9.1.jpg"/>

## Updating billing details

Select **Billing Details** from the left-hand menu to add to or update your team's billing information including email, address, and VAT ID (if applicable).

View [Adding custom information to invoices](/docs/administration/billing/#adding-custom-information-to-invoices) for information on modifying new and existing invoices.

## Editing authentication methods

> SSO is available on Postman Professional and Enterprise plans.

Select **Authentication** from the left-hand menu to configure or reconfigure your team's authentication methods.

See [Configuring SSO for a team](/docs/administration/sso/admin-sso/) for details on how to configure your team's custom SSO setup and manage user accounts.

## Understanding roles and permissions

Select **Roles and Permissions** from the left menu to view a complete list of permissions for users' roles at a team, collection, workspace, API, and mock server level.

View [Defining roles](/docs/collaborating-in-postman/roles-and-permissions/) for more information on roles you can assign to team members. Then, check out [Managing your team](/docs/administration/managing-your-team/managing-your-team/) for an overview of managing roles and users within your Postman team.

<img alt="Roles and permissions descriptions" src="https://assets.postman.com/postman-docs/dashboard-view-roles-and-permissions-v9.1.jpg"/>
