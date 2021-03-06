# Thin films: adhesion between plates

```{math}
\newcommand{\p}{\partial}
```

As an application of the thin film limit, we consider the force binding
two parallel plates with a thin film of fluid between them. For simplicity,
wwe consider circular disks with radius $a$ separated by a distance 
$h(t)\ll a$, with applied force n the disks
entirely in the $z$ direction and independent of the azimuthal coordinate 
$\theta$ (thus no torque is applied). We can also assume that the 
external pressure is independent of $\theta$. The active velocity
components are $u_r$, $w$, and we expect them to depend only on $r,z,t$. 
We assume that the foce is applied slowly enough that the time derivative
and advectove terms in the Navier-Stokes equation can be ignored, so that
we can work with the creeping flow equations. There is time
dependence, but we will take it as entering solely through the
no-flux boundary conditions as the plates are pulled apart (the separation
of the plates can change with time); this is just as in the other
creeping flow problems we studied. We will justify this condition 
*a posteriori*

Applying the same logic as our Cartesian treatment earlier, $\p_z p \ll \p_r p$
due to the small aspect ration $h/a$. The radial component of the thin
film equations is then:

$$
	\p_r p = \nu \p_z^2 u_r
$$

with $p = p(r,t)$. The game will be to compute the pressure force acting on 
the plates.

Since in our approximation $p = p(r,t)$, we can solve the radial component
of the thin film equations:

$$
	u_r = \frac{z(z-h)}{2\eta} \p_r p
$$

Next, we apply the incompressibility condition ${\vec \nabla}\cdot{\vec u} = 0$.
In cylindrical coordinates, when there is no angular dependence and the
angular velocity vanishes, this means

$$
	\frac{1}{r} \p_r (r u_r) + \p_z w = 0
$$

substituting our solution for $u_r$, integrating from $z = 0$ to $z$
and imposing $w = 0$ at $z = 0$, we have

$$
	w = - \frac{1}{2\eta r} \left(\frac{z^3}{3} - \frac{h z^2}{2}\right)
	\p_r (r \p_r p)
$$

Now apply this at $z = h(t)$.  The no-flux boundary conditions mean that 
$w = d_t h$, and we have:

$$
	\p_r (r \p_r p) = \frac{12 \nu r}{h^3} d_t h
$$

We take $h$ as a given function, so that this equation can be
integrated to find:

$$
	\p_r p = \frac{6\eta r}{h^3} d_t h + \frac{C(t)}{r}
$$

In order to avoid a logarithmically diverging pressure at $r = 0$, 
we take the arbitrary function $C$ to vanish. We integrate again to find:

$$
	p = \frac{3\eta r^2}{h^3} d_t h + D(t)
$$

where $D(t)$ is arbitrary. finally, at the edge of the disk $r = a$, 
we set $p = p_0$ where $p_0$ is he atmospheric pressure. This fixes $D$, so that

$$
	p = p_0 + \frac{3\eta (r^2 - a^2)}{h^3} d_t h
$$

Integrating this over the entire disk, we find that the upward force
exerted by the pressure is:

$$
	F = \int_{r \leq a} d^2 x (p - p_0) = - \frac{3\pi \eta a^4}{h^3} d_t h
$$

This is *negative*, an so an adhesive force. 

We finally should go back and check the cnditions for neglecting 
the time derivative terms. Since the vertical velocity is $w \sim d_t h$, 
the incompressibility condititions give $U \sim \frac{a}{h} d_t h$. 
In addition to requiring $h \ll a$, we require

$$
	Re \frac{h^2}{a^2} = \frac{U a}{\nu}  \frac{h^2}{a^2} \ll 1
$$

which gives $h d_t h \ll \nu$.



