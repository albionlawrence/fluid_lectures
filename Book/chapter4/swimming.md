# Swimming at low Reynolds number

```{math}
\newcommand{\p}{\partial}
\newcommand{\eps}{\epsilon}
\newcommand{\half}{\frac{1}{2}}
```

As we have argued, the fluid flow as $Re \to 0$ is
fixd completely by the boundary conditions at that time. 
The only way for an object to move forward at low Reynolds number
through some kind of repetitive motion is if it executes a protocol 
which takes a *loop* in the space of possible shapes. 
So, a single paddle will not do; a *flexible* paddle might, or 
two independent hinges.

Oher option are available -- fo example, a rotating corkscrew. We'll look at 
a simpler one, which is a wave traveling along a flexible membrane.

## Waving of a thin flexible sheet

We consider 2d flow again, with a membrane extended along teh $x$ direction
which is waving in the $y$ direction. We ignore, for now, the finite size
of his object. We wish to show tha this motion induces both oscillatory
flow of the fluid and an additional steady flow along the $x$ axis.
We can then boost into te rest frame of the steady flow, so that the
membrane itself is swimming in the $-x$ direction.

We take the membrane shape to be:

$$
	y = a \sin(kx - \omega t)
$$

In particular we take the infintesimal pieces of the sheet to reside at
fixed $x$, and move up and down. 

The exact boundary conditions will clearly be difficult to impose.
We will take the limit tha the oscillations are small compared to 
the wavelength: 

$$
	\eps = ak \ll 1
$$

(actually the wavelength is $\lambda = 2\pi/k$, but $\epsilon$ is
the parameter which will appear). 

Once again, because this is 2d incompressible flow, we can describe
the velociy in terms of a streamfunction:

```{math}
& u_x = \p_y \psi\\
& u_y - - \p_x \psi
```

Taking the curl of the slow/ceeping flow equation we find

$$
	(\nabla^2)^2 \psi = 0
$$

Because the individual elements of the membrane are oscillating vertically,
and the no-slip condition means that the fluid velocity at the membrane
equals the membrane velocity 

$$
	{\vec v}_{membrane} = {\hat y} \frac{d}{dt} a \sin(k x - \omega t)
	= - a\omega \cos(kx - \omega t)\ ,
$$

we have 

```{math}
& v_x = \p_y \psi(x,y = a\sin(kx - \omega t)) = 0\\
&v_y = - \p_x \psi(x,y = a\sin(kx - \omega t)) = 
- a \omega \cos(kx - \omega t)
```

These are obviously noninear boundary conditions. They are also time-dependent.
However, $x,t$ only appear *explicitly* in the equations in the form
$kx - \omega t$. If we solve the equations at $t = 0$, we can 
find solutions at other times $t$ by replacing $x \to x - \omega t/k$. 
So we will do that.

