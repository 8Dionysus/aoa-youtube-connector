# aoa-youtube-connector

Policy-gated YouTube evidence and publication-plan connector for AoA.

Phase 0 is an offline, policy-first skeleton. It makes no live API calls,
contains no credentials, and cannot publish content.

## Owned here

- YouTube-specific source policy and capability discovery
- normalized evidence-packet and publication-plan contracts
- provider-specific parsing, preparation, validation, and local decisions
- a fail-closed local CLI and repository validator

## Owned elsewhere

- cross-network campaign orchestration and editorial policy
- live MCP/HTTP composition, scheduling, queues, retries, and secret injection
- final publication authority and operator approval
- heavy captures, media, indexes, and generated corpora

## Current boundary

Public metadata is distinct from owner-only analytics and captions. Uploads require OAuth, resumable transfer, processing-state observation, and current project-audit checks; Community posts are not assumed to be API-publishable.

Official documentation: https://developers.google.com/youtube/v3/

API terms, scopes, quotas, review requirements, and pricing can change. Recheck
the official documentation before implementing or admitting a live adapter.

## Bootstrap checks

```bash
python -m pip install -e ".[dev]"
python scripts/validate_connector.py
ruff check .
pytest
aoa-youtube doctor --json
```

A green bootstrap proves only the source skeleton. It does not prove API access,
OAuth, deployment, publication, or consumer acceptance.
