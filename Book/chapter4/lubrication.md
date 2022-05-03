# Lubrication: sliding between surfaces

```{math}
\newcommand{\p}{\partial}
\newcommand{\half}{\frac{1}{2}}
\newcommand{\eps}{\epsilon}
```

Our last application will be to surfaces sliding past each other 
with a thin film of liquid between them. As you know, the presence
of a fluid can reduce the friction considerably.

If the surfaces are parallel the pressure is uniform and 
there is a frictional force exerted by the fluid, which you have 
worked out in various problem sets (eg the torque on
a rotating disk), computed form the tangential stress. 

However, if the surfaces are not quie parallel, pressure starts to become
important, and in fact will dominate the force on the surfaces. This can be
seen from dimensional analysis. Starting with the thin film equations

\begin{align}
	& 0 = - \p_x p + \eta \p_z^2 u\\
	& 0 = - \p_y p + \eta \p_z^2 v\\
	& 0 = - \p_z p + \eta \p_z^2 w\\
	& 0 = \p_x u + \p_y v + \p_z w
\end{align}

From this the pressure scales as $\eta U L/h^2$. The tangential stress 

$$
	{\vec t} = \eta \left[2({\hat n}\cdot{\vec\nabla} {\vec u} + {\hat n} \times
	({\vec\nabla}\times{\vec u})\right] 
$$

scales as $\eta U/h$ (see the first term, when ${\hat n}$ has a vertical
component, this will be the dominant term). The ratio of this term to the 
pressure term is of order the aspect ration $h/L$; the pressure force 
that is moving the bodies along dominates over the frictional force. The goal
is to work out these pressure forces.

To this end we will proceed by working out a couple of examples.
We will work with effectively 2d problems for simplicity.

## Linearly sliding surfaces

In the first problem we consider a flat plate at $z = 0$ moving at velocity
$U$ over a surface defined by $z = h(x)$. The lateral variation of $h$
will be important to us. The boundary conditions will be $u = U$, $w = 0$
at $z = 0$ and $u = w = 0$ at $z = h$. The fluid will be taken to extend
from $x = 0$ to $x = L$ with constant pressure $p_0$ on each side.

As before, $w \ll u, v$ means that $]p_z p \ll \p_{x,y} p$ so we assume
the pressure is independent of $z$. Then we can solve for the first of
the thin-film equations to find:

$$
	u = \frac{z^2}{2\eta} \p_x p + A z + B
$$

Demanding $u = U$ at $z = 0$ gives $B = U$. Demanding $u = 0$ at $z = h$ gives

$$ A = - \frac{U}{h} - \frac{h}{2\eta} \p_x p $$

Thus

\begin{align}
	u & = \frac{z (z - h)}{2\eta} \p_x p + \frac{U}{h}(h - z)\\
	& = \left[\frac{U}{h} - \frac{z}{2\eta} \p_x p\right](h -z)
\end{align}

We next apply the incompressibility condition. Integrating this over
a slice of constant $x$, the integral over $\p_z w$ vanishes as it is
a total derivative with vanishing boundary tems (due to the boundary
conditions on $w$. The remaining term is

$$
	\int_0^h(x) \p_x u = 0
$$

If we pull $\p_x$ out of this integral, we get 

$$
	\p_x \int_0^h(x) \p_x u - \p_x h u(x,z-h) = \int_0^h(x) \p_x u = 0
$$

because the boundary term vanishes. The upshot is that

$$
	Q = \int_0^h(x) \p_x u\ ,
$$

the flux of fluid through any vertical section, is the same for all $x$. We
can compute $Q$ from our solution:

$$
	Q = \half U h - \frac{h^3}{12\eta} \p_x p
$$

Given this, we have a differential equation for $p$:

$$
	\p_x p = 6\eta \left[\frac{U}{h^2} - \frac{2 Q}{h^3}\right]
$$

We integrate this with the boundary condition that $p = p_0$ at $x = 0$,
so that 

$$
	p - p_0 = 6\eta \left[ U \int_0^x \frac{dx'}{h^2(x')}
		- 2 Q \int_0^x \frac{dx'}{h(x')^2}\right]
$$

From this, $Q$ will be determined by the demand that $p = p_0$ at $x = L$:

