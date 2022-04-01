# Stokes Drag

```{math}
\newcommand{\p}{\partial}
\newcommand{\half}{\frac{1}{2}}
```

## Introduction: 

A feature of low-viscosity flow past an object is that the drag is
*linea* in the velocity of te object (or of the flow past a stationary object).
This is already apparent in dimensional analysis; to get a force per unit
mass due to the flow, we need a quantity with dimensions of $m/s^2$.
Now, balancing the pressure term against the viscosity, 


$$
	\frac{{\vec\nabla p}}{\rho} = \nu \nabla^2 {\vec u}
$$

and using the dimensionalization we found last time, we deduce
that $p \sim \rho \nu U/R$. This is the pressure per unit area, so the
force on our object is of order $p R^2 \sim \rho\nu U R \equiv \nu U R$.

We will verify this explicitly in a moment for the sphere, but we can first
note that the drag force is linear in the velocity. Thus, to maintain
a constant velociy we must apply a constant force. The resulting dynamics
is sometimes called *Aristotelian*.

## Flow past a sphere

Next we consider a sphere of radius $R$, centered at the origin, in
an incompressible fluid whose velocity asymptotes to a constant 
value ${\vec u} = U {\hat x}$  far from the sphere, and whose pressure 
asumptotes to a constant value $p_0$.

We write the flow in spherical coordinates $(r,\theta,\phi)$ for which
$r$ is the distance from the center of the sphere; $\theta$ the angle 
from the $x$ axis, and $\phi$ the azimuthal angle away from the $y$ axis 
in the $y-z$ plane. The oncoming flow as wll as he sphere is clearly
independent of $\phi$, and there is no force that would induce
motion in this direction so that we can write the velocity as

$$
	{\vec u} = u_r(r,\theta) {\hat r} + u_{\theta}(r,\theta){\hat \theta}
$$

Incompressibility meass that

$$
	{\vec\nabla}\cdot{\vec u} = \frac{1}{r^2} \p_r (r^2 u_r) + 
	\frac{1}{r\sin\theta} \p_{\theta} (\sin\theta u_{\theta}) = 0
$$

Multiplying through by $r^2\sin\theta$ we can rewrite this as:

$$
	\p_r (r^2 \sin\theta u_r) + \p_{\theta} (r \sin\theta u_{\theta})
$$

If we write $r^2 \sin\theta u_r = v_r$, 
$r\sin\theta u_{\theta} = v_{\theta}$, then Poincare's theorem tells 
us that we can write $\p_r v_r + \p_{\theta} v_{\theta} = 0$. Using the
Poincar&eacute; theorem, we can write $v_r =  \p_{\theta} \Psi$, 
$v_{\theta} = - \p_r \Psi$, or 

```{math}
:label: stream_fn
	u_r & = \frac{1}{r^2 \sin\theta} \p_{\theta}\Psi(r,\theta)\\
	u_{\theta} & =  - \frac{1}{r \sin\theta} \p_{r}\Psi(r,\theta)
```

Now let us return to the "creeping flow equations". Using (A.9)

$$
	{\vec\nabla} \times {\vec\nabla} \times {\vec u} = 
	{\vec \nabla} {\vec\nabla}\cdot{\vec u} - \nabla^2 {\vec u}
$$

combined with incompressibility, we have the equation

$$
	{\vec \nabla} p = - \eta {\vec\nabla} \times {\vec\nabla} \times {\vec u}
$$

where $\eta = \rho \nu$ is the shear viscosity. Next, we can use (A.40) 
of the text to write

\begin{align}
	 {\vec\nabla} \times {\vec u} & = \frac{1}{r}
		 (\p_r (r u_{\theta}) - \p_{\theta} u_r)  {\hat\phi}\\
		 & = 
		 \left( - \frac{1}{r\sin\theta} \p_r^2 \Psi
		 - \frac{1}{r} \p_{\theta} \frac{1}{r^2\sin\theta} \p_{\theta} \Psi\right) 
		 {\hat\phi}\\
		 & = - \frac{1}{r\sin\theta} \left( \p_r^2 \Psi + 
		 \frac{\sin\theta}{r^2} \p_{\theta}\frac{1}{\sin\theta}
		 \p_{\theta}\Psi\right) {\hat\phi}
\end{align}

Taking the curl again, we have

$$
	{\vec\nabla} p = \frac{\mu {\hat r} }{r^2\sin\theta} \p_{\theta} ( \p_r^2 \Psi +  
	\frac{\sin\theta}{r^2} \p_{\theta}\frac{1}{\sin\theta} \p_{\theta}\Psi)
	- \frac{\mu {\hat \theta}}{r\sin\theta} \p_r  ( \p_r^2 \Psi +  
	\frac{\sin\theta}{r^2} \p_{\theta}\frac{1}{\sin\theta} \p_{\theta}\Psi)
