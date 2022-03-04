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

If we choose $\p_s t = 1$, $\p_s x = A$, then $\p_s u$ = 0$ by 
the equations of motion. he game, then, is to solve these
equations to find a set of lines in $(t,x)$ on which $u$ is constant.
If we can do so, hen if for example the line $t = 0$ crossed these
lines transversally, then we can propagate the initial data along the 
characteristics.
