# Shallow water equations 2

```{math}
\newcommand{\p}{\partial}
```

Now that we have discussed the method of characteristics and found
characteristic equations for invariants $u \pm 2c$, we consider two 
applications: the flow caused by a dam break; and the formation of
a tidal bore.

## Dam break 

Consider, for $t <0$, a static situation wth water at constant height $h_0$
for $x < 0$, behind a dam at $x = 0$, and no water for $x > 0$. Then
we remove the dam and let the water begin to flow.

For $t < 0$ the characteristics are quite simple: $c_0 = \sqrt{g h_0}$, so
$\p_s t = 1$, $\p_s x = u \pm c_0$ are the characteristics along which
$u \pm 2 c_0$ are constant. Note that $u = 0$, so that 

$$
	d_t x = u \pm c_0 = \pm c_0
$$

are the characteristics: these are straight lines covering the 
quadrant $x < 0, t < 0$.

Now let us release the dam at $t = 0$. For $t < 0$ the characteristics 
remain the same. As they emerge, the will not remain straight. However, on the
characteristic cuves $C_{\pm}$, the invariants $\Gamma_{\pm} = u \pm 2c$ remain
invariant as we continue each beyond $t > 0$; that is, 
$\Gamma \pm 2 c = \pm 2 c_0$. If we follow two such charateristics $C_{\pm}$
which did not meet for $t < 0$, we expect that they begin to curve for $t > 0$.
If they meet at some later point $P$, then $u - 2 c = - 2 c_0$, 
$u + 2c = 2 c_0$, so that it is still true that $u = 0$, $c = c_0$. This is
a consistent solution, so we take it to be true, and we can continue the 
straight characteristics through to $t > 0$. 

This will break down for the characteristic $C_-$ emerging 
from $t = x = 0$, which is described by $x = - c_0 t$.
Beyond this, the $C_+$ charateristics will emerge and may
begin to (and indeed do) curve. Along these we will continue
to find $u + 2 c = 2 c_0$ for any charateristic. Negative charateristics
meeting these will solve $u - 2c = k$ for some constant $k$, so that
where these charateristics meet, $u = c_0 + k/2$, $c = \frac{1}{4}(2 c_0 - k)$.
In other words, $u, c$ are constant, and 

$$
	d_t x = u - c = \half c_0 + \frac{3 k}{4}
$$

in other words, these are straight lines determined by $k$.
In order that they do not cross for $t > 0$ which would ensure an
inconsistancy, they must emanate
from the origin.

