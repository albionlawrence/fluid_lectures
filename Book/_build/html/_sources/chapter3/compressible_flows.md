# Compressible flows: linear theory

```{math}
\newcommand\eps{\epsilon}
\newcommand\vv{{\vec v}}
```

While most of this course foused on incompressible flows, it is worth
spending a little time on compressible flows one encounters in particular
in gas dynamics. In this section we'll focus on the inviscid limit. The
Euler equations are as before:

$$
 \partial_t {\vec v} +_ {\vec v}\cdot{\vec \nabla} {\vec v} = - \frac{1}{\rho} {\vec \nabla} p + {\vec F}_{ext}\ ,
$$

but the continuity equation is

$$
	\partial_t \rho + {\vec \nabla}\cdot(\rho {\vec v}) = 
	\partial_t \rho + {\vec v}\cdot{\vec \nabla} \rho +
	\rho {\vec \nabla}\cdot{\vec v} = 0
$$

and the final term does not in general vanish. Finally, to close these
equations, we will need some kinf of equation of state $p = p(\rho)$.
In general $p$ will depend on othe themrodynamic variables such as temperature
as well, in which case we will need equations for those quantities;
we are assuming here that those are fixed. Two candidate equations of state 
are:

$$
	p = \rho T
$$

for an isothermal ideal gas; suc gases will have heat 
exchange between warmer compressed regions and colder rarified regions.
Another, for cases of no heat exchange, is the adiabatic gas law

$$
	p = C \rho^{\gamma}
$$

which turns out to be more relevant for sound waves. For this case, we can
define the *speed of sound* $c_s$ via:

$$
	c_s^2 = \frac{\partial p}{\partial \rho} \Big|_{fixed\ entropy} 
$$

For the equation of state above, 

$$
	c_s^2 = \gamma C \rho^{\gamma - 1} = \frac{\gamma p}{\rho}
$$

We will see below why we idenify this with the speed of sound waves.

## Sound waves

Once again we start from a static solution with constant density and pressure:
${\vec v} = 0$, $p= p_0$,  $\rho = \rho_0$, with backgound speed of sound 
$ c_{s0}^2 = \gamma p_0/\rho_0$. We expand

\begin{align}
	{\vec v} & = \eps \vv_1 + \eps^2 \vv_2 + \ldots\\
	\rho & = \rho_0 + \eps \rho_1 + \eps^2 \rho_2 + \ldots\\
	p & = p_0 + \eps p_1 + \eps^2 p_2 + \ldots
\end{align}

The Euler nd mass conservation equations are satisfied to order 
${\cal O}(\eps^0)$. At ${\cal O}(\eps)$, the equations are:

\begin{align}
	& \partial_t \vv_1 = - \frac{1}{\rho_0} {\vec\nabla} p_1\\
	& \partial_t \rho_1 + \rho_0 {\vec\nabla}\cdot{\vec v} = 0\\
	& p_1 = c_{s0}^2 \rho_1
\end{align}

Taking thecurl of the first equation, we have 
$\partial_t {\vec \nabla} \times \vv_1 = 0$, so hat vorticity is conserved.
If we perturb our system with irrotational flow, it remains irrotational,
so let us do hat. we can then wrote $\vv_1 = {\vec\nabla}\phi_1$, and
our equations become:

\begin{align}
	& \partial_t {\vec \nabla} \phi_1 + \frac{c_{s0}^2}{\rho_0} 
	{\vec\nabla} \rho_1 = 0\\
	& \partial_t \rho_1 + \rho_0 {\vac\nabla}^2 \phi_1 = 0
\end{align}

The first equation is in fact a pure gradient:

$$
	{\vec \nabla} \left(\partial_t \phi_1 + \frac{c_{s0}^2}{\rho_0} \rho_1\right) = 1
$$

The term in parentheses is therefore a funciton of time only. defining this as 
$D(t)$, if we redfine $\phi_1 \to \phi_1 - \int_0^t dt' D(t')$, then the velocities do not change, and we have

