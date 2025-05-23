---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "conveyor_ide_base_image Resource - conveyor"
subcategory: ""
description: |-
  IDE base image resource
---

# conveyor_ide_base_image (Resource)

IDE base image resource

## Example Usage

```terraform
resource "conveyor_ide_base_image" "my_image" {
  name         = "my image"
  description  = "My custom base ide image"
  iam_identity = "my-base-image-role"
  config = {
    vscode_config = {
      extensions = ["test_extension"]
    }
    build_steps = [
      {
        name = "step1"
        cmd  = "command one"
      }
    ]
  }
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `config` (Attributes) The configuration that defines this IDE base image (see [below for nested schema](#nestedatt--config))
- `name` (String) The name of the IDE base image

### Optional

- `description` (String) The description of the IDE base image
- `iam_identity` (String) The iam identity of the IDE base image

### Read-Only

- `id` (String) The id of the IDE base image

<a id="nestedatt--config"></a>
### Nested Schema for `config`

Optional:

- `build_steps` (Attributes List) Additional commands that customize the IDE environment (see [below for nested schema](#nestedatt--config--build_steps))
- `vscode_config` (Attributes) VS Code configuration of the IDE base image (see [below for nested schema](#nestedatt--config--vscode_config))

<a id="nestedatt--config--build_steps"></a>
### Nested Schema for `config.build_steps`

Required:

- `cmd` (String) The command that needs to be executed. Can contain multiple commands, separated by newlines.
- `name` (String) The name of the build step


<a id="nestedatt--config--vscode_config"></a>
### Nested Schema for `config.vscode_config`

Required:

- `extensions` (List of String) Enable user specific extensions
