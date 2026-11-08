# County-Level Stochastic SI Modeling of White-Nose Syndrome

Python | NetworkX | GeoPandas | NumPy | Monte Carlo Simulation

## Project Overview

This project explores potential disease spread through a geographic network of U.S. counties using stochastic modeling and Monte Carlo simulation.

Each county is represented as a single node in an undirected graph, with edges representing a geographic border between neighboring counties.

A stochastic Susceptible-Infected (SI) model is implemented to simulate potential disease transmission between adjacent counties. Monte Carlo simulations are used to estimate county-level infection probabilities over a five-step simulation.

The project combines graph theory, probability modeling, computational simulation, statistical analysis, and geographic data visualization using Python

This is an exploratory network simulation rather than a validated epidemiological forecast.

## Research Objectives

* Construct a nationwide county disease adjacency network using U.S. census data.
* Implement a stochastic disease-spread model using NetworkX.
* Conduct 1000 Monte Carlo simulations
* Estimate county-level infection probabilities over a 5-step timeline simulation.
* Visualize simulated infection probabilities using Census TIGER/Line geographic boundaries.

## Methodology

### County Network Construction

County adjacency relationships are obtained from the U.S. Census Bureau and represented as an undirected graph via NetworkX.

### Stochastic Disease Model

An SI model estimates infection probability based on the number of neighboring counties who are infected.

### Model Description

The model uses a county adjacency network constructed from the U.S. Census Bureau's county adjacency data.

A susceptible county's probability of becoming infected depends on the number of its infected neighboring counties:

\[
P\_i(t) = 1 - (1 - \\beta)^{k\_i(t)}
]

Where P\_i(t) is the infection probability for a county (i) at a time step (t).
\\beta is the assumed transmission probability.
k\_i(t) is the number of infected neighboring counties.

The model uses an SI framework, meaning infected counties remain infected throughout the simulation.

### Monte Carlo Simulation

1000 independent simulations are used to estimate county-level infection probabilities.

### Geographic Visualization

Simulation results are joined to Census county borders using five digit GEOIDs and visualized with GeoPandas.

### Results

The network contains 3225 county equivalent nodes, with 9479 connections across 7 connected components.

The average number of infected counties at the end of a simulated 5 year demonstration was approximately 14.79

### County-Level Simulation Results

See outputs/tables/County\_Infection\_Probailities.csv

### Version 0.2: Sensitivity Analysis

Version 0.2 expands on the original model by investigating how different assumed transmission probabilities affect
simulated disease spread.

The sensitivity analysis evaluates five transmission probability values:

* 0.02
* 0.05
* 0.10
* 0.20
* 0.40

Each scenario uses 1,000 Monte Carlo simulations over five simulation time steps.

The analysis calculates:

* Mean number of infected counties at each time step.
* 5th percentile of simulated outcomes.
* 95th percentile of simulated outcomes.
* Geographic distribution of baseline infection probabilities

### Initial Conditions and Assumptions

Two hypothetical counties are used as initial infection locations:

* Autauga County, Alabama (GEOID: 01001)
* Jefferson County, Colorado (GEOID: 08059)

The baseline transmission probability is set at 0.10

These initial locations and transmission parameters are illustrative assumptions, not verified historical WNS detections or calibrated epidemiological estimates.

Each simulation time step represents one model iteration; it has not been assigned a specific calendar duration

### Technologies

* Python
* Pandas
* NumPy
* NetworkX
* GeoPandas
* Matplotlib
* Seaborn
* Jupyter Notebook

### Running the Project

1. Clone this repository
2. Install the required packages using pip install -r requirements.txt
3. Follow the data setup instructions in data/README.md
4. Launch Jupyter from the project root directory
5. Open the notebook in notebooks/
6. Run the notebook cells sequentially

### Model Assumptions and Limitations

* Initial infection locations are hypothetical demonstration conditions
* Transmission probability is an assumed parameter that has not been calibrated against historical WNS spread
* The current model assumes disease spread only occurs between adjacent counties
* Infected counties remain infected until the end of the simulation
* Bat movement, cave density, environmental conditions, and surveillance coverage are note explicitly modeled
* Infection probabilities are conditional on the model assumptions and should not be interpreted as validated forecasts.

### Data Sources

* U.S. Census Bureau County Adjacency File, 2026
* U.S. Census Bureau TIGER/Line County Boundaries, 2026

See data/README.md for source links and data instructions

### Future Developments

Potential future developments include:

* Adding automated tests for model behavior.
* Incorporating historical WNS observations after verifying their definitions and geographic coverage.
* Investigating long-distance transmission pathways.
* Incorporating environmental and habitat-related factors.
* Exploring alternative transmission models.
* Evaluating model behavior under additional parameter combinations.

### Project Status

Version 0.2 - Exploratory stochastic modeling with Monte Carlo sensitivity analysis

