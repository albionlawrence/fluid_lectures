# Simple solutions in cylindrical coordinates

## Writing the Navier-Stokes equations

### Vectors and derivatives

We work in cylindrical coordinates $(r,\theta,z)$. There is a natural local basis of orthonormal vectors
${\hat e}_r(\theta)$, ${\hat e}_{\theta}(\theta)$, ${\hat e}_z$. It is important that the directions of
the first two of these depend on theta.

We can expand a vector such as velocity in these coordinates as: 

$$
	{\vec u} = u_r {\hat e}_r + u_{\theta} {\hat e}_{\theta} + u_z {\hat e}_z
$$

In taking derivatives of such a vctor, we must take into account that $\partial_{\theta} {\hat e}_r = {\hat e}_{\theta}$,
and $\partial_{\theta} {\hat e}_{\theta} = - {\hat e}_r$ (${\hat e}_z$ is constant). Thus, 

$$
	\partial_{\theta} {\vec u} = \left(\partial_{\theta} u_r - u_{\theta}\right){\hat e}_r 
	+ \left(\partial_{\theta} u_{\theta} + u_r\right) {\hat e}_{\theta} + \partial_{\theta} u_z {\hat e}_z
$$

This is the basis for the formulae in (A.35) of Acheson.

## Steady flow between rotating cylinders. 

Consider a fluid between concentric cylindrs with radii $r_1 < r_2$, rotating with angular velocities $\Omega_{1,2}$ about $r = 0$. 
We are interested in a static solution with constant pressure throughout. We expect that the velocity will be entirely in the
$heta$ direction and that it will be independent of $\theta, z$. The $\theta$ component of the Navier-Stokes equation for $u_{\theta}(r,t)$ is:

$$
	\nu \left( \partial_r^2 u_{\theta} + \frac{1}{r} \partial_r u_{\theta} - \frac{1}{r^2} u_{\theta}\right) = 0
$$

These equations are homogenous in $r$. Each term, actng on $r^k$, outputs the same power of $r$. We thus take the ans&auml;tz 
$u_{\theta} = c r^{\alpha}$ and get the *indicial equation* $\alpha (\alpha - 1) + \alpha - 1 = \alpha^2 -1 = 0$.
The solutions ae $\alpha = \pm 1$, so that

$$
	u = \frac{B}{r} + A r
$$

From here we can apply the "no-slip" boundary conditions $u(r_k) = r_k \Omega_k$ and solve for $A,B$:

$$
	A = \frac{\Omega_2 r_2^2 - \Omega_1 r_1^2}{r_2^2 - r_1^2}\ ; B = \frac{(\Omega_1 - \Omega_2) r_1^2 r_2^2}{r_2^2 - r_1^2}
$$


