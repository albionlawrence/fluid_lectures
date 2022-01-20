# Equations for Ideal Fluids

We will derive the equations of fluid dynamics somewhat more systematically 
later in the course. Our goal here is to write down some basic equations
and make them plausible. Recommended texts: {cite:p}`chorin1990mathematical,falkovich_2018,salmon1998lectures`.

## 1. Variables

### A. Background. 

We are going to imagine fluids in spac which is
some domain of ${\mathbb R}^d$. We will focus on solutions in $d = 2,3$.
$d = 2$ is often useful for large-scale ocean and atmospheric dynamics
as the aspect ratio of vertical to horizontal scales is small.

### B. Lagrangian description

In the continuum hypothesis we can consider a fluid as a collecion of
infiniesimal parcels. Each parcel will have a trajectory ${\vec x}(t)$,
and an associated velocity
```{math}
:label: lag_vel
{\vec v}({\vec x}(t),t) = \frac{d}{dt} {\vec x}(t)
```
We then assign each fluid particle a density $\rho({\vec x}(t), t)$,
temperature, and so on. The description is natural in terms of understanding
a fluid as a collection of parcels which are acted on by external forces
and by each other. It is also natural for certain types of measurements
such as [autonomous floats](http://www.argo.net/) in oceanography, and in
understanding the transport of materials (pollutants in the ocean and 
atmosphere).

### C. Eulerian description

In practice we often cannot or do not follow fluid parcels; rather we take
measurements at points in space and time as determined by our apparatus:
oceanographic moorings, measurements taken from ships or airplanes, and so on.
The description of fluid quantities ${\vec v}({\vec x},t)$, $\rho({\vec x}, t)$
at points in space and time is known as the *Eulerian description*.
This description is the dominant one used in fluid dynamics. It is
also the natural framework in which to do numerical experiments.

**Trajectories and streamlines**. In this language, we have two 
interesting sets of integral curves which
are discussed often. The first is the *trajectory* ${\vec x}(t)$. That is,
given ${\vec v}({\vec x},t)$, and some initial condition ${\vec x}(t_0)$,
the solutions to 
```{math}
:label: trajectory
\frac{d}{dt} {\vec x}(y) = {\vec v}(x,t)
```
has a unique solution which describes a line in ${\mathbb R}^d$. This solution
is a *trajectory*, one can think of it as the path in space and 
time of an object (autonomous float, phytoplankton, rubber duck) 
moving with a fluid parcel.

The second is the *streamline*. This is a representation of the velocity field
at *fixed* time. Here we introduce a parameter $s$, and solve the equation
```{math}
:label: streamline
\frac{\partial}{\partial s} {\vec x}(t,s) = {\vec v}({\vec x},t)
```
These are the integral curves for te velocity at a given time. If we placed
a large collection of little grains which moved with the fluid, a time lapse
photo of their motion over an infinitesimal time would show streamlines.


In general, if ${\vec v}$ is time-dependent, the streamlines and the 
trajectories will differ. The trajectories are only defined in space 
and time (although we  can plot the curves in space), while the
streamlines are defined at fixed time and the entire set of lines move with
time. The two only coincide when the velocity field is time-independent.


## 2. Equations

```{math}
:label: newton_second
\frac{d}{dt} {\vec p} = {\vec F}
```

where ${\vec p}$ is the momentum of a fluid parcel, and ${\vec F}$ is the
force acting on this parcel. We also assume that the mass of the parcel is
conserved: its density $\rho$ and volume $\delta V$ can change with time,
but 
```{math}
:label: mass_cons
\frac{d}{dt} m({\vec x}(t).t) = \frac{d}{dt} \rho \delta V = 0
```

### A. Continuity equation

Consider a fluid inside a fixed volume $W$. The total mass inside this volume
is 
```{math}
:label: mass_euler
M(W,t) = \int_W d^d \rho({\vec x},t)
```
Because the volume is fixed, 
```{math}
:label: mass_change
\frac{d}{dt} M = \int_W d^d x \frac{\partial \rho}{\partial t}
```
On the other hand, the total rate of mass flux into the volume is the
density times the velocity flux through the boundary 
surface ${\partial W}$:

\begin{align}
	\frac{d}{dt} M & =  - \int_{\partial W} d{\vec A}\cdot \rho {\vec v}\\
	& = \int_W d^d x {\vec \nabla} \cdot (\rho {\vec v})
\end{align}

where we have used the divergence theorem to rewrite the surface integral.
These definitions of $d_t M$ must be the same for any volume $W$, so we
finally have the continuity equation:
```{math}
:label: continuity
\frac{\partial \rho}{\partial t} + {\vec \nabla}\cdot (\rho {\vec v}) = 0
```

The focus of this course (not exclusive!) will be on  *incompressible fluids*. 
We can define these as fluids for which the density of a parcel does not 
change along a trajectory. In this case,
```{math}
:label: incomp
\frac{d}{dt} \rho({\vec x}(t), t) = \frac{\partial}{\partial t} 
\rho + {\vec v}\cdot {\vec\nabla} \rho \equiv D_t \rho = 0
```
Note that here we have defined he *convective derivative*


Combining this with the continuity equation gives us
```{math}
:label: nodiv
{\vec \nabla}\cdot {\vec v} = 0
```
Note that Acheson defines an ideal fluid as having constant
density. This plus the continuity equation implies that the velocity is
dovergence-free. In other references incompressibility, and not
constant density, is part of the crierion for an ideal fluid. We 
should note that there are important examples
of incompressible fluids which have variable density.

### B. Euler's equation

The next step is to write dynamical equations for the motion of the fluid.
We start with Newton's laws for a parcel. If the momentum is
```{math}
{\vec p} = M {\vec v}({\vec x}(t), t) = \rho \delta V {\vec v}({\vec x}(t), t)
```
then combining mass conservation with the chain rule, we find:
```{math}
\frac{d {\vec p}}{dt} = \delta V \rho \left(\frac{\partial}{\partial t}
{\vec v} + {\vec v}\cdot {\vec \nabla} {\vec v}\right) 
```
This is set equal to the force on the parcel. 

To complete the equations, we need an expression for the force
on a fluid parcel.  The force will get contributions from sources 
external to the fluid, such as gravity, and from the force due to 
neighboring parcels.

If we take the external force *per unit mass* on the particle to 
be ${\vec f}$, the total force will ${\vec F} = \rho \delta V {\vec f}$. 
An important example is a constant gravitational field acting on
the fluid, for which ${\vec f} = - g {\vec z}$, where $g$ is the gravitational
acceleration amd ${\vec z}$ the vertical direction.

An *ideal fluid*, in addition to being incompressible, is one in which 
the force exerted on a fluid parcel by neighboring parcels takes a specific
form. In particular, there is no shear stress exerted by one parcel on another:
the force is always perpendicular to the surface of the parcel, and takes the
form 
```{math}
{\vec f}_A = - p({\vec x},t) {\hat n}
```
where $p$ is some scalar quantity and ${\vec n}$ is he unit normal pointing
outward from the surface boundary. Noe that by Newton's thurd law, the
parcel will exert the force $p({\vec x},t) {\hat n}$ on the neighboring
parcel, for which $-{\hat n}$ is the unit normal pointing outwards from
that parcel. Integating ${\vec f}_A$ over the surface of the parcel, 
we find the total force on a parcel in volume $W$ is
```{math}
{\vec F} = - \int_{{\partial W}} d{\vec A} p = - \int_W
{\vec \nabla} p \sim - \delta V {\vec \nabla} p
```
where $\delta V$ is the volume of $W$. We identify $p$ with the *pressure*. 
Adding all of the forces together and dividing the whole momentum
equation by $\rho$ we get *Euler's equation*:
```{math} 
D_t {\vec v} = - \frac{1}{\rho} {\vec \nabla} p 
- \frac{1}{\rho} {\vec F}_{ext}
```

### C. Boundary conditions

To solve the above equations we will have to impose boundary conditions.
Since the equations of motion are first order in space, we can guess that
we only need a single boundary condition. This is not meant to be
completely obvious! 

A physical boundary condition is

$$
	{\vec u} \cdot {\vec n}\big|_{boundary} = 0
$$

where ${\vec n}$ is the unit normal at the boundary. That is, the
fluid should not be allowed to leave the boundary of the system. Certainly
there are times when you might want a different boundary condition.
For example, you may want to describe what is going on behind a filter mask.
This kind of boundary conition is in many ways a forefront subject. 
[This paper](https://journals.aps.org/prfluids/abstract/10.1103/PhysRevFluids.6.090501) 
shows that such a boundary condition leads to some real differences in how 
transported material is *mixed* by the fluid.

