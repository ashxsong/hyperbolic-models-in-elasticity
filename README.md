# Hyperbolic Models in Elasticity
This code computes the solutions to certain partial differential equations involved in the deformation of solid objects under externally acting forces. In particular, assuming the deformation is small, the 1-dimensional balance of momentum equation in $t$ and $x$ becomes

$$\partial_t^2 u - c^2 \partial_x^2 u = 0,$$

which is simply the 1-dimensional wave equation. First, the 1-dimensional wave equation can be rewritten as the following system of first-order partial differential equations:

$$\partial_t u + \partial_x v = 0,$$

$$\partial_t v + c^2 \partial_x u = 0.$$

The forward Euler time-stepping scheme with central differences for the interior and one-sided differences for the endpoints can be implemented to solve this. Additionally, reflecting boundaries can be included by setting $v = 0$ after every time step.

Next, a stabilization term can be added to get that

$$\partial_t u + \partial_x v - \epsilon \Delta u = 0,$$

$$\partial_t v + c^2 \partial_x u - \epsilon \Delta v = 0,$$

where $\epsilon = c_\text{stable} h^2$ and $c_\text{stable}$ is a real number chosen between $1$ and $32$.

Now, we consider the 1-dimensional nonlinear balance of momentum equation in $t$ and $x$, which is

$$\partial_t^2 u - c^2 \partial_x \left\\{(1 + \partial_x u)\left(\partial_x u + \frac{1}{2} (\partial_x u)^2\right)\right\\} = 0.$$

This equation can be rewritten as the following system of first-order partial differential equations:

$$\partial_t u + \partial_x v = 0,$$

$$\partial_t v + c^2 (1 + \partial_x u)\left(\partial_x u + \frac{1}{2}(\partial_x u)^2\right).$$



