---
layout: resource
page_title: "openwebui_models_config Resource"
sidebar_current: docs-openwebui-resource-models-config
description: |-
  Manages Open WebUI default model configuration.
---

# openwebui_models_config (Resource)

Updates default model settings in Open WebUI.

## Example Usage

### Minimal

```hcl
resource "openwebui_models_config" "default" {
  default_models = "gpt-4o"
}
```

### Full

```hcl
resource "openwebui_models_config" "default" {
  default_models        = "gpt-4o,custom-rag"
  default_pinned_models = "custom-rag"
  model_order_list      = ["custom-rag", "gpt-4o"]
}
```

## Argument Reference

* `default_models` (Optional) – Default model IDs.
* `default_pinned_models` (Optional) – Default pinned model IDs.
* `model_order_list` (Optional) – Ordered list of model IDs.

## Attribute Reference

* `id` – Singleton identifier for the models config.

## Import

Models config can be imported with any ID:

```bash
terraform import openwebui_models_config.default models
```
