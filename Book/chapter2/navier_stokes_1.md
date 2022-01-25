# Introduction to the Navier-Stokes equation

Recall that the Euler equation

```{math}
:label: Eulerrev
D_t {\vec v} = - \frac{1}{\rho} {\vec \nabla} {\vec v} + \frac{1}{\rho} {\vec F}_{ext}
```

is basically Newton's second law applied to fluid parcels. This was under the assumption that the
force between fluid elements took the form of contact forces. We also expect some kind of frictional
force. We expect that this should depend at least linearly on the velocity, and involve derivatives
of the velocity. 

*A priori* such forces could involve arbitrary powers of the velocity and arbitrary numbers of derivatives
of the velocity. We will assume he velocity is "slow" in some sense that has to be defined -- eg you
need a velocity scale $V$ compared to which it is small -- and the scales over which the velocity varies
are in some sense long, so that higher powers of derivatives are suppressed. Finally, we need this to be
a vector. At linear order in velocity, we could have a *Rayleigh drag* term 
${\vec F}_{drag} = - \lambda {\vec u}$. This can emerge as an approximation to he effects of a fluid
boundary, when the fluid is essentially two-dimensional. But it is clearly not a viscosity, which
we expect to appear when adjacent fluid particles move at different speeds. The next possibility would be
some contraction of $\partial_i \partial_j u_k$. Since we are (for now) considering incompressible fluids,
the only possibility is

$$
	{\vec F}_{viscosity} = \mu \nabla^2 {\vec u}
$$

Here $\mu$ is the *shear viscosity* (for compressible fluids, 
$\lambda {\vec \nabla} ({\vec \nabla} \cdot {\vec u})$ is known as the *bulk viscosity*). If we define
$\nu = \mu/\rho$, $\nu$ is called the *kinematic viscosity*, and appears in the standard presentation of the
*Navier-Stokes equation*:

```{math}
:label: navier-stokes
\frac{\partial}{\partial t} {\vec v} + {\vec v} \cdot {\vec \nabla} {\vec v} = 
	- \frac{1}{\rho} {\vec \nabla} p + \nu \nabla^2 {\vec u} + \frac{1}{\rho} {\vec F}_{ext}
```

Because this equation is second order in space, we need two boundary conditions. We will consider solid boundaries for the time
being. For these, one boundary condition (as we've said) is clearly ${\vec u} \cdot {\vec n} \big|_{boundary} = 0$. 
The standard additional boundary condition is the *no-slip* condition ${\vec u} \cdot {\vec t} = 0$, where ${\vec t}$ is *any* 
vector tangent to the boundary. It is this boundary condition which generates shear for objects in otherwise uniform irrotational flow. 
