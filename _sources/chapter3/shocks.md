# Shock waves in gas dynamics

```{math}
\newcommand{\half}{\frac{1}{2}}
\newcommand{\p}{\partial}
```

## 1d homentropic flow

We start with the momentum equation and the equations for
mass conservation:

\begin{align}
	& & \p_t u + u \p_x u = - \frac{1}{\rho} \p_x p\\
	& & \p_t \rho + \p_x (\rho u) = 0
\end{align}

We also assume that the gas is *homentropic*: that is, that the entropy
takes the form $S = \ln p/\rho^{\gamma} \equiv \ln c$ is not just 
conserved for each fluid element (as in (3.57) of Acheson), but constant 
throughout the flow. We will now solve Acheson problem 3.22 to find 
equations for the 1d homentropic gas which are more suitable for analysis 
via the method of characteristics. 

Letting $p = c \rho^{\gamma}$, we find

$$
	\p_t u + u \p_x u = - c \gamma \rho^{\gamma - 2} \p_x \rho
$$

Now let $a^2 = \gamma p/\rho = \gamma c \rho^{\gamma - 1}$ be the speed of sound
for small fluctuations about $u = 0$ and $p, \rho$ the background pressure and
density. Following the shallow water equation analysis, we will recast
our equations in tems of $u$ and $a$. 

Taking the derivative of the definition of $a^2$, we find

$$
	a \p_x a = \half \gamma c (\gamma - 1) \rho^{\gamma - 2} \p_x \rho
$$

so that

```{math}
:label: finalme
\p_t u + u \p_x u +  \frac{2}{\gamma - 1} a \p_x a = 0
```

Next, we recast the mass conservation equation as

$$
	\p_t \rho + u \p_x \rho + \rho \p_x u = 0
$$

By the same arguemnt as above, 
	
$$
	a \p_t a = \half \gamma c (\gamma - 1) \rho^{\gamma - 2} \p_t \rho
$$

Multiplying the mass conservation equation by 
$\frac{\gamma c}{a} \rho^{\gamma - 2}$, we find

$$
	\frac{2}{\gamma - 1} (\p_t a + u \p_x a) + a \p_x u = 0
$$

Finally, adding and subtracting this form of the mass conservation equation
from {eq}`finalme`, we get the equations

$$
	& & \left( \p_t + (u + c) \p_x\right) (u + \frac{2}{\gamma - 1} a)\\
	& & \left( \p_t + (u - c) \p_x\right) (u - \frac{2}{\gamma - 1} a)
$$ (swe_like)

You may realize at this point that these equations are very close to tose
for the shallow water equations with $c \to a$, except for the factor
of $\gamma - 1$ in the denominators of the right hand side.

## Moving piston

Now we can consider an analog of the todal bore problem, a piston moving 
with velocity $U = \alpha t$ into a gas that has initial sound speed $a_0$ 
and initial velocity $u = 0$. We can follow the discussion of the SWEs,
defining characteristic failies

$$
	C_{\pm}:\ \p_s t(s) = 1\ , \ \ \p_s x(s) = u \pm a
$$

with associated Riemann invariants

$$
	\Gamma_{\pm} = u \pm \frac{2}{\gamma - 1} a
$$

Once again, for $t < 0$, $u = 0, a = a_0$, 
$\Gamma_{\pm} = \pm  \frac{2}{\gamma - 1} a_0$, and the characteristics are

$$
	C_{\pm}:\ t = s\ ; \ \ d_t x = \pm a_0
$$

so characteristics are straight lines. As we continue to positive $t$, this
story continues until the $C_-$ geodesics hit the line $x = a_0 t$. Finally,
we can continue the $C_-$ geodesics past this point to the piston boundary at 
$x = \half \alpha t^2$. In this region the Riemann invariant $\Gamma_-$
is still

$$
	u - \frac{2}{\gamma - 1}a = - \frac{2}{\gamma - 1} a_0
$$

we can use this to solve for $a$ and apply the solution to the first equation
in {eq}`swe_like` to get:

$$
	\p_t u + \left(\half(\gamma+1) u + a_0\right) \p_x u = 0
$$

Defining $z = (\half(\gamma+1) u + a_0$ we once again find 
$\p_t z + z \p_x z = 0$. In analogy to teh shallow water equations,

$$
	u = F(x - (\half(\gamma + 1)u + a_0)t)
$$

At time $t = 2 a_0/((\gamma + 1)\alpha)$ the solutions become singular;
in this case the resulting singularity is called a *shock*. 

## Matching solutions across shock fronts

As in the case of the hydraulic jump, while we may not be able to describe
the shock itself without a fuller microscopic description, we can
constrain the flow on both sides of the shock. Here we demand not only
conservation of mass and momentum flux, but conservation of energy flux.
This last is distinct from the hydraulic jump case, in which we assume
the region at the jump can dissipate energy. The point here is that the
shock front is expected to be extremely thin; alhough in practice dissipative
processes are important inside the shock front, the front is too thin for these processes to deplete energy of fluid moving through it.

The result are the *Rankine-Hugoniot equations*:

$$
	& & \rho_1 u_1 = \rho_2 u_2\\
	& & p_1 + \rho_1 u_1^2 = p_2 + \rho_2 u_2^2\\
	& & \half u_1^2 + \frac{1}{\gamma - 1} a_1^2 = \half u_2^2 + 
	\frac{1}{\gamma - 1} a_2^2
$$

Finally, we demand that the entropy $S = \ln p\rho^{-\gamma}$ should increase
as fluid flows across the shock, so that

$$
	p_2 \rho_2^{-\gamma} \geq p_1 \rho_1^{-\gamma}
$$

In this case the Froude number (the ration of the fluid velocity to the
velociy of surface waves in the shallow water limit) is replaced by the Mach
number $M_i = u_i/a_i$. In the present case, some work leads to 

- $M_1 > 1$, $M_2 < 1$.
- $p_2 > p_1$, $\rho_2 > \rho_1$.
	


