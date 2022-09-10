---
title: "FALCON code"
layout: single
permalink: /falcon/
#toc: true
#toc_label: "Contents"
author_profile: false
sidebar:
  nav: "doc_falcon2"
---

*<span style="font-size:12px">The Gihub repository of this project can be found <a href="https://github.com/aleregorda/Code_description" target="_blank">here</a>. The .pdf file with a complete description of the code can be downloaded from <a href="/assets/files/FALCON_Description.pdf" target="_blank">here</a>, while at this [link](https://github.com/aleregorda/Code_description/archive/refs/heads/main.zip) you can download the .zip file containing all of the files.</span>*

<small>**<span style="color:orange">FALCON</span>** (**<span style="color:orange">F</span>**em **<span style="color:orange">AL</span>**gorithm for **<span style="color:orange">CO</span>**mputational a**<span style="color:orange">N</span>**alisys) is a FEM code written in Fortran90 used to study large-scale geodynamics system, such as continental rifting and subductions.</small>

# <span style="font-size:30px">Applications</span>
**(Working on it!)**
# <span style="font-size:22px"><u>Venus</u></span>
# <span style="font-size:22px"><u>Sesia</u></span>

# <span style="font-size:30px">Benchmarks</span>

*<span style="font-size:12px">The Gihub repository of this project can be found <a href="https://github.com/aleregorda/Benchmarks" target="_blank">here</a>. You can download the .zip file containing all the raw data of the benchmarks performed at this [link](https://github.com/aleregorda/Benchmarks/archive/refs/heads/main.zip).</span>*

Feature | Benchmark | Reference
---|---|---
Solver | <a href="/falcon/#stokes-flow" target="_blank">Stokes flow</a> | <a href="https://onlinelibrary.wiley.com/doi/book/10.1002/0470013826" target="_blank">Donea and Huerta (2003)</a>
Markers advection | <a href="/falcon/#zalesak-disk" target="_blank">Zalesak disk</a><br><a href="/falcon/#conservative-velocity-interpolation" target="_blank">Conservative Velocity Interpolation</a> | <a href="https://www.sciencedirect.com/science/article/pii/0021999179900512?via%3Dihub" target="_blank">Zalesak (1979)</a><br><a href="http://cedricthieulot.net/manual.pdf" target="_blank">FIELDSTONE (Stone 30)</a>
Momentum<br>equation | <a href="/falcon/#poiseuille-flow" target="_blank">Poiseuille flow</a><br><a href="/falcon/#instantaneous-2d-sphere" target="_blank">Instantaneous 2D sphere</a><br><a href="/falcon/#rayleigh-taylor-experiment" target="_blank">Rayleigh-Taylor experiment</a><br><a href="/falcon/#falling-block" target="_blank">Falling block</a> | <a href="https://se.copernicus.org/preprints/se-2014-49/" target="_blank">Thieulot (2014)</a><br><a href="http://cedricthieulot.net/manual.pdf" target="_blank">FIELDSTONE (12.2.22)</a><br><a href="https://agupubs.onlinelibrary.wiley.com/doi/abs/10.1029/97JB01353" target="_blank">Van Keken et al. (1997)</a><br><a href="https://www.sciencedirect.com/science/article/pii/S0031920103001900?via%3Dihub" target="_blank">Gerya and Yuen (2003)</a>
Sticky air and<br>free surface | <a href="/falcon/#2d-stokes-sphere" target="_blank">2D Stokes sphere</a><br><a href="/falcon/#stabilisation-algorithm" target="_blank">Stabilisation algorithm</a><br><a href="/falcon/#topography-relaxation" target="_blank">Topography relaxation</a><br><a href="/falcon/#spontaneous-subduction" target="_blank">Spontaneous subduction</a> | <a href="http://cedricthieulot.net/manual.pdf" target="_blank">FIELDSTONE (12.2.23)</a><br><a href="https://www.sciencedirect.com/science/article/pii/S0031920110000877?via%3Dihub" target="_blank">Kaus et al. (2010)</a><br><a href="https://academic.oup.com/gji/article/189/1/38/575556?login=false" target="_blank">Crameri et al. (2012)</a><br><a href="https://www.sciencedirect.com/science/article/pii/S0031920108001568" target="_blank">Schmeling et al. (2008)</a>
Nonlinear rheology | <a href="/falcon/#slab-detachment" target="_blank">Slab detachment</a><br><a href="/falcon/#indenter" target="_blank">Indenter</a><br><a href="/falcon/#brick" target="_blank">Brick</a> | <a href="https://www.sciencedirect.com/science/article/pii/S0012821X11000252?via%3Dihub" target="_blank">Schmalholz (2011)</a><br><a href="https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2008JB005591" target="_blank">Thieulot et al. (2008)</a><br><a href="https://se.copernicus.org/articles/9/267/2018/" target="_blank">Glerum et al. (2018)</a>
Energy equation | <a href="/falcon/#advection-stabilisation" target="_blank">Advection stabilisation</a><br><a href="/falcon/#simple-shear-heating" target="_blank">Simple shear heating</a><br><a href="/falcon/#shear-and-adiabatic-heating" target="_blank">Shear and adiabatic heating</a>
Energy+momentum | <a href="/falcon/#mantle-convection" target="_blank">Mantle convection</a><br><a href="/falcon/#visco-plastic-mantle-convection" target="_blank">Visco-plastic mantle convection</a><br><a href="/falcon/#thin-layer-entrainment" target="_blank">Thin layer entrainment</a>
Phase changes<br>and hydration | <a href="/falcon/#hydrated-sinking-cylinder" target="_blank">Hydrated sinking cylinder</a>
Melting | <a href="/falcon/#melting" target="_blank">Experimental melting curves</a>

# <span style="font-size:22px"><u>Stokes flow</u></span>
<small>This experiment is performed as explained by <a href="https://onlinelibrary.wiley.com/doi/book/10.1002/0470013826" target="_blank">Donea and Huerta (2003)</a>. The problem consists of determining velocity field (*u*, *v*) and pressure *p* in case of a manufactured solution with
prescribed body forces.
The domain is a unit square a constant viscosity and the penalty parameter is set to 10<sup>7</sup>. Velocity boundary
conditions are set to no slip (**v**=**0**) on all boundaries. The problem is performed for different grid resolution between
8×8 and 1024×1024 elements.</small>
<figure>
  <img src="/assets/images/errors-1.png" alt="errors" style="width:700px"/>
  <figcaption>Velocity and pressure error for the Stokes flow experiment between generated and analytical solution as a function of element size (panel a), and comparison between smoothed pressure and analytical solution as function of x coordinate for a grid resolution of 128×128 elements (panel b)</figcaption>
</figure>
<figure>
  <img src="/assets/images/MUMPS-1.png" alt="mumps" style="width:700px"/>
  <figcaption>Analysis, factorisation, solution and total solve times (panel a) and factorisation memory usage
(panel b) as a function of the total number of degrees of freedom for the Stokes flow experiment</figcaption>
</figure>

# <span style="font-size:22px"><u>Zalesak disk</u></span>
<small>This experiment is performed as explained by <a href="https://www.sciencedirect.com/science/article/pii/0021999179900512?via%3Dihub" target="_blank">Zalesak (1979)</a>. The benchmark is performed in a unit square domain with a grid resolution of 32×32 elements and values of Courant number (CFL) between 0.25 and 1.
The velocity field is prescribed in the entire domain.
At t=0, the disk is centred at position (0.5; 0.75) with a radius R=0.15 and has a vertical fissure 0.05 wide and 0.2 high.</small>
<figure>
  <img src="/assets/images/zal_marker-1.png" alt="zal_error" style="width:700px"/>
  <figcaption>Distance from the centre as function of time for values of Courant number of of 0.25, 0.3, 0.5, 0.75 and 1
(green, orange, blue, black and red, respectively).</figcaption>
</figure>

# <span style="font-size:22px"><u>Conservative Velocity Interpolation</u></span>
<small>The Conservative Velocity Interpolation (CVI) correction is checked by means of the <a href="/falcon/#stokes-flow" target="_blank">Stokes flow experiment</a>, as explained in <a href="http://cedricthieulot.net/manual.pdf" target="_blank">FIELDSTONE (Stone 30)</a>. The advection of Lagrangian markers is performed using either a 2nd-order or a 4th-order Runge-Kutta scheme with CFL=0.5 and an initial random distribution of 25 markers per element.</small>
<figure>
  <img src="/assets/images/CVI-1.png" alt="cvi" style="width:700px"/>
  <figcaption>Maximum and minimum number of markers per element, with or without the CVI correction and using either a 2nd-order or a
4th-order Runge-Kutta (RK) scheme.</figcaption>
</figure>

# <span style="font-size:22px"><u>Poiseuille flow</u></span>
<small>This experiment is performed as explained by <a href="https://se.copernicus.org/preprints/se-2014-49/" target="_blank">Thieulot (2014)</a>. The domain is a rectangle with L<sub>x</sub>=2 and L<sub>y</sub>=1, constant density and viscosity, gravity
acceleration equal to 0 and the penalty parameter is 10<sup>8</sup>. The grid is composed by 40×20 elements. Velocity boundary conditions are set to no slip (**v**=**0**) at the top and the bottom, and a parabolic profile is imposed on the sides, with v<sub>x</sub>=y(1−y) and v<sub>y</sub>=0.</small>
<figure>
  <img src="/assets/images/Poiseuille-1.png" alt="poiseuille" style="width:700px"/>
  <figcaption>Velocity field (panel a), pressure (panel b) and divergence velocity of a Poiseuille flow in case of the classic
penalty method (no iterations) and after one Uzawa iteration (panel c and d, respectively).</figcaption>
</figure>

# <span style="font-size:22px"><u>Instantaneous 2D sphere</u></span>
<small>The experiment is performed as explained in <a href="http://cedricthieulot.net/manual.pdf" target="_blank">FIELDSTONE (12.2.22)</a>. The domain is a unit square with gravity equal to -1. The fluid has constant density and viscosity. The sphere is in the middle of the domain with a radius
R=0.123456798 with constant density and viscosity higher than the fluid. Different types of velocity boundary conditions have been tested with grid resolutions between 16×16 and 512×512 elements and different average schemes for the viscosity (harmonic, geometric and arithmetic).
The velocity in the centre of the sphere, minimum and maximum velocities and pressures on the entire domain, v<sub>rms</sub> and average pressure on the entire domain have been compared to <a href="https://aspect.geodynamics.org/" target="_blank">ASPECT</a> and can be found <a href="https://github.com/cedrict/fieldstone/tree/master/images/stokes_sphere2D" target="_blank">here</a>.</small>
<figure>
  <img src="/assets/images/vrms_NS-1.png" alt="inst_sphere" style="width:700px"/>
  <figcaption>v<sub>rms</sub> as function of element size for the instantaneous 2D sphere experiment in case of no slip boundary
conditions and with different average schemes for the viscosity. Results are compared with results obtained by <a href="https://aspect.geodynamics.org/" target="_blank">ASPECT</a>.</figcaption>
</figure>

# <span style="font-size:22px"><u>Rayleigh-Taylor experiment</u></span>
<small>This experiment is performed as explained by <a href="https://agupubs.onlinelibrary.wiley.com/doi/abs/10.1029/97JB01353" target="_blank">Van Keken et al. (1997)</a>. The domain has L<sub>x</sub>=0.9142 and L<sub>y</sub>=1 and gravity equal to -1. Two fluids with same constant viscosities and different densities are distributed in the domain, with the lighter fluid at the bottom. The initial interface between the fluids is given by y(x)=0.2+0.02 cos(πx L<sub>x</sub>). The experiment is performed with grid sizes between 50×50 and 256×256 elements. Velocity boundary conditions are set to no slip at the top and the bottom, and to free slip at the sides of the domain.</small>
<figure>
  <img src="/assets/images/RT-1.png" alt="RT" style="width:700px"/>
  <figcaption>v<sub>rms</sub> of the Rayleigh-Taylor experiment as function of time for different resolution of the grid.</figcaption>
</figure>

# <span style="font-size:22px"><u>Falling block</u></span>
<small>This experiment is performed as explained by <a href="https://www.sciencedirect.com/science/article/pii/S0031920103001900?via%3Dihub" target="_blank">Gerya and Yuen (2003)</a> and <a href="https://www.sciencedirect.com/science/article/pii/S0031920111001336?via%3Dihub" target="_blank">Thieulot (2011)</a>. The domain is square with L<sub>x</sub>=L<sub>y</sub>= 500 km and the grid is composed by 50×50 elements with 25 markers in each element.
The block is initially centred at x=250 km; y=400 km and has a size of 100×100 km. The fluid
surrounding the block has constant viscosities and densities. The benchmark tests with different viscosities and densities
of the block, with higher density than the surrounding fluid. Velocity boundary conditions are set to free slip conditions on all sides of the
domain. The velocity in the centre of the falling block at t=0 is measured for all experiments and it is plotted as function of the viscosity contrast.</small>
<figure>
  <img src="/assets/images/Falling-1.png" alt="falling" style="width:700px"/>
  <figcaption>Initial velocity relative to the density contrast at the centre of the falling block as function of the viscosity
contrast between the block and the surrounding fluid.</figcaption>
</figure>

# <span style="font-size:22px"><u>2D Stokes sphere</u></span>
<small>This experiment is performed as explained in <a href="http://cedricthieulot.net/manual.pdf" target="_blank">FIELDSTONE (12.2.23)</a>, in a unit square domain with the gravity acceleration fixed to −1. The sphere has
constant densities and viscosities hogher than the surrounding fluid and it is initially centred at (0.5; 0.6) with radius R = 0.123456789.
The fluid surrounding the sphere occupies the domain for y≤0.75, while for y>0.75 there is air.
Velocity boundary conditions are set to free slip on all sides. The Courant number is set to 0.25. The experiments
run for 200 s using grid resolutions from 150×150 to 512×512 elements, with 25 randomly distributed markers per
element, and for different average schemes for the viscosity. The interface between the fluid and the air is tracked by
means of the markers chain. The results have been compared to <a href="https://aspect.geodynamics.org/" target="_blank">ASPECT</a> and can be found <a href="https://github.com/cedrict/fieldstone/tree/master/images/stokes_sphere_fs2D" target="_blank">here</a>.</small>
<figure>
  <img src="/assets/images/vrms_arithm-1.png" alt="sphere" style="width:700px"/>
  <figcaption>v<sub>rms</sub> for different grid resolutions as function of time in case of an arithmetic average.
  Results are compared with results obtained with <a href="https://aspect.geodynamics.org/" target="_blank">ASPECT</a>.</figcaption>
</figure>

# <span style="font-size:22px"><u>Stabilisation algorithm</u></span>
<small>This experiment is performed as explained by <a href="https://www.sciencedirect.com/science/article/pii/S0031920110000877?via%3Dihub" target="_blank">Kaus et al. (2010)</a>. The domain is square with
L<sub>x</sub>=L<sub>y</sub>=500 km and a grid resolution of 200×200 elements, each of them containing 16 markers. A buoyant fluid is overlain by a denser fluid.
The initial interface between the fluids has an initial sinusoidal shape of 5 km amplitude. Velocity boundary conditions
are set to free slip conditions at the sides and no slip at the bottom, while the top is free surface. The experiment
is performed with various fixed time steps. The vertical position of the free
surface at x=L<sub>x</sub> is tracked for each simulation, with or without the stabilisation algorithm.</small>
<figure>
  <img src="/assets/images/Kaus_random-1.png" alt="kaus" style="width:700px"/>
  <figcaption>Evolution of the y coordinate in x=L<sub>x</sub> as function of time for different time steps, with and without the
stabilisation algorithm.</figcaption>
</figure>

# <span style="font-size:22px"><u>Topography relaxation</u></span>
<small>This experiment is performed as explained by <a href="https://academic.oup.com/gji/article/189/1/38/575556?login=false" target="_blank">Crameri et al. (2012)</a>. The domain is rectangular with L<sub>x</sub>=2800 km and L<sub>y</sub>=700 km in case of free surface and L<sub>y</sub>=800 km in case of sticky air. The grid is composed by 256×64 elements for the free surface 560×320 elements for the sticky air. For both cases, there is a mantle of 600 km thickness overlain by a highly viscous cosine-shaped lithosphere with thickness between 93 and 107 km. Velocity boundary conditions are set to no slip at the bottom and free slip at the sides of the domain. In case of sticky air, velocities on top are set to free slip conditions.</small>
<figure>
  <img src="/assets/images/Crameri-1.png" alt="crameri" style="width:700px"/>
  <figcaption>Maximum topography as function of time in comparison with
the analytical solution (black line) and results obtained by <a href="https://academic.oup.com/gji/article/189/1/38/575556?login=false" target="_blank">Crameri et al. (2012)</a> with UNDERWORLD (yellow line) and SULEC (blue line).</figcaption>
</figure>

# <span style="font-size:22px"><u>Spontaneous subduction</u></span>
<small>This experiment is performed as explained by <a href="https://www.sciencedirect.com/science/article/pii/S0031920108001568" target="_blank">Schmeling et al. (2008)</a>, with both a sticky air and a true free
surface and using different average schemes for the viscosities. The domain is rectangular with L<sub>x</sub>=3000 km and
L<sub>y</sub>=700 km, a grid resolution of 256×64 elements with 50 markers per element and Courant number of 0.01. At the
beginning of the simulation, a denser 100 km-thick lithospheric layer is located
at the top of the domain for x between 1000 and 3000 km. In addition, a 200 km-depth lithospheric slab is already subducted in the mantle in order to have
a spontaneous subduction. In case of sticky air, a 50 km-thick air layer overlie the mantle. Velocity boundary conditions are set to free slip on the sides and on the bottom of the domain. In case of sticky air, velocities on the top boundary are set to free slip conditions as well.</small>
<figure>
  <img src="/assets/images/Subduction-1.png" alt="subduction" style="width:700px"/>
  <figcaption>Maximum depth of the slab as function of time. Red, green and blue Rectangular
areas indicate the range of times from <a href="https://www.sciencedirect.com/science/article/pii/S0031920108001568
" target="_blank">Schmeling et al. (2008)</a> when the slab tip reaches 500 km in case of sticky air (red, green and blue), and when the slab tip reaches 600 km in case of true free surface (gray).</figcaption>
</figure>

# <span style="font-size:22px"><u>Slab detachment</u></span>
<small>The slab detachment benchmark is performed as explained by <a href="https://www.sciencedirect.com/science/article/pii/S0012821X11000252?via%3Dihub" target="_blank">Schmalholz (2011)</a> and <a href="https://se.copernicus.org/articles/9/267/2018/" target="_blank">Glerum et al. (2018)</a>. The
domain is rectangular with L<sub>x</sub>=1000 km and L<sub>y</sub>=660 km and a grid resolution of 256×256 elements. A denser non-linear
viscous T-shaped layer is placed at the top of the domain and surrounded by a linear viscous fluid. The top layer is 80 km-thick and a 250 km-long and 80 km-wide slab is placed at x=L<sub>x</sub>/2. Velocity boundary conditions are set to free slip at the top and the bottom, and to no slip at the sides of the domain.</small>
<figure>
  <img src="/assets/images/Slab-1.png" alt="slab" style="width:700px"/>
  <figcaption>Effective viscosity for the slab detachment benchmark at the beginning of the evolution (panel a) and when
necking is complete (panel b).</figcaption>
</figure>

# <span style="font-size:22px"><u>Indenter</u></span>
<small>The indenter benchmark is performed as explained by <a href="https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2008JB005591" target="_blank">Thieulot et al. (2008)</a> and <a href="https://se.copernicus.org/articles/9/267/2018/" target="_blank">Glerum et al. (2018)</a>. The indenter benchmark simulate a rigid punch on a purely plastic von Mises material, for which exists an analytical
solution. The domain is a unit square with a grid resolution
of 256×256 elements. The gravity acceleration is set to 0. Velocity boundary conditions are set to no slip at the bottom and free
slip at the sides of the domain. The top of the domain is open with the exception of the central portion (punch area)
with width wp=0.125, where v<sub>y</sub>= −1.05 and v<sub>x</sub> is fixed either to 0 (rough punch experiment) or free (smooth punch
experiment).</small>
<figure>
  <img src="/assets/images/Indenter-1.png" alt="indenter" style="width:700px"/>
  <figcaption>Viscosity (panels a and b), strain rate (panels c and d), velocity (panels e and f) and pressure (panels g
and h) fields for rough (left column) and smooth (right column) punch experiments.</figcaption>
</figure>

# <span style="font-size:22px"><u>Brick</u></span>
<small>The experiment is perfomed as explained by <a href="https://se.copernicus.org/articles/9/267/2018/" target="_blank">Glerum et al. (2018)</a> to verify the correctness of the pressure-dependent plasticity for different angle of internal friction. The domain is rectangular with
L<sub>x</sub>=40 km and L<sub>y</sub>=10 km and a grid resolution of 512×128 elements. The maximum number of non-linear iterations is set to 1000. A
800 m-wide and 400 m-height inclusion is placed at the bottom of the domain at x=L<sub>x</sub>/2. The inclusion is surrounded by a non-linear viscous medium. Velocities are set to free slip conditions at the bottom of the domain and the top is open. Velocities on sides of the domain are fixed to v<sub>x</sub>=±2×10<sup>−11</sup> m s<sup>−1</sup> and v<sub>y</sub>=0. The experiment is performed in compressional and extensional contexts with an angle
of internal friction of the non-linear medium variable between 0° and 30°.</small>
<figure>
  <img src="/assets/images/Brick-1.png" alt="brick" style="width:700px"/>
  <figcaption>Shear band angles predicted for the brick experiment in case of compressional and extensional contexts as
function of different internal angle of friction (continuous black line and red dots), compared with theoretical Roscoe,
Artur and Coulomb angles (discontinuous black lines). Red lines indicate the range of angles calculated at different
depths.</figcaption>
</figure>

# <span style="font-size:22px"><u>Advection stabilisation</u></span>
# <span style="font-size:22px"><u>Simple shear heating</u></span>
# <span style="font-size:22px"><u>Shear and adiabatic heating</u></span>
# <span style="font-size:22px"><u>Mantle convection</u></span>
# <span style="font-size:22px"><u>Visco-plastic mantle convection</u></span>
# <span style="font-size:22px"><u>Thin layer entrainment</u></span>
# <span style="font-size:22px"><u>Hydrated sinking cylinder</u></span>
# <span style="font-size:22px"><u>Melting</u></span>