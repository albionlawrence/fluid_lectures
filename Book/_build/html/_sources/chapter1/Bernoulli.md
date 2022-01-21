# Bernoulli's Theorem

## 1. Isentropic motion

Here we will make recourse to a bit of thermodynamics. We can define
the *enthalpy* as
```{math}
:label: enthalpy
W = E + p V
```
where $E$ is the inernal energy. Using the first law of thermodynamics,
$dE = T dS - p d V$, where $S$ is the entropy, we find
```{math}
:label: denth
dW = T dS + V dp = T dS + \frac{1}{\rho} dp
```
For "isentropic" fluids, with no input of hea and no heat exchange between
fluid parcels, $dS = 0$ for each parcel, and $\frac{dp}{d\rho} = dW$. Thus
```{math}
\frac{\partial}{\partial t} {\vec v} + {\vec v} \cdot {\vec \nabla}
{\vec v} = - {\vec \nabla} W
```

## 2. Constant density

By the same argument, if $\rho$ is constant, then 

$$
	\frac{1}{\rho} {\vec \nabla} p = {\vec \nabla} \frac{p}{\rho}
$$


## 3. Bernoulli's theorem

Let us consider a velocity field ${\vec v}$ which is constant in time.
In this case, the trajectories of fluid parcels follow the streamlines
of the velocity field. COnsider an isotropic fluid with $H = W$ or a constant
density fluid with $H = p/\rho$. *Bernoulli's theorem* states that
in these cases, $H + \frac{1}{2} {\vec v}^2$ is constant along streamlines.

The proof starts with the vector identity

$$
	{\vec A} \times ({\vec \nabla}\times {\vec B}) = 
	A^i {\vec \nabla} B_i - {\vec A} \cdot {\vec \nabla} {\vec B}
$$

(where we have used Einstein summation notation). Applying this to 
${\vec A} = {\vec B} = {\vec v}$. 

$$
	{\vec v} \times ({\vec \nabla} \times {\vec v}) = 
	\frac{1}{2} {\vec \nabla} {\vec v}^2 - {\vec v} \cdot{\vec \nabla}
	{\vec v}
$$

Applying this to the Euler equation, and taking the case 
$\partial_t {\vec v} = 0$, we find
```{math}
:label: staticeuler
{\vec \nabla} (H + \frac{1}{2} {\vec v}^2) = {\vec v} \times({\vec \nabla}\times{\vec v})
```

Now the RHS is perpendicular to ${\vec v}$ since is a cross product with this
vector, and thus

$$
	{\vec v} \cdot {\vec \nabla}  (H + \frac{1}{2} {\vec v}^2) = 0
$$

But ${\vec v} \cdot {\vec \nabla}$ corresponds precisely to the derivative
along streamlines.

In the case of *irrotational* flow, we can write ${\vec v} = {\vec \nabla \phi}$. In this case,
the right hand side of Equation {eq}`staticeuler` clearly vanishes, and we can state that 
$(H + \frac{1}{2} {\vec v}^2$ is constant throughout the fluid.

Irrotational flows also have a version of Bernoulli's theorem when they are not steady.
In this case ${\vec v} = {\vec \nabla} \psi$, and we can run the same arguments as above to
write

$$
	\partial_t \phi + H +  \frac{1}{2} {\vec v}^2 = constant
$$

and we can set the constant to zero by shifting $\phi \to \phi + (constant t$ wihout changing ${\vec v}$.