$$
	\partial_yt \phi_1 + \frac{c_{s0}^2}{\rho_0} \rho_1 = 0
$$

Taking the time derivative of this equation and inserting the conservation
equation we are left with the wave equation

$$
	\partial_t^2\phi_1 - c_{s0}^2 {\vec \nabla}^2 \phi_1 = 0
$$

### Plane wave solutions

Let us consider waves propaating in three dimensions, with boundaries at 
infinity. We can attempt a separation of variables:

$$
	\phi_1 = X(x)Y(y)Z(z)T(t)
$$

Inserting this into the wave equation and dividing by $\phi_1$, we find:

$$
	{\ddot T}{T} - c_{s0}^2 
	\left(\frac{X''(x)}{X} + \frac{Y''(y)}{Y} + \frac{Z''(z)}{Z} \right) = 0
$$

Each term depends on an independent variable and thus must be equal to a
constant. Thus, we define

$$
	\frac{X''(x)}{X} = - k_x^2
$$

and similarly for $Y,Z$. For the solution to remain finie at infinity,
we must have $k_x^2 > 0$, so that a general solution to the above is

$$
	X = {\rm Re} X_0 e^{i k_x x}
$$

More generally, we have

$$
	X Y Z = {\rm Re} (A e^{- i {\vec k} \cdot {\vec x}
$$

(the minus sign is conventional). Finally, we have 

$$
	\frac{\ddot T}{T} = - c_{s0}^2 {\vec k}^2
$$

Defining $\omega = c_{s0} \sqrt{\vec k}^2$, we have the solution:

$$
	\phi_1 = {\rm Re} (C e^{i \omega t - i {\vec k} \cdot{\vec x}
$$

These describe *longitudinal waves*: ${\vec v}_1 = {\vec \nabla} \phi_1$ 
points in the direction ${\vec k}$. 

Note this is a complete set of solutions; in other words, for any initial
condition $\phi_1({\vec x},t=0)$, we can always decompose this via a Fourier
integral into plane waves:

$$
	\phi_i(x,t=0) = \int \frac{d^3 k}{(2\pi)^3} e^{- i {\vec k}\cdot{\vec x}}
	{\tilde \phi}({\vec k})
$$

from which the time evolution is:

$$
	\phi_i(x,t) = \int \frac{d^3 k}{(2\pi)^3} e^{i c_{s0} |{\vec k}| t - i {\vec k}\cdot{\vec x}}
	{\tilde \phi}({\vec k})
$$

Now let us consider the case of waves moving purely in the $x$ direction 
($k_y = k_z = 0$). In this case, $\omega = c_{s0}|k|$, $k = \pm |k|$, so
the solutions are:

$$
	\phi_k(x,t) = {\rm Re} A e^{ic_{s0} |k| - i ({\rm sign}(k)) |k| x}
$$

A general solution will be a linear combination of these; we thus find
that the general solution as the form:

$$
	f(x,t) = f_+(x + c_{s0} t) + f_-(x - c_{s0}t)
$$

Another way to see this is to define $x_{\pm} = x \pm c_{s0} t$. Is is
sraightforward to show, using the chain rule, that

$$ 
	\frac{\partial}{\partial x_+} \frac{\partial}{\partial x_-} \phi_1 = 0
$$

From this equation the above general solution follows immediately.

The upshot is that a given initial configuration always splits into a 
left- and right-moving wave packet, each of which travels at speed $c_{s0}$ 
without distortion. 

Finally, we can ask when the linnear approximaion is good. In the present case we will ask when $\eps \rho_1 \ll \rho_0$. Consider a solution at late times such
that the left- and right-moving wavepackets are well-=separated, and focus on one such (we will choose $f_-$ for specificity). Starting with

$$
	\partial_t v_1 = - \frac{1}{\rho_0} \partial_x p_1
$$

and using $\partial_t v_1 = c_{s0} \partial_x v_1$ so that

$$
	c_{s0} v_1 = - \frac{p_1}{\rho_0} + {\rm constant}
$$

We set the constant to zero by demanding that the velocity perturbation
vanishes when the pressure does (alternatively, by choosing the correct
frame of reference). Finally, setting $p_1 = c_{s0}^2 \rho_1$ we have

$$
	\eps v_1 = - \frac{c_{s0} \eps \rho_1}{\rho_0}
$$

From this we see that 

$$
	\eps \rho_1/\rho_0 \ll 1 \Rightarrow \frac{\eps v_1}{c_{s0}} \ll 1
$$

In other words the small amoplitude limit corresponds to velocity perturbations
much slower than the sound speed. 

### Spherical waves

Returning to three dimensions, let us consider spherically symmetric 
waves emanating from the origin. This means that $\phi_1(r,\theta,\phi) = \phi_1(r)$, so that

$$
	{\vec \nabla}^2 \phi_1 = \frac{1}{r^2} \partial_r (r^2 \partial_r) \phi_1
$$

The wave equation is then

$$
	\partial_t^2 - \frac{c_{s0}^2}{r^2} \partial_r (r^2 \partial_r) \phi_1 = 0
$$

If we set $phi_1 = f(r)/r$, then

$$
	\left(\partial_t^2 - c_{s0}^2 \partial_r^2\right) f = 0
$$

so that a general solution is

$$
	\phi_1 = \frac{f_+(r - c_{s0} t)}{r} +  \frac{f_-(r - c_{s0} t)}{r}
$$

which is a sum of waves outgoing from and ingoing to the origin.

## Supersonic flows past an airfoil

The next steps is to consider a steady (constant-velocity) 
flow ${\vec v} = U {\hat x}$, $p_0$, $\rho = \rho_0$, in the presence 
of a very thin airfoil. We expect that if the aifoil is sufficiently 
thin it will induce only a very small perturbation of the basic 
state, so that a linear theory, first order in perturbations, 
applies.

In this case we set

\begin{align} 
	{\vec v} & = U{\hat x} + \eps \vv_1 + \eps^2 \vv_2 + \ldots\\
	p & = p_0 + \eps p_1 + \eps^2 p_2 + \ldots\\
	\rho & = \rho_0 + \eps \rho_1 + \eps^2 \rho_2 + \ldots
\end{align}

We will assume that the airfoil is straight and long enough in the $y$ direction
that the perurbations depend on $x,z$ only, and that $v_y \equiv V$ vanishes,
leaving us with 2d flow. Setting $\vv_1 = u_1 {\hat x} + w_1 {\hat z}$, and following the same logic as before, we have the Euler equations
at order ${\cal O}(\eps)$: 

\begin{align}
	& \rho_0 U \partial_x u_1 = - \partial_x p_1\\
	& \rho_0 U \partial_x v_1 = - \partial_y p_1\\
\end{align}

and the mass conservation equation:

$$
	\rho_0(\partial_x u_q + \partial_y v_1) + U \partial_x \rho_1 = 0
$$

Next, we take the $x$ derivative of the second of te two Euler equations
above, and subtract the $y$ derivative of the first, to find:

$$
	\rho_0 U \partial_x (\partial_x v_1 - \partial_y u_1) = 0
$$

In other words the voriticity is $x$-independent at order ${\cal O}(\eps)$. 
Since it vanishes at  $x \to - \infty$, where the velocity is just 
$U{\hat x}$, it vanishes everywhere, and we can consider potential 
flow ${\vec v}_1 = {\vec \nabla} \phi_1$. Using this in the
mass conservation equations we find

$$
	\rho_0 {\vec \nabla}^2 \phi_1 + \frac{U}\partial_x \rho_1 = 0
$$

where the Laplacian is taken to be two-dimensional. 
Now once again we take the linearized version of the equation of state:
$p_1 = c_{s0}^2 \rho_1$, plug this into the equation above, and hen
use the $x$ component of the Euler equation to eliminate $p_1$, and we find

$$
	\left(1 - \frac{U^2}{c_{s0}^2}\right) \partial_x^2 \phi_1 + 
	\partial_y^2 \phi_1 = 0
$$

We define the *Mach number* as $M = \frac{U}{c_{s0}}$. we cna see that 
qualitatively the equations loof very different for $M > 1$ as fo $M < 1$, 
as it changes the relative sign of the derivatives.

The next step is to impose boundary conditions. Let the airfoil
shape be $y(x) = \eps f(x)$, with $y'(x) = \eps f'(x)$ ($y$ could get large 
if the wing is too wide, even if $y'$ is small; we will not consider that 
possibility). If we demand that the normal velocity
vanishes/the velocity is tangent ot the wing, then the boundary condition is

$$
	\frac{v_y}{v_x} \sim \frac{\eps v_1}{U + \eps u_1} \sim \eps f'(x)
$$

which at leadig order in $\eps$ becomes

$$
	v_1\Big|_{y = y(x)} = U f'(x)
$$

To leading oder in $\eps$ we can evaluate $v_1$ at $y = 0$, so that

$$
	v_1(x,0) = \partial_y \phi_1(x,0) = U f'(x)
$$

Now let us solve this equation for *supersonic flow* $M > 1$. In this case, we can define $\tau = \frac{x}{\sqrt{M^2 - 1}}$ and the equation of motion
for $\phi_1$ becomes

$$
	\left[\partial_{\tau}^2 - \partial_y^2\right] \phi_1 = 0
$$

This is essentially identical to the wave equation for sound waves, in which
"time" is a rescaled $x$. We know the general solutions:

$$
	\phi_1 = f_-(y - \tau) + f_+(y + \tau)
$$

which we can rewrite as

$$
	\phi_1 = f_-(x - \beta y) + f_+(x + \beta y)
$$

where $\beta = \sqrt{M^2 - 1}$. 

In such supersonic flow we assume that the airfoil will generate 
compression waves which travel at the speed $c_s$. By causality,
we expect the disturbance to trail the leading edge of the airfoil.
A basic argument is that at a point in time, the tip of the airfoil moving
through the fluid would generate a circular compression wave travelling 
at speed $c_s$. But the airfoil is moving faster than this compression 
wave, so it always leave the wave behind.

We take $\phi$ to vanish upstream of the airfoil. 
Now if we take the tip of the airfoil to lie at the origin, 
we expect $\phi$ to start changing first at the tip. By causality 
only $f_-$ can start to change above the wing (because $f_+$ nonzero 
near the tip would imply it is nonvanishing ahead of the airfoil, 
out to arbitrarily large values of $-x$ and $y$), 
while only $f_+$ can be nonzero below it. Thus $\phi$ will vanish 
all the way along $x = \beta y$ for $y > 0$, and along $x = - \beta y$ for 
$y < 0$. By continuity $F_+(0) = 0$ above the wing and $F_-(0) = 0$ below. 

Now let the wing have extent $L$. Imposing the boundary conditions we have
$\phi'_1 = f'_-(x) = - \frac{U}{B} f'(x)$, so that we get 
$\phi_1 = f_-(x) = - \frac{U}{\beta} f(x) + c$ for $y > 0^{+}$,
where $c$ is a constant which is set to
zero by demanding $f_+(0) = 0$. Similarly, below the wing we have
$\phi_1 = f_-(x) = - \frac{U}{\beta} f(x)$. Finally, 
For $x > L$ the airfoil vanishes again, so that $f_{\pm}(x > L) = 0$.

The full solution becomes

$$
	\phi_1 = - \frac{U}{\beta} f(x \mp \beta y) \ {\rm for}\  \pm y > 0,\ 0 < x \pm \beta y < L
$$

This means that the streamlines have the same shape as the airfoil; in
particular, $v_y = \partial_y \phi = U f'(x - \beta y)$ for $y > 0$, so that
$v_y/U \sim f'$.



