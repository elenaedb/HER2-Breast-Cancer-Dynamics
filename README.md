# Mathematical Modeling of HER2+/HER2− Breast Cancer Dynamics

### Phenotypic Plasticity, Competition, and Treatment Sequencing

## Project Overview

This project investigates the dynamics of **HER2-positive (HER2+) and HER2-negative (HER2−) breast cancer cell populations** through mathematical modeling, analytical methods, and numerical simulations in Python.

The objective is to understand how differences in proliferation rates, phenotypic plasticity, density-dependent growth, and interpopulation competition influence tumor evolution.

The models are progressively extended to explore the effects of **Paclitaxel, Notch inhibition, combined therapy, and treatment sequencing** on tumor population dynamics.

The analysis combines ordinary differential equations (ODEs), eigenvalue analysis, equilibrium calculations, and numerical integration.

## Mathematical Models

The project develops six interconnected modeling components.

| Model | Description |
|---|---|
| Malthusian Growth | Exponential population growth without density limitations |
| Logistic Growth | Density-dependent growth with a finite carrying capacity |
| Linear HER2 Model | Two interacting phenotypes with proliferation and phenotypic switching |
| Shared Logistic HER2 Model | Two-phenotype dynamics under a shared carrying capacity |
| 4C Competition Model | Asymmetric competition between HER2+ and HER2− populations |
| Therapy and Sequencing Models | Simulated drug effects and alternative treatment schedules |

### Model Parameters

The main parameters include:

| Parameter | Description | Value |
|---|---|---:|
| K₁ | HER2+ proliferation rate | 1.0 |
| K₂ | HER2− proliferation rate | 0.7 |
| K₁₂ | HER2+ → HER2− transition rate | 0.09 |
| K₂₁ | HER2− → HER2+ transition rate | 0.09 |
| C | Reference carrying capacity | 1,000,000 |
| C₁₂ | Competition coefficient: HER2− on HER2+ | 0.4 |
| C₂₁ | Competition coefficient: HER2+ on HER2− | 0.8 |

These values represent model assumptions used to investigate theoretical population dynamics, rather than parameters estimated from patient-level clinical data.

## Numerical Methods

The analysis uses several mathematical and computational techniques:

1. **Ordinary Differential Equations:** Mathematical representation of population growth, phenotypic transitions, competition, and treatment effects.
2. **Analytical Solutions:** Closed-form solutions for classical growth models.
3. **Numerical Integration:** Forward Euler and Runge–Kutta methods (`solve_ivp`, RK45).
4. **Eigenvalue and Eigenvector Analysis:** Investigation of dominant growth modes and long-term phenotype composition.
5. **Equilibrium Analysis:** Calculation of coexistence equilibria under density-dependent competition.
6. **Treatment Simulations:** Numerical comparison of monotherapy, combined therapy, and treatment sequencing strategies.

## Main Results

### 1. Linear HER2 Population Dynamics

The linear two-phenotype model predicts a stable asymptotic population composition determined by the dominant eigenvector.

| Result | Value |
|---|---:|
| Dominant eigenvalue (λ+) | 1.025 |
| Second eigenvalue (λ−) | 0.675 |
| Asymptotic HER2+ proportion | 78.3% |
| Asymptotic HER2− proportion | 21.7% |

Numerical simulations reproduced the analytical asymptotic composition and showed convergence toward the same phenotype proportions under different initial conditions.

### 2. Density-Dependent Growth and Competition

Introducing a shared carrying capacity limits total population growth, while asymmetric competition modifies the equilibrium composition.

| Model | HER2+ proportion | HER2− proportion |
|---|---:|---:|
| Linear model (asymptotic) | 78.3% | 21.7% |
| Shared logistic model (simulation) | 77.9% | 22.1% |
| 4C competition model (analytical equilibrium) | 75.0% | 25.0% |

The competition model predicts a coexistence equilibrium of approximately **882,353 HER2+ cells** and **294,118 HER2− cells** under the selected parameter values.

The numerical simulation approaches this analytical equilibrium, illustrating how competition can modify the long-term composition of heterogeneous tumor populations.

### 3. Treatment Simulations

The competition model was extended to investigate three simplified therapeutic scenarios:

- **Paclitaxel monotherapy:** Additional treatment-induced death affecting HER2+ cells.
- **Notch inhibition:** Treatment-dependent suppression of HER2− proliferation.
- **Combined therapy:** Simultaneous inclusion of both treatment mechanisms.

The simulations investigate changes in total tumor population and phenotype composition during and after drug administration.

### 4. Treatment Sequencing

Three treatment strategies were evaluated:

1. Paclitaxel followed by Notch inhibition.
2. Notch inhibition followed by Paclitaxel.
3. Simultaneous administration of both treatments.

**Simulated Total Tumor Population**

| Treatment Strategy | End of Treatment (t = 7) | Final Observation (t = 20) |
|---|---:|---:|
| Paclitaxel → Notch inhibition | 668,110 | 1,184,826 |
| Notch inhibition → Paclitaxel | 591,937 | 1,190,114 |
| Simultaneous treatment | 404,619 | 1,200,711 |

Under the selected model parameters, simultaneous treatment produced the lowest tumor population at the end of the treatment period.

However, this advantage did not persist at the final observation time. The simulated populations continued to evolve after treatment, highlighting the importance of considering both immediate effects and longer-term dynamics.

These results demonstrate that treatment order and timing can influence theoretical tumor trajectories. They do not establish the clinical superiority of any treatment strategy.

## Interpretation and Limitations

The analysis illustrates how mathematical modeling can provide insights into heterogeneous tumor population dynamics.

The main findings suggest that:

- Phenotypic switching and proliferation differences influence long-term population composition.
- Density-dependent growth and competition modify equilibrium behavior.
- Therapeutic interventions may alter both total tumor size and phenotype distribution.
- Treatment sequencing can produce different short-term and long-term outcomes.

However, several limitations should be considered:

- **Theoretical framework:** The models represent simplified biological mechanisms.
- **Assumed parameters:** Proliferation, competition, and treatment-related parameters are not calibrated against clinical patient data.
- **Simplified treatment dynamics:** Drug effects do not represent complete pharmacokinetic or pharmacodynamic behavior.
- **Deterministic modeling:** Stochastic fluctuations and additional tumor heterogeneity are not explicitly represented.
- **Clinical applicability:** The simulations are exploratory and have not been externally validated.

Further development could involve parameter estimation from experimental data, sensitivity analysis, uncertainty quantification, and validation against observed tumor dynamics.

## Requirements

The project was developed using **Python** and the following libraries:

- `NumPy`
- `SciPy`
- `Matplotlib`

Install the required packages using:

```bash
pip install numpy scipy matplotlib jupyter
```

## How to Run

1. Download or clone this repository.
2. Open `HER2_Breast_Cancer_Modeling.ipynb` in Jupyter Notebook, JupyterLab, or another compatible Python environment.
3. Install the required libraries if necessary.
4. Execute all cells sequentially to reproduce the numerical simulations and visualizations.

The notebook contains the mathematical models, parameter definitions, simulation outputs, and graphical representations.

No external dataset is required.

## Tools and Technologies

Python | Mathematical Modeling | Ordinary Differential Equations | Numerical Simulation | Eigenvalue Analysis | Computational Oncology | Tumor Population Dynamics

