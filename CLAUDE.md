# CLAUDE.md

See `AGENTS.md` and the canonical Harn connector authoring guide:

- https://github.com/burin-labs/harn/blob/main/docs/src/connectors/authoring.md

## Provider Notes

- Keep Box API calls scoped to `api.box.com` and `upload.box.com`.
- Prefer least-privilege Box file/folder and webhook permissions for artifact
  workflows.
- Treat Box V2 webhooks as signed item-change events and Box Events API
  cursors as the polling path for durable change processing.
