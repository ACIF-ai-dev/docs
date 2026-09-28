# Published documentation

This repository is generated from `ACIF-ai-dev/tobuilder-backend` `docs/api/`.
Do not edit here — edits made in the Mintlify web editor are overwritten by the next sync.

Manual sync: `bash scripts/docs-publish-sync.sh docs/api <published-repository-dir> <source-sha>`
Check that the published copy has no `/v1/console` paths: `grep -c '/v1/console' <published-repository-dir>/openapi.json`   # expect 0
Check for OpenAPI drift: `sha256sum docs/api/openapi.json <published-repository-dir>/openapi.json`

Source commit: 6cf37990b3c690ed539edf06d34e0447f11f6292
