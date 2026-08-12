# multimodal-repurpose

**A rare-disease-focused, multi-modal agentic reasoning framework for systematic drug repurposing.**

Of the 7,000+ characterized rare diseases affecting ~300M people globally, fewer than 5% have an FDA-approved therapeutic. `multimodal-repurpose` addresses this gap by orchestrating three complementary evidence modalities — knowledge graph topology, geometric structural binding inference, and real-time literature synthesis — within a single iterative, MCP-grounded agent loop.

## Core Contributions
- 🧬 **Knowledge Graph Reasoning**: Rare-disease-tagged KG (PrimeKG + Hetionet + Orphanet/HPO) with path-based and embedding-based link prediction.
- 🔬 **Structural Binding Module**: Geometric deep learning inference for drug–target affinity, contextualized against disease pathways.
- 📚 **Literature Co-Reasoning Agent**: LLM-driven, tool-grounded literature synthesis to validate and explain hypotheses in real time.
- 🔌 **MCP Tool Abstraction**: Standardized, portable tool-calling layer decoupling the reasoning agent from any specific bioinformatics backend.
- 📊 **Calibrated Confidence Scoring**: Multi-objective, uncertainty-aware ranking that aggregates heterogeneous evidence signals into a single interpretable score.
- 🎯 **Rare-Disease Evaluation Protocol**: Benchmarks beyond AUROC — mechanistic coherence, evidence coverage, and phenotype alignment for sparse, low-degree disease nodes.

## Why This Matters
Existing approaches (KGE/GNN link prediction, structural docking, un-augmented LLM synthesis) each fail rare diseases in isolation — sparse graphs, missing mechanistic context, or hallucination-prone reasoning. This project unifies them into a single, reproducible, evidence-ranked pipeline.

## Status
🚧 Actively under development — Week 1: KG construction & MCP scaffolding.
