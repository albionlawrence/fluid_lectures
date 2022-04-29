# Thin film flow on a slope

```{math}
\newcommand{\p}{\partial}
\newcommand{\half}{\frac{1}{2}}
```

The next example we visit is that of a thin film of water on an inclined plane.
There are a few notable features of this problem:
  - As compared to previous problems, we have an external force (gravity).
  - We will be interested in the time-evolving profile of the film.
  We will find that this is described by a nonlinear differential equation in
  space and time, despite the fact that the creeping flow equations are
  linear and have no time derivative.
  
We consider an inclined plane with slope $\alpha$ under the force of gravity,
which we take ot act with force $-m g {\hat z}'$ where ${\hat z}'$ is the 
vertical diection. We consider 2d flow, with one vertical and one horizontal
direction. As with the treatment of the flow of a river, we work in coordinates
$(x,z)$ along and perpendicular to the plane.

The thin film equations now include the gravitational force:

\begin{align}
	& - \p_x p + \nu \nabla^2 u + \rho g \sin\alpha = 0\\
	& - \p_z p - \rho g \cos\alpha = 0\\
	& \p_x u + \p_z w = 0
\end{align}

where, in this approximation, we drop the viscosity term in the
vertical momentum equation. We take the fluid profile to be defined
by $z = h(x,y)$

Next we need to consider the boundary conditions. At the plane they are the
no-slip and no-flux conditions $u = w = 0$. At the free surface we need to 
impose diffrent boundary conditions. We assume that the normal stress
at the interface $z = h(x,y)$ is equal to the atmospheric pressure, and that the
tangential viscous stress *vanishes*. (This would be different
if the air was replaced by a high-viscosity fluid; then there can
be tangential voiscous stress). 

To impose this, we assume that the slope *of the film* with respect to the
inclined plane is small. This means we can take the direction perpendicular
to the film to be $\sim {\hat z}$ and the direction tangent to
the film to be $\sim {\hat x}$. Finally, the vertical velocity in the {\hat z}$
direction should equal to $d_t h$, The boundary conditions at the free surface
then become

\begin{align}
	& p(x, z = h,t) = p_0\\
	& \eta \p_z u = 0
	& w = \p_t h + u \p_x h
\end{align}
We can see from this last equation that the boundary conditions
introduces nonlinearity into the equations.

The second equation in the thin film equations is straightforward to solve:

$$
	p = - \rho g z \cos\alpha + f(x,t)
$$

Using $p = p_0$ at $z = h$, we have $f = p_0 + \rho g h(x,t) \cos\alpha$, or

$$
	p = \rho g (h - z) \cos\alpha + p_0
$$

We can insert this into the second momentum equations to find:

$$
	\eta \p_z^2 u = - g \sin\alpha + g \p_x h \cos\alpha
$$

We drop the last term under the assumption that the slope $\p_x h$ is small:
that is, he pressure contributes minimally to the vertical shear. Integrating
this equation once from $z = h$, using the no-stress condition at $z = h$
(this is why we integrate from there and not from the plane), we find

$$
	\eta \p_z u = - g (z - h) \sin\alpha 
$$

Integrating again from the plane wheer $u = 0$, we find

$$
	u = \frac{g \sin \alpha}{\eta} \left( h z - \half z^2\right)
$$

Now we can solve the incompressibility condition:

$$
	\p_z w = - \p_z u = - \frac{g z \sin\alpha}{\eta} \p_x h
$$

Since $\p_x h$ multiplies the only term on the RHS, and we expect $w$ to be
small, we cannot ignore this. Integrating once from the plane, and using
the no-flux boundary codnitions, we have

$$
	w = - \frac{g z^2 \sin\alpha}{2 \eta}\p_x h
$$

Finally we impose the boundary conditions on $w$ at the free surface.
A bit of algebra leads to the equation

$$
	0 = \p_t h + u \p_x h - w = \p_t h + \frac{g\sin\alpha}{\nu} h^2 \p_x h
$$

Note the similarity to some of the nonlinear equations for dam breaks etc.
We could this this equation with the same techniques, eg the
method of characteristics. For not we will not go that far. We do note
that as with that problem, the full solution arises from the implicit equation

$$
	h = F(x -  \frac{g\sin\alpha}{\nu} h^2 t)
$$

where $F$ is an arbitrary function. This could potentially develop
singularities since the effective speed of different elements of the layer is
$c =  \frac{g\sin\alpha}{\nu} h^2$, so that the higher parts flow faster.

We assume that the profile stretches from some $x = 0$ up the slope 
to a "nose" $x = x_N(t)$ down the plane. We expect the slope to get 
smaller and smaller at $x = 0$ as the film stretches, but the above 
pileup should lead to a steper slope at the nose. In practice surface 
tension effects will be considerable at the nose, a fact we ignore.

We can attempt a *similarity solution* to the above equation. Noting
$g/\nu$ has dimension $1/LT$, and $x/t$ has dimensions of velocity, we 
choose 

$$
	h_{sim} = \left(\frac{\nu}{\sin]alpha}\right)^{1/2} \sqrt{\frac{x}{t}}
$$

We can show that this is an exact solution. In problem 7.10, which I 
did not assign, you can show that if you start from a film which 
is defined by a constant slope $\beta$ above the plane,
extending from $x = 0$, the film asymptotes to the above solution
at large times. To see this, let us consider a family of initial conditions
and solve the problem exactly (this is problem 7.10 in the book).

At $t = 0$, we demand $h = \beta x$. Using the general form of our solution,
this means $F(x) = \beta x$, so that

$$
	h = \beta \left(x -  \frac{g\sin\alpha}{\nu} h^2 t\right)
$$

This is a quadratic equation we can solve, to find:

$$
	\frac{2 g \sin\alpha}{\nu} h = - \frac{1}{\beta t} + 
		\sqrt{\frac{1}{\beta^2 t^2} + \frac{4g\sin\alpha}{\nu}\frac{x}{t}}
$$

As $t \to \infty$, the second term in the square root dominates. The square
root then scales as $1/\sqrt{t}$ and dominates over the first term on
the RHS of the exact expression for $h$. The similarity solution then
follows. Note that it is independent of $\beta$.

We assume this solution extends to the nose. Finally, we demand that the
total area of the blob does not change with time (fluid is not being added
or evaporated):

$$
	\ont_0^{x_N(t)} dx h_{sim}(x,t) = A =  
	\left(\frac{\nu}{\sin]alpha}\right)^{1/2} \frac{2 x_N^{3/2}}{3 t^{1/2}}
$$

so that

$$
	x_N(t) = \left(\frac{9 A^2 g \sin\alpha}{4\nu}\right)^{1/3} t^{1/3}
$$

As it happens, this agrees well wih experiment.



