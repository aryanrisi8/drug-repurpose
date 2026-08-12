# Colab, Drive, GitHub, and MCP Setup

## Recommended Layout

Use GitHub for reproducible code and Drive for large state.

```text
Google Drive/
└── multimodal-repurpose/
    ├── data/
    │   ├── raw/
    │   │   ├── optimuskg/
    │   │   └── hetionet/
    │   ├── interim/
    │   ├── processed/
    │   └── manifests/
    ├── artifacts/
    │   ├── embeddings/
    │   ├── models/
    │   └── checkpoints/
    ├── reports/
    └── runs/
```

The GitHub repo should contain source code, notebooks, configs, documentation, schemas, and small manifests only.

## Colab Workflow

1. Open Colab.
2. Select a GPU runtime when needed.
3. Mount Google Drive.
4. Clone or pull the GitHub repo.
5. Install dependencies inside the Colab session.
6. Read large files from Drive.
7. Save generated datasets, embeddings, and model outputs back to Drive.
8. Commit only code/config/manifest changes to GitHub.

## MCP Placement

MCP servers do not need a GPU. Keep them lightweight and reproducible.

Recommended split:

- Local or cloud-hosted MCP servers expose tools for KG lookup, literature retrieval, and structural evidence lookup.
- Colab notebooks generate heavy artifacts such as embeddings, candidate rankings, and structure-derived scores.
- MCP tools should read from stable files, APIs, or databases, not from temporary Colab runtime paths.

For early development, write MCP servers locally in `mcp_servers/` and use small sample files. When stable, point them to Drive-exported artifacts or a hosted database.

## Secrets

Do not commit API keys or tokens.

Use Colab Secrets, environment variables, or a local `.env` file ignored by Git.

Typical secrets later:

- `GITHUB_TOKEN`
- `NCBI_API_KEY`
- `OPENAI_API_KEY`
- Literature or structure database tokens if required

## What Goes Where

```text
GitHub:
- Python package code
- notebooks/*.ipynb
- configs/*.yaml templates
- docs/
- data/manifests/*.json
- schema summaries

Google Drive:
- OptimusKG downloads
- Hetionet downloads
- processed graph tables
- embeddings
- trained models
- candidate rankings
- generated reports

Colab runtime:
- temporary package installs
- short-lived caches
- active GPU jobs
```

## Day 1 Practical Order

1. Initialize GitHub repo.
2. Push this scaffold.
3. Run `notebooks/00_colab_bootstrap.ipynb`.
4. Confirm Drive folders exist.
5. Add OptimusKG download/access details to `data/manifests/optimuskg_manifest.template.json`.
6. Start schema inspection in a new notebook or script.
