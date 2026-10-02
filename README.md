# Geometry and Topology of Data — 2026

Course materials for students of **Geometry and Topology of Data** (Topologiczna Analiza Danych).

## Repository structure

```
.
├── Lectures/          # materials from lectures (slides, interactive demos)
│   └── lecture1/
├── Labs/              # lab assignments (Jupyter notebooks)
├── pyproject.toml     # Python environment definition (uv)
├── uv.lock            # exact, reproducible package versions
└── requirements.txt   # the same package list, for reference / plain pip
```

- **Lectures** — supplementary materials for each lecture, e.g. interactive HTML demos
  (open them directly in a web browser).
- **Labs** — lab assignments as Jupyter notebooks. Work on them inside the course
  environment described below.

## Setting up the environment

The environment is managed with [uv](https://docs.astral.sh/uv/) and uses **Python 3.11**
(some TDA packages with C++/Cython extensions are not yet compatible with Python 3.12+).

### 1. Install uv

macOS / Linux:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

(or on macOS: `brew install uv`)

Windows (PowerShell):

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

### 2. Clone the repository

```bash
git clone https://github.com/pdabrowskitumanski/tda_mini_2026.git
cd tda_mini_2026
```

### 3. Create the environment

```bash
uv sync
```

This downloads Python 3.11 if needed, creates a virtual environment in `.venv/`
and installs all packages at the exact versions pinned in `uv.lock`.

> **Note:** `cechmate` depends on `phat`, which is built from source (from GitHub).
> You need a C++ compiler and `git`:
> on macOS run `xcode-select --install`; on Linux install `build-essential` (or equivalent);
> on Windows install "Desktop development with C++" from Visual Studio Build Tools.

### 4. Run JupyterLab

```bash
uv run jupyter lab
```

Alternatively, activate the environment manually:

```bash
source .venv/bin/activate      # macOS / Linux
.venv\Scripts\activate         # Windows
jupyter lab
```

In VS Code, choose the interpreter / kernel located in `.venv`.

### Updating

When new materials are published, pull them and re-sync the environment:

```bash
git pull
uv sync
```

## Main packages

| Area | Packages |
|------|----------|
| Scientific core | numpy, scipy, pandas, matplotlib, seaborn, scikit-learn, jupyterlab |
| Biomolecular data, knots | biopython, topoly, networkx |
| Dimensionality reduction & intrinsic dimension | umap-learn, scikit-dimension |
| Optimal transport, time-delay embeddings | POT, giotto-tda |
| Persistent homology | gudhi, ripser, persim, cechmate, tadasets |
| Mapper | kmapper, plotly |
| Graph curvature | GraphRicciCurvature |
| Topological deep learning | torch, torch-geometric, toponetx, topomodelx |
| Quantum TDA (optional) | qiskit |
