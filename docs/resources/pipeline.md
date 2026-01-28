---
layout: resource
page_title: "openwebui_pipeline Resource"
sidebar_current: docs-openwebui-resource-pipeline
description: |-
  Manages Open WebUI pipelines.
---

# openwebui_pipeline (Resource)

Registers pipelines in Open WebUI either by URL or by uploading a bundle.

## Example Usage

### Minimal

```hcl
resource "openwebui_pipeline" "remote" {
  url = "https://example.com/pipelines/support.zip"
}
```

### Full

```hcl
resource "openwebui_pipeline" "local" {
  source_path = "./pipelines/support.zip"
  url_idx     = 1
}
```

## Argument Reference

Exactly one of `url` or `source_path` must be provided.

* `url` (Optional) – Remote pipeline URL to register.
* `source_path` (Optional) – Local pipeline bundle to upload.
* `url_idx` (Optional) – Pipeline URL index (defaults to `0`).

## Attribute Reference

* `id` – Unique pipeline identifier.
* `pipeline_id` – Pipeline identifier reported by the API.
* `details_json` – Raw JSON describing the pipeline returned by the API.

## Import

Pipelines can be imported by ID. If a non-zero `url_idx` is required, use `pipeline_id:url_idx`:

```bash
terraform import openwebui_pipeline.remote pipeline-123
terraform import openwebui_pipeline.remote pipeline-123:1
```
