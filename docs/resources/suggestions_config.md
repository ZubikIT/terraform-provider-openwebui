---
layout: resource
page_title: "openwebui_suggestions_config Resource"
sidebar_current: docs-openwebui-resource-suggestions-config
description: |-
  Manages Open WebUI default suggestions configuration.
---

# openwebui_suggestions_config (Resource)

Updates the default prompt suggestions shown in Open WebUI.

## Example Usage

### Minimal

```hcl
resource "openwebui_suggestions_config" "default" {
  suggestions = [
    {
      title   = ["Support"]
      content = "How can we help you today?"
    }
  ]
}
```

### Full

```hcl
resource "openwebui_suggestions_config" "default" {
  suggestions = [
    {
      title   = ["Support", "FAQ"]
      content = "What can we help you with today?"
    },
    {
      title   = ["Billing"]
      content = "Questions about invoices or subscriptions?"
    }
  ]
}
```

## Argument Reference

* `suggestions` (Required) – List of suggestion objects.
  * `title` (Required) – List of title strings.
  * `content` (Required) – Suggestion content.

## Attribute Reference

* `id` – Singleton identifier for the suggestions config.

## Import

Suggestions config can be imported with any ID:

```bash
terraform import openwebui_suggestions_config.default suggestions
```

## Notes

Open WebUI does not currently expose a read endpoint for suggestions. The provider stores the last applied values in state.
