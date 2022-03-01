# The Shallow Water System

```{math}
\newcommand{\p}{\partial}
```

The first example we will work with are the *shallow water equations*. These
are simplifications of the Navier-Stokes equation when the height of the 
fluid region is small compared to its length, and they are extremely
important as model equations for planetary oceans and atmospheres.

## The shallow water equations

We begin with he incompressible Navier-Stokes equations with constant density:

\begin{align}
	& \p_t u + u \p_x u + v \p_y u + w \p_z u = - \frac{1}{\rho} \p_x p\\
	& \p_t v + u \p_x v + v \p_y v + w \p_z v = - \frac{1}{\rho} \p_y p\\
	& \p_t w + u \p_x u + v \p_y w + w \p_z u = - \frac{1}{\rho} \p_z p - g\\
	&\p_x u \p_y v + \p_z w = 0
\end{align}

We consider a fluid extending from $z = 0$ to height $h(x,y,t)$ (in general 
we can also work with nontrivial bottom topography, but we will for now 
consider flat bottoms.) The boundary condiions are 

\begin{align}
	w(x,y,0,t) & = 0\\
	w \Big|_{z = h} & = \frac{d}{dt} h(x,y,t) = \p_t h + u\p_x h + v \p_x h
\end{align}

where in the second line we have used he fact that $w$ a the surface 
should be the velocity of a fluid parcel

We first convert the incompressibility condition to an equation for the height
by integrating the former over the entire vertical water column:

$$
	\int_0^h dz {\vec\nabla}\cdot{\vec u} = 0 
	= \int_0^{h} dz (\p_x u + \p_y v) + w(x,y,\eta,t)
$$

where we have used the boundary conditions. Next, we can pull the horizontal
deivatives outside of the integral if we subtract their action on the
integration limits.

$$
	w + \p_x \int_0^{h} dz u + \p_y \int_0^{h} dz v - u \p_x h - v \p_y h = 0
$$

Substituting the top boundary conditions, we have

$$
	\p_t h + \p_x \int_0^{h} dz u + \p_y \int_0^{h} dz v = 0
$$

Next we start to make some approximations. Assuming that characteristic
vertical scales are of order $H$, horizonal scales of order $L$, and time 
scales of order $T$, we set $w \sim H/T$, $u, v \sim L/T$. Thus $w$ is
considerably smaller than $u,v$. There is no reason for the pressure term to
drop out, so we rplace the momentum equation for $w$ with the hydrostatic
condition (we will justify this self-consistently at the end). We can then 
set $\p_z p = - \rho g$, or $p = p_0 + \rho g (h - z)$. The horizontal
momentum equations become, after we drop the terms proportional to u:

\begin{align}
	& \p_t u + u \p_x u + v \p_y u = - g \p_x h\\
	& \p_t v + u \p_x v + v \p_y v = - g \p_y h
\end{align}

Since the right hand side is independent of $z$, we can start with $u,v$
constant in $z$, and it will continue to be so. Then the integrals
in our conservation condition just become multupilication by $h$ and we have

$$
	\p_t h + \p_x (h u) + \p_y (h v) = 0
$$

Note that this appears as a conservation equation much like that of the
density, in the compressible case. We do not impose incompressibility on 
the horizontal velocities; a divergence will be compensated by a change in
heigh, so that the total mass of the fluid is conserved.

These are the *shallow water equations*. Now note that if we consider
the scaling of the momentum equations, then balancing the advective derivative
against the bouyancy forcing we have $u^2 \sim g H$, and matching this to the 
first term, a time scale of $T^{-1} \sim u/L \sim \sqrt{g H}/L$. We then have
$w \sim H/T \sim (H/L) \sqrt{g H} \ll \sqrt{g H} \sim u$, and our
approximations are self-consistent.
