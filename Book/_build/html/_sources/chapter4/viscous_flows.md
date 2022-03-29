# Flows at low Reynolds number

```{math}
\newcommand{\p}{\partial}
```

In our discussion of wave motion we have been focusing on the inviscid limit
of the fluid equations. There is much more to say about this limit, which is
important for many "real-world" ("real-universe?") applications. 

To fill out our picture of the range of fluid motion, we will spend osme time
considering flows with extremely *low* viscosity.

## Generalities: "Creeping Flow"

Let us return to the full Navier-Stokes equations:

$$
	\p_t {\vec u} + {\vec u}\cdot{\vec\nabla}{\vec u} = 
	- \frac{1}{\rho}{\vec \nabla} p + \nu \nabla^2 {\vec u} + 
	{\vec f}_{external}
$$

The last term corresponds to an externall applied force, and we shall ignore
it. 

Now we consider an object in this fluid with characteristic size $R$,
and the fluid velocity ar from this object having a characteristic scale $U$.
The time scale for a fluid element to cross the object is $T = R/U$.

If we assume that 

$${\vec u}({\vec x},t) = U {\vec {\tilde u}}({\vec x}/R = \chi, t/T = \tau) $$

such that 

$$ {\tilde {\vec u}},\ \p_{\chi} {\tilde {\vec u}},\ \p_{\tau} {\tilde {\vec u}}
\sim {\cal O}(1)\ ,$$

then the left-hand side of the Navie-Stokes equation scales as $U^2/R = U/T$,
while the viscosity term on the right hand side scales as $\nu U/R^2$.
This latter term dominates over the left hand side if

$$
	Re = \frac{(U^2/R)}{\nu U/R^2} = \frac{U R}{\nu} \ll 1
$$

that is, if the Reynolds number is small. In this chapter we take
this to be true, and assume the pressure erm is of order the viscosity
term.

By way of interpretation, note that $U_{visc} = \nu/R$ has dimensions
of velocity, and we can thus write $Re = U/U_{visc}$. Thus, viscosity 
will become more important than the kinematic transport of fluid momentum
when the velocity is low: thus, low-viscosity flow is sometimes 
called *creeping flow*.
