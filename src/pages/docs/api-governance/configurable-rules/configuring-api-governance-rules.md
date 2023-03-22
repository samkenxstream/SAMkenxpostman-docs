---
title: "Configuring API Governance rules"
updated: 2023-03-06
search_keyword: "api governance, schema validation, api schema vulnerabilities"
---

> [Configurable governance rules are available on Postman Enterprise plans.](https://www.postman.com/pricing) If you don't have an Enterprise account, you'll be able to see the API Governance page, but you won't be able to turn rules on or off or add new rules.

You can customize the API Governance rules that Postman applies to your [API definitions](/docs/api-governance/api-definition/api-definition-warnings/). Adhering to these API Governance rules at the start of the API lifecycle keeps your API consistent without requiring extra work at later stages. This can prevent unnecessary delays for your organization.

> Only Team Admins with a [Developer role](/docs/collaborating-in-postman/roles-and-permissions/#team-roles) can manage API Governance rules for their team.

<img alt="API governance dashboard" src="https://assets.postman.com/postman-docs/api-governance-dashboard-10.12.jpg"/>

## Contents

* [Accessing the configurable API Governance rules](#accessing-the-configurable-api-governance-rules)
* [Adding rules to your API Governance configuration](#adding-rules-to-your-api-governance-configuration)
    * [Importing rules from the rule library](#importing-rules-from-the-rule-library)
    * [Adding custom rules](#adding-custom-rules)
* [Turning configured rules on and off](#turning-configured-rules-on-and-off)
* [Removing rules from your API Governance configuration](#removing-rules-from-your-api-governance-configuration)

## Accessing the configurable API Governance rules

1. Go to the [Postman home screen](https://go.postman.co/).
1. Select **API Governance** from the team information pane.

## Adding rules to your API Governance configuration

In addition to the rules turned on by default in Postman, you can add other rules to your team's rule library from the rule library. You can also create your own custom rules.

### Importing rules from the rule library

The rule library contains Postman's API governance guidelines and Zalando's RESTful API and event guidelines. Navigate to the [governance dashboard](#accessing-the-configurable-api-governance-rules), then select **Import** to open the rule library.

You can select **View all** below a set of guidelines to view all of its rules. Details and API format requirements are available under the rule name. Select **Import** next to a rule to import it. To import all rules for a particular set of guidelines, select **Import All**.

<img alt="Import API Governance rule from Postman library" src="https://assets.postman.com/postman-docs/import-postman-rule-from-rule-library-10.12.0.jpg"/>

Once you import new rules from the library, you need to [turn them on](#turning-configured-rules-on-and-off) in the API Governance dashboard.

### Adding custom rules

You can create new custom governance rules for Postman to evaluate your API's definition. Postman provides you with a boilerplate rule to help you start writing your custom governance rules. You can also use snippets of commonly-used property-value pairs to help you write your custom governance rules.

To add a custom rule, do the following:

1. Go to the [Postman home screen](https://go.postman.co/), and then select **API Governance** from the team information pane.
1. Select the **Rule Library** tab.
1. Select **Create Rule**.
1. Define the rule in the editor. It must adhere to [custom rule guidelines](/docs/api-governance/configurable-rules/spectral/).

    You can use a curated list of commonly-used property-value pair snippets to write your rules. Snippets are available in the right pane of the editor. Selecting a snippet adds the property-value pair automatically to your rule, helping you get started quickly with writing rules. Once added to your rule, you can edit the snippets to meet your specific requirements.

    > Postman will prompt you with suggestions as you enter text. Select one to autocomplete your rule.

1. The rule must be valid YAML or JSON. Use the dropdown list to choose the correct syntax.
1. Select **Create**.

    <img alt="Create a custom API Governance rule" src="https://assets.postman.com/postman-docs/v10/api-governance-create-custom-rule-v10-2.jpg"/>

1. Find your new rule under **Created by your team** and [turn it on](#turning-configured-rules-on-and-off).

You can also select **Upload file(s)** to upload a new rule in valid YAML or JSON format.

> You can't create a custom rule that duplicates an existing rule.

## Turning configured rules on and off

You can turn individual governance rules on or off for various workspaces to meet your team's development needs. To do so, select **Workspace Groups**. You can create a new group of workspaces to apply individual governance rules to by selecting **Create Group**, or you can select an existing group to update its governance configuration. To apply individual governance rules to all workspaces, select the default **All workspaces** group.

To turn a governance rule on or off for a workspace group, select an existing group, and then select **Edit**. To turn a governance rule on, select the checkbox next to the rule name. To turn a governance rule off, clear the checkbox next to the rule name.

<img alt="Turn individual rules on and off" src="https://assets.postman.com/postman-docs/api-governance-turn-rules-on-off-10.12.0.jpg"/>

Once you've made the desired changes, select **Review Changes**, then **Apply Changes** to save them. Your team will only see violations in your API's definition for the governance rules that have been explicitly applied to the workspace it resides in.

## Removing rules from your API Governance configuration

To remove an API Governance rule, locate the rule in your team's rule library and select the delete icon <img alt="Delete icon" src="https://assets.postman.com/postman-docs/icon-delete-v9.jpg#icon" width="12px"> next to its name. You can later choose to [re-import it from the rule library](#importing-rules-from-the-rule-library).

If you remove a custom rule using the delete icon <img alt="Delete icon" src="https://assets.postman.com/postman-docs/icon-delete-v9.jpg#icon" width="12px">, you'll need to add it back into Postman using [**Create Rule**](#adding-custom-rules) if you want to use it again.
