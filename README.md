# RNADesignAgent

A tool-first, calibrated multi-agent system for RNA bioinformatics design and
analysis. The language model orchestrates, reviews and reports — every
designed molecule traces to a deterministic generator call, and every
prediction claim is checked against the measured capability of the tool that
produced it.

The system packages 41 scientific tools (20 vendored external repositories)
behind local microservices and exposes them through 11 domain workflows:
mRNA design (CDS and full-length), siRNA and ASO design, sgRNA design, RNA
structure prediction and inverse folding (secondary and tertiary), aptamer
design, RNA–ligand and RNA–protein interaction scoring, and IRES prediction.

## Quick start

```bash
git clone --recurse-submodules https://github.com/xlab-BioAI/RNADesignAgent.git
cd RNADesignAgent/rna_agent_system
pip install -r requirements.txt
PYTHONPATH="$(pwd):$PYTHONPATH" python cli/form_chat.py
```

The CLI walks you through a resource check, workflow selection, automatic
microservice startup and a structured per-workflow form. Three submodules are
pinned to patched forks and several services need manually placed model
weights — see the deployment guide before your first run.

## Documentation

All documentation lives under [`rna_agent_system/docs/`](rna_agent_system/docs/):

| Document | Purpose |
|----------|---------|
| [`docs/README.md`](rna_agent_system/docs/README.md) | Project overview and quick start |
| [`docs/DEPLOYMENT.md`](rna_agent_system/docs/DEPLOYMENT.md) | Full environment setup, weights, compilation, curl examples |
| [`docs/WORKFLOWS.md`](rna_agent_system/docs/WORKFLOWS.md) | The 11 domain workflows in depth |
| [`docs/TOOLS.md`](rna_agent_system/docs/TOOLS.md) | All 41 tools, port registry, microservice notes |
| [`docs/ARCHITECTURE.md`](rna_agent_system/docs/ARCHITECTURE.md) | Seven-layer architecture and core module APIs |

## Benchmarks and data

The benchmark datasets used in the paper are included under
[`rna_agent_system/data/benchmarks/`](rna_agent_system/data/benchmarks/README.md)
(210-task platform benchmark, 31-session process-aware benchmark, and the
mRNA/aptamer target sets). The frozen final-form datasets, the external
anchor sets, the packaged capability map and the model-usage register are
deposited at Zenodo under DOI [10.5281/zenodo.22736194](https://doi.org/10.5281/zenodo.22736194).
See [`docs/README.md` §8](rna_agent_system/docs/README.md) for how to
reproduce a benchmark task through the CLI.

## License

Released under the license in [`LICENSE`](LICENSE).
