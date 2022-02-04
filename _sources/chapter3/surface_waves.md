# Surface waves

We will open with waves on the surface of an *inviscid* fluid, bounded from above by another 
fluid (think the ocean and atmosphere), in a small-amplitude regime so that we
can linearize the equations of motion about a static configuration with a flat
interface. As with any physical small oscillation, waves arise from a restoring 
force. For surface waves the sources of a restoring force are gravity and surface
tension. Waves whose dynamics are dominated by gravity are called *surface
gravity waves*, while those with dynamics dominated by surface tension are called
*capillary waves*. 

(These are distinct from *gravitational waves* of the kind measured by LIGO!).

## Dispersion relations

Before launching into a detailed mathematical analysis, we can already estimate the
very different dispersion relations for each of these waves, in the "deep water"
limit that the depth of the water is so large that it does not impact surface waves.

### Surface gravity waves

First let us consider waves for which the restoring force is gravity. Absent viscosity, 
we wish to relate $\omega$, with units of $1/time$, to $k$ with units of $1/length$. The
only additional consant availabe is $g$ with units of $length/(time)^2$, leading to

$$
	\omega(k)^2 = c gk
$$

with $c$ a constant (it is in fact 1).

Note that the phase velocity is $v_p = \sqrt{\frac{g}{k}}$ and the group velocity $v_g = \frac{1}{2} \sqrt{\frac{g}{k}$.
The upshow is that long wavelength (low $k$) modes travel more quickly.

### Capillary waves

Next consider the case that surface tension is the dominant restoring force. The surface tension is 
$\alpha \sim (mass)/(time)^2 = (force)/(length)$. To relate $\omega$ and $k$ we need another quantity
with mass dimension in it ;the density is the obvopus answer. So $\alpha/\rho \sim (length)^3/(time)^2$.
thus, we have

$$
	\omega^2(k) = \frac{\alpha k^3}{\rho}
$$

In this case $v_p = \alpha \sqrt{k}/\rho$ and $v_g = \frac{3\alpha \sqrt{k}}{2\rho}$; so long wavelengths
(smaall $k$) travel more slowly than short wavelength ones.
