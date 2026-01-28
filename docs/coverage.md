---
layout: page
page_title: "OpenWebUI Provider Coverage"
description: |-
  Coverage summary for Open WebUI API resources and data sources.
---

# Coverage Summary

This page outlines which Open WebUI API areas are covered by the provider.

## Resources

* Knowledge bases (`openwebui_knowledge`)
* Knowledge file attachments (`openwebui_knowledge_file`)
* Models (`openwebui_model`)
* Prompts (`openwebui_prompt`)
* Groups (`openwebui_group`)
* Tools (`openwebui_tool`)
* Tool valves (`openwebui_tool_valves`)
* Pipelines (`openwebui_pipeline`)
* Pipeline valves (`openwebui_pipeline_valves`)
* Files (`openwebui_file`)
* Config import (`openwebui_config_import`)
* Admin configs:
  * Connections (`openwebui_connections_config`)
  * Tool servers (`openwebui_tool_servers_config`)
  * Code execution (`openwebui_code_execution_config`)
  * Models (`openwebui_models_config`)
  * Suggestions (`openwebui_suggestions_config`)
  * Banners (`openwebui_banners_config`)
* OAuth clients (`openwebui_oauth_client`)

## Data Sources

* Knowledge (`openwebui_knowledge`)
* Models (`openwebui_model`)
* Prompts (`openwebui_prompt`)
* Groups (`openwebui_group`)
* Tools (`openwebui_tool`)
* Pipelines (`openwebui_pipeline`)
* Files (`openwebui_file`, `openwebui_files`)
* Config export (`openwebui_config_export`)
* Users (`openwebui_user`)
* Tool server verification (`openwebui_tool_server_verify`)

## Notes

* Pipeline list payloads are loosely typed in the OpenAPI spec; the provider preserves them as raw JSON.
* The suggestions config endpoint does not expose a read API, so state is maintained from the last apply.
* Config export/import payloads can contain secrets; treat `config_json` as sensitive.
* OAuth client registration is write-only; state is preserved from the last apply.

## Not Yet Covered

* User-generated content resources such as chats, notes, folders, or evaluations.
* Task automation endpoints (autocomplete, titles, tags, etc.).
* Media generation endpoints (audio, images).
