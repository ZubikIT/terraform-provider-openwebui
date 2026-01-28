# Admin OpenWebUI Example

This example focuses on admin-oriented resources: config export/import, OAuth client registration, and tool server verification.

## Usage

1. Copy the contents of `main.tf` into your configuration directory.
2. Provide values for the `openwebui_endpoint` and `openwebui_token` variables.
3. If you want to apply a config import, set `apply_config_import = true`.
4. Supply OAuth client or tool server variables to enable those resources.
5. Initialise and apply:

```bash
terraform init
terraform apply
```
