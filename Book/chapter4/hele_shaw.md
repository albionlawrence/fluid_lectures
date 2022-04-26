# Thin film example: the Hele-Shaw cell

```{math}
\newcommand{\p}{\partial}
```

We first consider the example of plates at constant vertical coordinates 
$z = 0,h$, with fluid driven by horizontal pressure gradients, and rigid 
objects placed in the cell that the fluid must flow around (we take these
to be straigt in the vertical direction). 

In this case $u,v$ must vanish due to the  no-slip boundary conditions at 
$z = 0,h$. In the previous section, this fixes $A,B,C,D$ so that 

\begin{align}
	& u = - \frac{z(h-z)}{2\nu} \p_x p\\
	& v = - \frac{z(h-z)}{2\nu} \p_y p
\end{align}

Note here that in he approximation that $p = p(x,y)$, the ratio $u/v$ is 
$z$-independent. Thus the flow direction, and the streamlines, are
$z$-independent. 

Furthermore, 

$$
	{\vec u}_{hor.} = - \frac{z(h-z)}{2\eta} {\vec \nabla}_{hor.} p(x,y)
$$

where the subscripts denote the horizontal components of the vectors. In
other words, at any fixed $z$ the horizontal velocities are pure gradients.
Their curl (or the 2d analogs) is therefore zero:

$$
	\p_y u - \p_x v = 0
$$

so that the 2d flow is *irrotational*.

In irrotational flow, the circulation around any closed loop which can be
shrunk to zero vanishes. This is because the vanishing of the circulation
is based on the formula:

$$
	\Gamma = \oint_{\p D} {\vec dx}\cdot {\vec u} = \int_D d^2 x {\vec \nabla}
		\times {\vec u} = 0
$$

If $D$ is not simply connected, there are multiple boundary components in
$\p D$, and all that ${\vec \nabla}\times {\vec u} = 0$ gives us is 
that the sum of the circulation over boundary components vanishes.

In the present case, however, the fact that ${\vec u}$ is a gradient means 
that at any fixed $z$ and for any closed contour $C$,

$$
	\Gamma = - \frac{z(h-z)}{2\eta} \oint_C dx \p_x p + dy \p_y p
$$

Since $p$ is single-valued, and the above is a total derivative over
a closed contour, $\Gamma = 0$. This is true even if $C$ surrounds
some internal obstacle. Thus the circulation vanishes around any obstacle.
A particular consequence is that there is no lift.
