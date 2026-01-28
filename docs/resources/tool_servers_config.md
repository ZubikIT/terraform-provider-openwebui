---
layout: resource
page_title: "openwebui_tool_servers_config Resource"
sidebar_current: docs-openwebui-resource-tool-servers-config
description: |-
  Manages Open WebUI tool server configuration.
---

# openwebui_tool_servers_config (Resource)

Updates tool server connection settings in Open WebUI.

## Example Usage

### Minimal

```hcl
resource "openwebui_tool_servers_config" "default" {
  connections = [
    {
      url  = "https://tools.example.com"
      path = "/openapi.json"
    }
  ]
}
```

### Full

```hcl
resource "openwebui_tool_servers_config" "default" {
  connections = [
    {
      url       = "https://tools.example.com"
      path      = "/openapi.json"
      type      = "openapi"
      auth_type = "bearer"
      key       = var.tool_server_token
      headers_json = jsonencode({
        "x-client" = "terraform"
      })
      config_json = jsonencode({
        timeout = 30
      })
    }
  ]
}
```

## Argument Reference

* `connections` (Required) – List of tool server connections.
  * `url` (Required) – Base URL for the tool server.
  * `path` (Required) – OpenAPI document path.
  * `type` (Optional) – Connection type (for example `openapi`).
  * `auth_type` (Optional) – Authentication type.
  * `headers_json` (Optional) – JSON object of headers.
  * `key` (Optional, Sensitive) – Authentication key.
  * `config_json` (Optional) – JSON object with extra configuration.

## Attribute Reference

* `id` – Singleton identifier for the tool servers config.

## Import

Tool servers config can be imported with any ID:

```bash
terraform import openwebui_tool_servers_config.default tool_servers
```
