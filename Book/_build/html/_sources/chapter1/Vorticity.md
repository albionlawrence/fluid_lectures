# Vorticity

A central concept of fluid dynamics is *vorticity*, defined in three
dimensions as
```{math}
:label: vorticity
{\vec \omega} = {\vec \nabla} \times {\vec v}
```
If you are comforable with the curl being a (pseudo)scalar in two
dimenions, the definition is basically the same. Alternate definitions
in 2d are:

$$
	\omega_{2d} = \epsilon^{ij}\partial_i v_j
$$

where $\epsilon^{ij}$ is the totally antisymmetric tensor with $\epsilon^{12} = 1$,
we are using Einstein summation notation for repeated indices, and we are 
using the notation

$$
	\partial_i \equiv \frac{\partial}{\partial x^i}
$$

[For afficionados of differential forms, if we let $v$ with lower indices
be a 1-form, $\omega = dv$ is a two-form. In 3 dimensions a two-form
is dual to a vector; in 2 dimensions it is dual to a scalar. This is the
path to defining vorticity in higher dimensions if one wanted to do that.

Vorticity is crucial for a number of reasons; physically it records how
the shape of a fluid element distorts in a nontrivial manner. 

## Motivation and interpretation

A nice discussion is in the text, I would like to offer a more general
one (see for example {cite:p}`chorin1990mathematical`.) The essential point
is that a constant velocity field ${\vec v}$ is not by itself all that
interesting (or particularly physical -- the velocity usually goes to zero at 
the boundaries).  What is interesting is when the velocity changes in space and
time. Let us focus on characerizing the former. 

Consider a velocity field $v_i({\vec x})$. Let

$$
	{\vec x} = {\vec x}_0 + \delta {\vec x}
$$

A local sense of the variation of velocity can be found by doing a Taylor
expansion. To first order in $\delta {\vec x}$, 

$$
	v_i(x_0^j + \delta x^j) = v^i(x_0) +  \delta x^j \partial_j
	v_i(x_0) + ...
$$

Again, we are using Einstein summation notation here. Now we can write

\begin{align}
	\partial_j v_i & = & \frac{1}{2}\left(\partial_j v_i + 
	\partial_i v_j\right) + 
	\frac{1}{2} \left(\partial_j v_i - \partial_i v_j\right) \\
	& = & S_{ij} + \omega_{ij}
\end{align}

$S_{ij}$ is called the *strain tensor*, and $\omega_{ij}$ is the 
*vorticity tensor*. In the second case, for $d = 2$ dimensions, 
$\omega = \epsilon^{ij} \omega_{ij}$ is the vorticity as defined in the
text. In three dimensions,

$$
	\omega^i \equiv \epsilon^{ijk} \partial_j v_k = ({\vec \nabla}\times{\vec v})^i
$$

is the usual definiion of the vorticity. Here $\epsilon^{ijk}$ is
the totally antisymmetric tensor in $d = 3$, such that $\epsilon^{123} = 1$.

Returning to an interpretation of $S$ and $\omega$, 

\begin{align}
	\delta v_i(x_0) & = & v_i({\vec x}_0 + \delta {\vec x}) - v_i({\vec x}_0)\\
	& = & S_{ij} \delta x^j + \omega_{ij} \delta x^j
\end{align}

If we adopt the Lagrangian picture, with $\delta x(t)$ corresponding to
the physical location of a fluid parcel near ${\vec x}_0$, then 
$\delta v_i = \frac{d}{dt} \delta x^i$, and we have

$$
	\frac{d}{dt} \delta x^i = S_{ij} \delta x^i + \omega_{ij} \delta x^j
$$

Now consider a blob of fluid surrounding ${\vec x}_0$ defined by a collection
of such vectors. As a symmetric matrix, $S_{ij}$ will have three real 
eigenvalues $s^{\alpha}$ $\alpha \in {1,2,3}$ and associated eigenvectors
or *principle axes* $h^{\alpha}_i$, such that 
$S_{ij} h^{\alpha}_j = s^{\alpha} h^{\alpha}_i$.
If $\delta x$ points in one of these directions, it will stretch or
shrink in time depending onthe sign of $s^{\alpha}$. In other words, 
$S_{ij}$ will cause he blob to stretch or shrink along the principle axes.

On the oher hand, if $\epsilon^{ijk} \omega_{jk} \equiv \omega^i$, then
we can use the identity

$$
	\epsilon^{ijk} \epsilon_{ilm} = \delta^j_l \delta^k_m 
	- \delta^j_m \delta^k_l
$$

to show that

$$
	\omega_{ij} = 2 \epsilon_{ijk} \omega^k
$$

and so

$$
	\omega_{ij} \delta x^j = 2 \epsilon_{ijk} \delta x^j \omega^k
	= 2 (\delta {\vec x} \times {\vec \omega})^i
$$

If $S_{ij}$ were vanishing, then

$$
	\frac{d}{dt} \delta {\vec x} = 2 \delta{\vec x} \times {\vec \omega}
$$

describes a rotation of $\delta {\vec x}$ about the axis defined by $\omega$,
with angular velocity $2|\omega|$. 

## Irrotational flows

When ${\vec \omega} = {\vec \nabla} \times {\vec v} = 0$ throughout the flow, we say the flow is *irrotational*. This
flow will have special properties. In particular, in any simply connected region, we can write
${\vec v} = {\vec \nabla} \phi$. We call $\phi$ the potential, and he associated flow potential flow.

## Two-dimensional Incompressible flow

Any vector which is divergenceless can b written as a curl (in a simply connected region). 
In three dimensions this is no obvious simplification -- you trade a vector for a vector -
but in two dimensions, this means that you can write

$$
	{\vec v} = - \partial_y \psi {\hat x} + \partial_x \psi {\hat y}
$$

for some scalar *streamfunction* $\psi$. In this case, $\omega = \nabla^2 \psi$. 
This is a useful object in two dimensions and variants are important for large-scale
atmospheric and oceanic flows: the streamfunction $\psi$ can be written as the integral of the
velocity and so becomes a measure of tansport across a line.

