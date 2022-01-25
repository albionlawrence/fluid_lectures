# Vorticity Dynamics

The vorticity itself has dynamics which gives additional information about fluid flows.
In some cases it is either a conserved quantity or a piece of a concerved quantity.

## Circulation

We will work mostly with $d = 3$ but much of this holds in $d = 2$.

For some initial time $t_0$, consider a closed loop $L$ of fluid particles. As these evolve in time (at least for short
enough times), the particles will evolve to lie along a new loop $L(t)$. We define the *circulation*
as

$$
	C(t) = \oint_{L(t)} d{\vec \ell}\cdot {\vec v(t)}
$$

which captures the part of the velocity field that is running along the loop $L$.
Now first consider the case that $L$ can be shrunk to a point. Thus, there is a 
surface $A$ whose only boundary is $L$, and we can use Stoke's theorem to find:

\begin{align}
	C(t) & = & \oint_{L(t)} d{\vec \ell}\cdot {\vec v(t)}\\
	& = & \int_{A(t)} d{\vec A} \cdot ({\vec \nabla}\times {\vec v})\\
	& = & \int_{A(t)} d{\vec A} \cdot {\vec \omega}(t)
\end{align}
$d{\vec A}$ denotes an infinitesimal area element on A, with the direction perpendicular to that element.
In two dimensions we would replace $d{\vec A} \cdot {\vec \omega}$ with $dA \omega$. 
In this case, the circulation vanishes when the fluid is irrotational.

However, if $L$ surrounds a boundary of the fluid, this argument fails. Imagine a cylinder or
perhaps a wing which spans the fluid, and let $C$ encircle this. If we choose a second loop $L'$
such that there is a surface $A$ whose boundaries are $L$ and $L'$ -- that is, such that $L$ can
be smoothly deformed to $L'$, sweeping out $A$ -- tthen

\begin{align}
	\left[ \oint_{L(t)} - \oint_{L'}\right] d{\vec \ell}\cdot {\vec v(t)}
	& = & C(t) -  \oint_{L'} d{\vec \ell}\cdot {\vec v(t)}\\
	& = &  \int_{A(t)} d{\vec A} \cdot {\vec \omega}(t)
\end{align}

Thus for an irrotational flow, the best we can say is that $C$ is invariant under smooth 
deformations of $L$.

## Kelvin's theorem

Now let us study the dynamics of $C$:

$$
	d_t C(t) = \oint \left(d_t ({\vec v}) \cdot d{\vec \ell}(t) + {\vec v} \cdot d_t d{\vec \ell}(t)\right)
$$

I claim that the second term on the RHS vanishes. This is because

$$
	\frac{d}{dt} d\ell^i = dv^i = \frac{\partial v^i}{\partial x^j} dx^j = 
	d\ell^j \partial_j v^i
$$

so that

$$ v_i 	\frac{d}{dt} d\ell^i = v^i d\ell^j \partial_j v^i =  d\ell^j\partial_j \frac{1}{2} {\vec v}^2 $$

This is a total derivative and vanishes upon integrating over a closed loop.

Now inside the integral,

$$
	\frac{d}{dt} v^i = \left[ \partial_t + {\vec v} \cdot {\vec \nabla}\right] v^i
$$

Applying Euler's equation, we find

$$
	d_t C = - \oint d{\vec \ell_i} \frac{\partial_i p}{\rho} 
$$

Now there are three cases where this vanishes:

1. if $p = p(\rho)$, we can write $\frac{1}{\rho} {\vec \nabla} p = {\vec \nabla q}$. This is because
for any function of a single variable $f(\rho)$, we can always find a $g(\rho)$ such that 
$\partial_i f/\rho = \partial_i g$. The integrand above is a total derivative. 

2. $\rho$ is constant.

3. Isentropic flow. In this case, as we hae shows, $\frac{1}{\rho} {\vec \nabla} p = {\vec \nabla} W$,
and he same argument holds.

The time-independence or conservation of circulation in these cases is known as Kelvin's Theorem.

## Vorticity dynamics

We can also find equations of motion for the vorticity itself. This is often convenient. If we start with the
Euler equations

$$
	\partial_t {\vec v} + {\vec v} \cdot {\vec \nabla} {\vec v} = - \frac{1}{\rho} {\vec \nabla} p
$$

Recalling that

$$
	{\vec v} \cdot {\vec \nabla} {\vec v} = \frac{1}{2} {\vec v}^2 - {\vec v} 
	\times ({\vec \nabla} \times {\vec v} = \frac{1}{2} {\vec v}^2 - {\vec v} \times {\vec \omega}
$$

we can take the curl of the Euler's equation, using the fact that the curl of the gradient 
vanishes and that a vector has vanishing cross product with itself, to find:

$$
	\p_t \omega - {\vec \nabla} \times ({\vec v} \times {\vec \omega}) = \frac{1}{\rho^2} {\vec \nabla} \rho \times
	{\vec \nabla p}
$$

The right hand side vanishes if $p = p(\rho)$. if $\rho$ is constant, or if the fluid is isentropic.

### Incompressible flows

When the fluid is incomressible, we may write

\begin{align}
	{\vec \nabla} \times ({\vec v} \times {\vec \omega}) & = & 
	{\vec v} {\vec \nabla}\cdot{\vec \omega} - {\vec \omega} {\vec \nabla}\cdot{\vec v}
	+ {\vec \omega}\cdot {\vec v} - {\vec v} \cdot {\vec \omega}\\
	& = & {\vec \omega}\cdot {\vec v} - {\vec v} \cdot {\vec \omega}
\end{align}

where we have used incompressibility combined with the fact that the divergence of a curl vanishes.
Thus,

$$
	D_t {\vec \omega} -  {\vec \omega}\cdot {\vec v} = \frac{1}{\rho^2} {\vec \nabla} \rho \times
	{\vec \nabla p}
$$

Note that in two dimensions, the second term on the left hand side drops out and we have

$$
	D_t \omega = \frac{1}{\rho^2} {\vec \nabla} \rho \times
	{\vec \nabla p}
$$

In the cases above for which the RHS vanishes, $\omega$ is conserved all along the flow. Recall that for two-
dimensional incompressible flow, we may write ${\vec v} = (- \partial_y \psi, \partial_x \psi)$, and then
$\omega = \nabla^2 \psi$. In these cases where the RHS vanishes, the vorticity equations become a 
closed set of equations for $\psi$ which do not involve the pressure. 

### Steady incompressible flows in 2d

In this case, ${\vec v} \cdot{\vec \nabla} \omega = 0$, and the vorticity is conserved along streamlines.
In particular, if we have an object inside a fluid which is flowing from infinity and incoming fluid is
irroational far from the object, it will remain irrotational. We can then use the theory of potential
flows to describe such a system. As we will see in a few weeks (and as discussed in the text), this turns
out to be important for understanding basic aerodynamics.

However, you may recall the picture such as the dog which graces the notes of this textbook; or you may
think about what happens when you drag your hand fast enought through still water. Turbulent vortices appear.
Howe is this consistent with the above? The answer is that we have ignored the effects of *viscosity*.
As we will see starting next week, viscosity can generate and dissipate vorticity, and it becomes important
near the boundaries of the fluid. The upshot is that if one begins with slow, essentially irrotational
flow and cranks up the velocity, the boundary layer of the fluid near the object will expand and generate
a turbulent wake.