At this point, we are going to nondimensionalize the problem. This
will make the formulae simpler (fewer parameters floating around,
and will isolate the dimensionless parameters which control
the solution. We rescale

```{math}
& k x = X\\
&k y = Y\\
&\frac{k}{\omega a} \psi = \Psi
```

All of the capitalized quantities are now dimensionless. The 
form of the bulk equations for the steamfunction remain unchanged:

$$
	\left(\p_X^2 + \p_Y^2\right)^2 \Psi = 0
$$

The boundary conditions become

```{math}
& \p_Y \Psi(X,Y = \eps \sin X) = 0\\
& \p_X \Psi(X, Y = \eps \sin X) = \cos X
```

We are going to try and solve these equations in a power series in
$\eps$. Looking at the structure of these equations, we see
$\Psi$ should start at ${\cal O}(1)$ in order that
the second equation be solvable, so:

$$
	\Psi = \Psi_0 + \eps \Psi_1 + \eps^2 \Psi_2 + \ldots
$$

(unlike the book, I prefer to match the index of $\Psi$ with the
order of $\eps$).  We can expand the boundary conditions in $\eps$:

```{math}
& \p_Y \Psi(X,0) + \eps \sin X \p_Y^2 \Psi(X,0) + \ldots = 0\\
& \p_X \Psi(X,0) + \eps \sin X \p_Y \p_X \Psi(X,0) + \ldots = \cos X
```

Inserting the above expansion we have:

```{math} 
:label: expansion
& \p_Y \Psi_0(X,0) = 0\\
& \p_X \Psi_0(X,0) = \cos X\\
& \p_Y \Psi_1 + \sin X \p_Y^2 \Psi_0 = 0\\
& \p_X \Psi_1 + \sin X \p_Y \p_X \Psi_0 = 0
```

At lowest order we are working on the UHP and the boundary conditions
depend only on $X$; thus we will try a separation-of-variables
ans&auml;tz $\Psi_0 = F(X) G(Y)$. The boundary conditions
already guarantee that $F(X) = \sin X$. The bulk equation for $G$ is then

$$
	\left(\p_Y^2 - 1\right)^2 G = 0
$$

Setting $\Phi = (\p_Y^2 - 1) G$, we find

$$
	\Phi = A' e^Y + B' e^{-Y}
$$

is the most general solution. Now in solving

$$
	\left(\p_Y^2 - 1\right)^2 G = \Phi =  A' e^Y + B' e^{-Y}
$$

a general solution takes the form

$$
	G = C e^Y + D e^{-Y} + {\tilde G}
$$

where ${\tilde \Psi}$ is a *particular* solution to:

$$
	\left(\p_Y^2 - 1\right) {\tilde G} =  A' e^Y + B' e^{-Y}
$$

which can be:

$$
	{\tilde G} = \half Y (A' e^Y + B' e^{-Y})
$$

Now for $Y > 0$ we need ${\vec v} \to 0$ as $Y \to \infty$ so we must have $A' = C = 0$.
Now we must impose the boundary conditions at $Y =0$. Since $F(X) = \sin x$, 
$u_y = - \p_X \Psi_0 = \cos X$ is
satisfied at $y = 0$ if $D = 1$. Finally $\p_Y G = 0$, which means $\half B' - 1 = 0$, and the
solution for $y > 0$ becomes

$$
	G = (1 + Y) e^{-Y}
$$

while for $Y < 0$, we must have $B' = D = 0$, and after the same arguments:

$$
	G = (1 - Y) e^Y
$$

Thus

```{math}
\Psi & = (1 + Y) e^{-Y} \sin X\ \ {\rm for}\ Y > 0\\
& = (1 - Y) e^Y \sin X \ \ {\rm for}\ Y < 0
```

Now we can sove for $\Psi_1$ in {eq}`expansion`. This still satisfies the
equation $(\p_X^2 + \p_Y^2)^2 \Psi_1 = 0$.
Le us start with $Y \to 0^+$, for which:

```{math}
& \p_Y \Psi_1 - \sin^2 X = 0\\
& \p_X \Psi_1 = 0
```

We further write $\sin^2 X = \half(1 - \cos 2 X)$. Now $\Psi_1$ is the sum of two terms,
one for which $\p_Y \psi_{1a} = \half$ at $Y = 0$, and one for which 
$\p_Y \Psi_{1b} + \half \cos 2 X = 0$. The latter piece will again be solved as before with

$$
	\Psi_{1b} = (E + F y) e^{-2Y} \cos 2X
$$

To solve for $\Psi_{1a}$ he boundary conditions suggest we consider constant $x$ dependence
in our separation-of-variables ans&umla;tz so that $\p_Y^4 \Psi_{1a} = 0$. This is solved by
the cubic

$$
	\Psi_{1a} = H_0 + H_1 Y + H_2 Y^2 + H_3 Y^3
$$

Now we need to combine these. Using $\p_X \Psi_1 = 0$ we find $E = 0$. $H_0$ has no
physical meaning as only derivatives of $\Psi$ are physical, and we can set it to zero.
$H_{2,3}$ will give components of he veocity scaling as  
$U_{X} = \p_Y \Psi = \sim 2 H_2 Y + 3 H_3 Y^2 \to \pm \infty$ as $y \to \infty$
so we must set $H_{2,3} = 0$. Finally, we want $\p_Y \Psi_1 = \sin^2 X = \half(1 - \cos 2X)$
at $Y = 0$, so we must have $H_1 = \half$, $F = - \half$, or

$$
	\Psi_1 = \half \left(Y - Y e^{-2Y}\cos 2 X\right)
$$

So that

$$
	\Psi = (1 + Y) e^{-Y} \sin X + \eps \half  \left(Y - Y e^{-2Y}\cos 2 X\right)
$$

Redimensionalizing and shifing $kx \to kx - \omega t$, 

$$
	\psi = \frac{\omega a}{k} \left[ \left(1 + ky\right) e^{-ky}\sin(kx - \omega t)
		+ \half \eps ky  \left(1 - e^{-2ky} \cos (2kx - 2\omega t)\right)\right] + \ldots
$$

we can compute the velocity:

```{math}
& u_x = \p_y \psi = - \eps \omega y e^{-k y} \sin(kx - \omega t)
+ \eps^2 c \left[\half + (ky - \half)e^{-2ky} \cos(2(kx - \omega t))\right] + \ldots\\
& u_y = - \p_x \psi = \eps c \left(1 + k y\right) e^{-ky} \cos(kx - \omega t)
+ \eps^2 c ky e^{-2k y} \sin(2kx - 2 \omega t) + \ldots
```

Here $c = \omega/k$; note further
that the rescaling $\Psi \to \psi$ means ta even though it appears that $\Psi$ was nonvanishing
as $\eps \to 0$, ${\vec u}$ is still vanishing in this limit.

The upshot is that in addition to an oscillatory flow, we have a steady component

$$
	{\vec u}_{steady} = \half \eps^2 c {\hat x} = \frac{k a^2 \omega}{2} {\hat x}
$$

If we boost into the rest frame of the steady flow, each infinitesimal piece of the
membrane will be moving as:

```{math}
& x = x_0 - \frac{k a^2 \omega t}{2}\\
& y = a \sin\left[kx_0 - \left(\half k^2 a^2 + 1\right)\omega t\right]
```



