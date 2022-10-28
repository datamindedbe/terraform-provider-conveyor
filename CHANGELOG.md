# Changelog

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