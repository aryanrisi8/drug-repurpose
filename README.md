# multimodal-repurpose

An MCP-grounded multi-agent system for rare-disease drug repurposing that co-reasons across knowledge-graph topology, structural binding inference, and literature evidence with calibrated uncertainty scoring.

## Compute and Storage Model

This project is designed for a machine without a local GPU.

- **GitHub** stores code, notebooks, configs, schemas, and small manifests.
- **Google Drive** stores large datasets, generated embeddings, model checkpoints, reports, and candidate tables.
- **Google Colab** runs GPU-heavy notebooks and writes outputs back to Drive.
- **Local Codex workspace** is used for editing, planning, lightweight inspection, and MCP server development.

Large biomedical data files should not be committed to Git.

## First Run

1. Create a GitHub repository named `multimodal-repurpose`.
2. Upload or push this folder to that repository.
3. Create the Drive folders described in [docs/colab_drive_github_setup.md](docs/colab_drive_github_setup.md).
4. Open [notebooks/00_colab_bootstrap.ipynb](notebooks/00_colab_bootstrap.ipynb) in Colab.
5. Run the bootstrap notebook to mount Drive, clone the GitHub repo, install dependencies, and verify GPU availability.

## Week 1 Target

- Pin OptimusKG access/version.
- Create a data manifest.
- Inspect OptimusKG schema.
- Keep Hetionet as a separate benchmark dataset.
- Generate initial graph statistics and a lightweight baseline.
