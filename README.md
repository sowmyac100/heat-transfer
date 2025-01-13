# heat-transfer
Setup
Grid Setup:

Creates a 2D grid (temperature) to represent the spacecraft's components.
Each grid cell is a "node" where temperature is tracked.
Grid size, node spacing (dx, dy), and time step (dt) are defined.
Heaters:

Positions of heaters are defined as (x, y) coordinates.
Each heater can turn on or off and adds heat to nearby nodes when on.
Boundary Conditions:

The edges of the grid are kept at a constant ambient temperature (e.g., 20°C).


Simulation Logic
Heater Control Logic (update_heater_logic):

Turns heaters on or off based on the temperature at their location.
Example rule: If a node's temperature is below 40°C, turn the heater on.
Apply Heater Effects (apply_heater_effect):

Creates a heat_source grid, where heat is added only at heater locations when they are active.
Heat Equation Update (step_heat_equation):

Updates the temperature grid for each time step using the heat equation.
Accounts for:
Heat diffusion between neighboring nodes.
Heat input from heaters.
