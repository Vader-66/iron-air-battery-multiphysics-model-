Iron-Air Battery Multiphysics Model

Overview

This project develops a simplified, physics-based Python model to simulate the discharge behavior of an iron-air battery. The model integrates electrochemical performance, oxygen mass transport, and thermal behavior to investigate how operating conditions influence battery performance.

The objective is to build a foundational multiphysics simulation framework that can be expanded through literature-based parameterization, experimental validation, and sensitivity analysis.

Model Components

The model incorporates three coupled components:

1. Electrochemical Model

State-of-charge (SOC) tracking during constant-current discharge

Simplified open-circuit voltage (OCV) relationship as a function of SOC

Butler–Volmer-based activation overpotential

Ohmic voltage losses

Oxygen concentration overpotential and limiting-current estimation

2. Oxygen Mass Transport

Oxygen consumption based on electrochemical reaction stoichiometry

Effective oxygen replenishment through a lumped mass-transfer model

Estimation of oxygen transport limitations during discharge

3. Thermal Model

Approximation of irreversible heat generation from voltage losses

Heat dissipation to the ambient environment

Temperature evolution during battery discharge

Governing Equations

State of charge:

[
\frac{dSOC}{dt}=-\frac{I}{3600Q}
]

Oxygen mass balance:

k_La(C_{O_2,\mathrm{bulk}}-C_{O_2})

\frac{I}{4FV}
]

Thermal energy balance:

\dot Q_{\mathrm{generated}}-\dot Q_{\mathrm{removed}}
]

The coupled differential equations are solved using SciPy's solve_ivp numerical integration function.

Technologies Used

Python

NumPy

SciPy

Matplotlib

Jupyter Notebook

Repository Contents

File

Description

Iron_Air_Battery_Multiphysics_Model.ipynb

Main notebook containing the model, simulation, and visualizations

README.md

Project overview, methodology, and instructions

requirements.txt

Python package dependencies

Getting Started

Clone or download this repository.

Install the required Python packages:

pip install -r requirements.txt

Launch Jupyter Notebook:

jupyter notebook

Open Iron_Air_Battery_Multiphysics_Model.ipynb and run the notebook cells.

Model Assumptions and Limitations

This is an exploratory engineering model. Its parameters are illustrative placeholders and have not been experimentally calibrated or validated.

Key assumptions include:

A simplified, assumed linear relationship between SOC and open-circuit voltage.

Effective Butler–Volmer activation kinetics.

Lumped oxygen mass transport rather than spatially resolved transport through porous electrodes.

A simplified thermal energy balance with lumped heat capacity and heat transfer.

Constant-current discharge under a simplified representation of iron-air electrochemistry.

The model is not intended to reproduce proprietary Form Energy cell designs or predict commercial battery performance.

Future Work

Potential extensions include:

Parameter estimation using literature or experimental discharge data.

Sensitivity analysis across discharge current and operating temperature.

Improved oxygen transport and porous-electrode modeling.

More detailed electrochemical reaction and voltage modeling.

Model validation against published iron-air battery performance data.

Interactive visualization of battery operating scenarios.

Project Status

Initial integrated electrochemical, oxygen mass transport, and thermal simulation implemented. Further parameterization, validation, and performance analysis remain ongoing.
