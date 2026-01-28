---
layout: resource
page_title: "openwebui_code_execution_config Resource"
sidebar_current: docs-openwebui-resource-code-execution-config
description: |-
  Manages Open WebUI code execution configuration.
---

# openwebui_code_execution_config (Resource)

Updates code execution and code interpreter settings in Open WebUI.

## Example Usage

### Minimal

```hcl
resource "openwebui_code_execution_config" "default" {
  enable_code_execution = true
  code_execution_engine = "jupyter"

  enable_code_interpreter = true
  code_interpreter_engine = "jupyter"
}
```

### Full

```hcl
resource "openwebui_code_execution_config" "default" {
  enable_code_execution       = true
  code_execution_engine       = "jupyter"
  code_execution_jupyter_url  = "https://jupyter.example.com"
  code_execution_jupyter_auth = "token"
  code_execution_jupyter_auth_token = var.jupyter_token
  code_execution_jupyter_timeout    = 30

  enable_code_interpreter            = true
  code_interpreter_engine            = "jupyter"
  code_interpreter_prompt_template   = "Use the provided notebook for analysis."
  code_interpreter_jupyter_url       = "https://jupyter.example.com"
  code_interpreter_jupyter_auth      = "basic"
  code_interpreter_jupyter_auth_password = var.jupyter_password
  code_interpreter_jupyter_timeout       = 30
}
```

## Argument Reference

* `enable_code_execution` (Required) – Whether code execution is enabled.
* `code_execution_engine` (Required) – Engine used for code execution.
* `code_execution_jupyter_url` (Optional)
* `code_execution_jupyter_auth` (Optional)
* `code_execution_jupyter_auth_token` (Optional, Sensitive)
* `code_execution_jupyter_auth_password` (Optional, Sensitive)
* `code_execution_jupyter_timeout` (Optional)
* `enable_code_interpreter` (Required) – Whether the code interpreter is enabled.
* `code_interpreter_engine` (Required)
* `code_interpreter_prompt_template` (Optional)
* `code_interpreter_jupyter_url` (Optional)
* `code_interpreter_jupyter_auth` (Optional)
* `code_interpreter_jupyter_auth_token` (Optional, Sensitive)
* `code_interpreter_jupyter_auth_password` (Optional, Sensitive)
* `code_interpreter_jupyter_timeout` (Optional)

## Attribute Reference

* `id` – Singleton identifier for the code execution config.

## Import

Code execution config can be imported with any ID:

```bash
terraform import openwebui_code_execution_config.default code_execution
```
