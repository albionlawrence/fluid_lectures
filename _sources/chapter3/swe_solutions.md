# Shallow water equations 2

```{math}
\newcommand{\p}{\partial}
\newcommand{\half}{\frac{1}{2}}
```

Now that we have discussed the method of characteristics and found
characteristic equations for invariants $u \pm 2c$, we consider two 
applications: the flow caused by a dam break; and the formation of
a tidal bore.

## Dam break 

Consider, for $t <0$, a static situation wth water at constant height $h_0$
for $x < 0$, behind a dam at $x = 0$, and no water for $x > 0$. Then
we remove the dam and let the water begin to flow.

For $t < 0$ the characteristics are quite simple: $c_0 = \sqrt{g h_0}$, so
$\p_s t = 1$, $\p_s x = u \pm c_0$ are the characteristics along which
$u \pm 2 c_0$ are constant. Note that $u = 0$, so that 

$$
	d_t x = u \pm c_0 = \pm c_0
$$

are the characteristics: these are straight lines covering the 
quadrant $x < 0, t < 0$.

Now let us release the dam at $t = 0$. For $t < 0$ the characteristics 
remain the same. As they emerge, the will not remain straight. However, on the
characteristic cuves $C_{\pm}$, the invariants $\Gamma_{\pm} = u \pm 2c$ remain
invariant as we continue each beyond $t > 0$; that is, 
$\Gamma \pm 2 c = \pm 2 c_0$. If we follow two such charateristics $C_{\pm}$
which did not meet for $t < 0$, we expect that they begin to curve for $t > 0$.
If they meet at some later point $P$, then $u - 2 c = - 2 c_0$, 
$u + 2c = 2 c_0$, so that it is still true that $u = 0$, $c = c_0$. This is
a consistent solution, so we take it to be true, and we can continue the 
straight characteristics through to $t > 0$. 

This will break down for the characteristic $C_-$ emerging 
from $t = x = 0$, which is described by $x = - c_0 t$.
Beyond this, the $C_+$ charateristics will emerge and may
begin to (and indeed do) curve. Along these we will continue
to find $u + 2 c = 2 c_0$ for any charateristic. Negative charateristics
meeting these will solve $u - 2c = k$ for some constant $k$, so that
where these charateristics meet, $u = c_0 + k/2$, $c = \frac{1}{4}(2 c_0 - k)$.
In other words, $u, c$ are constant, and 

$$
	d_t x = u - c = \half c_0 + \frac{3 k}{4}
$$

These are straight lines determined by $k$.
In order that they do not cross for $t > 0$ which would ensure an
inconsistancy, they must emanate
from the origin. Along these characteristics, then, $x = (u - c) t$ or 
$u - c = x/t$. If we combine with $u + 2c = c_0$, we find by subtracting 
these to find $c$, or adding a linear combination to find $u$,

\begin{align}
	& & c = \frac{1}{3} \left(2 c_0 - \frac{x}{t}\right)\\
	& & u = \frac{1}{3} \left(c_0 + 2 \frac{x}{t}\right)
\end{align}

Since $c$ cannot be negative, we must have $x \leq 2t$. Therefore,
using $h = c^2/g$, 

\begin{align}
	& & h = h_0 \qquad x < - c_0 t\\
	& & h = \frac{1}{9g} \left(2 c_0 - \frac{x}{t}\right)^2 \qquad
	- c_0 t \leq x  \leq 2 c_0 t \\
	& & h = 0 x >  2c_0 t
\end{align}

where $c_0 = \sqrt{h_0 g}$. 

## Nonlinear distortion

By plotting out the solution, it should be clear that the discontinuity
smooths out with time (though there will be a kink at $x = - c_0 t$). 
This is the result of the nonlinearity of the problem. Following the
text, let us consider the $x \in [- c_0t, 2 c_0 t]$. Starting with
$(\p_t + (u - c) \p_x) (u - 2c) = 0$, and using $u + 2 c = 2 c_0$ 
in this region, we find

$$
	\p_t c + (2 c_0 - 3c) \p_x c = 0
$$

Defining $z = 3c - 2 c_0$, this becomes

$$
	\p_t z - z \p_x z = 0
$$

This is a nonlinear equation whose general solution is the implicit one:

$$
	z = F(x + zt)
$$

for any function $F$.

Now at $t = 0$, $z = z(0) = F(x)$. Just after $t = 0$, say at $t = \epsilon$,
$h$ (and thus $z$) is strongly decreasing across $x = 0$. At some later $t$, 
the same value of $z$ which was at $x_0$ for $t = 0 + \epsilon$ occurs at 
$x = - t z$. Larger values of $z(\epsilon)$ and thus of $h(\epsilon)$ 
propagate to the left more quickly, leading to a nonlinear distortion of the
initial step.

