---
layout: data-source
page_title: "openwebui_config_export Data Source"
sidebar_current: docs-openwebui-data-source-config-export
description: |-
  Exports Open WebUI configuration.
---

# openwebui_config_export (Data Source)

Exports the full Open WebUI configuration as JSON.

## Example Usage

### Minimal

```hcl
data "openwebui_config_export" "current" {}
```

### Full

```hcl
data "openwebui_config_export" "current" {}

resource "openwebui_config_import" "restore" {
  config_json = data.openwebui_config_export.current.config_json
}
```

## Argument Reference

No arguments are required.

## Attribute Reference

* `config_json` – Full configuration export payload as JSON.

## Notes

* `config_json` can include sensitive values; treat outputs and state accordingly.
