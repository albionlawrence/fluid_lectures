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
