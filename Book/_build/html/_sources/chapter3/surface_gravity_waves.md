# Surface Gravity Waves

We will open with waves on the surface of a fluid, bounded from above by another 
fluid (think the ocean and atmosphere), in a small-amplitude regime so that we
can linearize the equations of motion about a static configuration with a flat
interface. As with any physical small oscillations, waves arise from a restoring 
force. For surface waves the sources of a restoring force are gravity and surface
tension. Waves whose dynamics are dominated by gravity are called *surface
gravity waves*, while those with dynamics dominated by surface tension are called
*capillary waves*. 

(These are distinct from *gravitational waves* of the kind measured by LIGO!)

## Setup in 2 dimensions

For simplicity we will work in 2 dimensions corresponding to a horizontal and a vertical direction. 
We start by considering a fluid of constant density and finite depth, as shown here:

![Finite depth setup](SGW.png "Basic setup")

We will take the atmospheric pressure to be constant at the fluid interface (pretty good approximation for
ocean waves). We consider small amplitude waves about the basic state $\zeta = 0$, ${\vec v} = 0$, and assume the flow
is *irrotational*: since we are working with the inviscid equations, we are guaranteed this so long as
the initial state at $t = 0$ is irrotational (2d vorticity is conserved along fluid trajectories). 
This means we can consider ${\vec v} = {\vec \nabla}\phi$. Bernoulli's equation (just the Euler equation
for this case) plus incompressibility gives us:

\begin{align}
	& \partial_t \phi +  \frac{p}{\rho} + \frac{1}{2}({\vec \nabla}\phi)^2 + g z = 0 \\
	& {\vec \nabla} \cdot {\vec v} = \nabla^2 \phi = 0
\end{align}

To solve this we must further supplement this with boundary conditions. In this case, at $z = - j$ we must have
$v)z = \partial_z \phi = 0$, At the free surface, we demand $v_z = \partial_z \phi = \partial_t \zeta$.
Thus, at the surfface where $p = p_0$, we have $p_0 =  - \rho(\partial_t \phi + g \zeta$. Taking the time deivative of
this and using teh boundary conditions, we find:

\begin{align}
	& \partial_t^2 \phi + g \partial_z \phi\Big|_{z = \zeta} = 0\\
	& \nabla^2 \phi = 0
\end{align}


