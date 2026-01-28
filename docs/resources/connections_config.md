---
layout: resource
page_title: "openwebui_connections_config Resource"
sidebar_current: docs-openwebui-resource-connections-config
description: |-
  Manages Open WebUI connections configuration.
---

# openwebui_connections_config (Resource)

Updates connection-related settings in Open WebUI.

## Example Usage

### Minimal

```hcl
resource "openwebui_connections_config" "default" {
  enable_direct_connections = true
  enable_base_models_cache  = true
}
```

### Full

```hcl
resource "openwebui_connections_config" "default" {
  enable_direct_connections = false
  enable_base_models_cache  = false
}
```

## Argument Reference

* `enable_direct_connections` (Required) – Whether direct connections are enabled.
* `enable_base_models_cache` (Required) – Whether base model caching is enabled.

## Attribute Reference

* `id` – Singleton identifier for the connections config.

## Import

Connections config can be imported with any ID (the provider treats it as a singleton):

```bash
terraform import openwebui_connections_config.default connections
```
