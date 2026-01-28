---
layout: data-source
page_title: "openwebui_pipeline Data Source"
sidebar_current: docs-openwebui-data-source-pipeline
description: |-
  Retrieves pipeline details from Open WebUI.
---

# openwebui_pipeline (Data Source)

Fetches a pipeline by ID or URL.

## Example Usage

### Minimal

```hcl
data "openwebui_pipeline" "remote" {
  pipeline_id = "pipeline-123"
}
```

### Full

```hcl
data "openwebui_pipeline" "remote" {
  url     = "https://example.com/pipelines/support.zip"
  url_idx = 1
}
```

## Argument Reference

* `pipeline_id` (Optional) – Pipeline identifier to retrieve.
* `url` (Optional) – Pipeline URL to look up when `pipeline_id` is not provided.
* `url_idx` (Optional) – Pipeline URL index (defaults to `0`).

## Attribute Reference

* `id` – Unique pipeline identifier.
* `details_json` – Raw JSON describing the pipeline returned by the API.
