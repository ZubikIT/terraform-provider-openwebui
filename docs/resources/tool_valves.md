---
layout: resource
page_title: "openwebui_tool_valves Resource"
sidebar_current: docs-openwebui-resource-tool-valves
description: |-
  Manages valve settings for Open WebUI tools.
---

# openwebui_tool_valves (Resource)

Manages valve settings for a tool.

## Example Usage

### Minimal

```hcl
resource "openwebui_tool_valves" "calculator" {
  tool_id = openwebui_tool.calculator.id
}
```

### Full

```hcl
resource "openwebui_tool_valves" "calculator" {
  tool_id = openwebui_tool.calculator.id
  valves_json = jsonencode({
    enabled = true
  })
}
```

## Argument Reference

* `tool_id` (Required) – Tool identifier to configure valves for.
* `valves_json` (Optional) – JSON payload describing valve settings.

## Attribute Reference

* `id` – Identifier of the tool valves resource (mirrors `tool_id`).
* `spec_json` – JSON schema describing available valve settings.

## Import

Tool valves can be imported by tool ID:

```bash
terraform import openwebui_tool_valves.calculator calculator
```
