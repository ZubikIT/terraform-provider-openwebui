---
layout: resource
page_title: "openwebui_oauth_client Resource"
sidebar_current: docs-openwebui-resource-oauth-client
description: |-
  Registers OAuth clients with Open WebUI.
---

# openwebui_oauth_client (Resource)

Registers an OAuth client with Open WebUI. The API does not provide a read endpoint, so state is preserved from the last apply.

## Example Usage

### Minimal

```hcl
resource "openwebui_oauth_client" "github" {
  url       = "https://github.com/login/oauth"
  client_id = "github-client-id"
}
```

### Full

```hcl
resource "openwebui_oauth_client" "github" {
  url         = "https://github.com/login/oauth"
  client_id   = "github-client-id"
  client_name = "GitHub"
  type        = "oauth"
}
```

## Argument Reference

* `url` (Required) – OAuth provider URL.
* `client_id` (Required) – OAuth client identifier to register.
* `client_name` (Optional) – Display name for the OAuth client.
* `type` (Optional) – OAuth client type query parameter.

## Attribute Reference

* `id` – OAuth client identifier (mirrors `client_id`).

## Notes

* The Open WebUI API does not expose a read endpoint for OAuth clients, so state is preserved from the last apply.

## Import

OAuth clients can be imported by client ID:

```bash
terraform import openwebui_oauth_client.github github-client-id
```
