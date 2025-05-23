---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "conveyor_environment_user Resource - conveyor"
subcategory: ""
description: |-
  Links a user to a Conveyor environment.
---

# conveyor_environment_user (Resource)

Links a user to a Conveyor environment.

## Example Usage

```terraform
resource "conveyor_environment" "dev" {
  name = "dev"
}

resource "conveyor_environment_user" "my_environment_user" {
  environment_id = conveyor_environment.dev.id
  user_id        = "test@gmail.com"
  role           = "admin"
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `environment_id` (String) The id of the environment to add the user to.
- `role` (String) The role the user should have on the environment, either `admin`, `contributor` or `operator`.
- `user_id` (String) The email address of the user to add using only lowercase letters.

### Read-Only

- `id` (String) The ID of this resource.

## Import

Import is supported using the following syntax:

```shell
export ENV_ID=$(conveyor env get --name dev -ojson | jq -r ".id")
terraform import conveyor_environment_user.my_environment_user "$ENV_ID"/test@gmail.com
```
