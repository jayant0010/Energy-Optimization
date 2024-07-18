# Energy Optimization with Pyomo

## Overview

This project uses Pyomo, a Python-based optimization modeling language, to optimize the use of a battery storage system for minimizing electricity costs over a 24-hour period. The model incorporates parameters for heating demand, cooling demand, solar generation, and electricity prices.

## Model Description

The model aims to achieve the following:

- **Minimize the total cost of electricity** by optimizing grid usage and battery charge/discharge operations.
- **Satisfy heating and cooling demands** at each hour by managing the balance between grid usage, solar generation, and battery discharge.

### Parameters

- `heating_demand`: List of heating demand (in kWh) for each hour.
- `cooling_demand`: List of cooling demand (in kWh) for each hour.
- `solar_generation`: List of solar power generation (in kWh) for each hour.
- `electricity_prices`: List of electricity prices (in $/kWh) for each hour.
- `battery_capacity`: Maximum capacity of the battery (in kWh).
- `battery_max_charge`: Maximum charge/discharge rate of the battery (in kW).
- `battery_initial_charge`: Initial charge of the battery (in kWh).

### Decision Variables

- `grid_usage[t]`: Amount of electricity purchased from the grid at hour `t`.
- `battery_charge[t]`: Amount of electricity charged into the battery at hour `t`.
- `battery_discharge[t]`: Amount of electricity discharged from the battery at hour `t`.
- `battery_level[t]`: Current charge level of the battery at hour `t`.

### Constraints

1. **Energy Balance**: Ensures the battery level is correctly updated considering charging and discharging.
2. **Demand Satisfaction**: Guarantees that the combined supply from the grid, solar generation, and battery discharge meets or exceeds the heating and cooling demands.

### Objective Function

The objective function minimizes the total cost of electricity purchased from the grid over the 24-hour period.

## Installation

To run this project, you need to have Python and Pyomo installed. You can install the required packages using pip:

```bash
pip install pyomo