$$

Now define 

$$
	D^2 \equiv \p_r^2 + \sin\theta\p_{\theta}\frac{1}{\sin\theta} \p_{\theta}
$$

and we have

```{math}
:label: pressure_eqn
	\p_r p & = \frac{\mu}{r^2 \sin\theta} \p_{\theta} D^2 \Psi\\
	\frac{1}{r} \p_{\theta} p & = - \frac{\mu}{r\sin\theta} \p_r D^2 \Psi
```

Now multiply the second line by $r$, take $\p_{\theta}$ of the first line and
subtract $\p_r$ of the second line, multiply everything by $\sin\theta$, and we
find $(D^2)^2 \Psi = 0$.

The next goal is to solve this. We first look for a solution as $r \to \infty$.
${\vec u} \to  U {\hat x}$ means in spherical coordinates $u_r \to U \cos\theta$,
$u_{\theta} \to - U \sin\theta$. We can plug this into the equations defining $\Psi$.
Using $\p_{\theta} \Psi = r^2 \sin\theta u_r = r^2 U \sin\theta\cos\theta$, which
can be solved by taking $\Psi = \half r^2 U \sin^2\theta$, which yields the correct
expression for $u_{\theta}$ as well. 

Based on this, and the fact that the object in the center is spherically symmetric, we
expect no further change to the angular dependence as we appoach the sphere.
we will assume that $\Psi = f(r) \sin^2\theta$, in which case 

$$
	D^4 \Psi = 0 \Rightarrow \left(\p_r^2 - \frac{2}{r^2}\right)^2 f = 0
$$

We can search for solutions of power law type by setting $f = r^n$. Inserting this
into te above gives us

\begin{align}
	 \left(\p_r^2 - \frac{2}{r^2}\right)^2 r^n & = 
	 (n(n - 1) - 2) \left(\p_r^2 - \frac{2}{r^2}\right) r^{n-2} \\
	 & = (n(n-1) - 2)((n-2)(n-3) - 2)
\end{align}

This vanishes when either of the quadratic expressions shown vanishes. 
$n(n-1) - 2 = n^2 - n - 2 = (n - 2)(n+1) = 0$ if $n = 2, -1$. Similarly,
$(n-2)(n-3) - 2 = n^2 - 5 n + 4 = (n-4)(n-1) = 0$ of $n = 1,4$. Thus,
the general solution is

$$
	f(r) = \frac{A}{r} + B r + C r^2 + D r^4
$$

To match the behavior at infinity, $D = 0$; the dominant part is $C r^2$, 
and we have $\Psi = f \sin^2\theta \Rightarrow \half r^2 U \sin^2\theta$, so that
$c = \half U$. 

Next, we need to impose the boundary conditions, which amount to $u_r(R,\theta)
= u_{\theta}(R,\theta) = 0$. The condition on $u_r$ gives $f(R) = 0$. The condition
on $u_{\theta}$ gives $f'(R) = 0$. These are two equations in two unknowns $A,B$ and 
the full solution becomes

$$
	\Psi = \frac{1}{4} U \left(2 r^2 + \frac{R^2}{r} - 3 R r\right)\sin^2\theta
$$

## Drag on the sphere

Now that we know the property of he flow, we would like to compute the drag force.
Recall that in the Navier-Stokes equation 

$$ 
	\rho D_t {\vec u} = - {\vec\nabla} p + \eta \nabla^2 {\vec u} 
$$

where $\eta = \nu\rho$ is the hear viscosity,
the left hand side describes the force on a fluid parcel. Nowever, we cannot consider
this as the force on a large body immersed in the fluid. The force above is the sum of
the forces acting on each side of the fuid parcel. This is why, for example, the viscosity
depends on the *second* derivative of the velocity; if the velocity varied linearly in, say,
the vertical direction, the relative velocity on each side of a fluid element 
(in a frame in which that element is at rest) would be equl and opposite; assuming we
are looking at sliding fricion. proportional to velocity, this means hat the "frictional"
viscous force cancels. Similary, the pressure exerts a force perpendicular to any surface 
element, so that a constent pressure will exert a net force of zero on any fluid element;
only in the presence of a gradient will the force on two sides of a fluid element
be different.

Properly speaking one would derive this force by making use of the stress tensor of the 
fluid. This concept is discussed at ength in Chapter 6 and while interesting would take us
in a more formal/mathematical direction than I want to go here. Here we will cheat a little
and imagine that we replace the sphere with a blob of fluid. The force on the whole blob will
the the volumet integral 

$$
	{\vec F} = \int_V d^3 x \left[ - {\vec\nabla} p + \eta
	{\vec \nabla} \cdot{\vec \nabla} {\vec u}
	\right]
$$

Note that both terms are total derivatives. In components we can write 

$$ ({\vec\nabla} p)^i = (\p_j \delta_{ji} p) $$

