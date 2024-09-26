# Model Classification Network (MCN)  
__Manu Jayadharan__  
__Initial date: Sept, 2024__

## About the Project
The Model Classification Network (MCN) is designed for the classification of time series data derived from various dynamical systems.

## ode_models_dictionary
The `ode_models_dictionary` is a collection of ordinary differential equation systems that serve as the training data for our classification approach. This dictionary is structured to facilitate easy access and understanding of various dynamical systems.

### Dictionary Structure:
----------------------
This dictionary contains entries for various dynamical systems. Each key in the dictionary corresponds to the name of a system (e.g., 'Lorenz', 'Van_der_Pol', 'Rössler').

Each system entry is a dictionary with the following structure:

- **DCF_values**: 
  - The first entry represents the type of functions that appear on the right-hand side (RHS), for example, 'Poly' for polynomials, 'Rat' for rational functions, etc.
  - The second entry represents the highest degree of terms appearing on the RHS; for example, for polynomials, a value of 2 means a second-degree polynomial.
  - The third entry represents the number of hidden states.

- **rhs_function**: A lambda function that computes the right-hand side of the ordinary differential equation (ODE) system. It takes the following arguments:
  - `t` (float): The time variable.
  - `y` (list): The state variables of the system.
  - `params` (list): The parameters of the system.

- **parameters**: A list of tuples, where each tuple contains:
  - A list of parameters (list): The parameters for the system.
  - A list of initial conditions (list): The initial conditions for the system.
  - A string description (str): A description of the behavior corresponding to the corresponding pair of parameters and initial conditions. This description can be one of the following:
    - 'chaotic': The system exhibits chaotic behavior.
    - 'cyclic': The system exhibits cyclic behavior.
    - 'fixed point': The system converges to a fixed point.
    - 'NA': The behavior is unknown.
