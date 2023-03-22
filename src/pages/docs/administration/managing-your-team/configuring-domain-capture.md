---
title: "Configuring domain verification and capture"
order: 143
page_id: "configuring_domain_capture"
warning: false
updated: 2023-03-07
contextual_links:
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Blog posts"
  - type: link
    name: "Introducing Domain Capture: Group Your Organization’s Postman Users into a Single Team"
    url: "https://blog.postman.com/introducing-domain-capture/"

---

> **[Domain verification and capture are available on Postman Enterprise plans.](https://www.postman.com/pricing)**

Verify a domain to view all user accounts in Postman that have been created with your organization’s domains and subdomains. Enable domain capture to manage all of these user accounts in Postman. With domain capture, you can merge all of your organization's Postman users into a single Postman team and ensure that any new users who sign up for Postman with your domain are automatically added.

To enable domain capture, [Team Admins](/docs/collaborating-in-postman/roles-and-permissions/#team-roles) must first [add and verify a domain or subdomain](#adding-and-verifying-a-domain). Once the domain is verified, they can create a request to [enable domain capture](#enabling-domain-capture). Once the request to enable domain capture is approved, they can [contact Postman support](#contacting-support-to-manage-accounts) to manage [unclaimed accounts](#viewing-unclaimed-accounts).

## Contents

* [Prerequisites for domain verification and capture](#prerequisites-for-domain-verification-and-capture)

* [Adding and verifying a domain](#adding-and-verifying-a-domain)

    * [Verifying a domain later](#verifying-a-domain-later)

    * [Viewing verification details](#viewing-verification-details)

    * [Viewing unclaimed accounts](#viewing-unclaimed-accounts)

* [Enabling domain capture](#enabling-domain-capture)

    * [User experience](#user-experience)

    * [Contacting support to manage accounts](#contacting-support-to-manage-accounts)

* [Deleting a domain](#deleting-a-domain)

* [Domain capture FAQs](#domain-capture-faqs)

## Prerequisites for domain verification and capture

You must be a [Postman Team Admin](/docs/collaborating-in-postman/roles-and-permissions/#team-roles) to add and verify a domain and enable domain capture for your team.

The following is required to add and verify a domain and enable domain capture:

* Your team must be on the [Postman Enterprise](https://www.postman.com/pricing) plan.
* Your team must be on [Postman version 9 or later](/docs/administration/updating/).

The following is required to enable domain capture:

* [SSO](/docs/administration/sso/admin-sso/) must be configured and enabled.
    * Alternative authentication methods (Postman or Google sign in) must be turned off.

It's recommended that you enable [SSO provisioning](/docs/administration/scim-provisioning/scim-provisioning-overview/) to ease the process of onboarding new users and [Auto-Flex](/docs/administration/billing/#using-auto-flex) to ensure that your team can automatically accommodate all users that may be added to your Postman team when domain capture is enabled.

## Adding and verifying a domain

[Team Admins](/docs/collaborating-in-postman/roles-and-permissions/#team-roles) can add domains and subdomains to your team by navigating to the [domain dashboard](https://go.postman.co/settings/team/domain-capture). Once you add your verification **TXT Record** to your DNS configuration, Postman's team will verify your domain or subdomain. Your domain must be verified before you can view and manage all user accounts in Postman created with your organization’s domains and subdomains.

1. Open Postman and select **Team > Team Settings** in the Postman header. Select **Authentication** in the left sidebar.
1. Confirm that your team has only the SSO authentication method enabled. Then, select the **Domains** tab.

    > Your team must have only SAML-based SSO authentication methods enabled to set up domain capture. Alternative authentication methods such as Postman or Google sign in must be turned off.

1. Select **Add Domain**.

    ![Select Add Domain](https://assets.postman.com/postman-docs/v10/select-add-domain-v10.jpg)

1. Enter the domain or subdomain you'd like to add, and then select **Generate Verification Record**.

    <img alt="Generate verification record" src="https://assets.postman.com/postman-docs/v10/enter-domain-name-v10.jpg" width="450px"/>

1. Select <img alt="Copy icon" src="https://assets.postman.com/postman-docs/icon-copy-v9.jpg#icon" width="15px"> **Copy** to copy the **TXT Record**, and then add it to your domain's DNS configuration.

    > Instead, you can select **Verify Later** if you're not ready to add the **TXT Record** to your domain's DNS configuration. To verify your domain later, see [Verifying a domain later](#verifying-a-domain-later).

1. Select the **I have added the TXT record to the DNS tool** checkbox, and then select **Verify Domain**. Postman's team will check your requested domain and update its status to `VERIFIED` in your domain dashboard. Team Admins will receive an email notification when the domain is verified.

    <img alt="Add domain TXT record" src="https://assets.postman.com/postman-docs/v10/add-domain-verification-record-v10.jpg" width="450px"/>

    > You can reach out to [Postman support](https://www.postman.com/support/) to check the status of your domain verification request.

1. Once your domain is verified, you can [create a request to enable domain capture](#enabling-domain-capture).

### Verifying a domain later

Optionally, you can verify a domain later if you didn't verify the domain when you added it.

To verify a domain you've already added, do the following:

1. Open Postman and select **Team > Team Settings** in the Postman header. Select **Authentication** in the left sidebar.
1. Select **Verify** next to the domain with the `UNVERIFIED` status you want to verify.

    > You can also select **Manage** next to the domain with the `UNVERIFIED` status you want to verify, and then select **View Verification Details**.

    ![Verify domain later](https://assets.postman.com/postman-docs/v10/verify-domain-later-v10.jpg)

1. Select <img alt="Copy icon" src="https://assets.postman.com/postman-docs/icon-copy-v9.jpg#icon" width="15px"> **Copy** to copy the **TXT Record**, and then add it to your domain's DNS configuration.
1. Select the **I have added the TXT record to the DNS tool** checkbox, and then select **Verify Domain**. Postman's team will check your requested domain and update its status to `VERIFIED` in your domain dashboard. Team Admins will receive an email notification when the domain is verified.

    <img alt="Verify unverified domain" src="https://assets.postman.com/postman-docs/v10/verify-unverified-domain-later-v10.jpg" width="450px"/>

    > You can reach out to [Postman support](https://www.postman.com/support/) to check the status of your domain verification request.

1. Once your domain is verified, you can [create a request to enable domain capture](#enabling-domain-capture).

### Viewing verification details

Team Admins can view verification details for verified and unverified domains by navigating to the [domain dashboard](https://go.postman.co/settings/team/domain-capture). The verification details display the verification **TXT Record**.

1. Open Postman and select **Team > Team Settings** in the Postman header. Select **Authentication** in the left sidebar.
1. Select **Manage** next to the domain you want to view verification details for.
1. Select **View Verification Details**.

### Viewing unclaimed accounts

Unclaimed accounts are accounts associated with a verified domain that aren't part of your team. Team Admins can view unclaimed accounts by navigating to the [domain dashboard](https://go.postman.co/settings/team/domain-capture).

1. Open Postman and select **Team > Team Settings** in the Postman header. Select **Authentication** in the left sidebar.
1. Select **Manage** next to the domain with the `VERIFIED` status you want to view unclaimed accounts for, and then select **View Accounts**.

    > Optionally, you can select the number of unclaimed accounts next to the domain in the domain dashboard.

1. View the list of accounts not part of your team.

    <img alt="View unclaimed accounts" src="https://assets.postman.com/postman-docs/v10/view-unclaimed-accounts-v10.jpg" width="450px"/>

1. Optionally, you can select **Export CSV** to export the list as a CSV file. You will receive an email containing the download link.

## Enabling domain capture

After the domain or subdomain is [added and verified](#adding-and-verifying-a-domain), Team Admins can create a request to enable domain capture by navigating to the [domain dashboard](https://go.postman.co/settings/team/domain-capture). To enable domain capture, a Team Admin must create a request with Postman support. Once the request is approved, Team Admins can work with Postman support to manage [unclaimed accounts](#viewing-unclaimed-accounts).

To enable domain capture, do the following:

1. Open Postman and select **Team > Team Settings** in the Postman header. Select **Authentication** in the left sidebar.
1. Select **Manage** next to the domain with the `VERIFIED` status you want to enable domain capture for.
1. Select **Request To Claim**. Postman support will then contact Team Admins to explain the effects of enabling domain capture.
1. Once the request is approved, you can [contact Postman support](#contacting-support-to-manage-accounts) to manage [unclaimed accounts](#viewing-unclaimed-accounts).

To view the status of your request to enable domain capture, select **Manage** next to the domain. After you select **Request To Claim**, the request status is changed to `REQUEST SENT`.

![Request to claim sent](https://assets.postman.com/postman-docs/v10/request-to-claim-sent-v10.jpg)

Once the request is approved, a notification will display towards the top of the screen explaining that **Account Capture has been enabled**.

![Domain capture enabled](https://assets.postman.com/postman-docs/v10/domain-capture-enabled-v10.jpg)

> To turn off domain capture, you must [contact Postman support](#contacting-support-to-manage-accounts).

### User experience

When domain capture is enabled, new Postman users who sign up for Postman with your domain or subdomain are automatically added to your team.

Existing Postman users with accounts associated with the domain or subdomain will only be able to access Postman after joining your team. This applies to existing users who are part of other teams and existing individual users. The next time existing users sign in to Postman, they will get a notification that your team manages their account. Existing users can join the team using this notification.

<img alt="Domain capture join team notification" src="https://assets.postman.com/postman-docs/domain-capture-join-team-9.4.jpg" width="350px"/>

> You won't be able to selectively pick users you'd like to add to your team. Once enabled, the number of unclaimed accounts will reduce as these users sign in and join your team.

Existing users who were on other Postman teams will lose access to all data from their earlier teams, including personal workspaces. No data will be transferred from their earlier teams to their new team. Users won't be able to remain on or join extra Postman teams with their captured accounts.

> To transfer an existing user's collections and environments from their earlier teams to their new team, [contact Postman support](#contacting-support-to-manage-accounts).

For more details about the effects of enabling domain capture, see [Domain capture FAQs](#domain-capture-faqs).

> If users experience any issues when moving to your Postman team, reach out to [Postman support](https://www.postman.com/support/).

### Contacting support to manage accounts

Once the request is approved to [enable domain capture](#enabling-domain-capture), Team Admins can contact Postman support by navigating to the [domain dashboard](https://go.postman.co/settings/team/domain-capture). Contact Postman support to claim accounts not part of your team, merge teams into your team, and restrict users to only work in your team.

1. Open Postman and select **Team > Team Settings** in the Postman header. Select **Authentication** in the left sidebar.
1. Select **Manage** next to the domain with the `VERIFIED` status you want to contact support about.

    > Domain capture must be enabled for the domain you want to contact support about.

1. Select **Contact Support**.

    ![Contact support about managing accounts](https://assets.postman.com/postman-docs/v10/domain-capture-enabled-v10.jpg)

## Deleting a domain

Team Admins can delete domains and subdomains from your team by navigating to the [domain dashboard](https://go.postman.co/settings/team/domain-capture).

1. Open Postman and select **Team > Team Settings** in the Postman header. Select **Authentication** in the left sidebar.
1. Select **Manage** next to the domain you want to delete.
1. Select **Delete Domain**.

## Domain capture FAQs

### What happens to captured users and their data (collections, environments) when domain capture is enabled?

The experience for captured users depends on their prior team status:

* If a captured user is already on your organization's team, nothing changes for them.
* If a captured user isn't part of any team:
    * All existing user sessions are revoked.
    * The next time the user logs in, they will be prompted to join your organization's team using SSO.
    * When the user authenticates into your organization's team using SSO, their existing data will be transferred to the team.
* If a captured user is part of an existing free or paid team:
    * They're removed from their existing team.
    * All existing user sessions are revoked.
    * The next time the user logs in, they will be prompted to join your organization's team using SSO.
    * Users can authenticate into your organization's team using SSO.
    * They will lose access to all data from their earlier teams, including personal workspaces. No data will be transferred from their earlier teams to their new team.
        > To transfer an existing user's collections and environments from their earlier teams to their new team, [contact Postman support](#contacting-support-to-manage-accounts).
* If a captured user is the last Admin of an existing free team:
    * They're removed from the team and the remaining users are assigned the [Admin role](/docs/collaborating-in-postman/roles-and-permissions/#team-roles).
    * All existing user sessions are revoked.
    * The next time the user logs in, they will be prompted to join your organization's team using SSO.
    * Users can authenticate into your organization's team using SSO.
    * They will lose access to all data from their earlier teams, including personal workspaces. No data will be transferred from their earlier teams to their new team.
        > To transfer an existing user's collections and environments from their earlier teams to their new team, [contact Postman support](#contacting-support-to-manage-accounts).
* If a captured user is the last Admin of an existing paid team:
    * Postman support will contact your Team Admins to discuss how to approach this prior to verifying the domain you've added to your team.
    * All existing user sessions are revoked.
    * The next time the user logs in, they will be prompted to leave their existing team.
    * They will need to contact [Postman support](https://www.postman.com/support/) to assign the Admin role to another team member and remove them from the team.
    * Users can authenticate into your organization's team using SSO.
    * They will lose access to all data from their earlier teams, including personal workspaces. No data will be transferred from their earlier teams to their new team.
        > To transfer an existing user's collections and environments from their earlier teams to their new team, [contact Postman support](#contacting-support-to-manage-accounts).

### Can a Team Admin view the list of user accounts that will be captured before enabling domain capture?

Yes, a Team Admin can view the list of the unclaimed Postman accounts that will be captured prior to confirming they'd like to enable domain capture. To learn more, see [Viewing unclaimed accounts](#viewing-unclaimed-accounts).

### Does adding a domain automatically add all the team members with the organization’s domain to the organization’s team?

No, after a Team Admin adds a domain, they must create a request for Postman's team to verify the domain or subdomain. Once both criteria are met, a Team Admin can create a request to enable domain capture. Postman support will then contact Team Admins to explain the effects of enabling domain capture. To learn more, see [Enabling domain capture](#enabling-domain-capture).
