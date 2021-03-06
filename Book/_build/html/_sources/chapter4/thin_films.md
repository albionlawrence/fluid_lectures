# Thin Film approximation

```{math}
\newcommand{\p}{\partial}
```

The next level of approximation we will address is that of a thin film: 
a 3- or 2-d flow wih a small *aspect ratio*. That is, consider a flow
between plates placed at vertical locations $z = 0$, $z = h(x,y)$.
We consider motions with some characteristic *horizontal* 
length scale $L$ such that $h \ll L$, and characteristic 
horizontal length velocity $U$.

In this limit of low aspect ration the equations simplify
substantially, to a version of th ecreeping flow equations, even at large 
horizontal Reynolds number $UL/\nu$. Due to the no-flux boundary conditions, 
the vertical velocity will be qite sall, but the vertical *derivatives* 
will scale as $\p_z \sim 1/h \gg \p_{x,y} \sum 1/L$. 

First, in the incompressibility conditions 

$$
	\p_x u + \p_y v + \p_z w = 0
$$

the first two terms by supposition scale as $U/L$. If $W$ has its own characteristic velocity $W$, the final term scales as $W/h$, which means that 

$$
	W \sim \frac{h U}{L} \ll U
$$

so the vertical velocity is comparably small. 
We cannot ignore it entirely however; it appears in the divergence
equation at the same order as the horizontal divergence (which
does not vanish), and the vertical component of the (vector)
Navier-Stokes equation is proportional to $W$.

Next, in the limit of low aspect ratio, we expect 
$\nu \nabla^2{\vec u} \sim \nu \p_z^2 {\vec u}$.

Finally, we can compare the nonlinear advection term 
${\vec u}\cdot{\vec \nabla} {\vec u}$ to the viscosity term
$\nu \p_z^2 {\vac u}$. The latter scales as $\nu U/h^2$ for 
the horizontal component and $\nu W/h^2$ for the vertical component, 
while the former scales as $U^2/L$ (note that $w\p_z \sim W/h \sim 
U/L$ as well, by the demand above that $\p_z u$ balance 
the horizontal divergence). Thus, the ratio of these terms is

$$
	\frac{advection}{viscosity} \sim \frac{U L}{\nu} \frac{h^2}{L^2}
	= Re \frac{h^2}{L^2}
$$

If we set the time scalee to be $T = L/U$, the $\p_t {\vec u}$ term scales
as the advection term does. In other words, in he thin film limit the
creeping flow approximation will work even at large horizontal Reynolds number.

The thin film limit of the creeping flow equations is thus: 

\begin{align}
	& \p_x p = \eta \p_z^2 u \\
	& \p_y p = \eta \p_z^2 v \\
	& \p_z p = \eta \p_z^2 w \\
	& \p_x u + \p_y v + \p_z w = 0
\end{align}

From these equations, because $W \ll U$, 
$\p_z p \sim \nu W/h^2 \ll \p_{x,y} \sim \nu U/h^2$.
We can assume in the first two equations that $p$ is
therefore a function of $x,y$ alone, so that 

\begin{align}
	& u = \frac{z^2}{2\eta} \p_x p + A(x,y) z + B(x,y)\\
	& v = \frac{z^2}{2\eta} \p_y p + C(x,y) z + D(x,y)
\end{align}

To progress any further requires solving for the boundary conditions. 

Before continuing it is worth considering the
stress vector

$$
	{\vec t} = - p{\vec n} + \eta \left[2{\vec n} \cdot {\vec \nabla} {\vec u}
	+ {\vec n} \times \left({\vec \nabla} \times {\vec u}\right)\right]
$$

From the equations above, $p \sim \eta U L/h^2$, while the largest 
component of the group in square brackets is $\eta U/h$ from the ${\hat z}$
component of ${\hat n}$. The pressure is thus larger by a factor of $L/h$, and
thus dominates the force acting on the boundaries; the tangential force, 
due to viscosity, induced by the horizontal flow is much smaller.



