---
layout: data-source
page_title: "openwebui_file Data Source"
sidebar_current: docs-openwebui-data-source-file
description: |-
  Retrieves file metadata from Open WebUI.
---

# openwebui_file (Data Source)

Fetches a file by ID.

## Example Usage

### Minimal

```hcl
data "openwebui_file" "support_doc" {
  file_id = "65e5e86e-0e23-4cd8-8eee-447c6923f632"
}
```

### Full

```hcl
data "openwebui_file" "support_doc" {
  file_id = openwebui_file.support_doc.id
}
```

## Argument Reference

* `file_id` (Required) – Identifier of the file to retrieve.

## Attribute Reference

* `id` – Unique file identifier.
* `filename` – Filename as stored by Open WebUI.
* `hash` – File hash.
* `user_id` – Owner user ID.
* `data_json` – JSON data payload returned by Open WebUI.
* `meta_json` – JSON metadata returned by Open WebUI.
* `created_at` / `updated_at` – Timestamps.
