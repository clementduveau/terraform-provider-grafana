---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "grafana_oncall_escalation_chain Resource - terraform-provider-grafana"
subcategory: "OnCall"
description: |-
  HTTP API https://grafana.com/docs/oncall/latest/oncall-api-reference/escalation_chains/
---

# grafana_oncall_escalation_chain (Resource)

* [HTTP API](https://grafana.com/docs/oncall/latest/oncall-api-reference/escalation_chains/)

## Example Usage

```terraform
data "grafana_team" "my_team" {
  name = "my team"
}

data "grafana_oncall_team" "my_team" {
  name = data.grafana_team.my_team.name
}

resource "grafana_oncall_escalation_chain" "default" {
  provider = grafana.oncall
  name     = "default"

  // Optional: specify the team to which the escalation chain belongs
  team_id = data.grafana_oncall_team.my_team.id
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `name` (String) The name of the escalation chain.

### Optional

- `team_id` (String) The ID of the OnCall team (using the `grafana_oncall_team` datasource).

### Read-Only

- `id` (String) The ID of this resource.

## Import

Import is supported using the following syntax:

```shell
terraform import grafana_oncall_escalation_chain.name "{{ id }}"
```
