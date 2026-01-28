---
layout: resource
page_title: "openwebui_banners_config Resource"
sidebar_current: docs-openwebui-resource-banners-config
description: |-
  Manages Open WebUI banner configuration.
---

# openwebui_banners_config (Resource)

Updates banners displayed in Open WebUI.

## Example Usage

### Minimal

```hcl
resource "openwebui_banners_config" "default" {
  banners = [
    {
      id          = "maintenance"
      type        = "warning"
      content     = "Scheduled downtime tonight."
      dismissible = true
      timestamp   = 1735689600
    }
  ]
}
```

### Full

```hcl
resource "openwebui_banners_config" "default" {
  banners = [
    {
      id          = "maintenance"
      type        = "warning"
      title       = "Maintenance"
      content     = "Scheduled downtime tonight."
      dismissible = true
      timestamp   = 1735689600
    },
    {
      id          = "launch"
      type        = "info"
      title       = "New Features"
      content     = "Explore the latest updates in the workspace."
      dismissible = false
      timestamp   = 1735693200
    }
  ]
}
```

## Argument Reference

* `banners` (Required) – List of banner objects.
  * `id` (Required) – Banner identifier.
  * `type` (Required) – Banner type.
  * `title` (Optional) – Banner title.
  * `content` (Required) – Banner content.
  * `dismissible` (Required) – Whether the banner can be dismissed.
  * `timestamp` (Required) – Unix timestamp associated with the banner.

## Attribute Reference

* `id` – Singleton identifier for the banners config.

## Import

Banners config can be imported with any ID:

```bash
terraform import openwebui_banners_config.default banners
```
