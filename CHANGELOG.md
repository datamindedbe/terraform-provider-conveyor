# Changelog

## 0.8.1 (2026-11-27)

### features

- Added support for `package_ids` in the `conveyor_service_account` resource and data source.

### bugfixes

- Fixed destroying a `conveyor_team_user` failing when the user no longer exists.

## 0.8.0 (2026-10-06)

### features

- Added support for `based_on` in `conveyor_ide_base_image`.
- Added support for service accounts with new resources `conveyor_service_account` and `conveyor_service_account_token`,
  data source `conveyor_service_account` and ephemeral resource `conveyor_service_account_token`.

## 0.7.0 (2026-02-24)

### features

- Added support for new `conveyor_project_links` soda icon

### breaking changes

- The `default_ide_config` on the `conveyor_project` resource is not a computed field anymore.
  This means that if you do not specify it, it will remove the default IDE config from the project whereas before it would keep the existing config.
  If you want to keep the existing config, you need to explicitly set it in terraform or set `ignore_changes = [default_ide_config]` in a lifecycle block.
- The default environment version is now 3, instead of 2.

## 0.6.0 (2025-09-24)

### features
- Added support for new `conveyor_project_links` dollar and euro icons
- Added support for new data source `conveyor_ide_base_image`

### bugfixes
- Fixed issues with importing non-existent resources for: `conveyor_ide_base_image`, `conveyor_user`, `conveyor_package`
- Fixed import of `conveyor_ide_base_image` not working

## 0.5.3 (2025-09-11)

### bugfixes

- Fixes an issue with `conveyor_user` where importing a user and setting `skip_invitation_email` would trigger updates, while updates are not supported.
- Fixes an issue with `conveyor_user` after imports where the ID would trigger an update, while it does not change

## 0.5.2 (2025-08-18)

### features
- We have delayed some checks from configuration to runtime, this allows for cases where the Conveyor resources are
  applied conditionally. In an environment where the Conveyor resources would not be applied, no credentials have to be
  passed to the Conveyor provider.
- Support creating environments with Airflow 3.
- Allow to skip sending the invitation email, when inviting new users

### bugfixes
- Update the `conveyor_alert_config` example and its documentation.

## 0.5.1 (2025-05-13)

### features
- Add support for managing the default IDE base image for a project
- Added iam_identity to `conveyor_ide_base_image` resource

### bugfixes
- Fix that the `conveyor_ide_base_image` resource correctly processes optional `vscode_config` and `buildSteps` attributes within the configuration.

## 0.5.0 (2025-04-18)

### features
- Added support for `conveyor_user` resource

### bugfixes
- Do not allow user emails with uppercase letters as Conveyor always uses lowercase letters.
- Fix an issue where updating an environment with a secrets backend configuration would fail.
- Allow the provider to correctly handle users and teams that are linked to an environment or project when it gets deleted outside of terraform.

## 0.4.3 (2025-01-28)

### features
- Add support for managing IDE base images

## 0.4.2 (2024-09-19)

### features
- Update project links to include the latest icons

## 0.4.1 (2024-08-05)

In this release the provider got upgraded from v5 to v6 of the terraform plugin protocol.
This means the provider will only work with terraform >=1.0.

### features
- Added support for managing project links

## 0.4.0 (2024-07-16)

### features
- Package support

## 0.3.1 (2024-01-23)

### features
- Support configuring secrets backend in Airflow configuration
- Added support for Conveyor SSO Group mapping to teams

## 0.3.0 (2023-11-28)

### features
- Add oidc url to cluster datasource

## 0.2.1 (2023-10-09)

### features
- Add support for setting the default ide environment id on a project
- Allow changing the order of tags on a project
- Allow adding the git_sub_folder of a project
- Support several provider configuration options: CICD tokens, profile and allowed_tenant_id
- Add support for setting the Navbar color for Airflow on an environment
- Support deleting tags in the CLI

## 0.2.0 (2023-08-22)

### features
- Add support for the defaultIdeConfig on a project
- Add support for alert config on a project

## 0.1.5 (2023-07-10)

### bugfixes
- Order the tagIds read just like the users has input them to ensure that you do not get constant changes while applying

## 0.1.4 (2023-04-25)

### features
- Add the available tag colors to the documentation of the `conveyor_tag` resource
- Automatically open the login pop-up when not logged in, instead of printing an error

## 0.1.3 (2023-04-19)

### features
- Add examples and import statements for `conveyor_tag` and `conveyor_project_tags`

## 0.1.2 (2023-04-19)

### features
- Allow defining and retrieving tags through the `conveyor_tag` resource and data source.
- Project tags can be configured through the `conveyor_project_tags` resource.

## 0.1.1 (2023-03-29)

### features

- Adds support for supplying a default role on a project through the `conveyor_project` resource.
- Modifies the default value for the `datahub_integration.cluster` property on the `conveyor_environment` resource.
  This now defaults to the name of the environment instead of "prod".

## 0.1.0 (2023-03-15)

### features

- Adds support for listing the users of a project through the `conveyor_project_users` datasource
- Adds support for listing the teams of a project through the `conveyor_project_teams` datasource
- Adds support for listing the users of an environment through the `conveyor_environment_users` datasource
- Adds support for listing the teams of an environment through the `conveyor_environment_teams` datasource
- The `conveyor_team` datasource now exposes the `users` attribute

## 0.0.9 (2023-02-27)

### features

- Adds support for setting the Airflow configuration

## 0.0.8 (2023-02-21)

### features

- Adds support for the conveyor Airflow Datahub integration
- Added defaults to our terraform docs

## 0.0.7 (2022-11-22)

### bugfixes

- Fixed some typos in the environment terraform resources

## 0.0.6 (2022-10-28)

### bugfixes

- Fixed an issue where m2m credentials would result in a failure when trying to use the provider

## 0.0.5 (2022-10-27)

### features
- Added support for import `conveyor_team` and `conveyor_team_user`

### bugfixes

- Show an error message when the user is not logged in
- Use the same token used by the recent conveyor CLIs

## 0.0.4 (2022-08-12)

### features

- Improved the docs for Conveyor teams

## 0.0.3 (2022-08-12)

### features

- Added support for Conveyor teams

## 0.0.2 (2022-06-07)

### features

- The provider now works with the CONVEYOR prefix environment variables, which are preferred over the old DATAFY prefix
- The provider stores tokens in ~/.conveyor instead of ~/.datafy

## 0.0.1 (2022-05-19)

### features

- Rename provider from dmcloud to conveyor
