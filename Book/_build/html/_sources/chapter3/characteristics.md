# The Method of Chaacteristics

```{math}
\newcommand{\p}{\partial}
```

## Introduction

The essential point of the method of characteristics is as follows.
Let us say we have a equation

$$
	\p_t u + A(x,t,u) \p_x u = 0
$$

This is a nonlinear first order differential equation. We looks for
paths $t(s), x(s)$ such that $u$ is constant all along the
path. Using the chain rule, we find:

$$
	\p_s u = \p_s t \p_t u + \p_s x \p_x u = 0
$$

If we choose $\p_s t = 1$, $\p_s x = A$, then $\p_s u = 0$ by 
the equations of motion. he game, then, is to solve these
equations to find a set of lines in $(t,x)$ on which $u$ is constant.
If we can do so, then if for example the line $t = 0$ crossed these
lines transversally, then we can propagate the initial data along the 
characteristics.

This can be generalized to the case of multiple variables (we will
study a case with two).  In general, the quantities conserved along the
characteristics will be called *Riemann invariants* and there is a procedure
for at leas trying to identify them. A more general discussion can be found
in Chapter 3 of {cite:p}`chorin1990mathematical`; we will actually discuss
the case of 2 variables ($u$ and $h$ for the shallow water equations.  
In this more general case, there are separate families of 
characteristics for each invariant and one will not be constant along
the other's characteristics.

Note also:

- There is no guarantee that we can *find* the characteristics.

- If the characteristics cross, we hit a discontinuity as the invariants
will jump across the locus where hey meet; in other words we will hit a shock. 
This is a case we will discuss.

## Example: linear equations

Let us consider the simple case

$$
	\p_t u + a(x,t) \p_x u = b(x,t)
$$

where $a,b$ are known. Here we demand

\begin{align}
	& & \p_s t = 1\\
	& & \p_s x = a(x,t)
\end{align}

These are first order (nonlinear) ODEs which can in principle be solved
to find the characteristics.  In this case,

$$
	\p_s u(t(s),x(s)) = b
$$

so that $v + \int_{s_0}^s d\tau b(x(\tau),t(\tau))$ is conserved 
along characteristics.

In the simple case that $b= 0, a = v$, the characteristics are:
$t = s$ (here we choose $s$ to remove the integration constant), 
$x = v s + x_0$, that is, they are straight lines $x - v t = x_0$.
Given any initial condition $v(x,0) = v(x_0)$, the solution is then
$v(x - vt)$. 

## Example: shallow water equations

Here we return to the SWEs for one hoizontal direction:

\begin{align}
	& & \p_t u + u \p_x u = - g \p_x h\\
	& & \p_t h + \p_x (u h) = 0
\end{align}

Here we have two equations. In fact we can unpack them by defining
$c = \sqrt{g h}$ (for linearized surface gravity waves in the shallow water
limit, this is the phase velocity), for which the equations can be written

\begin{align}
	& & \p_t u + u \p_x u + 2c \p_x c = 0\\
	& & \p_t (2c) + u \p_x (2c) + c \p_x u = 0
\end{align}

The sum and difference give:

$$
	\left[ \p_t + (u \pm c) \p_x \right] (u \pm 2c) = 0
$$

For these cases, we have two families of characteristics,

\begin{align}
	& & \p_s t = 1\\
	& & \p_s x = u \pm c
\end{align}

along which the Riemann invariants $\Gamma_{\pm} = u \pm 2c$ are conserved.
The game now is to solve the characteristic equations, which we will do in two
specific situations.
