---
layout: data-source
page_title: "openwebui_files Data Source"
sidebar_current: docs-openwebui-data-source-files
description: |-
  Lists files in Open WebUI.
---

# openwebui_files (Data Source)

Lists files available to the current user, optionally filtering by filename.

## Example Usage

### Minimal

```hcl
data "openwebui_files" "all" {}
```

### Full

```hcl
data "openwebui_files" "support" {
  filename = "*.txt"
  content  = true
  skip     = 0
  limit    = 100
}
```

## Argument Reference

* `filename` (Optional) – Filename pattern to search for (supports wildcards).
* `content` (Optional) – Whether to include file content metadata (defaults to `true`).
* `skip` (Optional) – Number of results to skip.
* `limit` (Optional) – Maximum number of results to return.

## Attribute Reference

* `files` – List of files matching the query. Each item includes `id`, `filename`, `hash`, `user_id`, `data_json`, `meta_json`, `created_at`, and `updated_at`.