$$
	Q = \half U \frac{\int_0^L \frac{dx}{h^2(x)}}{\int_0^L \frac{dx}{h^3(x)}}
$$

First, it is easy to check that if $h$ is constant, $Q = U h/2$, $p = p_0$
everywhere, and the fluid friction will dominate the force between the plates.

To get a more nontrivial answer we consider a linear slope for the top surface,

$$ h = h_1 + (h_2 - h_1)\frac{x}{L} $$

The integrals are doable if a bit annoying, but the upshot is that

$$
	Q = U \frac{h_1 h_2}{h_1 + h_2}
$$

and

$$
	p - p_0 = 6\nu U L \frac{(h_1 - h)(h_2 - h)}{(h_2^2 - h_1^2) h^2}
$$

If $h_2 < h_1$ the top and bottom are negative so that $p - p_0 > 0$,
and we have a nontrivial pressure. Because of the slope there is a lateral
component as well as a vertical component, and these will be large
compared to the tangential stresses (by dimensional analysis, but it 
can be checked).

## Eccentic rotating cylinders

The next example is a fixed outer cyliner with radius $r = (1 + \eps) a$,
and an off-center inner cylinder with radius $a$ rotating with
tangential velocity $U = a\Omega$. We take the origin to be the
center of the outer cylinder. The inner cylinder will be offset by
$a\eps\lambda$ with $\lambda \in [0,1]$. The equation for the
radial position of the inner cylinder is

$$
	r_{inner}(\theta) = a + a\eps\lambda \cos\theta
$$

The straightforward way to see this is to set 
$(x - a\eps\lambda)^2 + y^2 = a^2$, and rewrite in polar
coordinates $x = r \cos\theta$, $y = r\sin\theta$. At fixed
$\theta$, the radial distance between the inner and outer
cylinders is thus

$$
	h(\theta) = a\eps(1 - \lambda\cos\theta)
$$

If $\eps \ll 1$, the local geometry of the surfaces are flat, and
we can at any $\theta$ approximate this by the previous example with
a linear slope, with the coordinate $x \sim a\theta$. The upshot is that 

$$
	u_{\theta} = \left[ \frac{U}{h(\theta)} - \frac{z}{2\eta a} \p_{\theta} p
	\right] (h(\theta) - z)
$$

where $z$ is the distance across the gap. 

Similarly, we can use the incompressibility condition to demand that the
flux btween the cylinders

$$
	Q = \half U h(\theta) - \frac{h^3}{12\eta a} \p_{\theta} p 
$$

is constant in $\theta$. This is somewhat less trivial to integrate but
it can be done. The boundary condition we must impose is that 
$p(0) = p(2\pi)$.  As ever, this boundary condition fixes $Q$, which 
in this case is:

$$
	Q = U a \eps \left(\frac{1 - \lambda^2}{2 + \lambda^2}\right)
$$

Note that if $\lambda = 1$ the cylinders touch and the flow goes to zero, 
as you may expect. If $\lambda = 0$, there is flow.

Next, we can try to get some information about $p$. NOte that $h(\theta)$ is
even in $\theta$. Looking at the equation for $Q$, this means $\p_{\thea} p$ is
even, or $p$ is odd. By symmetry, there is thus no
force in the $x$ direction, but there is a net force in the $+y$ direction.
If we integrate $p(\theta)$, we find that

$$
	F = \frac{12\pi \eta U \lambda}{\eps^2 (1 - \lambda^2)^{1/2}(2 + \lambda^2)}
$$

so the load on the inner cylinder can in fact be quite large if $\lambda \to 1$.

Finally, we can show that for a sufficiently large value of $\lambda$ a
counterrotating eddy can appear on the side with the larger gap. Again
solving the differential equations, we find

$$
	\p_r u\big|_{r = h} = \frac{2 U a \eps \lambda}{h^2}
		\left[ \frac{4\lambda^2 - 1}{\lambda(2 + \lambda^2)} - \cos\theta
		\right]
$$

If $\lambda > \half(\sqrt{13} - 3) \sim .3$, there is a range
for which $\p_r \theta$ is positive at $z = h$, so that the flow
is counter-rotating.

