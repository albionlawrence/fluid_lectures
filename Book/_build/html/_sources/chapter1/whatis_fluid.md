# What is a Fluid?

## 1. Characterization

I highly recommend the introductory chapter of Batchelor's book 
{cite:p}`batchelor2000introduction` `for an 
in-depth discussion of this issue.

### A *continuous medium* with material at every point.
  
  This is of course a mathematical abstraction. A fluid is comprised of
  individual molecules and at sufficiently short distances the continuum
  approximation breaks down. In practice fluid mechanics is a *coarse-grained*
  description of materials.
  
  The assumption is that if we coarse-grain over a large enough volume, the
  material can be effectively described by a set of quantities which vary
  smoothly in space and time, eg:
    1. *velocity*: ${\vec v}({\vec x},t)$
	2. *density*: $\rho({\vec x},t)$ (we will often take this to be constant)
	3. *temperature*: $T({\vec x},t)$ 
	4. For ocean water, *salinity* (salt content): $S({\vec x},t)$
	5. For the atmosphere, *specific humidity* $q = \rho_{vapor}/\rho$.
  and so on.

Density, temperature, and so on are themodynamic quantities that we typically 
define in equilibrium. A dynamic fluid will not be in equilibrium and in many
interesting examples it is constantly being driven out of equilibrium. As
an example, the solar heating of the atmosphere varies from the equator to
th poles, varies with time over the seasons and over longer times as 
the Earth's roational axis and orbital characteristics change. In this class
we will be assuming that the fluid is in local thermal equilibrium, such
that thermodynamic quantities make sense but vary in space and time.


### Deformation under shear

Fluids always deform under *shear stress*: essentially, a gradient of force
across some planar surface. There may be friction, corresponding to a 
force between two layers sliding on top of each other, but there is no 
restoring force.
  
## 2. Examples

Note that for our purposes, a fluid could be a liquid, a gas, a plasma, and
so on.  Examples of fluids:

  1. Planetary fluids: oceans, atmospheres, ice sheets, magma
  2. Astrophysics and cosmology: protons and electrons in the 
  early universe, solar interiors, accretion disks, protoplanetary disks,
  near-horizon geometry of black holes (spacetime as an effective fluid)
  3. Condensed matter physics: superfluids, quantum hall fluids
  4. Biological media (blood, mucous,...)
  5. Plasma in heavy ion collisions

In other words this subject is everywhere: biological physics, soft and
hard condensed matter physics, nuclear physics, astrophysics, cosmology,
earth science, and so on. 


