---
layout: data-source
page_title: "openwebui_tool_server_verify Data Source"
sidebar_current: docs-openwebui-data-source-tool-server-verify
description: |-
  Verifies Open WebUI tool server connectivity.
---

# openwebui_tool_server_verify (Data Source)

Verifies a tool server connection. The data source fails if verification fails.

## Example Usage

### Minimal

```hcl
data "openwebui_tool_server_verify" "server" {
  url  = "https://tools.example.com"
  path = "/"
}
```

### Full

```hcl
data "openwebui_tool_server_verify" "server" {
  url       = "https://tools.example.com"
  path      = "/"
  auth_type = "bearer"
  key       = var.tool_server_key

  headers_json = jsonencode({
    "x-client" = "terraform"
  })
  config_json = jsonencode({
    timeout = 30
  })
}
```

## Argument Reference

* `url` (Required) – Tool server base URL to verify.
* `path` (Required) – Tool server path to verify.
* `type` (Optional) – Tool server type.
* `auth_type` (Optional) – Authentication type.
* `headers_json` (Optional) – Headers JSON for the tool server.
* `key` (Optional) – Authentication key for the tool server.
* `config_json` (Optional) – Tool server config JSON.

## Attribute Reference

* `verified` – Whether the tool server verification succeeded.

## Notes

* Verification is a live API call; failures surface as read errors.
* `headers_json` and `config_json` should contain JSON object strings.
