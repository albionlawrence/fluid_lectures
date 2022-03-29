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
us that we can write $\p_r v_r + \p_{\theta} v_{\theta} = 0$. Using 
Poincar&eacute; theorem, we can write $v_r =  \p_{\theta} \Psi$, 
$v_{\theta} = - \p_r \Psi$, or 

\begin{align}
	u_r & = \frac{1}{r^2 \sin\theta} \p_{\theta}\Psi(r,\theta)\\
	u_{\theta} & =  - \frac{1}{r \sin\theta} \p_{r}\Psi(r,\theta)
\end{align}

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

\begin{align}
	\p_r p & = \frac{\mu}{r^2 \sin\theta} \p_{\theta} D^2 \Psi\\
	\frac{1}{r} \p_{\theta} p & = - \frac{\mu}{r\sin\theta} \p_r D^2 \Psi
\end{align}

Now multiply the second line by $r$, take %\p_{\theta} of the first line and
subtract $\p_r$ of he second line, multiply everything by $\sin\theta$, and we
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


