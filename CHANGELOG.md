# Changelog

## 0.6.0 24/09/2025

### features
- Added support for new `conveyor_project_links` dollar and euro icons
- Added support for new data source `conveyor_ide_base_image`

### bugfixes
- Fixed issues with importing non-existent resources for: `conveyor_ide_base_image`, `conveyor_user`, `conveyor_package`
- Fixed import of `conveyor_ide_base_image` not working

## 0.5.3 11/09/2025

### bugfixes

- Fixes an issue with `conveyor_user` where importing a user and setting `skip_invitation_email` would trigger updates, while updates are not supported.
- Fixes an issue with `conveyor_user` after imports where the ID would trigger an update, while it does not change

## 0.5.2 18/08/2025

### features
- We have delayed some checks from configuration to runtime, this allows for cases where the Conveyor resources are
  applied conditionally. In an environment where the Conveyor resources would not be applied, no credentials have to be
  passed to the Conveyor provider.
- Support creating environments with Airflow 3.
- Allow to skip sending the invitation email, when inviting new users

### bugfixes
- Update the `conveyor_alert_config` example and it's documentation.

## 0.5.1 13/05/2025

### features
- Add support for managing the default IDE base image for a project
- Added iam_identity to `conveyor_ide_base_image` resource

### bugfixes
- Fix that the `conveyor_ide_base_image` resource correctly processes optional `vscode_config` and `buildSteps` attributes within the configuration.

## 0.5.0 18/04/2025

### features
- Added support for `conveyor_user` resource

### bugfixes
- Do not allow user emails with uppercase letters as Conveyor always uses lowercase letters.
- Fix an issue where updating an environment with a secrets backend configuration would fail.
- Allow the provider to correctly handle users and teams that are linked to an environment or project when it gets deleted outside of terraform.

## 0.4.3 28/01/2025

### features
- Add support for managing IDE base images

## 0.4.2 19/09/2024

### features
- Update project links to include the latest icons

## 0.4.1 05/08/2024

In this release the provider got upgraded from v5 to v6 of the terraform plugin protocol.
This means the provider will only work with terraform >=1.0.

### features
- Added support for managing project links

## 0.4.0 16/07/2024

### features
- Package support

## 0.3.1 23/01/2024

### features
- Support configuring secrets backend in Airflow configuration
- Added support for Conveyor SSO Group mapping to teams

## 0.3.0 28/11/2023

### features
- Add oidc url to cluster datasource

## 0.2.1 09/10/2023

### features
- Add support for setting the default ide environment id on a project
- Allow changing the order of tags on a project
- Allow adding the git_sub_folder of a project
- Support several provider configuration options: CICD tokens, profile and allowed_tenant_id
- Add support for setting the Navbar color for Airflow on an environment
- Support deleting tags in the CLI

## 0.2.0 22/08/2023

### features
- Add support for the defaultIdeConfig on a project
- Add support for alert config on a project

## 0.1.5 10/06/2023

### bugfixes
- Order the tagIds read just like the users has input them to ensure that you do not get constant changes while applying

## 0.1.4 25/04/2023

### features
- Add the available tag colors to the documentation of the `conveyor_tag` resource
- Automatically open the login pop-up when not logged in, instead of printing an error

## 0.1.3 19/04/2023

### features
- Add examples and import statements for `conveyor_tag` and `conveyor_project_tags`

### 0.1.2 19/04/2023

### features
- Allow defining and retrieving tags through the `conveyor_tag` resource and data source.
- Project tags can be configured through the `conveyor_project_tags` resource.

## 0.1.1 29/03/2023

### features

- Adds support for supplying a default role on a project through the `conveyor_project` resource.
- Modifies the default value for the `datahub_integration.cluster` property on the `conveyor_environment` resource.
  This now defaults to the name of the environment instead of "prod".

## 0.1.0 15/03/2023

### features

- Adds support for listing the users of a project through the `conveyor_project_users` datasource
- Adds support for listing the teams of a project through the `conveyor_project_teams` datasource
- Adds support for listing the users of an environment through the `conveyor_environment_users` datasource
- Adds support for listing the teams of an environment through the `conveyor_environment_teams` datasource
- The `conveyor_team` datasource now exposes the `users` attribute

## 0.0.9 27/02/2023

### features

- Adds support for setting the Airflow configuration

## 0.0.8 21/02/2023

### features

- Adds support for the conveyor Airflow Datahub integration
- Added defaults to our terraform docs

## 0.0.7 22/11/2022

### bugfixes

- Fixed some typos in the environment terraform resources

## 0.0.6 28/10/2022

### bugfixes

- Fixed an issue where m2m credentials would result in a failure when trying to use the provider

## 0.0.5 27/10/2022

### features
- Added support for import `conveyor_team` and `conveyor_team_user`

### bugfixes

- Show an error message when the user is not logged in
- Use the same token used by the recent conveyor cli's

## 0.0.4 12/8/2022

### features

- Improved the docs for Conveyor teams

## 0.0.3 12/8/2022

### features

- Added support for Conveyor teams

## 0.0.2 7/6/2022

### features

- The provider now works with the CONVEYOR prefix environment variables, which are preferred over the old DATAFY prefix
- The provider stores tokens in ~/.conveyor instead of ~/.datafy

## 0.0.1 19/5/2022

### features

- Rename provider from dmcloud to conveyor
