# Published documentation

This repository is generated from `ACIF-ai-dev/tobuilder-backend` `docs/api/`.
Do not edit here — edits made in the Mintlify web editor are overwritten by the next sync.

Manual sync: `bash scripts/docs-publish-sync.sh docs/api <published-repository-dir> <source-sha>`
Check that the published copy has no `/v1/console` paths: `grep -c '/v1/console' <published-repository-dir>/openapi.json`   # expect 0
Check for OpenAPI drift: `sha256sum docs/api/openapi.json <published-repository-dir>/openapi.json`

Source commit: 8dfca76a4281b07dbe0604db70f0cd24cafb462d
