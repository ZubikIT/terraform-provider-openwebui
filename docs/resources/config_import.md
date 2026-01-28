---
layout: resource
page_title: "openwebui_config_import Resource"
sidebar_current: docs-openwebui-resource-config-import
description: |-
  Applies configuration exports to Open WebUI.
---

# openwebui_config_import (Resource)

Imports a full configuration export payload into Open WebUI.

## Example Usage

### Minimal

```hcl
resource "openwebui_config_import" "restore" {
  config_json = file("./config-export.json")
}
```

### Full

```hcl
data "openwebui_config_export" "current" {}

resource "openwebui_config_import" "restore" {
  config_json = data.openwebui_config_export.current.config_json
}
```

## Argument Reference

* `config_json` (Required) – Full configuration export payload as JSON.

## Attribute Reference

* `id` – Singleton identifier for the config import resource.

## Notes

* `config_json` can include sensitive values; treat Terraform state accordingly.
* Read operations refresh state from the export endpoint, so server-side defaults may appear in state.

## Import

Config import can be imported with any ID (the provider treats it as a singleton):

```bash
terraform import openwebui_config_import.restore config_import
```
