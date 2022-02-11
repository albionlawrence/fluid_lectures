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
and $v_g = \frac{1}{2} \sqrt{\frac{g}{k}}$. So long-wavelength modes propagate more qucly than short-wavelength modes.
We can see this in the atmosphere in the satellite picture of the Tonga explosion that we saw earlier.

Another limit is "shallow water", in which $kh \ll 1$, so the wavelength is long compared to the height. This is often
an important limit in both the linear and nonlinear problem, in part as planetary fluids have important motion on scales larger
than the fluid depth. In this limit, $\omega^2 = gh k^2$, so the phase and group velocity are $v = \sqrt{gh}$,
and the waves are nondispersive: Gaussian wavepackets will remain Gaussian and not spread. The pressure wave
you see in the Tonga explosion viseo has the same dispersion relation (with $c$ = speed of sound).

## Solutions and their properties

Given the above, we have found that oscillatory solutions take the form:

$$
	\phi = C \cos(\omega(k) t - kx - \delta) \cos(k(z + h))
$$

where $\delta$ is an arbitrary phase. We can now write the physical variables as:

\begin{align}
	\zeta & = & - \frac{1}{g} \partial_t \phi = C\frac{\omega}{g} \sin(\omega t - k x - \delta) \cosh[k(z + h)] \\
	v_x & = & \partial_x \phi = C k \sin(\omega t - k x - \delta) \cosh[k(z + h)] \\
	v_z & = & \partial_z \phi = C k \cos(\omega t - k x - \delta) \sinh[k(z + h)]
\end{align}

Note the nontrivial phase relations. At the crests (at fixed $z$), $\zeta$ is maximal when $v_x$ is positive and minimal 
when $v_x$ is negative, while $v_z$ will as expected vanish here. 

With this we can test he validity of the linear regime. This will hold when the advective term ${\vec v} \cdot {\vec\nabla} {\vec v}$
is small compared to linear terms such as ${\dot {\vec v}}$. The latter $\sim \omega C k$; the former $\sim C^2 k^3$. Thus,

$$
	C^2 k^3 \ll C \omega k \Rightarrow \frac{\omega}{k} = c_p \gg C k \sim |{\vec v}|
$$

In other words ${\vec v}$ must be small compared to the phase velocity. 

## Lagrangian picture

It is worth understanding what individual particles are doing in this flow. For this, we would like to solve the
equations:

\begin{align}
	{\dot x}(t) & = & v_x = C k \sin(\omega t - k x - \delta) \cosh[k(z + h)] \\
	{\dot z}(t) & = & v_z = C k \cos(\omega t - k x - \delta) \sinh[k(z + h)]
\end{align}

These are horribly nonlinear, even though the underlying equations are linear. However, we are
assuming ${\vec v}$ is in some sense small, in that $C k^2/\omega \equiv \epsilon \ll 1$. 
We will write ${\vec x} = {\vec x}_0 + \epsilon {\vec x}_1 + \epsilon^2 {\vec x}_2 + \ldots$, where
${\vec x_0}$ is a constant. We will also write
and $v_x = \epsilon \omega/k \sin(\omega t - k x - \delta) \cosh[k(z + h)]$, and similarly for $v_z$.

Now expanding the Lagrangian particle equations in powers of $\epsilon$, we find to lowest order:

\begin{align}
	{\dot x}_1 & = & \frac{\omega}{k} \sin(\omega t - k x_0 - \delta) \cosh[k(z_0 + h)]\\
	{\dot x}_1 & = & \frac{\omega}{k} \cos(\omega t - k x_0 - \delta) \sinh[k(z_0 + h)]\\
\end{align}

With a bit of algebra, we find that to this order,

$$
	\frac{(x - x_0)^2}{\cosh^2(k(z_0 + h))} + \frac{(z - z_0)^2}{\sinh^2(k(z_0 + h))} = \frac{\epsilon^2}{k^2}
$$

This is the equation for an ellipse. In the deep water limit, with $k (z_0 + h) \gg 1$, the hyberbolic functions
become exponentials and we get a circle:

$$
	(x - x_0)^2 + (z - z_0)^2 = \frac{\epsilon^2}{k^2} e^{- k(z_0 + h)}
$$

Thus, even though the=is "monochromatic wave" wave may be moving at the phase velocity,
to lowest order the particles are just moving in circles. which get smaller at depth.

It is worth at least mentioning the effects of the next order corrections. At this point the above equations are
not in fact technically adequate as at order $\epsilon^2$, the nonlinear term in Euler's equations will also 
contribute. However, in the deep water limit this ends up no contributing. 
Since we are looking at inviscid flow, we can use Bernoulli's theorem

$$
	\partial_t \phi + \frac{1}{2} {\vec v}^2 + g z + \frac{p}{\rho} = 0
$$

together with the boundary conditions. We would expand $\phi, \zeta, p$ in $\epsilon$, and the first 
nonlinear correction appears at order $\epsilon^2$. This has the form

$$
	\partial_t \phi_2 + \frac{p_2}{\rho} + \frac{1}{2} \left({\vec v}_1\right)^2 + {\vec v}_2 \cdot
	{\vec v}_0 + g z = 0
$$

Since ${\vec v^{(0)} = 0$ we have the same equation as for $\phi_1,{\vec v}_1$, but with the term  
$\frac{1}{2} \left({\vec v}_1\right)^2$. Next, as before we work at $z = \eta$, 
expanding $\eta = \epsilon \zeta_1 + \epsilon^2 \zeta_2 + \ldots$. Solving 
the boundary cunditions order by order we have $\partial_t \zeta_k = \partial_z \phi_k$.

At the surface we have

$$
	\partial_t \phi_2 + \frac{p_2}{\rho} + \frac{1}{2} \left({\vec v}_1\right)^2 + g \zeta_2 = 0
$$

Taking the time derivative of this equation, and imposing the boundary conditions, we get

$$
	\partial_t^2 \phi_2 + \frac{p_2}{\rho} + {\vec v}_1\cdot {\dot {\vec v}_1} + g \partial_z \phi_2  = 0
$$

Now let us work in the deep water limit, replacing the hyberbolic funvtions in ${\vec v}_1$ with exponentials, 
we find that the nonlinear term $v_x {\dot v}_x + v_z {\dot v})z = 0$. Thus the second order solutions solve the same
equations as the first order solutions, and we can to this order maintain the form of the velocities and Lagrangian
trajectories.

This still leaves us with solving the equations for ${\vec x}_2$. Expanding the Lagrangian equations for ${\vec x}$
to order $\epsilon^2$, we find:

$$
	{\dot x}_2 & = & - \frac{\omega}{2 k} x_1 \cos(\omega t - k x_0) e^{k(z_0 + h)} 
	+ \frac{\omega}{2k} z_1 \sin(\omega t - k x_0) e^{k(z_0 + h)}\\
$$

and similarly for $z_2$. Now inserting the first order solutions in, we find

$$
	{\dot x}_2 = \frac{\omega}{2k} e^{2 k (z_0 + h)}
$$

So we get a constant drift at this order, known as the *Stokes drift*, which is extremely important in
understanding transport of particles by waves.
