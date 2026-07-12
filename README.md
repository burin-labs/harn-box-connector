# harn-box-connector

Pure-Harn Box connector for file artifact workflows.

The surface is deliberately connector-shaped, not document-renderer shaped:

- Normalize signed Box V2 webhook deliveries into Harn connector events.
- Poll the Box Events API from Harn-managed `stream_position` state.
- Dispatch common Box file, folder, event, representation, upload, and webhook
  APIs through allowlisted egress descriptors.
- Build deterministic request descriptors for artifact export/import flows.

Document rendering and manifest vocabulary stay in `harn-documents`; this
package owns the external Box boundary.

## Provider

- Provider id: `box`
- API hosts: `api.box.com`, `upload.box.com`
- Recommended app permissions for artifact workflows:
  - read/write files and folders
  - manage webhooks

## Useful methods

- `files.get`
- `files.content`
- `files.representations`
- `folders.items`
- `events.get`
- `files.upload`
- `webhooks.create`
- `webhooks.delete`
- `webhooks.list`
- `artifact.export_request`
- `artifact.import_request`

## References

- Box API reference:
  <https://developer.box.com/reference>
- Box Events:
  <https://developer.box.com/reference/get-events>
- Box Webhooks:
  <https://developer.box.com/guides/webhooks>
- Box webhook signatures:
  <https://developer.box.com/guides/webhooks/v2/signatures-v2>
- Box PDF representations:
  <https://developer.box.com/guides/representations/pdf>

## Validation

```sh
harn connector test . --provider box
```

The smoke tests use Harn HTTP mocks and do not call Box APIs.
