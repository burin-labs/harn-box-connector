# AGENTS.md

Pure-Harn Box connector for signed webhooks and the Events API cursor.

Shared connector authoring rules live in the Harn guide:

- [Connector authoring guide](https://github.com/burin-labs/harn/blob/main/docs/src/connectors/authoring.md)

Put shared connector guidance in the Harn guide and keep only
provider-specific notes and local hazards here.

`CLAUDE.md` is a symlink to this file. Edit `AGENTS.md` only.

## Provider notes

- Keep API calls scoped to `api.box.com` and `upload.box.com`.
- Use the exact OAuth scopes declared in `harn.toml`; do not replace them with
  broad permission descriptions.
- Treat signed Box V2 webhooks as item-change notifications and the Events API
  cursor as the durable polling path.
