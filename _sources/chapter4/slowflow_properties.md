# General properties of creeping flow

```{math}
\newcommand{\p}{\partial}
```

Before continuing we wish to break and describe two general (and important!) 
properties of the creeping flow equations: first, that for fixed boundary 
conditions, a given solution is *unique*; second, that the solutions
are *reversible* (also known as the "scallop theorem"): if we flip the
sign of the boundary conditions, we flip the sign of the whole flow,
which presents a chalenge for low-$Re$ swimming.

## Uniqueness

The first thing we wish to show is that for fixed Dirichlet boundary conditions
${\vec u}({\vec x})\Big|_B = {\vec u}_B({\vec x})$, the solutions to the
creeping flow equations are *unique*. Note that the equations

```{math}
:label: creep
	& - {\vec\nabla} p + \eta \nabla^2 {\vec u} = 0\\
	& {\vec\nabla}\cdot{\vec u} = 0
```

have no time derivatives. This means that the solution at *any* time is
governed by the boundary conditions, and time-dependent flow will
only occur throug time-dependent boundary conditions. This is very much 
in contrast to the full Navier-Stokes equations, in which the time
derivative matters, and solutions depend on initial conditions.

To see this we consider the possibility that there are two solutions,
${\vec u}_{i=1,2}$ and $p_{i=1,2}$, satisfying the same boundary 
conditions ${\vec u}_i({\vec x})\Big|_B = {\vec u}_B({\vec x})$. 
Because the creeping flow equations are linear, the difference 
${\vec V} = {\vec u}_2 - {\vec u}_1$, $P = p_2 - p_1$ 
also solves the creeping flow equations with ${\vec D}\Big|_B = 0$.

Now let us take the dot product of ${\vec V}$ with ({ref}`creep`)
acting on $P,{\vec V}$, and integrate the result over the domain D
with boundary $\p D = B$:

$$
	\int_D d^d x \left(- \Delta^i \nabla_i P + \eta V^j \nabla^i \nabla_i V_j\right) = 0
$$

Here I have expressed the dot product in terms of sums over indices, using Einstein summation notation,
to make sure we get the next step right, and kept the dimension general (could be 2 or 3, or 10, or whatever). 
We now wish to integrate the result by parts. Since the
boundary terms are proportional to $V$ (with no derivative acting on it), they will vanish.
Furthermore, upon integrating by parts, the bulk part of the first term is proportional to
$\nabla^i V_i \equiv {\vec\nabla}\cdot{\vec V}$, which vanishes due to incompressibility of 
both ${\vec u}_i$. Thus, we are left with

$$
	\eta \int_D d^d x \p_i V_j \p_i V_j= 0
$$

But this is a sum (over $i,j$ of squares at every point in $D$, which means that $\p_i V_j = 0$
for every $i,j$ and every point in $D$. Because it is true for very $i$, $V_j$ must be constant
in every direction. Since it vanishes at the boundary, it must vanish everywhere, and
${\vec v}_1 = {\vec v}_2$, thus proving uniqueness.

## Reversibility

The next statement follows from the above statement, together with the fact that the creeping flow
equations have no time derivatives. Note that our argument about uniqueness was completely independent
of time. Thus, the flow at any time is completely detemined by the boundary conditions at a given time.
This is of course not exactly physical -- knowledge that the boundary has moved should propagate with
some speed less than that of light! -- but is a result of our approximation. Nonetheless, or slow, low-$Re$ flow it
is basically correct. 

A particular consequence is that the equations are *time-reversible*. Time reversal at a given time 
flips the sign of ${\vec u}$ -- imagine a movie of a agged fluid parcel suddenly run backwards in time.
The solution with ${\vec u} \to - {\vec u}$ is a solution with the reversed boundary conditions 
${\vec u}_B \to - {\vec u}_B$, and is in fact the unique solution. A particular consequence, beautifully described
in {cite:p}`purcell1977life`, is that attempts to swim by a motion followed by its reverse will produce no net
motion of the body. This is called the "Scallop theorem" by Purcell, as you can imagine a scallop trying to
move by opening and closing its hinge. At high Reynolds number, it could close quickly, jet forward, and then
open slowly. At low Reynolds number this will not work and you need to swim by some more complex protocol
involving a nontrivial cycle in the space of shapes of your body.
