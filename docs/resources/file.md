---
layout: resource
page_title: "openwebui_file Resource"
sidebar_current: docs-openwebui-resource-file
description: |-
  Manages uploaded files in Open WebUI.
---

# openwebui_file (Resource)

Uploads and manages files in Open WebUI.

## Example Usage

### Minimal

```hcl
resource "openwebui_file" "support_doc" {
  source_path = "./docs/support_faq.txt"
}
```

### Full

```hcl
resource "openwebui_file" "support_doc" {
  source_path = "./docs/support_faq.txt"
  metadata_json = jsonencode({
    category = "support"
  })
  process               = true
  process_in_background = true
}
```

## Argument Reference

* `source_path` (Required) – Local path to the file to upload.
* `metadata_json` (Optional) – JSON metadata sent during upload.
* `process` (Optional) – Whether Open WebUI should process the file (defaults to `true`).
* `process_in_background` (Optional) – Whether processing is queued in the background (defaults to `true`).

## Attribute Reference

* `id` – Unique file identifier.
* `filename` – Filename as stored by Open WebUI.
* `hash` – Hash returned by Open WebUI for the file.
* `user_id` – Identifier of the user who owns the file.
* `data_json` – JSON data payload returned by Open WebUI.
* `meta_json` – JSON metadata returned by Open WebUI.
* `created_at` – Unix timestamp of file creation.
* `updated_at` – Unix timestamp of last update.

## Import

Files can be imported by their file ID:

```bash
terraform import openwebui_file.support_doc 65e5e86e-0e23-4cd8-8eee-447c6923f632
```
