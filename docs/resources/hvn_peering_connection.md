---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "hcp_hvn_peering_connection Resource - terraform-provider-hcp"
subcategory: ""
description: |-
  The HVN peering connection resource allows you to manage a peering connection between HVNs.
---

# hcp_hvn_peering_connection (Resource)

The HVN peering connection resource allows you to manage a peering connection between HVNs.

## Example Usage

```terraform
resource "hcp_hvn" "hvn_1" {
  hvn_id         = "hvn-1"
  cloud_provider = "aws"
  region         = "us-west-2"
  cidr_block     = "172.25.16.0/20"
}

resource "hcp_hvn" "hvn_2" {
  hvn_id         = "hvn-2"
  cloud_provider = "aws"
  region         = "us-west-2"
  cidr_block     = "172.18.16.0/20"
}

resource "hcp_hvn_peering_connection" "peer_1" {
  hvn_1 = hcp_hvn.hvn_1.self_link
  hvn_2 = hcp_hvn.hvn_2.self_link
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `hvn_1` (String) The unique URL of one of the HVNs being peered.
- `hvn_2` (String) The unique URL of one of the HVNs being peered.

### Optional

- `id` (String) The ID of this resource.
- `timeouts` (Block, Optional) (see [below for nested schema](#nestedblock--timeouts))

### Read-Only

- `created_at` (String) The time that the peering connection was created.
- `expires_at` (String) The time after which the peering connection will be considered expired if it hasn't transitioned into `ACCEPTED` or `ACTIVE` state.
- `organization_id` (String) The ID of the HCP organization where the peering connection is located. Always matches the HVNs' organization.
- `peering_id` (String) The ID of the peering connection.
- `project_id` (String) The ID of the HCP project where the peering connection is located. Always matches the HVNs' project.
- `self_link` (String) A unique URL identifying the peering connection

<a id="nestedblock--timeouts"></a>
### Nested Schema for `timeouts`

Optional:

- `create` (String)
- `default` (String)
- `delete` (String)

## Import

Import is supported using the following syntax:

```shell
# The import ID requires the first HVN ID in the format {hvn_1_id}:{peering_id}
terraform import hcp_hvn_peering_connection.peer_1 hvn-1:peer-1
```
