# County-Level Stochastic SI Modeling of White-Nose Syndrome

Python|NetworkX|GeoPandas|NumPy|Monte Carlo Simulation

## Project Overview

This project explores potential disease spread through a geographic network of U.S. counties using stochastic modeling and Monte Carlo simulation.

Each county is represented as a single node in an undirected graph, with edges representing a geographic border between neighboring counties.

A stochastic Susceptible-Infected (SI) model is implemented to simulate potential disease transmission between adjacent counties. Monte Carlo simulations are used to estimate county-level infection probabilities over a five-step simulation.

This is an exploratory network simulation rather than a validated epimeiological forecast.

## Research Objectives 
 - Construct a nationwide county disease asjacency network using U.S. census data.
 - Implement a stochastic disease-spread model using NetworkX.
 - Conduct 1000 Monte Carlo simulations
 - Estimate county-level infection probabilities over a 5-step timeline simulation.
 - Visualize simulated infection probabilities using Census TIGER/Line geographic boundaries.

## Methodology

### County Network Construction

County adjacency relationships are obtained from the U.S. Census Bureau and represented as an undirected graph via NetworkX.

### Stochastic Disease Model

an SI model estimates infection probability based on the number of neihgboring counties who are infected.

### Monte Carlo Simulation

1000 independent simulations are used to estimate county-level infection probabilities.

### Geographic Visualization

Simulation results are joined to Census county borders using five digit GEOIDs and visualized with GeoPandas.

### Results

The network contains 3225 county equivelant nodes, with 9479 connections across 7 connected components.

The average number of infected counties at the end of a simulated 5 year demonstration was approximately 14.79

### County-Level Simulation Results

See outputs/tables/County_Infection_Probailities.csv

### Technologies

- Python
- Pandas
- NumPy
- NetworkX
- GeoPandas
- Matplotlib
- Seaborn
- Jupyter Notebook

### Running the Project
1. Clone this repository
2. Install the required packages using pip install -r requirements.txt
3. Follow the data setup instructions in data/README.md
4. Launch jupyter from the project root directory
5. Open the notebook in notebooks/
6. Run the notebook cells sequentially

### Model Assumptions and Limitations

- Initial infection locations are hypothetical demonstration conditions
- Transmission probability is an assumed parameter that has not been calibrated against historical WNS spread
- The current model assumes disease spread only occurs between adjacent counties
- Infected counties remain infected until the end of the simulation
- Bat movement, cave density, environmental conditions, and surveillance coverage are note explicitly modeled
- Infection probailities are conditional on the model assumptions and should not be interpreted as validated forecasts.

### Data Sources

- U.S. Census Bureau County Adjacency File, 2026
- U.S. Census Bureau TIGER/Line County Boundaries, 2026

See data/README.md for source links and data instructions