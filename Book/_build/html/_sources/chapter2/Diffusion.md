# Introduction to diffusion

In the Navier-Stokes equation, $D_t {\vec v} = - \frac{1}{\rho} {\vec\nabla} p + \nu \nabla^2 {\vec v}$, the vorticity
term appears somewhat as a "diffusion term". To understand what is meant by this, let me introduce a couple of
comments about diffusion (as I don't know how many of you have encountered it yet).

Einstein showed that the probability distrubution of a set of random walkers followed a diffusion equation

$$
	\partial_t P({\vec x},t) = D \nabla^2 P
$$
where $P(x,t)$ is the probability density of the particle: that is, $P dx$ is the probability to find the
particle in an interval $[x- \frac{1}{2} dx, x + \frac{1}{2} dx]$.

This can be thought of as the equation for the density of some "tracer particles" in a static fluid, which move
by random Brownian motion (every time $\delta t$, the particle moves some fixed $\delta x$ with uniform
probability in any direction), scattering off of the fluid particles. In one dimension, the derivation is
straightfoward:

$$
	P(x, t + \delta t) = \frac{1}{2} (P(x + \delta x, t) + P(x - \delta x, t))
$$

Expanding the left hand side to leading nontrivial order in $\delta t$,

$$
	P(x, t + \delta t) = P(x, t) + \delta t {\dot P}(x, t)
$$

When expanding the right hand side, the terms linear in $\delta x$ cancel. The terms $P(x,t)$ cancel in the equation
so we are left with

$$
	\delta T \partial_t P = \frac{1}{2} \delta x^2 \partial_x^2 P + ...
$$

we have left out higher orders in $\delta t$, $\delta x$. This is he diffusion equation with 
$D = \frac{\delta x^2}{2\delta t}$. Nete that this has the same dimension as the kinematic viscosity,
as it must, since it converts the Laplacian into something with dimensions of a time derivative.
For multiple diffusing particles, we can replace $P$ with the density (thinking of the density as the
probability of a single particle being at a given position, times the number of particles).

It is worth noting that if we set $t - = i \tau$, we get something with the mathematical structure of
the (free) Schr&ouml;dinger equation. This is sometimes a useful trick (for example if you know solutions
to one, you can do this rotation to get solutions to the other. More generally just as the wave function
has an interpretation in terms of a Feynman path integral, such diffusive systems have a path integral
representation.)

Solutions of this equation spread out or diffuse in time. A classic example is a solution such that

$$
	P(x,0) = \delta(x)
$$

corresponding to a particle (or collection of particles) starting at a fixed location. The corresponding
solution to the diffusion equation is

$$
	P(x,t) = \frac{1}{\sqrt{2 Dt}} e^{-\frac{x^2}{4Dt}}
$$

Note in this equation that the width of the distribution scales as $\Delta x \sim \sqrt{2 D t}$. This is characteristic
of diffusion processes and can be guessed from dimensional analysis. If we assume that $P$ varies by order ${\cal O}(1)$ 
over time scale $T$ and distance scale $X$, $P = P(t/T, x/X)$ and we assume derivatives of the arguments are 
order ${\cal O}(1)$. Setting $t = T \tau$, $x = L y$, 

$$ 
	\partial_{\tau} P = \frac{T D}{L^2} \partial_y^2 P
$$

Since by supposition the deivatives are order 1, $L^2 \sim T D$.

These equations can be solved by Fourier transform. We know that we can write

$$
	P(x,t) = \int_{-\infty}^{\infty} \frac{dk}{\sqrt{2pi}} {\tilde P}(k,t) e^{i k x}
$$

In terms of this integral, the diffusion equation becomes

$$
	\int_{-\infty}^{\infty} \frac{dk}{\sqrt{2\pi}} \left(\dot{\tilde P} + D k^2 {\tilde P}\right) e^{i k x} = 0
$$

Integrating the above over $\int_{-\infty}^{\infty} \frac{dx}{\sqrt{2\pi}} e^{-i q x}$ and using

$$
	\int_{-\infty}^{\infty} \frac{dx}{2\pi} e^{i x (k - q)} = \delta(k - q)
$$

we find $\dot{\tilde P} + D k^2 {\tilde P} = 0$, solved by $P(k,t) = P(k,0) e^{- D k^2 t}$. For delta function
initial conditions above, $P(k,0) = \frac{1}{\sqrt{2\pi}}$. Thus,

\begin{align}
	P(x,t) & = & \int_{-\infty}^{\infty} \frac{dk}{\sqrt{2pi}} {\tilde P}(k,t) e^{i k x}\\
	& = & \int_{-\infty}^{\infty} \frac{dk}{2\pi} e^{i k x - D k^2 t}
\end{align}

This is just a Gaussian integral. Complete the square in the exponential, 

$$
	D k^2 t - i k t = Dt (k^2 - \frac{ix}{Dt} k - \frac{x^2}{4 D^2t^2}) + \frac{x^2}{4 Dt}
$$

and using

$$
	\int_{-\infty}^{\infty} dx e^{-\alpha x^2} = \sqrt{\frac{\pi}{a}}
$$

we get the desired answer.

The diffusion equation is central in fluid mechanics problems both for understanding viscosity and when the
fluid is transporting additional quantities. This could be thermodynamic quantities like temperature, or
the concentration of some chemical like salt or carbon. For example, if $p = p(\rho, T)$ is the equation
of state, the Navier-Stokes equation plus mass conservation $D_t \rho = 0$ no longer close (there are four equations for
five unknowns ${\vec v}$, $\rho$, $T$); we need an equation for $T$ which is typically 

$$
	D_t T = D_{temp} \nabla^2 T
$$

where $D_{temp}$ is the *thermal diffusivity* (do not confuse it with a derivative operator such as $D_t$. Unfortunately
this notation is canonical in the literature). Actually in the ocean and atmosphere a slightly differnt quantity 
known as *potential temperature* is used, but that is a longer story. 

These equations are known as *advection-diffusion* equations. Advection refers to the ${\vec v}\cdot{\vec \nabla} T$ term in $D_t$, describing the time derivative of the quanity along a fluid trajectory; without diffusion, blobs of a quantity move with the fluid. If $D = 0$ and the velocity is constant in the $x$ direction for example,

$$
	T(x,t) = T(x - vt)
$$

is a solution.
