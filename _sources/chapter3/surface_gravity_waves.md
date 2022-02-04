# Surface Gravity Waves

We will open with waves on the surface of a fluid, bounded from above by another 
fluid (think the ocean and atmosphere), in a small-amplitude regime so that we
can linearize the equations of motion about a static configuration with a flat
interface. As with any physical small oscillations, waves arise from a restoring 
force. For surface waves the sources of a restoring force are gravity and surface
tension. Waves whose dynamics are dominated by gravity are called *surface
gravity waves*, while those with dynamics dominated by surface tension are called
*capillary waves*. 

(These are distinct from *gravitational waves* of the kind measured by LIGO!)

## Setup in 2 dimensions

For simplicity we will work in 2 dimensions corresponding to a horizontal and a vertical direction. 
We start by considering a fluid of constant density and finite depth, as shown here:

![Finite depth setup](SGW.png "Basic setup")

We will take the atmospheric pressure to be constant at the fluid interface (pretty good approximation for
ocean waves). We consider small amplitude waves about the basic state $\zeta = 0$, ${\vec v} = 0$, and assume the flow
is *irrotational*: since we are working with the inviscid equations, we are guaranteed this so long as
the initial state at $t = 0$ is irrotational (2d vorticity is conserved along fluid trajectories). 
This means we can consider ${\vec v} = {\vec \nabla}\phi$. Bernoulli's equation (just the Euler equation
for this case) plus incompressibility gives us:

\begin{align}
	& \partial_t \phi +  \frac{p}{\rho} + \frac{1}{2}({\vec \nabla}\phi)^2 + g z = 0 \\
	& {\vec \nabla} \cdot {\vec v} = \nabla^2 \phi = 0
\end{align}

We will assume that the perturbations are in some sense small, in particular that $\zeta \ll h$, and 
To solve this we must further supplement this with boundary conditions. In this case, at $z = - j$ we must have
$v_z = \partial_z \phi = 0$, At the free surface, we demand $v_z = \partial_z \phi = \partial_t \zeta$.
Thus, at the surface where $p = p_0$, we have $p_0 =  - \rho(\partial_t \phi + g \zeta$. Taking the time deivative of
this and using the boundary conditions, we find:

\begin{align}
	& \partial_t^2 \phi + g \partial_z \phi\Big|_{z = \zeta} = 0\\
	& \nabla^2 \phi = 0
\end{align}

We are going to look for solutions which oscillate in $t,x$: that is, they take the form

$$
	\phi(x,z,t) = {\rm Re} \left[ C e^{i k x - \omega(k) t} F(z) \right]
$$

Laplace's equation then gives us $\partial_z^2 F = k^2 F$, which means $F = A e^{kz} + B e^{-kz}$. If we
impose $\partial_z \phi(z = -h) = 0$, some algebra leads to $F = D \cosh k(z + h)$. 

Next, we impose the boundary condition at $z = \zeta$. In general this boundary condition is nonlinear: to be precise we would
set $\partial_t^2 \phi(x,\zeta,t) + g \partial_z\phi(x,\zeta,t)$. We will keep the equation at zeroth order in $\eta$, so that 
$\partial_t^2 \phi(x,0,t) + g \partial_z \phi(x,0,t) = 0$. Plugging our general solution into this, we find that 

$$
	\omega^2(t) = g k \tanh k h
$$

There are two obvious limits here. In the first, $k h \gg 1$, corresponding to wavelengths much shorter than the
fluid depth. This is a "deep water" limit and in this case $\omega^2 = g k$, so that $v_p = \sqrt{\frac{g}{k}}$
and $v_g = \frac{1}{2} \sqrt{\frac{g}{k}$. So long-wavelength modes propagate more qucly than short-wavelength modes.
We can see this in the atmosphere in the satellite picture of teh Tonga explosion that we saw earlier.

Another limit is "shallow water", in which $kh \ll 1$, so the wavelength is long compared to the height. This is often
an important limit in both the linear and nonlinear problem, in part as planetary fluids have important motion on scales larger
than the fluid depth. In this limit, $\omega^2 = gh k^2$, so the phase and group velocity are $v = \sqrt{gh}$,
and the waves are nondispersive: Gaussian wavepackets will remain Gaussian and not spread. The pressure wave
you see in the Tonga explosion viseo has the same dispersion relation (with $c$ = speed of sound).

