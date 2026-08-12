# MCP and Colab Notes

Colab is good for GPU jobs, but it is not ideal as a permanent MCP host because runtimes disconnect and URLs change.

Use this pattern:

1. Run heavy graph embedding, structural, or batch literature jobs in Colab.
2. Save stable artifacts to Google Drive.
3. Keep MCP servers small and deterministic.
4. Point MCP servers to stable artifact locations, APIs, or a hosted database.

## Early MCP Servers

```text
mcp_servers/
├── kg_server/
│   └── tools for entity lookup, relation lookup, path retrieval
├── literature_server/
│   └── tools for paper lookup, claim classification, contradiction checks
└── structural_server/
    └── tools for drug-target and protein-structure evidence
```

## Recommended Development Order

1. Start with local file-backed MCP prototypes using tiny sample tables.
2. Validate tool inputs and outputs.
3. Move large generated artifacts to Drive.
4. Later, migrate frequently queried artifacts into SQLite, DuckDB, Neo4j, Postgres, or another hosted store.

## What MCP Should Return

Every evidence-returning tool should include:

- entity identifiers
- relation type
- provenance/source
- evidence category
- confidence or missing-data flag
- timestamp or source date when available

This prevents the agent layer from confusing treatment evidence, side-effect evidence, contraindication evidence, and loose association.
