# Changelog

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
