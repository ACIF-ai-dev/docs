# Published documentation

This repository is generated from `ACIF-ai-dev/tobuilder-backend` `docs/api/`.
Do not edit here — edits made in the Mintlify web editor are overwritten by the next sync.

Manual sync: `bash scripts/docs-publish-sync.sh docs/api <published-repository-dir> <source-sha>`
Check that the published copy has no `/v1/console` paths: `grep -c '/v1/console' <published-repository-dir>/openapi.json`   # expect 0
Check for OpenAPI drift: `sha256sum docs/api/openapi.json <published-repository-dir>/openapi.json`

Source commit: 794d9ce5677d69ef0517c829ce146f2f90f1d33e
