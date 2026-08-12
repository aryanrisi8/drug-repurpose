# Week 1 Day 1 Checklist

## Goal

Set up OptimusKG access, pin the data version, inspect the schema, and create the initial data manifest while keeping Hetionet separate.

## Checklist

- [ ] Use GitHub repo `https://github.com/aryanrisi8/drug-repurpose.git`.
- [ ] Push this scaffold to GitHub.
- [ ] Create Google Drive project folders using `notebooks/00_colab_bootstrap.ipynb`.
- [ ] Confirm Colab GPU is available for heavy experiments.
- [ ] Identify the exact OptimusKG source, version, access URL, and license.
- [ ] Fill `data/manifests/optimuskg_manifest.json` from the template.
- [ ] Download OptimusKG raw files into Drive, not Git.
- [ ] Inspect node columns, edge columns, entity types, relation types, and provenance fields.
- [ ] Save schema notes under `kg/schema/`.
- [ ] Identify rare-disease identifiers available in OptimusKG.
- [ ] Create a separate Hetionet manifest from the template.
- [ ] Keep Hetionet under the benchmark path only.

## Output Files to Produce

```text
data/manifests/optimuskg_manifest.json
data/manifests/hetionet_manifest.json
kg/schema/optimuskg_schema_summary.md
reports/optimuskg_initial_stats.md
```

## Rules

- Do not commit raw graph data.
- Do not mix Hetionet edges into OptimusKG.
- Record versions, source URLs, access dates, and checksums.
- Label missing evidence explicitly instead of treating missing data as negative evidence.
