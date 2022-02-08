# Linear waves

We will start with *linear waves*. Roughly speaking, this means that we start with a background solution
${\vec V}$, $\rho_0$, $p_0$ to the Navier-stokes equation, write ${\vec v} = {\vec V} + {\vec \delta v}$, 
$\rho = \rho_0 + \delta \rho$, $p = p_0 + \delta p$, and expand the
fully nonlinear equations such as

$$
	\partial_t {\vec v} + {\vec v} \cdot {\vec\nabla} {\vec v} = - \frac{1}{\rho} {\vec\nabla} p + \nu \nabla^2 {\vec v} - {\hat g} {\hat z}
$$

to first order in ${\vec \delta v}$, $\delta\rho$, $\delta p$. The result is a set of linear partial differential equations.

In the case of shear or stratified flows, with ${\vec V}$, $\rho_0$, $p_0$ depending on space (or space and time), the
equations can still be quite complicated. 

## Dispersion relations

When the background is constant, however, we get linear equations
with constant coefficients, and we ca (depending on boundary conditions) find a complete basis of solutions 
of the form $e^{i \omega t - i {\vec k}\cdot{\vec x}}$. The equations of motion 
then give a *dispersion relation* $\omega(k)$ which characterizes the dynamics of the wave. 

For example, different dispersion relations will allow for long- or short-wavelength modes to travel faster, 
meaning ripples in a fluid excited by a disturbance will be more widely or narrowly spaced, respectively, as 
one looks farther from the disturbance. Through the *phase velocity* $v_p = \omega/k$ and the *group velocity* 
$v_g = \frac{d\omega}{dk}$ (here I have written the expressions for one-dimensional flow, for simplicity's sake), 
we can work out how quickly the wave travels and evolves, and so on.

## Phase and group velocity

Let $\phi(x,t)$ solve some linear differential equation with constant coefficients. This could be the Schr\"odinger equation
$i \hbar \partial_t \phi = \frac{\hbar^2}{2m} \partial_x^2 \phi$, for which $\omega(k) = \frac{\hbar k^2}{2m}$; or the
relativistic wave equation (Klein-Gordon equation) $\partial_t^2 \phi = c^2 \partial_x^2 \phi$ for which $\omega = c k$. 

In actual solutions to linear differential equations, we build *wave packets* of the form

$$
	\phi(x,t) = \int_{-\infty}^{\infty} dk {\tilde\phi}(k) e^{i \omega(k) t - i k x}
$$

The point is that if $ e^{i \omega(k) t - i k x}$ solves the wave equation for every $k$, and the equation is *linear*, 
then sums of soluions are sill solutions (as long as the boundary conditions also hold). 

In this equation, the role of the phase velocity is reasonably clear; for a component of a given 
wavelength $k$, $v_p = \omega/k$ will tell you how fast a crest of valley will move; when $x = v_p t$, 
the phase factor for a given $k$ remains constant in $t$.

Unless $\omega(k) = ck$ for $c = v_p$ constant, each component will travel at a different speed, and we expect the
wave to *disperse* as the different wavenumbers separate. (Thus the term *dispersion relation*). To get some sense 
of the behavior of a wavepacket, let us consider one that is built from a small range of wavenumbers. This mean that
it should make sense to expand $\omega(k)$ about a fixed wavenumebr $k_0$: 

$$
	\omega(k) = \omega(k_0) + (k - k_0) \omega'(k) + 
	\frac{1}{2} (k - k_0)^2 \omega''(k_0) + \ldots \equiv \omega_0 + (k - k_0) v_g(k_0) + 
$$

Plugging this into our wavepacket above, we find:

$$
	\phi(x,t) = e^{ -i k_0 (x - v_p(k_0) t)} 
	\int_{-\infty}^{\infty} dk {\tilde\phi}(k) e^{- i (k- k_0) (x - v_g t) - \ldots}
$$	

The integrand controls the shape or *envelope* of the wavepacket in $x$; and clearly this
envelope moves with velocity $v_g$. If we think of a wave with wavenumber $k_0$ modulated
by some envelope function

$$
	\psi(x) = \int_{-\infty}^{\infty} dk {\tilde\phi}(k) e^{- i (k- k_0) (x - v_g t) - \ldots}
$$

the wave and the envelope will generally travel at different speeds.

As a concrete example, we can choose

$$
	{\tilde \phi}(k) = {\tilde \phi}_0 \ell \sqrt{\pi} e^{-\frac{\ell^2 (k - k_0)^2}{4}}
$$

In this case the Fourier integral above can be done explicitly, and we find

$$
	\phi(x,t) = \frac{{\tilde \phi}_0 \ell}{2} 
	\frac{e^{i \omega_0 t - i k_0 x}}{\sqrt{\frac{\ell^4}{16} + \frac{t^2 (\omega''(k_0))^2}{4}}}
	e^{- \frac{(x - \omega'(k_0) t)^2}{\ell^2 + 4\frac{t^2}{\ell^2} (\omega''(k_0))^2}}
$$

Here we see that $v_g = \omega'$ gives he velocity of the packet; higher derivatives of $\omega$ 
cause dispersion and distortion of the packet.

So far we have been discussing waves propagating in 1 dimension. In higher dimensions, the most natural
definition of the group velocity is as a vector ${\vec c}_g = {\vec nabla} \omega(k)$. This will have
a definite direction depending on the velocity. The results cam sometimes be surprising for water waves.
For solutions to the wave equation $c_s^2 \partial_t^2 \phi - c_s^2 {\vec\nabla}^2 \phi = 0$ (for some $c_s$), 
$\omega = c_s \sqrt{\vec k}^2$, so ${\vec c_g} = c_s {\hat k}$, where ${\hat k}$ is the unit vector pointing
along ${\vec k}$. In other words, the group velocity vector points along wavefronts. For *internal gravity
waves*, which we will discuss, in a certain short wavelength limit, the group velocity is *parallel* 
to the wavefronts. 

## Group velocity and the large-time response

For dispersive waves, at sufficiently large times, we expect the different wavelengths to saeparate out in space.
In this setup, we expect that *locally* in space and time, the wavenumber will be reasonably constant and vary slowly ($\Delta k/k \ll 1$.
where $\Delta k$ is the variation over a wavelength in space or a period in time), and that
it will vary slowly in. The mathematics in this situation is close to that of geometric optics and
the WKB approximation.

Given some wave equation we will consider a solution of the form $\phi(x,t) = {\rm Re} A(x,t) e^{i\theta(x,t)}$. Of course we can always
write $\phi$ in such a form: the question is whether it is meaningful to do so. The upshot is that we are assuming in this
presentation that $A$ is slowly varying in $x,t$, 

If we define

$$
	k = \frac{\partial\theta}{\partial x}\ ; \ \ \omega = - \frac{\partial \theta}{\partial t}\ ,
$$

we can write

$$
	\theta = \int \left[ k dx - \omega dt \right]
$$

Given this equation,

$$
	\partial_t k + \partial_x \omega = 0 = \partial_t k +  \partial_x k \partial_k \omega = \partial_t k + c_g  \partial_x k
$$

That is, if we follow a trajectory moving with the group velocity, $k$ will remain constant. NOte this generalized naturally to higher
dimensions:

$$
	\partial_t {\vec k} + {\vec c}\cdot{\vec \nabla} {\vec k} = 0
$$

(These equations are central to ray tracing, a technique used when the variation of the local
wavelength is slow, essentially the geometric optics approximation). The solution is:

$$
	k(x,t) = f(x - c_g(x,t) t)
$$

This is a bit implicit but it does encode the fact that $k$ remains constant along the lines $x = c_g(k) t$ 
from which we can see that if $c_g(k)$ is not constant, some wavenumebrs will move faster than others, 
indicating dispersion. 

If we build up a wave packet with Fourier modes, this form can be justified for large $x,t$ by the *stationary phase* 
approximation. It is worth sketching this out. Consider a wavepacket

$$
	\phi(x,t) = \int \frac{dk}{2\pi} e^{i k x - i \omega(k) t} {\tilde \phi}(k)
$$

In the lage $x,t$ limit the exponential will generally be varying very rapidly with $k$ and these oscillations will integrate to
nearly zero. The only regions that will contribute ae those near which the argument $\theta$ of the integral satisfies 
$\partial_k \theta = 0$. This will occur when $x = \partial_k \omega(k) t = c_g t$, and we can rougly write:

$$
	\phi(x,t) \sim e^{i k(x,t) - i \omega(k(x,t)) x} {\tilde \phi}(k(x,t))
$$

A more careful treatment will give additional contributions to the prefactor of the integral.
