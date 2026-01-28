---
layout: provider
page_title: "OpenWebUI Provider"
sidebar_current: docs-openwebui-index
description: |-
  Interact with Open WebUI knowledge bases, models, prompts, and groups using Terraform.
---

# OpenWebUI Provider

The OpenWebUI provider lets you manage knowledge bases, models, prompts, and groups through Terraform. It communicates with an Open WebUI deployment via the REST API and requires a bearer token for authentication.

> **2.0.0** – Releases are now shipped automatically to the Terraform Registry when you push a tag that matches `v*.*.*`. Prompt commands are normalised with a leading `/`, and the group resource has dropped unsupported JSON arguments.

## Example Usage

```hcl
terraform {
  required_providers {
    openwebui = {
      source  = "nickcecere/openwebui"
      version = "~> 2.0"
    }
  }
}

provider "openwebui" {
  endpoint = "https://openwebui.example.com/api/v1"
  token    = var.openwebui_token
}
```

## Authentication

Authentication uses an HTTP bearer token. Supply it either directly with the `token` argument or through the `OPENWEBUI_TOKEN` environment variable.

## Configuration Reference

The provider supports the following configuration arguments:

* `endpoint` (Optional) – Base URL for your Open WebUI instance (defaults to `http://localhost:3000/api/v1`).
* `token` (Optional, Sensitive) – API token for authenticating requests. Can also be set via `OPENWEBUI_TOKEN`.

## Environment Variables

* `OPENWEBUI_ENDPOINT` – Overrides the API endpoint.
* `OPENWEBUI_TOKEN` – Supplies the API token when the provider block omits `token`.

## Available Resources

* [`openwebui_knowledge`](resources/knowledge)
* [`openwebui_model`](resources/model)
* [`openwebui_prompt`](resources/prompt)
* [`openwebui_group`](resources/group)
* [`openwebui_tool`](resources/tool)
* [`openwebui_tool_valves`](resources/tool_valves)
* [`openwebui_pipeline`](resources/pipeline)
* [`openwebui_pipeline_valves`](resources/pipeline_valves)
* [`openwebui_file`](resources/file)
* [`openwebui_knowledge_file`](resources/knowledge_file)
* [`openwebui_config_import`](resources/config_import)
* [`openwebui_connections_config`](resources/connections_config)
* [`openwebui_tool_servers_config`](resources/tool_servers_config)
* [`openwebui_code_execution_config`](resources/code_execution_config)
* [`openwebui_models_config`](resources/models_config)
* [`openwebui_suggestions_config`](resources/suggestions_config)
* [`openwebui_banners_config`](resources/banners_config)
* [`openwebui_oauth_client`](resources/oauth_client)

## Available Data Sources

* [`openwebui_knowledge`](data-sources/knowledge)
* [`openwebui_model`](data-sources/model)
* [`openwebui_prompt`](data-sources/prompt)
* [`openwebui_group`](data-sources/group)
* [`openwebui_tool`](data-sources/tool)
* [`openwebui_pipeline`](data-sources/pipeline)
* [`openwebui_file`](data-sources/file)
* [`openwebui_files`](data-sources/files)
* [`openwebui_config_export`](data-sources/config_export)
* [`openwebui_user`](data-sources/user)
* [`openwebui_tool_server_verify`](data-sources/tool_server_verify)

## Import

Most resources support import; refer to each resource page for the supported ID format. Singleton config resources accept any ID, and composite resources (like knowledge attachments) document their composite ID format.

Use the `terraform import` command with the relevant resource type and identifier, for example:

```bash
terraform import openwebui_group.example 65e5e86e-0e23-4cd8-8eee-447c6923f632
```

## Coverage

See [coverage](coverage) for a summary of supported API areas.

## Limitations

This provider is experimental. It reflects the REST API behaviour captured in the supplied `openapi.json` and may require adjustments for other Open WebUI versions. Acceptance tests are available but require a live Open WebUI instance and admin credentials.
