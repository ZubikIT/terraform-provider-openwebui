---
layout: data-source
page_title: "openwebui_user Data Source"
sidebar_current: docs-openwebui-data-source-user
description: |-
  Retrieves user details from Open WebUI.
---

# openwebui_user (Data Source)

Fetches a user by ID or query string.

## Example Usage

### Minimal

```hcl
data "openwebui_user" "support" {
  query = "jim@school.edu"
}
```

### Full

```hcl
data "openwebui_user" "support" {
  user_id = "65e5e86e-0e23-4cd8-8eee-447c6923f632"
}
```

## Argument Reference

* `user_id` (Optional) – Identifier of the user to retrieve.
* `query` (Optional) – Search query used to resolve a user when `user_id` is not provided.

## Attribute Reference

* `id` – Unique user identifier.
* `name` – User name.
* `email` – User email.
* `username` – User username.
* `role` – User role.
* `profile_image_url` – Profile image URL.
* `bio` – User bio.
* `last_active_at` / `updated_at` / `created_at` – Timestamps.
