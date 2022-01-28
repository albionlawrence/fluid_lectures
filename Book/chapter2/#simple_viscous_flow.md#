# Simple examplew of viscous flow

## Channel flow

The book goes through many examples: let me discuss a particularly simple one, the steady flow of viscous fluid in 
two dimensions through a straight channel. Let the walls of the channel be at $y = 0,L$, extending in the $x$ direction,
while the fluid is flowing entirely along the $x$ direction, and is $t$-independent. Incompressibility sets
$\partial_x u = 0$, so that $u = u(y)$. We will look for a solution fo which $p = p(x)$, so that the fluid is being pushed
down the channel. Plugging these solutions into he Navier-Stokes equation, we find

$$ \frac{1}{\rho} \partial_x p(x) = \nu \partial_y^2 u(y) $$

Each side depends on an independent variable, so they must be equal to a constant $\nu c$. We can write
$u(y) = c y^2 + d y + e$. We set $u = 0$ at $y = 0$, so that $e = 0$, and also at $y = L$, so that
$c L^2 + d L = 0$, or $d = - c L$, so that $u(y) = c (y^2 - L y)$. $c$ is thus set by the pressure gradient.
Since $\partial_x p = \nu \rho c = \mu c$, $p = \mu c x + p_0$. 

## Flow down a plane.

Anther example, discussed in the book, is one of a layer of water with height $h$ 
undergoing steady flow down an incline at angle $\alpha$ from the ground, with atmospheric pressure 
$p_0$ at the top of the fluid. Take the problem to be two-dimensional with $x,z$ the directions parallel and 
perpendicular to the incline, and $z = 0$ the incline and $z = h$ the upper boundary. Let $p = p(z)$, and
${\vec u} = u(z) {\hat x}$, where incompressibility kills the $x$ dependence. 

The Navier-Stokes equations in components become:

\begin{align}
	& & \frac{1}{\rho} d_z p + g \cos\alpha = 0 \\
	& & \nu d_z^2 u + g\sin\alpha = 0
\end{align}

NOte that ${\vec u} \cdot {\vec\nabla} {\vec u} = 0$ automatically. At $z = 0$ the boundary 
conditions are $u(0) = 0$, At $z = h$, the no-slip condition is clearly false.
At such a fluid interface, we instead impose the "no stress" condition on the tangential stress
The tangential stress is taken to be proportional to $\partial_z v$, so this must vanish. The pressure, as stted
above, is $p(h) = p_0$. The resoluting solution is

\begin{align}
	p(z) & = & p_0 + \rho g (h - z) \\
	u(z) & = & \frac{g}{2\nu} \sin\alpha (2 h z - z^2)
\end{align}

This is an idealized situation with a flat bottom. In practice, deviations fom flatness will start to lead
to nonvanishing intertial terms, and turbulent flow is possible. If we assume that the hill has a rise angle $\beta$,
and a length scale $L \sim h \beta$, the natural Reynolds number is

$$
	Re = \frac{u \beta h}{\nu} = \frac{g\alpha\beta H^3}{\nu^2}
$$

For water $\nu \sim 10^{-4} m^2/s$. If we cnsider a puddle with $h \sim 1 mm$, and $\alpha \sim .01$, 
we find for laminar flow $v \sim 5cm/sec$. Add an imperfection and 
then $Re \sim 50\beta$. 

For a large slow river with $h \sim 10 m$, $\alpha \sim 10^{-4}$, we would find $v \sim 100 
km/sec$ which is crazy. Here however $Re \sim 10^{12} \beta$. Thus, the slightest imperfection 
leads to turbulence, and our solution above is invalid.
