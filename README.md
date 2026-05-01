# Modeling Collective Forgetting in Opinion Dynamics

This repository contains the code used for the final report:

**Modeling Collective Forgetting: Integrating a Forgetting Kernel into Opinion Dynamics Frameworks**

The project extends the classical DeGroot opinion dynamics model by introducing a finite-horizon exponential forgetting kernel. The code supports simulations of the baseline DeGroot model and the forgetting-augmented model under different network structures and initial opinion distributions.

## Repository structure

```text
collective-forgetting-opinion-dynamics/
├── notebooks/
│   ├── 01_main_simulation.ipynb
│   └── 02_results_and_figures.ipynb
├── report_figures/
│   └── figures used in the final report
├── outputs/
│   └── CSV outputs, if generated
├── requirements.txt
├── .gitignore
└── README.md
```

## Main notebooks

### `notebooks/01_main_simulation.ipynb`

This notebook contains the main simulation code for the single-topic forgetting-kernel study. It includes model definitions, network generation, initial condition generation, baseline DeGroot simulation, forgetting-kernel simulation, metric calculation, and hyperparameter tuning.

### `notebooks/02_results_and_figures.ipynb`

This notebook contains the result-output version used for generating report figures and tables. It produces the figures used in the final report, including convergence plots, trajectory gap plots, disagreement plots, per-agent trajectory plots, scenario-level comparison plots, hyperparameter heatmaps, and spectral analysis plots.

## Setup

Create a Python environment and install the dependencies:

```bash
pip install -r requirements.txt
```

The code was developed using Python 3.10+ and standard scientific Python libraries.

## Reproducing the results

To reproduce the reported results:

1. Clone or download this repository.
2. Install the dependencies using `requirements.txt`.
3. Open the notebooks in Jupyter Notebook, JupyterLab, or VS Code.
4. Run `notebooks/01_main_simulation.ipynb` first.
5. Run `notebooks/02_results_and_figures.ipynb` to regenerate report figures and outputs.

All figures are designed to be saved locally by the notebooks.

## Models implemented

The repository includes:

- Classical DeGroot model:
  
  `x(t+1) = W x(t)`
- Finite-horizon exponential forgetting kernel:
  
  `K(tau) = exp(-lambda * tau) / sum_s exp(-lambda * s)`
- Forgetting-augmented update:
  
  `x(t+1) = W * sum_tau K(tau) x(t-tau)`
- Augmented-state representation for spectral analysis.

## Network structures

The simulations include multiple network structures:

- Watts-Strogatz small-world networks
- Erdős-Rényi random networks
- Barabási-Albert scale-free networks

## Initial opinion distributions

The simulations include several initial opinion configurations:

- Normal
- Bimodal
- Skewed

## Evaluation metrics

The notebooks compute several metrics used in the report:

- Convergence time
- Path gap
- Final gap
- Average disagreement
- Change in disagreement
- Impact score
- Spectral comparison of baseline and augmented systems

## Reproducibility notes

The notebooks use a fixed random seed where applicable. Some figures may differ slightly across environments due to plotting backends or library versions, but the qualitative patterns should remain consistent.

## Code availability statement for report

You may include the following statement in the final report:

> The code used to generate the simulations and figures in this report is publicly available at: **[insert GitHub repository URL here]**. The repository contains the notebooks, dependency file, and instructions required to reproduce the reported results.

## Author

Dejia Lancelot Dong
