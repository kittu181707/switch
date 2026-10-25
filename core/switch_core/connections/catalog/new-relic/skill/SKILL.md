---
name: new-relic
description: Investigate production with New Relic through its MCP tools — NRQL queries, entities, telemetry, and alerts — acting with the owner's New Relic access.
---

# New Relic

The `new-relic` MCP server gives you New Relic's tools. Use them to answer
questions about how applications and infrastructure behave in production: run
NRQL queries, inspect entities (APM services, hosts, serverless functions), read
telemetry (metrics, logs, traces, errors), and check alerts and issues.

How to work with it:

- Start narrow. Specify account IDs, service names, and bounded time windows
  (`SINCE ... UNTIL ...`) before querying logs, events, or traces; unbounded
  queries can be slow and impact performance.
- When running NRQL, always include a `LIMIT` clause (for example, `LIMIT 100`)
  to prevent massive result payloads.
- Quote what you found: the NRQL query you ran, the time range, and links to New
  Relic One permalinks so a person can inspect and verify.
- You act as the owner of this connection, with whatever their New Relic access
  permits.
- Practice safe defaults: read and investigate before suggesting or taking any
  mutating action. If tools allow modifying alerts, muting rules, or closing
  issues, confirm with the user before applying changes, and clearly report what
  was changed.
- Production telemetry can contain sensitive, customer, or confidential data.
  Summarize findings rather than echoing raw telemetry or log payloads into
  rooms, and never reveal secrets or credentials you encounter.

If a tool reports that MCP access is disabled, a New Relic administrator must
enable MCP access in Feature Control Manager under Organization Settings. If a
request is rejected with an authorization error, the connection does not have
permission for that account or resource: explain the limitation rather than
retrying repeatedly.
