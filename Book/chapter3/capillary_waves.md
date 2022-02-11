# Capillary waves

Next we wish to add the effect of surface tension. This arises in an interface between two fluids -- water and air, 
oil and water, alcohol and water. It is typically expressed in the free energy of a fluid as the the coefficient 
$\gamma$ of an area-dependent term $F_{st} = \sigma A$, where $A$ is the area of the surface. Fluids are bound together by
an intermolecular force, and the tension arises from the difference in attractive force between molecules of the different fluids;
thus the specific value depends on what fluids are n each side of the interface, the temperature, the presence of impurities, and so on.
Furthermore, the surface tension can be positive or negative. When positive -- for water and air, or water and oil -- the fluids are
inmiscible; wen negative, the fluids will mix rapidly. (You can find an excellent and not-too-long discussion of all this
in {cite:p}`batchelor2000introduction`.)

We expect the surface tension to change the boundary conditions for the fluid surface. For the present purposes I will
resort to some hand-waving. A good general derivation of the effects of surface tension would follow from
writing the different stresses on fluid elements in terms of the stress tensor. That formalism will
be developed later.

We are considering waves above a flat surface so let us restrict ourselves to that. When the interface is flat, 
the tension exerts an equal and opposite force on each of the surface fluid elements. When it is curved, there will be a net force 
perpendicular to the fluid surface. This force should be matched by a jump in pressure across the surface (otherwise we take
the pressure to be continuous.)  If we consider a linear wave propagating in the $x$ direction, the curvature of the surface 
is clearly proportional to $\partial_x^2 \zeta$, so we expect the vertical force to be $\propto \sigma \partial_x^2 \zeta$.
It turns out that this proportionality is an equality (when $\sigma is defined as above. Thus we demand, at the boundary,

$$
	p_0 - p = \sigma \frac{\partial^2 \zeta}{\partial x^2}
$$

where $p_0$ is the pressure of the air (or of the fluid above the fluid under consideration).

Now we again wich to consider irrotational flow, for a small perurbation from the resting state. We 
return to Bernoulli's equation:

$$
	\partial_t \phi + \frac{p}{\rho} + \frac{1}{2} {\vec u}^2 + g \eta = 0 = 
$$

Assuming again that $\phi, {\vec u}, \eta \sim {\cal O}(\epsilon)$ and ignoring ${\cal O}(\epsilon^2)$ terms, we find
can absorb the constant $p_0$ into $\partial_t \phi$, and combine these two equations to find

$$
	\partial_t \phi + g \eta - \frac{\sigma}{\rho} \frac{\partial^2}{\partial x}^2 \eta = 0
$$

We combine these with $v_z = \partial_z \phi = \partial_t \eta$ to get the boundary equations of motion.
Finally, the solution must solve Laplace's equation $\nabla^2 \phi = 0$.

As before, Laplace's equation combined with the bottom boundary conditions leads to 

$$
	\phi = A \cos(\omega t - k x - \delta) \cosh(k(z + h))
$$

with $\delta$ an arbitrary phase. The top boundary conditions then impose a dispersion relation $\omega(k)$. 
We can then get general solutions by linear combinations
of these solutions. For a fixed value of $k$, $\partial_x^2$ acting on the sin gives $- k^2$, so for this wave the boundary conditions
are the same as for the surface gravity wave if we replace $g \to g + \frac{\sigma}{\rho} k^2$, so that

$$
	\omega^2(k) = \left(g + \frac{\sigma}{\rho} k^2\right) k \tanh kh
$$

In the limit $kh \to \infty$ (deep water), this bcomes

$$
	\omega^2(k) \sim gk + \frac{\sigma}{\rho} k^3
$$

Note that if the $gk$ term is subdominant, as will happen for sufficiently large $k$, this is exactly the form
we deduced by dimensional analysis.

With this in hand we can ask when we make a transition between gravity waves and capilary waves. The surface tension
dominates when $k^2 \gg \frac{g \rho}{\sigma}$. Taking $g \sim 9.8 m/s^2$, $\rho \sim 10^3 kg/m^3$ and $\sigma \sim .07 N/m$,
we find $\lambda = \frac{2\pi}{k} \ll .017 m \ 1.7 cm$. 

Note that the phase speed in deep water is

$$
	c = \frac{\omega}{k} = \sqrt{\frac{g}{k} + \frac{\sigma}{\rho} k}
$$

There is clearly a $k$ for which this is minimal. 

Now consider the observed phenomenal of water flowing steadily past an obstacle (stone, fishing line, etc). If the flow is not
too fast and we do not excite turbulent motion, we ofen see steady waves about the object. This is obly possible if, in the rest frame
of the fluid, the waves are mving with phase velocity $U$. Thus $U$ must be less than the mininum possible phase
velocity given when $k = \sqrt{\rho g/\sigma}$, or $c^2 = 2 \sqrt{g \sigma/\rho}$. Above this velocity both capilary waves
and gravity waves can propagae with velocity $U$. The former have a group velocity larger han the phase velocity, and the latter smaller,
so we will see upstream capillary waves and downstream gravity waves.