Note that if we had the equation $\p_t z + z \p_x z = 0$, the general solution
would have been $z = F (x -  zt)$, and distortions would have traveled to
the right with larger $z$ traveling faster. If the initial configuration
had $z$ *decreasing* to the right, we would get the wave pilong up
on itself, with $\p_x z = F'(x - zt) - t \p_x z F'(x - zt)$ or

$$
	\p_x z = \frac{F'(x - zt)}{1 + t F'(x - zt)}
$$

This first becomes steepest at the maximum negative slope of $F$, determined
by the maximum $F_0$ at $t = 0$, $t = - 1/F_0$.

## Bore

We now consider the opposite case. For $x > 0$, we begin for $t < 0$
with a fluid at rest, at height $h_0$. for $t > 0$, we begin moving the 
dam to the right with an *accelerated* speed $U = \alpha t$, 
so that there is no fluid when $x < \half \alpha t^2$. 

For $t < 0$, $x < 0$, $u, c = 0$. For $t < 0$, $x > 0$, $u = 0$, $c = c_0$, 
and the two characteristics $C_{\pm}$ are $\p_s t = 1, \p_s x = u \pm c_0$, 
so that $\p_t x = u \pm x_0 = \pm c_0$. 

As we begin to move the dam at $t = 0$, the same argument as above applies. 
The invariants $\Gamma_{\pm} = u \pm 2c = \pm 2 c_0$. If two charateristics
have not met for $t < 0$, we expect them to meet for $t > 0$, at which point,
solving $\Gamma_{\pm} = \pm 2 c_0$ gives $u = 0$, $c = c_0$. This works
up to the positive-slope charateristic $C_+$ which leaves the origin,
$x = c_0 t$. Thus we have water which remains still to the right of 
$x = c_0 t$, and is distorted between $\half \alpha t^2 < x < c_0 t$.
Within this distorted region, we expect the characteristics $C_-$ to continue
(at least close to $x = c_0 t$). For these, $\Gamma_- = u - 2c = - 2 c_0$ still
holds. We can inser this into the equation $[\p_t + (u + c) \p_x](u + 2c) = 0$
to find:

$$
	\p_t u + \left(\frac{3 u}{2} + c_0\right) \p_x u = 0
$$

setting $z = \frac{3 u}{2} + c_0$ and considering the previous section, we find
the general solution:

$$
	u = F\left[x - \left(\frac{3 u}{2} + c_0\right)t\right]
$$

This wil break down at finite time. Now we can find $F$ by imposing boundary
conditions $u(x = \half \alpha t^2) = \alpha t$ which gives

$$
	\alpha t = F(- \alpha t^2 - c_0 t)
$$

We can invert this to find

$$
	F(\xi) = \half \left[- c_0 + (c_0^2 - 4\alpha \xi)^{1/2}\right]^{1/2}
$$

We can now solve for $u$ to find:

$$
	u = - \half(c_0 - \frac{3}{2} \alpha t) + [(c_0 - \frac{3}{2} \alpha t)^2 - 4\alpha(x - c_0 t)]^{1/2}
$$

Using $u = 2(c - c_0)$, 

$$
	c = c_0 - \frac{1}{4}\left(c_0 - \frac{3}{2} \alpha t\right) + \frac{1}{4} 
	[(c_0 - \frac{3}{2} \alpha t)^2 - 4\alpha(x - c_0 t)]^{1/2}
$$

As $t$ gets larger, $c$ is largest at $x = \alpha t$, and decreases to 
$x = c_0 t$ where $c = c_0$, the resting value. When $t = 2 c_0/(3\alpha)$,
the square root has a zero at $x = c_0 t$, and thus becomes singular. The
shallow water equations break down; in practice a sudden jump in height occurs,
called a *bore* or *hydraulic jump*. 

Just for fun, here is a discussion of hydraulic jumps and their uses. Note that
in the tank demonstration a barries is placed downstream of a flowing current. You could imagine being in the rest frame of the current, in which it looks
like te barrier is moving upstream, as in our problem,

<iframe width="560" height="315" src="https://www.youtube.com/embed/7tjf8HWiR3Y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

It is also worth looking more closely at the characteristics in the region
$t > x/c_0$, where $x = c_0 t$ is the bounding characteristic below which
$C_{\pn}$ are intersecting straight lines and $c = c_0$, $u = 0$. First,
the plate itself has the trajectory $x = \half \alpha t^2$, so that 
above the curve $t = \sqrt{2 x/\alpha}$, there is no fluid. 

Now firs consider the characteristic $C_-$ which cross $x = c_0 t$. Along these
characteristics, $u - 2 c = - 2 c_0$. Along characteristics $C_+$ emanating
from the wall trajectory, we have $u + 2c = {\rm constant)$, so that
$u, c$ remain constant along any trajectory $C_+$ in this region. At the
point $C_+$ hits the wall,  $u = d_t x = \alpha t_1$; 
$u - 2 c = c_0$ along any characteristic $C_+$ so 

