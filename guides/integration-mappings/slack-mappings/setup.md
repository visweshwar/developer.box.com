---
rank: 2
related_endpoints:
  - delete_integration_mappings_slack_id
  - get_integration_mappings_slack
  - post_integration_mappings_slack
  - put_integration_mappings_slack_id
related_guides:
  - integration-mappings/slack-mappings/create-mapping
  - integration-mappings/slack-mappings/list-mappings
  - integration-mappings/slack-mappings/update-mapping
  - integration-mappings/slack-mappings/delete-mapping
required_guides: []
related_resources: []
alias_paths: []
category_id: integration-mappings
subcategory_id: integration-mappings/slack-mappings
is_index: false
id: integration-mappings/slack-mappings/setup
type: guide
total_steps: 7
sibling_id: integration-mappings/slack-mappings
parent_id: integration-mappings/slack-mappings
next_page_id: integration-mappings/slack-mappings/list-mappings
previous_page_id: integration-mappings/slack-mappings
source_url: >-
  https://github.com/box/developer.box.com/blob/main/content/guides/integration-mappings/slack-mappings/setup.md
---
# Slack Integration Mappings Setup

Before starting work with Integration Mappings API, perform
the following steps.

## Roles

Make sure you have an Admin or a Co-admin role.

## Install and configure Box for Slack

1. Install [Box for Slack][1] in the relevant Slack workspace or
organizations.
2. Enable the [Box as Content Layer for Slack][2].
3. Make sure the service account you are using is
a collaborator on the folder that will be mapped.
For details, see [Set service account as co-owner][3].

## Create Box application

1. Create a [custom app with OAuth authentication][4]
in the [Box developer console][5]
2. Open the application and
enable the **Manage enterprise properties** application
scope under **Configuration** > **Application Scopes**. 

<Message info>

For Slack-side channel validation, the [Integration Mappings API][6]
is calling the Slack API.

</Message>

## Authorization

To authorize your Integration Mappings requests:

1. Navigate to the [custom app][7] that you
have created as one of the prerequisites.
2. Generate a [developer token][8] and add it to
the HTTP header of each request: 

```bash
Authorization: Bearer {developer_token}
```

<Message info>

The developer token is valid for 60 minutes. After that time you need
to generate it again.

</Message>

[1]: https://support.box.com/hc/en-us/articles/360044195313-Installing-and-Using-the-Box-for-Slack-Integration
[2]: https://support.box.com/hc/en-us/articles/4415585987859-Box-as-the-Content-Layer-for-Slack
[3]: g://integration-mappings/slack-mappings/create-mapping#set-service-account-as-co-owner
[4]: g://authentication/oauth2/oauth2-setup
[5]: https://app.box.com/developers/console
[6]: e://get-integration-mappings-slack
[7]: g://applications/custom-apps
[8]: g://authentication/tokens/developer-tokens