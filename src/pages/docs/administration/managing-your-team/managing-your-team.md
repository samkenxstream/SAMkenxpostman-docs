---
title: "Managing your team"
order: 121
updated: 2022-12-19
page_id: "managing_your_team"
warning: false
contextual_links:
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Videos"
  - type: link
    name: "Postman 101 for Admins"
    url: "https://youtu.be/rEKvQO8EYR8"
  - type: link
    name: "Collaboration and Governance for API Teams | Postman Intergalactic"
    url: "https://youtu.be/4rxpdcGeixs"
  - type: subtitle
    name: "Blog posts"
  - type: link
    name: "How to Securely Deploy Postman at Scale, Part 1: User Management"
    url: "https://blog.postman.com/how-to-securely-deploy-postman-at-scale-user-management/"
  - type: link
    name: "Govern Your Public API Collections More Effectively"
    url: "https://blog.postman.com/govern-your-public-api-collections-more-effectively/"

---

> **[Some team options are only available on Postman Professional and Enterprise plans.](https://www.postman.com/pricing)**

Postman provides a variety of options to customize your team's experience, from the initial setup to ongoing team and plan management. As a Team Admin, you can streamline the onboarding process for your team, manage access control, and keep your team up to date with the latest version of Postman.

## Contents

* [Setting up your team](#setting-up-your-team)
* [Managing team members](#managing-team-members)
    * [Inviting users](#inviting-users)
        * [Understanding invite permissions](#understanding-invite-permissions)
    * [Managing invites](#managing-invites)
    * [Removing team members](#removing-team-members)
    * [Managing team roles](#managing-team-roles)
    * [Managing partners](#managing-partners)
    * [Managing guests](#managing-guests)
* [Managing your team’s Postman plan](#managing-your-teams-postman-plan)
    * [Changing team size](#changing-team-size)
    * [Upgrading your plan](#upgrading-your-plan)
* [Updating your team’s Postman version](#updating-your-teams-postman-version)
* [Next steps](#next-steps)

## Setting up your team

Once you've created your Postman team, you can take the following steps to enable an efficient user onboarding process:

* Use the [Onboarding checklist](/docs/administration/onboarding-checklist/) to ensure that Postman is available on all devices used by your organization and that it functions as expected.
* [Enable team discovery](/docs/collaborating-in-postman/working-with-your-team/enabling-team-discovery/) to let other Postman users from your organization request to join your team.
* [Configure SSO](/docs/administration/sso/admin-sso/) ([Professional and Enterprise plans only](https://www.postman.com/pricing)).
* [Configure SCIM provisioning](/docs/administration/scim-provisioning/scim-provisioning-overview/) ([Enterprise plans only](https://www.postman.com/pricing)).

## Managing team members

You can invite collaborators, remove existing team members, and update user permissions at any time directly in Postman.

### Inviting users

1. From your [team dashboard](https://go.postman.co/settings/team/members), select **Invite People**.
1. Enter the email addresses of the people you want to invite.

    > You can also upload a text or CSV file with the email addresses of the people you want to invite. To do so, select **Add from file**.

1. Use **Roles** to assign these users one or more [team roles](/docs/collaborating-in-postman/roles-and-permissions/#team-roles).
1. Select **Send Invite**.

<img alt="Invite users to team" src="https://assets.postman.com/postman-docs/v10/team-invite-people-v10.jpg" width="400px"/>

You can also invite a user to join your team with a link. To do so, select **Copy Invite Link**.

#### Understanding invite permissions

As a Team [Admin or Super Admin](/docs/collaborating-in-postman/roles-and-permissions/#team-roles), you can directly send invites for any role type. On [Free, Basic, and Professional plans](https://www.postman.com/pricing/), team members with the Developer role can invite external users as Developers automatically, without the need for approval by a Team Admin. You can review pending invites on your [team dashboard](https://go.postman.co/settings/team/members) under **Invites sent**. For more details, see [Managing invites](#managing-invites).

If the team member sending the invite isn't a Developer inviting another Developer on a Free, Basic, or Professional plan or a Team Admin on any plan, their suggestion to add external users to your Postman team will be shared with you for approval. You can review these invite suggestions in your [team dashboard](https://go.postman.co/settings/team/members) under **Suggestions**. For more details, see [Managing invites](#managing-invites).

You can also let Postman users from your company request to join your team by enabling [team discovery](/docs/collaborating-in-postman/working-with-your-team/enabling-team-discovery/#enabling-team-discovery).

> [Postman Enterprise](https://www.postman.com/pricing) teams can enable [SCIM provisioning](/docs/administration/scim-provisioning/scim-provisioning-overview/), which enables you to create, update, and deactivate user accounts at scale through your identity provider (IdP).

### Managing invites

As a Team Admin, you can manage [pending invites](#invites-sent), review [suggestions](#suggestions) from team members without permission to send invites directly, and review [invite links](#invite-links).

#### Invites sent

You can also review pending invites that team members have submitted in your [team dashboard](https://go.postman.co/settings/team/members) under **Invites sent**. To resend an invite, hover over the person's name and select **Resend Invite**. To copy the invite link, select the copy invite link icon <img alt="Copy invite link icon" src="https://assets.postman.com/postman-docs/icon-copy-v9.jpg#icon" width="15px">. To delete the invite, select the revoke invite icon <img alt="Revoke invite icon" src="https://assets.postman.com/postman-docs/icon-close.jpg#icon" width="16px">.

<img alt="Review invites sent" src="https://assets.postman.com/postman-docs/v10/team-manage-invite-requests-v10.jpg"/>

#### Suggestions

If the team member sending an invite isn't a Developer inviting another Developer (on Free, Basic, or Professional plans) or if they aren't a Team Admin (on any plan), you or another team member with the Admin or Super Admin role must review the invite suggestion. You can review these invite suggestions in your [team dashboard](https://go.postman.co/settings/team/members) under **Suggestions**.

To approve the suggestion and invite the user to your team, select **Invite**. To delete the invite, select the revoke invite icon <img alt="Revoke invite icon" src="https://assets.postman.com/postman-docs/icon-close.jpg#icon" width="16px">.

<img alt="Review invite suggestions" src="https://assets.postman.com/postman-docs/v10/team-manage-invite-suggestions-v10.jpg"/>

#### Invite links

You can review the invites your team has sent by opening your [team dashboard](https://go.postman.co/settings/team/members) and selecting [**Invite links**](https://go.postman.co/settings/team/manage-invite-links) from the left menu. The list provides information about which users generated links, when they were generated, when they expire, and their URL.

<img alt="Invite links dashboard" src="https://assets.postman.com/postman-docs/team-manage-invite-links-v9.2.jpg"/>

To copy an active invite URL, hover over its row and select the copy icon <img alt="Copy link icon" src="https://assets.postman.com/postman-docs/icon-copy-v9.jpg#icon" width="15px">.

To revoke an active invite, hover over its row and select the delete icon <img alt="Delete link icon" src="https://assets.postman.com/postman-docs/icon-delete-v9.jpg#icon" width="12px" />.

### Removing team members

To remove a member from your team, go to your [team dashboard](https://go.postman.co/settings/team/members). Select the delete icon <img alt="Delete icon" src="https://assets.postman.com/postman-docs/icon-delete-v9.jpg#icon" width="12px"> next to the team member's name.

![Removing a team member](https://assets.postman.com/postman-docs/v10/remove-team-member-v10.jpg)

When you remove a team member from your team, you will still retain access to any data they have shared with the team. Reassign their personal workspaces to another team member to ensure the team continues to have access to any unshared work done by the user being removed. Then to confirm, select **Remove Member**.

<img alt="Confirmation for removing a team member" src="https://assets.postman.com/postman-docs/remove-user-from-team-v9.2.jpg" width="400px"/>

> Note that when you remove a member from your team, this doesn't automatically reduce the number of paid seats for your team unless the member was added by [Auto-Flex](/docs/administration/billing/#using-auto-flex) during the current Auto-Flex cycle. If you want to reduce the number of paid seats on your team, a member of your team with the [Billing role](/docs/collaborating-in-postman/roles-and-permissions/#team-roles) can [edit your plan](/docs/administration/billing/#changing-your-plan).

### Managing team roles

Each team member must have one or more team roles assigned to them, which will allow them to perform different actions within your team. Roles can be granted to team members individually, or to members of a [group](/docs/administration/managing-your-team/user-groups/).

You can change a team member's roles from your [team dashboard](https://go.postman.co/settings/team/members).

Search for a specific user by typing their name or email address in the search field. You can also filter users by role type. Select the roles next to the user you'd like to update, then select the roles you'd like to assign or remove. Select **Update Roles** to confirm your changes.

<img alt="Edit team roles" src="https://assets.postman.com/postman-docs/v10/update-team-roles-v10.1.jpg"/>

Teams can have two support accounts at no extra cost. Support accounts are team members with only Admin or Billing roles. Team members with a Super Admin or Developer role will consume a paid seat on your team.

For full details about the Postman team roles that you can assign as a Team Admin, see [Team roles](/docs/collaborating-in-postman/roles-and-permissions/#team-roles). Some roles are only available for teams with [Postman Professional or Enterprise](https://www.postman.com/pricing) plans.

### Managing partners

> **[Partners are available on Postman Enterprise plans.](https://www.postman.com/pricing)**

You can manage external partners similarly to internal team members. To learn more, see [Partner Workspaces](/docs/collaborating-in-postman/using-workspaces/partner-workspaces/).

### Managing guests

You can manage external users who have permission to view specific collections and send requests in the collections. External users with these permissions are assigned the [Guest role](/docs/collaborating-in-postman/roles-and-permissions/#team-roles). A [Team Admin](/docs/collaborating-in-postman/roles-and-permissions/#team-roles) can change an external user's role to the Developer role by going to your [team dashboard](https://go.postman.co/settings/team/members) and selecting **Convert**. When you change an external user's role from the Guest role to the Developer role, they are added to the team and get access to all team resources and workspaces.

![Convert Guest role](https://assets.postman.com/postman-docs/v10/convert-guest-role-v10.jpg)

> Your team must have [available seats](/docs/administration/billing/#changing-your-plan) or [Auto-Flex enabled](/docs/administration/billing/#using-auto-flex) to change an external user's role from the Guest role to the Developer role.

A Team Admin can also view the workspaces and collections a user assigned the Guest role can access. Go to your [team dashboard](https://go.postman.co/settings/team/members), and select **View resources**. Select the workspace name or collection name to open it in a new tab. You can also select the user's name to go to their Postman profile.

<img alt="View collections a Guest can view" src="https://assets.postman.com/postman-docs/v10/view-guest-collections-v10.jpg" width="500px"/>

To learn more about sharing collections with external users, see [Allowing external users to view collections](/docs/collaborating-in-postman/sharing/#allowing-external-users-to-view-collections).

## Managing your team’s Postman plan

You can manage your team size or upgrade your plan at any time during your team's billing cycle.

### Changing team size

If you want to change your team's size, you have two different options:

* **Change the number of paid seats** - Team members with the Billing role can change your team's number of paid seats in the [billing dashboard](https://go.postman.co/billing/overview).
* **Turn on Auto-Flex** - Your team can invite more users without having to pay in advance for more seats with [Auto-Flex](/docs/administration/billing/#using-auto-flex).

For more information, see [Team and plan changes](/docs/administration/billing/#team-and-plan-changes).

### Upgrading your plan

Team members with the Billing role can upgrade your team plan in the [billing dashboard](https://go.postman.co/billing/overview). For more information, see [Changing your plan](/docs/administration/billing/#changing-your-plan).

## Updating your team’s Postman version

If your team isn't on the latest version of the desktop app, you can update your team to ensure everyone has access to the complete Postman API development experience. To do so, see [Updating your team to the current version of Postman](/docs/administration/updating/).

## Next steps

After you set up your Postman team, you can use reports to get insights into your team's API development, including tests, documentation, and monitoring coverage.

* To learn more about Postman's reporting feature, visit [Using reports](/docs/reports/reports-overview/). (_[Enterprise teams](https://www.postman.com/pricing/) only._)
