---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "hcp_boundary_cluster Resource - terraform-provider-hcp"
subcategory: ""
description: |-
  This resource allows you to manage an HCP Boundary cluster
---

# hcp_boundary_cluster (Resource)

This resource allows you to manage an HCP Boundary cluster

## Example Usage

```terraform
resource "hcp_boundary_cluster" "example" {
  cluster_id = "boundary-cluster"
  username   = "test-user"
  password   = "Password123!"
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `cluster_id` (String) The ID of the Boundary cluster
- `password` (String, Sensitive) The password of the initial admin user. This must be at least 8 characters in length. Note that this may show up in logs, and it will be stored in the state file.
- `username` (String) The username of the initial admin user. This must be at least 3 characters in length, alphanumeric, hyphen, or period.

### Optional

- `timeouts` (Block, Optional) (see [below for nested schema](#nestedblock--timeouts))

### Read-Only

- `cluster_url` (String) A unique URL identifying the Boundary cluster.
- `created_at` (String) The time that the Boundary cluster was created.
- `id` (String) The ID of this resource.
- `state` (String) The state of the Boundary cluster.

<a id="nestedblock--timeouts"></a>
### Nested Schema for `timeouts`

Optional:

- `create` (String)
- `default` (String)
- `delete` (String)

## Import

Import is supported using the following syntax:

```shell
# The import ID is {cluster_id}
terraform import hcp_boundary_cluster.example boundary-cluster
```