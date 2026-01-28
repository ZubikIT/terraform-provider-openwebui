---
layout: resource
page_title: "openwebui_pipeline_valves Resource"
sidebar_current: docs-openwebui-resource-pipeline-valves
description: |-
  Manages valve settings for Open WebUI pipelines.
---

# openwebui_pipeline_valves (Resource)

Manages valve settings for a pipeline.

## Example Usage

### Minimal

```hcl
resource "openwebui_pipeline_valves" "support" {
  pipeline_id = openwebui_pipeline.remote.id
}
```

### Full

```hcl
resource "openwebui_pipeline_valves" "support" {
  pipeline_id = openwebui_pipeline.remote.id
  url_idx     = 0
  valves_json = jsonencode({
    enabled = true
  })
}
```

## Argument Reference

* `pipeline_id` (Required) – Pipeline identifier to configure valves for.
* `url_idx` (Optional) – Pipeline URL index (defaults to `0`).
* `valves_json` (Optional) – JSON payload describing valve settings.

## Attribute Reference

* `id` – Identifier of the pipeline valves resource (mirrors `pipeline_id`).
* `spec_json` – JSON schema describing available valve settings.

## Import

Pipeline valves can be imported by pipeline ID. If a non-zero `url_idx` is required, use `pipeline_id:url_idx`:

```bash
terraform import openwebui_pipeline_valves.support pipeline-123
terraform import openwebui_pipeline_valves.support pipeline-123:1
```