Both terms then appear as divergences, and we can reduce the volume integral to a boundary
integral:

$$
	{\vec F} = \int_S d^2 x \left[ - {\hat n} p({\vec x},t) + \eta n^i \p_i {\vec u}\right]
$$

where ${\hat n}$ is the unit normal perpendicular to the surface, which for a sphere
in shperical coordinates is ${\hat r}$. We assume the force of the
fluid on the body is the same as he force of the fluid on a the region taken up by the body,
if said region were replaced with the fluid. We might worry somewhat about the no-slip
condition on the sphere but the force due to the viscosity is proportional to th *gradient*,
so, roughly speaking, the drag due to viscosity is from the friction between the 
layer stuck to the sphere, and the next layer out.

The next step is, then, to compute $p$ and ${\vec u}$ near the sphere. ${\vec u}$ can 
becomputed from {eq}`stream_fn` by taking the appropriate derivatives of $\Psi$. 
To find $p$, we integrate {eq}`pressure_eqn`. The upshot is that

$$
	p = p_{\infty} - \frac{3 \mu U R}{2 r^2} \cos\theta
$$

Now we note that there is no $\phi$ dependence in any of our expressions, 
nor will ${\vec u}$ have any ${\hat\phi}$ component. 

Let us first compute the force due to the pressure. Because ${\hat r}$ itself varies with 
$\theta$, we will work in cylindrical coordinates, $(x,\rho,\phi)$. In this case we have
${\hat r} = {\hat x} \cos\theta + {\hat\rho}\sin\theta$. Again, we expect that the
${\hat\rho}$ component will cancel upon integration over $\phi$, as the vector 
at $\phi$ is equal and opposite to that at $\phi + \pi$. Thus, 

\begin{align}
	{\vec F}_{pressure} & = - 2\pi R^2 \int d\theta \sin\theta {\hat x} \cos\theta
	\left( p_{\infty} - \frac{3 \mu U R^3 }{2 r^2} \cos\theta\right)\\ 
	& = 3\pi \mu U R \int_{-1}^1 dy y^2  \\
	& = 2\pi\mu U R
\end{align}

where in the second line we note the term with $p_{\infty}$ vanishes as $\sin\theta$ 
is odd and $\cos\theta$ even across the equator $\theta = \pi/2$, and in he third line we set
$y = \cos\theta$.

The next step is to compute the contribution of the viscosity terms:

$$
	{\vec F}_{visc} = \eta R^2 \int^{2\pi}_0 d\phi \int_0^{\pi} d\theta\sin\theta
		\p_r {\vec u}
$$

Now $\p_r u_r(r = R) = 0$, as can be seeb by direct calculation. As for
$\p_r (u_{\theta}{\hat\theta}$, the component of ${\hat\theta}$ perpendicular to
the $x$-axis will integrate to zero due to the integral over the azimuthal direction
because that vector is odd under shifts $\phi \to \phi + \pi$ and there is
no further $\phi$-dependence in the integral. Since ${\hat \theta} = - {\hat x} \sin\theta + 
{\hat\rho} \cos\theta$, we are left with:

$$
	{\vec F}_{visc} = - 2\pi R^2 \eta \eta \int_0^{\pi} d\theta\sin^2\theta
	\p_r u_{\theta} {\hat x} 
$$

We can compute $\p_r u_{\theta} = - \frac{3U}{2R}\sin\theta$; plugging this in
${\vec F}_{visc} = 4\pi \eta U R {\hat x}$, we find that ${\vec F} = 6\pi \eta U R$. 

As it happens, while this result matches experiment reeasonably well, 
creeping flow fails to account for
the drag in other situations such as a cylinder (a circle in 2d). To see how
this might fail, note that if we take the divergence of he creeping flow equation
incompessibility means the viscosity term drops out, and $\nabla^2 p = 0$. 

Now we expect any non-constant term to be proportional to positice powers of ${\vec U}$.
For constant ${\vec U}$ one can show that the only term linear that solves Laplace's equation
is $p \sim U\cos\theta/r$. Integrating the creeping flow equations

$$
	\p_r p = \eta \frac{1}{r} \p_r (r \p_r u_r)
$$
one finds $u_r \sim (\ln r)^2$ which gets large at large $r$. Thus for any fixed $\nu$,
the velocity increases and teh Reynolds number grows. In other 3d examples, we might expect
the gradient of $U$ to fall off at large distances. Even though $U$ may be small, the small
gradient eans he characeristic distance scale is growing, so that $U L/\nu$ gets large.
Either way, the low-Reynolds-number approximation ceases to pertain and our expression
may well break down.

Acheson describes a more precise expression by presenting a solution 
for the creeping flow close to the sphere, and the high-Re flow far from
the sphere. There is an overlapping region where these can be matched. 
This strategy is important in addressing boundary-layer problems.