$$ 
	c = \half u + c_0 = \half \alpha t_1 + c_0
$$

Now along $C_+$, $\p_s t = 1 \Rightarrow t = s$, and

$$
	\p_s x = d_t x = (u + c) = c_0 + \frac{3}{2} \alpha t_1
$$

Finally, setting he initial conditions as $x = \alpha t_1^2$ at $t = t_1$, 
we have

$$
	x = \half \alpha t_1^2 + \left(c_0 + \frac{3}{2} c_0 t_1 \right)(t - t_1)
$$

Note that this means $x$ increases *more quickly* than $c_0 t$, and the
curve $C_+$ will eventually cross $x = c_0 t$. When this happens, because
$u, c$ ar econstant along these charateristics, but differ between
characteristics, we get a singularity and the equations break down.

Said another way, the formation of a singularity in the flow -- a shock or some
oter breakdown of the quations at hand -- occurs when two charateristics in
a family $C_i$ cross; since the Riemann invariant $\Gamma_i$ varies within
this family, the solution becomes multivalued at this point.

## Hydraulic jumps

![hydraulic](hj_pic.jpeg) 

*Image from Wikipedia entry on hydraulic jumps*

In general a hydraulic jump occurs when a thin layer of fluid flows towards a
a thicker layer; alternatively, by working in a moving frame, the 
thicker layer could be pushed towars the thinner one, as above. At the jump the
shallow water equations will break down; fully turbulent flow is activated,
and acts to dissipate energy. This being said, we can learn a bit about 
the jump within the shallow water approximation, assuming it holds on each side
of the jump, by demanding mass and momentum are conserved; and that the jump
region dissipates energy, so that the fluid loses energy as it propagates
through the shock. 

We take the flow upstream from the jump to have velocity $U_1$ and 
height $h_1$, and downstream from the jump to have velocity $U_2$ and
heig $h_2$. The density is constant throughout. 

A dimensionless number which helps characterize shallow water flow is
the *Froude number*, the ratio of the fluid velocity to the speed
of surface waves:

$$
	 Fr = \frac{U}{\sqrt{g h}}
$$

This is an analog of the Mach number (velocity
compared to the speed of sound waves) an indeed flow with $Fr < 1$ is called 
*subcritical* while flow with $Fr > 1$ is called *supercritical*.

1. *Mass conservation*. We demand that the mass flux entering the jump is equal
to that leaing the jump. The mass per unit area upstream is $h_1 \rho$ and
downstream is $h_2 \rho$, and the mass flux on each side is $U_i h_i \rho$, so
we demand

$$ 
	U_1 h_1 = U_2 h_2
$$

2. *Momentum conservation*. We demand that the *flux* of momentum into the jump
is equal to that out of the jump, that is, that momentum is no lost in the
jump. Momentum flux gets two contributions in this case. The first
is the direct transport of momentum by the flow. That is, if the momentum per
unit area is $\rho h_i U_i$, the momentum *flux* is $\rho h_i U_i^2$.
Newton's second law ${\dot p} = f$ also tells us that momentum flux
will get a contirbution from any force acting on the fluid. In this case
it will be the pressure, which on each side of the jump is

\begin{align}
	\int_0^{h_i} dy p_i & = \int_0^{h_i} dy \rho g (h_i - y)\\
	& = & \rho g h_i^2
\end{align}

Combining these, and factoring out the common factor of $\rho$, we have

$$
	\half g h_1^2 + h_1 U_1^2 = \half g h_2 + h_2 U_2^2
$$

3. *Energy should be dissipated*. As you are asked to show in problem (3.20),
the rate of energy loss hrough the jump is

$$
	{\dot E} = \frac{\rho g U_1 (h_2 - h_1)^3}{h_2}
$$

From these equations we can quickly deduce a few aspects of the flow.
First, the demand that the energy dissipation be positive means
that $h_2 > h_1$, si that the system jumps upwards.

Secondly, the Froude numbers upstream of and downstream from 
the jump can be written entirely in terms of $h_i$, using
mass an momentum conservation:

\begin{align}
	Fr_1 & = & \frac{U_1}{\sqrt{g h_1}} = 
	\sqrt{\frac{h_2(h_1 + h_2)}{2 h_1^2}}\\
	Fr_2 & = & \frac{U_2}{\sqrt{g h_2}} =
	\sqrt{\frac{h_1(h_1 + h_2)}{2 h_2^2}}
\end{align}

Since $h_1 + h_2 > 2 h_1$, we have

$$
	F_1 > \sqrt{\frac{2 h_1 h_2}{2 h_1^2}} = \sqrt{\frac{h_2}{h_1}} > 1
$$

Similarly, using $h_1 + h_2 < 2 h_2$,

$$
	F_2 < 0
$$

So the flow transitions across the jump from supercritical to subcritical.



