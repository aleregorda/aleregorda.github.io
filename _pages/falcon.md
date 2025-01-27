---
title: <span style="color:orange;font-size:40px">FALCON</span><br><span style="font-size:30px">(**<span style="color:orange">F</span>**em **<span style="color:orange">AL</span>**gorithm for **<span style="color:orange">CO</span>**mputational a**<span style="color:orange">N</span>**alisys)</span>
layout: single
classes: wide
#read_time: true
permalink: /falcon/
#toc: true
#toc_label: "Contents"
author_profile: false
sidebar:
  nav: "doc_falcon"
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/sub_T_large.png
#  actions:
    #- label: "Learn More"
      #url: "/terms/"
  #caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
#excerpt: 

---

# <span style="color:orange;font-size:24px">Introduction</span>

<small><span style="color:orange">FALCON</span> is a FEM code written in Fortran90 used to study large-scale geodynamics system, such as continental rifting and subductions. <a href="/assets/files/FALCON_Description.pdf" target="_blank">Here</a> you can download the .pdf file with the complete description of all the fetures implemented in the code and all the benchmarks performed. The Gihub repository of this project can be found <a href="https://github.com/aleregorda/Code_description" target="_blank">here</a> and you can download the .zip file containing all of the files at this <a href="https://github.com/aleregorda/Code_description/archive/refs/heads/main.zip" target="_blank">link</a>.</small>
<br>
<br>

<span style="color:white;font-size:14px">*Table - List of the features implemented in <span style="color:orange">FALCON</span> and of the benchmarks performed.*</span>

<a href="/falcon/#features-implemented" target="_blank"><span style="color:white">Feature implemented</span></a> | <a href="/falcon/#benchmarks" target="_blank"><span style="color:white">Benchmark</span></a> | Reference
---|---|---
<a href="/falcon/#governing-equations" target="_blank">Governing equations</a> | <a href="/falcon/#stokes-flow" target="_blank">Stokes flow</a> | <a href="https://onlinelibrary.wiley.com/doi/book/10.1002/0470013826" target="_blank">Donea and Huerta (2003)</a>
<a href="/falcon/#lagrangian-markers" target="_blank">Lagrangian markers</a> | <a href="/falcon/#zalesak-disk" target="_blank">Zalesak disk</a><br><a href="/falcon/#conservative-velocity-interpolation" target="_blank">Conservative Velocity Interpolation</a> | <a href="https://www.sciencedirect.com/science/article/pii/0021999179900512?via%3Dihub" target="_blank">Zalesak (1979)</a><br><a href="http://cedricthieulot.net/manual.pdf" target="_blank">FIELDSTONE (Stone 30)</a>
<a href="/falcon/#momentum-and-energy-equations" target="_blank">Momentum equation</a> | <a href="/falcon/#poiseuille-flow" target="_blank">Poiseuille flow</a><br><a href="/falcon/#instantaneous-2d-sphere" target="_blank">Instantaneous 2D sphere</a><br><a href="/falcon/#rayleigh-taylor-experiment" target="_blank">Rayleigh-Taylor experiment</a><br><a href="/falcon/#falling-block" target="_blank">Falling block</a> | <a href="https://se.copernicus.org/preprints/se-2014-49/" target="_blank">Thieulot (2014)</a><br><a href="http://cedricthieulot.net/manual.pdf" target="_blank">FIELDSTONE (12.2.22)</a><br><a href="https://agupubs.onlinelibrary.wiley.com/doi/abs/10.1029/97JB01353" target="_blank">Van Keken et al. (1997)</a><br><a href="https://www.sciencedirect.com/science/article/pii/S0031920103001900?via%3Dihub" target="_blank">Gerya and Yuen (2003)</a>
<a href="/falcon/#momentum-and-energy-equations" target="_blank">Energy equation</a> | <a href="/falcon/#advection-stabilisation" target="_blank">Advection stabilisation</a><br><a href="/falcon/#simple-shear-heating" target="_blank">Simple shear heating</a><br><a href="/falcon/#shear-and-adiabatic-heating" target="_blank">Shear and adiabatic heating</a> | <a href="https://www.sciencedirect.com/science/article/abs/pii/S0031920111001336?via%3Dihub" target="_blank">Thieulot (2011)</a><br><span style="color:lightblue">Analytical solution</span><br><a href="https://www.cambridge.org/core/books/introduction-to-numerical-geodynamic-modelling/F2CDB0729FE6DE586BCD9B18C059AE07" target="_blank">Gerya (2010)</a>
<a href="/falcon/#momentum-and-energy-equations" target="_blank">Momentum and<br>energy equations</a> | <a href="/falcon/#mantle-convection" target="_blank">Mantle convection</a><br><a href="/falcon/#visco-plastic-mantle-convection" target="_blank">Visco-plastic mantle convection</a><br><a href="/falcon/#thin-layer-entrainment" target="_blank">Thin layer entrainment</a> | <a href="https://academic.oup.com/gji/article/98/1/23/622167?login=false" target="_blank">Blankenbach et al. (1989)</a><br><a href="https://agupubs.onlinelibrary.wiley.com/doi/10.1002/2015GC005807" target="_blank">Tosi et al. (2015)</a><br><a href="https://agupubs.onlinelibrary.wiley.com/doi/epdf/10.1029/97JB01353" target="_blank">Van Keken et al. (1997)</a>
<a href="/falcon/#non-linear-rheologies" target="_blank">Non-linear rheologies</a> | <a href="/falcon/#slab-detachment" target="_blank">Slab detachment</a><br><a href="/falcon/#indenter" target="_blank">Indenter</a><br><a href="/falcon/#brick" target="_blank">Brick</a> | <a href="https://www.sciencedirect.com/science/article/pii/S0012821X11000252?via%3Dihub" target="_blank">Schmalholz (2011)</a><br><a href="https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2008JB005591" target="_blank">Thieulot et al. (2008)</a><br><a href="https://se.copernicus.org/articles/9/267/2018/" target="_blank">Glerum et al. (2018)</a>
<a href="/falcon/#sticky-air-and-free-surface" target="_blank">Sticky air and<br>free surface</a> | <a href="/falcon/#2d-stokes-sphere" target="_blank">2D Stokes sphere</a><br><a href="/falcon/#stabilisation-algorithm" target="_blank">Stabilisation algorithm</a><br><a href="/falcon/#topography-relaxation" target="_blank">Topography relaxation</a><br><a href="/falcon/#spontaneous-subduction" target="_blank">Spontaneous subduction</a> | <a href="http://cedricthieulot.net/manual.pdf" target="_blank">FIELDSTONE (12.2.23)</a><br><a href="https://www.sciencedirect.com/science/article/pii/S0031920110000877?via%3Dihub" target="_blank">Kaus et al. (2010)</a><br><a href="https://academic.oup.com/gji/article/189/1/38/575556?login=false" target="_blank">Crameri et al. (2012)</a><br><a href="https://www.sciencedirect.com/science/article/pii/S0031920108001568" target="_blank">Schmeling et al. (2008)</a>
<a href="/falcon/#phase-changes-and-hydration" target="_blank">Phase changes<br>and hydration</a> | <a href="/falcon/#hydrated-sinking-cylinder" target="_blank">Hydrated sinking cylinder</a> | <a href="https://se.copernicus.org/articles/5/537/2014/se-5-537-2014.pdf" target="_blank">Quinquis and Buiter (2014)</a>
<a href="/falcon/#mantle-melting" target="_blank">Mantle melting</a> | <a href="/falcon/#melting" target="_blank">Experimental melting curves</a> | <a href="https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2002GC000433" target="_blank">Katz et al. (2003)</a>

# <span style="color:orange;font-size:24px">Features implemented</span>

# <span style="color:lightblue;font-size:18px"><u>Governing equations</u></span>
<small>The code is written in Fortran90 and uses the finite element method (FEM) with quadrilateral Q<sub>1</sub>×P<sub>0</sub> elements (continuous bilinear velocity and discontinuous constant pressure), associated with <a href="http://mumps.enseeiht.fr/" target="_blank">MUMPS</a> (<a href="https://epubs.siam.org/doi/10.1137/S0895479899358194"  target="_blank">Amestoy et al., 2001</a>, <a href="https://dl.acm.org/doi/10.1145/3242094" target="_blank">2019</a>) that is a software package for solving systems of linear equations by means of a direct method. Since Q<sub>1</sub>×P<sub>0</sub> elements do not satisfy Ladyzhenskaya, Babuska and Brezzi (LBB) stability condition (<a href="https://onlinelibrary.wiley.com/doi/book/10.1002/0470013826" target="_blank">Donea and Huerta, 2003</a>), elemental pressure is elaborated in post-processing to avoid spurious pressures by means of a double interpolation to smooth the pressure. The thermo-mechanics of crust-mantle systems is described by means of the conservation of mass, momentum and energy equations. The time step dt is chosen in according to Courant-Friedrichs-Lewy condition (<a href="https://www.semanticscholar.org/paper/Computational-fluid-dynamics-%3A-the-basics-with-Anderson/de202c3c494e91d352784dcf553d45ddd8b255b9" target='_blank'>Anderson, 1995</a>).</small>

# <span style="color:lightblue;font-size:18px"><u>Lagrangian markers</u></span>
<small>Elemental properties (density, viscosity, thermal conductivity, specific heat and thermal expansion) are related to the composition of each element, determined by means of Lagrangian markers that are characteristic of different materials in the domain. The advection of the markers is performed by either a 2nd-order or a 4th-order Runge-Kutta in space, interpolating the velocity field on each marker by means of the shape functions. The interpolated velocity is then
corrected by means of the Conservative Velocity Interpolation (CVI; <a href="https://agupubs.onlinelibrary.wiley.com/doi/10.1002/2015GC005824
" target="_blank">Wang et al., 2015</a>). The initial distribution of the markers is created using the open-source code library <a href="https://geodynamicworldbuilder.github.io/" target="_blank">Geodynamic World Builder</a> (<a href="https://se.copernicus.org/articles/10/1785/2019/"  target="_blank">Fraters et al., 2019</a>). During the simulation, each marker carries memory of temperature, pressure and accumulated strain and the number of markers contained in each element is maintained between a minimum and a maximum by adding or deleting random markers inside the elements. In this way elements are never empty and maintain a number of markers inside a prefixed range.</small>

# <span style="color:lightblue;font-size:18px"><u>Momentum and energy equations</u></span>
<small>The code implements a so-called penalty formulation for which the flow is not truly incompressible but very weakly compressible. This allows to eliminate the pressure from the momentum equation that is then solved for the velocity field, while the pressure can be recovered as a post-processing step. One strong requirement is that the penalty coefficient λ must be many orders of magnitude larger than the dynamic viscosity η (typically between 5 and 8 orders of magnitude).
<br>The stabilisation of the advection term of the energy equation, needed to avoid possible oscillations in the thermal solution in the case when advection dominates over diffusion, is implemented by means of a streamline-upwind Petrov–Galerkin (SUPG) method, for which the advection term is modified follows the discussion in <a href="https://www.sciencedirect.com/science/article/abs/pii/S0031920111001336?via%3Dihub" target="_blank">Thieulot (2011)</a> and <a href="https://se.copernicus.org/preprints/se-2014-49/" target="_blank">Thieulot (2014).</a></small>

# <span style="color:lightblue;font-size:18px"><u>Non-linear rheologies</u></span>
<small>Non-linear rheologies are implemented combining viscous creep (dislocation and diffusion) and plastic yielding. The viscous creep η<sub>cp</sub> is calculated as the harmonic average between η<sub>df</sub> and η<sub>ds</sub>, while the plastic yielding is implemented rescaling η<sub>cp</sub> in order to limit the stress below the yield stress σ<sub>y</sub> determined following the Drucker-Prager criterion. Plastic yielding and viscous creep are then combined to obtain a viscoplastic viscosity η<sub>vp</sub> assuming that they are independent processes and the effective viscosity η<sub>eff</sub> is capped by the minimum and the maximum viscosity to avoid extremely low or high viscosities. Viscous creep and plastic yielding are non-linear rheologies because of their dependence on the velocity field through pressure and strain rates. Therefore, the solution is determined by means of Picard-type iterations, until convergence of the velocity field. The temporal evolution of the accumulated strain ϵ has been implemented as in Fuchs and Becker (<a href="https://academic.oup.com/gji/article/218/1/601/5435465" target=_blank>2019</a>, <a href="https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2020JB020335" target=_blank>2021</a>). Strain softening is taken into account for both viscous creep and plastic viscosity by means of the accumulated strain ϵ memorised by each marker. Softening in the viscous creep determines a linear decrease of η<sub>vc</sub> by means of a viscous strain softening factor W<sub>S</sub>, while plastic softening is simulated with a linear decrease of internal friction angle ϕ(ϵ) and cohesion C(ϵ).</small>

# <span style="color:lightblue;font-size:18px"><u>Sticky air and free surface</u></span>
<small>The Earth’s surface can be treated by means of either the so-called sticky-air or a true free surface method, both of them implemented in the code. In the sticky-air method the surface is approximated with the introduction of a buoyant layer with a viscosity at least four orders of magnitude lower than the crust (<a href="https://www.sciencedirect.com/science/article/abs/pii/S0031920108001568?via%3Dihub" target="_blank">Schmeling et al., 2008</a>; <a href="https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2011GL050046" target="_blank">Crameri et al., 2012</a>) and the interface between lithosphere and air is defined using a chain of passive markers that are advected as the Lagrangian markers.
In the true free surface case the top boundary is assumed stress-free and velocities are not fixed. In this case topography variations are described by vertical deformations of the mesh that depend on the velocity field of the nodes that identify the free surface, while horizontal deformations are not taken into account. This procedure is known as the Arbitrary Lagrangian-Eulerian (ALE) method and its implementation follows the technique described in <a href="https://www.sciencedirect.com/science/article/abs/pii/S0031920111001336?via%3Dihub" target="_blank">Thieulot (2011)</a> . The stability algorithm proposed by <a href="https://www.sciencedirect.com/science/article/abs/pii/S0031920110000877?via%3Dihub" target="_blank">Kaus et al. (2010)</a> is implemented to avoid instabilities due to high density differences at the free surface when using too large time steps.</small>

# <span style="color:lightblue;font-size:18px"><u>Phase changes and hydration</u></span>
<small>Variations of effective density, specific heat and coefficient of thermal expansion during the evolution of crustal and mantle materials at different pressure-temperature (p-T) conditions are computed by means of <a href="https://www.perplex.ethz.ch/" target=_blank>Perple_X</a> software package (<a href="https://www.sciencedirect.com/science/article/abs/pii/S0012821X05002839?via%3Dihub" target=_blank>Connolly, 2005</a>). In the case that hydration is switched on, the amount of bound and free water is memorised by each marker, following the implementation of <a href="https://se.copernicus.org/articles/5/537/2014/se-5-537-2014.pdf" target="_blank">Quinquis and Buiter (2014)</a>; hydration and dehydration processes are related to the amount of bound water of each marker and to the maximum amount of water it can transport, i.e. if the amount of bound water exceeds the maximum amount of water, the marker dehydrates and releases free water that can hydrates under-saturated markers. Bound water is advected together with the markers, neglecting the effect of bound water diffusion, while free water simply migrates vertically and is not coupled to the solid-phase flow of the mantle wedge.</small>

# <span style="color:lightblue;font-size:18px"><u>Mantle melting</u></span>
<small>Melt fraction in the mantle depends on temperature (T), pressure (p) and the water content in the melt (in wt.%). The determination of the melt fraction is implemented as explained by <a href="https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2002GC000433" target="_blank">Katz et al. (2003)</a>. In case of melting, viscous creep viscosity and effective density are modified according to <a href="https://agupubs.onlinelibrary.wiley.com/doi/10.1002/2016GL071186" target=_blank>Wang et al. (2016)</a>.</small>


# <span style="color:orange;font-size:24px">Benchmarks</span>

<small>This is a brief description of the benchmarks performed to verify that <span style="color:orange">FALCON</span> correctly solves a wide range of problems, as in the Table below. The Gihub repository with the results of all the benchmarks can be found <a href="https://github.com/aleregorda/Benchmarks" target="_blank">here</a>. You can download the .zip file containing all the raw data at this <a href="https://github.com/aleregorda/Benchmarks/archive/refs/heads/main.zip)" target="_blank">link</a>.</small>

# <span style="color:lightblue;font-size:18px"><u>Stokes flow</u></span>
<small>This experiment is performed as explained by <a href="https://onlinelibrary.wiley.com/doi/book/10.1002/0470013826" target="_blank">Donea and Huerta (2003)</a>. The problem consists of determining velocity field (*u*, *v*) and pressure *p* in case of a manufactured solution with
prescribed body forces.
The domain is a unit square a constant viscosity and the penalty parameter is set to 10<sup>7</sup>. Velocity boundary
conditions are set to no slip (**v**=**0**) on all boundaries. The problem is performed for different grid resolution between
8×8 and 1024×1024 elements.</small>
<figure>
  <img src="/assets/images/errors-1.png" alt="errors" style="max-width:100%"/>
  <figcaption>Velocity and pressure error for the Stokes flow experiment between generated and analytical solution as a function of element size (panel a), and comparison between smoothed pressure and analytical solution as function of x coordinate for a grid resolution of 128×128 elements (panel b).</figcaption>
</figure>
<figure>
  <img src="/assets/images/MUMPS-1.png" alt="mumps" style="max-width:100%"/>
  <figcaption>Analysis, factorisation, solution and total solve times (panel a) and factorisation memory usage
(panel b) as a function of the total number of degrees of freedom for the Stokes flow experiment.</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>Zalesak disk</u></span>
<small>This experiment is performed as explained by <a href="https://www.sciencedirect.com/science/article/pii/0021999179900512?via%3Dihub" target="_blank">Zalesak (1979)</a>. The benchmark is performed in a unit square domain with a grid resolution of 32×32 elements and values of Courant number (CFL) between 0.25 and 1.
The velocity field is prescribed in the entire domain.
At t=0, the disk is centred at position (0.5; 0.75) with a radius R=0.15 and has a vertical fissure 0.05 wide and 0.2 high.</small>
<figure>
  <img src="/assets/images/zal_marker-1.png" alt="zal_error" style="max-width:100%"/>
  <figcaption>Distance from the centre as function of time for values of Courant number of of 0.25, 0.3, 0.5, 0.75 and 1
(green, orange, blue, black and red, respectively).</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>Conservative Velocity Interpolation</u></span>
<small>The Conservative Velocity Interpolation (CVI) correction is checked by means of the <a href="/falcon/#stokes-flow" target="_blank">Stokes flow experiment</a>, as explained in <a href="http://cedricthieulot.net/manual.pdf" target="_blank">FIELDSTONE (Stone 30)</a>. The advection of Lagrangian markers is performed using either a 2nd-order or a 4th-order Runge-Kutta scheme with CFL=0.5 and an initial random distribution of 25 markers per element.</small>
<figure>
  <img src="/assets/images/CVI-1.png" alt="cvi" style="max-width:100%"/>
  <figcaption>Maximum and minimum number of markers per element, with or without the CVI correction and using either a 2nd-order or a
4th-order Runge-Kutta (RK) scheme.</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>Poiseuille flow</u></span>
<small>This experiment is performed as explained by <a href="https://se.copernicus.org/preprints/se-2014-49/" target="_blank">Thieulot (2014)</a>. The domain is a rectangle with L<sub>x</sub>=2 and L<sub>y</sub>=1, constant density and viscosity, gravity
acceleration equal to 0 and the penalty parameter is 10<sup>8</sup>. The grid is composed by 40×20 elements. Velocity boundary conditions are set to no slip (**v**=**0**) at the top and the bottom, and a parabolic profile is imposed on the sides, with v<sub>x</sub>=y(1−y) and v<sub>y</sub>=0.</small>
<figure>
  <img src="/assets/images/Poiseuille-1.png" alt="poiseuille" style="max-width:100%"/>
  <figcaption>Velocity field (panel a), pressure (panel b) and divergence velocity of a Poiseuille flow in case of the classic
penalty method (no iterations) and after one Uzawa iteration (panel c and d, respectively).</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>Instantaneous 2D sphere</u></span>
<small>The experiment is performed as explained in <a href="http://cedricthieulot.net/manual.pdf" target="_blank">FIELDSTONE (12.2.22)</a>. The domain is a unit square with gravity equal to -1. The fluid has constant density and viscosity. The sphere is in the middle of the domain with a radius
R=0.123456798 with constant density and viscosity higher than the fluid. Different types of velocity boundary conditions have been tested with grid resolutions between 16×16 and 512×512 elements and different average schemes for the viscosity (harmonic, geometric and arithmetic).</small>
<figure>
  <img src="/assets/images/vrms_NS-1.png" alt="inst_sphere" style="max-width:100%"/>
  <figcaption>Root-mean-square velocity (v<sub>rms</sub>) as function of element size for the instantaneous 2D sphere experiment in case of no slip boundary
conditions and with different average schemes for the viscosity. Results are compared with results obtained by <a href="https://aspect.geodynamics.org/" target="_blank">ASPECT</a>.</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>Rayleigh-Taylor experiment</u></span>
<small>This experiment is performed as explained by <a href="https://agupubs.onlinelibrary.wiley.com/doi/abs/10.1029/97JB01353" target="_blank">Van Keken et al. (1997)</a>. The domain has L<sub>x</sub>=0.9142 and L<sub>y</sub>=1 and gravity equal to -1. Two fluids with same constant viscosities and different densities are distributed in the domain, with the lighter fluid at the bottom. The initial interface between the fluids is given by y(x)=0.2+0.02 cos(πx L<sub>x</sub>). The experiment is performed with grid sizes between 50×50 and 256×256 elements. Velocity boundary conditions are set to no slip at the top and the bottom, and to free slip at the sides of the domain.</small>
<figure>
  <img src="/assets/images/RT-1.png" alt="RT" style="max-width:100%"/>
  <figcaption>Root-mean-square velocity (v<sub>rms</sub>) of the Rayleigh-Taylor experiment as function of time for different resolution of the grid.</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>Falling block</u></span>
<small>This experiment is performed as explained by <a href="https://www.sciencedirect.com/science/article/pii/S0031920103001900?via%3Dihub" target="_blank">Gerya and Yuen (2003)</a> and <a href="https://www.sciencedirect.com/science/article/pii/S0031920111001336?via%3Dihub" target="_blank">Thieulot (2011)</a>. The domain is square with L<sub>x</sub>=L<sub>y</sub>= 500 km and the grid is composed by 50×50 elements with 25 markers in each element.
The block is initially centred at x=250 km; y=400 km and has a size of 100×100 km. The fluid
surrounding the block has constant viscosities and densities. The benchmark tests with different viscosities and densities
of the block, with higher density than the surrounding fluid. Velocity boundary conditions are set to free slip conditions on all sides of the
domain.</small>
<figure>
  <img src="/assets/images/Falling-1.png" alt="falling" style="max-width:100%"/>
  <figcaption>Initial velocity relative to the density contrast at the centre of the falling block as function of the viscosity
contrast between the block and the surrounding fluid.</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>2D Stokes sphere</u></span>
<small>This experiment is performed as explained in <a href="http://cedricthieulot.net/manual.pdf" target="_blank">FIELDSTONE (12.2.23)</a>, in a unit square domain with the gravity acceleration fixed to −1. The sphere has
constant densities and viscosities hogher than the surrounding fluid and it is initially centred at (0.5; 0.6) with radius R = 0.123456789.
The fluid surrounding the sphere occupies the domain for y≤0.75, while for y>0.75 there is air.
Velocity boundary conditions are set to free slip on all sides. The Courant number is set to 0.25. The experiments
run for 200 s using grid resolutions from 150×150 to 512×512 elements, with 25 randomly distributed markers per
element, and for different average schemes for the viscosity. The interface between the fluid and the air is tracked by
means of the markers chain.</small>
<figure>
  <img src="/assets/images/vrms_arithm-1.png" alt="sphere" style="max-width:100%"/>
  <figcaption>Root-mean-square velocity (v<sub>rms</sub>) for different grid resolutions as function of time in case of an arithmetic average.
  Results are compared with results obtained with <a href="https://aspect.geodynamics.org/" target="_blank">ASPECT</a>.</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>Stabilisation algorithm</u></span>
<small>This experiment is performed as explained by <a href="https://www.sciencedirect.com/science/article/pii/S0031920110000877?via%3Dihub" target="_blank">Kaus et al. (2010)</a>. The domain is square with
L<sub>x</sub>=L<sub>y</sub>=500 km and a grid resolution of 200×200 elements, each of them containing 16 markers. A buoyant fluid is overlain by a denser fluid.
The initial interface between the fluids has an initial sinusoidal shape of 5 km amplitude. Velocity boundary conditions
are set to free slip conditions at the sides and no slip at the bottom, while the top is free surface. The experiment
is performed with various fixed time steps.</small>
<figure>
  <img src="/assets/images/Kaus_random-1.png" alt="kaus" style="max-width:100%"/>
  <figcaption>Evolution of the y coordinate in x=L<sub>x</sub> as function of time for different time steps, with and without the
stabilisation algorithm.</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>Topography relaxation</u></span>
<small>This experiment is performed as explained by <a href="https://academic.oup.com/gji/article/189/1/38/575556?login=false" target="_blank">Crameri et al. (2012)</a>. The domain is rectangular with L<sub>x</sub>=2800 km and L<sub>y</sub>=700 km in case of free surface and L<sub>y</sub>=800 km in case of sticky air. The grid is composed by 256×64 elements for the free surface 560×320 elements for the sticky air. For both cases, there is a mantle of 600 km thickness overlain by a highly viscous cosine-shaped lithosphere with thickness between 93 and 107 km. Velocity boundary conditions are set to no slip at the bottom and free slip at the sides of the domain. In case of sticky air, velocities on top are set to free slip conditions.</small>
<figure>
  <img src="/assets/images/Crameri-1.png" alt="crameri" style="max-width:100%"/>
  <figcaption>Maximum topography as function of time in comparison with
the analytical solution (black line) and results shown by <a href="https://academic.oup.com/gji/article/189/1/38/575556?login=false" target="_blank">Crameri et al. (2012)</a> with UNDERWORLD (yellow line) and SULEC (blue line).</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>Spontaneous subduction</u></span>
<small>This experiment is performed as explained by <a href="https://www.sciencedirect.com/science/article/pii/S0031920108001568" target="_blank">Schmeling et al. (2008)</a>, with both a sticky air and a true free
surface and using different average schemes for the viscosities. The domain is rectangular with L<sub>x</sub>=3000 km and
L<sub>y</sub>=700 km, a grid resolution of 256×64 elements with 50 markers per element and Courant number of 0.01. At the
beginning of the simulation, a denser 100 km-thick lithospheric layer is located
at the top of the domain for x between 1000 and 3000 km. In addition, a 200 km-depth lithospheric slab is already subducted in the mantle in order to have
a spontaneous subduction. In case of sticky air, a 50 km-thick air layer overlie the mantle. Velocity boundary conditions are set to free slip on the sides and on the bottom of the domain. In case of sticky air, velocities on the top boundary are set to free slip conditions as well.</small>
<figure>
  <img src="/assets/images/Subduction-1.png" alt="subduction" style="max-width:100%"/>
  <figcaption>Maximum depth of the slab as function of time. Red, green and blue Rectangular
areas indicate the range of times from <a href="https://www.sciencedirect.com/science/article/pii/S0031920108001568
" target="_blank">Schmeling et al. (2008)</a> when the slab tip reaches 500 km in case of sticky air (red, green and blue), and when the slab tip reaches 600 km in case of true free surface (gray).</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>Slab detachment</u></span>
<small>The slab detachment benchmark is performed as explained by <a href="https://www.sciencedirect.com/science/article/pii/S0012821X11000252?via%3Dihub" target="_blank">Schmalholz (2011)</a> and <a href="https://se.copernicus.org/articles/9/267/2018/" target="_blank">Glerum et al. (2018)</a>. The
domain is rectangular with L<sub>x</sub>=1000 km and L<sub>y</sub>=660 km and a grid resolution of 256×256 elements. A denser non-linear
viscous T-shaped layer is placed at the top of the domain and surrounded by a linear viscous fluid. The top layer is 80 km-thick and a 250 km-long and 80 km-wide slab is placed at x=L<sub>x</sub>/2. Velocity boundary conditions are set to free slip at the top and the bottom, and to no slip at the sides of the domain.</small>
<figure>
  <img src="/assets/images/Slab-1.png" alt="slab" style="max-width:100%"/>
  <figcaption>Effective viscosity for the slab detachment benchmark at the beginning of the evolution (panel a) and when
necking is complete (panel b).</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>Indenter</u></span>
<small>The indenter benchmark is performed as explained by <a href="https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2008JB005591" target="_blank">Thieulot et al. (2008)</a> and <a href="https://se.copernicus.org/articles/9/267/2018/" target="_blank">Glerum et al. (2018)</a>. The indenter benchmark simulate a rigid punch on a purely plastic von Mises material, for which exists an analytical
solution. The domain is a unit square with a grid resolution
of 256×256 elements. The gravity acceleration is set to 0. Velocity boundary conditions are set to no slip at the bottom and free
slip at the sides of the domain. The top of the domain is open with the exception of the central portion (punch area)
with width wp=0.125, where v<sub>y</sub>= −1.05 and v<sub>x</sub> is fixed either to 0 (rough punch experiment) or free (smooth punch
experiment).</small>
<figure>
  <img src="/assets/images/Indenter-1.png" alt="indenter" style="max-width:100%"/>
  <figcaption>Viscosity (panels a and b), strain rate (panels c and d), velocity (panels e and f) and pressure (panels g
and h) fields for rough (left column) and smooth (right column) punch experiments.</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>Brick</u></span>
<small>The experiment is perfomed as explained by <a href="https://se.copernicus.org/articles/9/267/2018/" target="_blank">Glerum et al. (2018)</a> to verify the correctness of the pressure-dependent plasticity for different angle of internal friction. The domain is rectangular with
L<sub>x</sub>=40 km and L<sub>y</sub>=10 km and a grid resolution of 512×128 elements. The maximum number of non-linear iterations is set to 1000. A
800 m-wide and 400 m-height inclusion is placed at the bottom of the domain at x=L<sub>x</sub>/2. The inclusion is surrounded by a non-linear viscous medium. Velocities are set to free slip conditions at the bottom of the domain and the top is open. Velocities on sides of the domain are fixed to v<sub>x</sub>=±2×10<sup>−11</sup> m s<sup>−1</sup> and v<sub>y</sub>=0. The experiment is performed in compressional and extensional contexts with an angle
of internal friction of the non-linear medium variable between 0° and 30°.</small>
<figure>
  <img src="/assets/images/Brick-1.png" alt="brick" style="max-width:100%"/>
  <figcaption>Shear band angles predicted for the brick experiment in case of compressional and extensional contexts as
function of different internal angle of friction (continuous black line and red dots), compared with theoretical Roscoe,
Artur and Coulomb angles (discontinuous black lines). Red lines indicate the range of angles calculated at different
depths.</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>Advection stabilisation</u></span>
<small>The 1D advection problem proposed by <a href="https://onlinelibrary.wiley.com/doi/book/10.1002/0470013826" target="_blank">Donea and Huerta (2003)</a> and <a href="https://www.sciencedirect.com/science/article/abs/pii/S0031920111001336?via%3Dihub" target="_blank">Thieulot (2011)</a> is performed to verify the
effectiveness of the SUPG method to stabilise the advection term of the energy equation. The domain is a 1D segment
with L<sub>x</sub>=1 composed by 50 elements and a discontinuity in the thermal field placed at x=0.25. Temperature is set
to 1 for x ≤ 0.25 and to 0 for x > 0.25. Velocity is set to u<sub>x</sub>=1 in the entire domain. The simulation is performed
for 250 time steps, with dt = 0.002, so the thermal discontinuity should be at x = 0.75 at the end of the simulation.
Temperature profiles at the end of the simulation are function of the dimensionless coefficient γ = τu<sub>x</sub>/h.</small>
<figure>
  <img src="/assets/images/Advection-1.png" alt="advection" style="max-width:100%"/>
  <figcaption>Temperature profile as function of x for the advection stabilisation benchmark. Purple line indicates the
initial temperature profile; the green line indicates the analytical temperature profile after 250 time steps; blue line
indicates the temperature profile after 250 time steps in case of the classic Galerkin method (γ=0); orange line
indicates the temperature profile after 250 time steps in case of the SUPG method (γ=0.045).</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>Simple shear heating</u></span>
<small>This exercise is performed in an unit square domain composed by 128×128 elements. The velocity field is prescribed
on the entire domain with u<sub>x</sub>=(L<sub>y</sub>−y)y; viscosity, density and specific heat are fixed to 1, while thermal
conductivity and radiogenic energy are fixed to 0. Therefore, the energy equation can be simplified and fixing T(t=0)=0, the temperature can be find as
T(t)=H<sub>s</sub>t, where shear heating H<sub>s</sub> can be calculated as H<sub>s</sub>(x,y)=(1−2y)<sup>2</sup>.</small>
<figure>
  <img src="/assets/images/Analytical_Shear-1.png" alt="shear" style="max-width:100%"/>
  <figcaption>Velocity (panel a), temperature (panel b) and shear heating (panel c) as function of the y coordinate
for the simple shear experiment. The solutions predicted by the model (red lines) are compared with the analytical
solutions (dashed blue lines).</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>Shear and adiabatic heating</u></span>
<small>This problem is performed as presented in Exercise 9.4 in <a href="https://www.cambridge.org/core/books/introduction-to-numerical-geodynamic-modelling/F2CDB0729FE6DE586BCD9B18C059AE07" target="_blank">Gerya (2010)</a>. Two materials are vertically separated in a
rectangular domain with L<sub>x</sub>=1000 km, L<sub>y</sub>=1500 km and a grid resolution of 30×20 elements. Constant thermal
coefficient expansion (α=3×10<sup>−5</sup> K<sup>−1</sup>), temperature (T=1300 K) and gravity acceleration (g<sub>y</sub>=−10 ms<sup>2</sup>) are
assumed in the whole domain. Fluid 1 on the left side of the domain has lower densitiea nd viscosities with respect to fluid 2 on the right side of the domain. Velocity boundary conditions are set to free slip on all sides of the domain.</small>
<figure>
  <img src="/assets/images/Energy-1.png" alt="energy" style="max-width:100%"/>
  <figcaption>Comparison between shear (first column), adiabatic (second column) and total (third column) energy
predicted by the code (panels a, b and c) and those created using example <i>Shear adiabatic heating.m</i> from Exercise
9.4 in <a href="https://www.cambridge.org/core/books/introduction-to-numerical-geodynamic-modelling/F2CDB0729FE6DE586BCD9B18C059AE07" target="_blank">Gerya (2010)</a> (panels d, e and f).</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>Mantle convection</u></span>
<small>This problem is performed as presented by <a href="https://academic.oup.com/gji/article/98/1/23/622167?login=false" target="_blank">Blankenbach et al. (1989)</a>(constant viscosity cases), in a 2D unit square domain with gravity acceleration g<sub>y</sub> = 10<sup>10</sup>Ra. The experiment is performed with three different Rayleigh numbers (Ra=10<sup>4</sup>, 10<sup>5</sup> and 10<sup>6</sup>) and with different grid resolution (between 32×32 and 128×128 elements).
The fluid has constant viscosity, initial density, heat capacity, thermal conductivity (η =ρ0=Cp=k=1), reference temperature (T<sub>0</sub>=0) and thermal expansion coefficient (α=10<sup>−10</sup>). Temperatures are set to 0 on top and 1 on bottom of the domain. Velocity boundary conditions are set to free slip on all sides. The initial temperature field is given by T(x,y)=(1−y)+0.01 cos(πx) sin(πy).</small>
<figure>
  <img src="/assets/images/Convection.png" alt="mantle" style="max-width:100%"/>
  <figcaption>Root-mean-square velocity (v<sub>rms</sub>) (panels a, c and e) and Nusselt number (panels b, d and f) as function of time for different grid resolution. Panels a and b show the results for Ra=10<sup>4</sup>; panels c and d show the results for Ra=10<sup>5</sup>; panels e and f show the results for Ra=10<sup>6</sup>. Purple lines indicate the convergence values for the v<sub>rms</sub> and the Nusselt number from <a href="https://academic.oup.com/gji/article/98/1/23/622167?login=false" target="_blank">Blankenbach et al. (1989)</a> at the steady state.</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>Visco-plastic mantle convection</u></span>
<small>This benchmark is performed as Cases 1-5a described in <a href="https://agupubs.onlinelibrary.wiley.com/doi/10.1002/2015GC005807" target="_blank">Tosi et al. (2015)</a> in a 2D unit square domain with two different grid resolutions of 32×32 and 100×100 elements. Reference viscosity, reference density, heat capacity,
thermal conductivity and thermal expansion coefficient are fixed to a constant value of 1 (η<sub>0</sub>=ρ<sub>0</sub>=C<sub>p</sub>=k=α=1), while the gravity has been chosen as g<sub>y</sub>=10<sup>2</sup>, in order to obtain a Rayleigh number Ra=10<sup>2</sup>. Temperatures are set to 0 on top and 1 on bottom of the domain. Velocity boundary conditions are set to free slip on all sides. The initial temperature field is given by
T(x,y)=(1−y)+0.01 cos(πx) sin(πy)
The viscosity field η is calculated as the harmonic average between a linear part η<sub>lin</sub> that depends on temperature only or on temperature and depth y and a nonlinear-plastic part η<sub>pl</sub> that depends on the strain rate ϵ̇.
See <a href="https://agupubs.onlinelibrary.wiley.com/doi/10.1002/2015GC005807" target="_blank">Tosi et al. (2015)</a> for more details.
<figure>
  <img src="/assets/images/table_tosi.png" alt="visc_mantle" style="max-width:100%"/>
  <figcaption>Results of the viscoplastic mantle convection benchmark for different grid resolutions in Cases 1-5 compared with results obtained with ELEFANT and YACC (100×100 elements, from <a href="https://agupubs.onlinelibrary.wiley.com/doi/10.1002/2015GC005807" target="_blank">Tosi et al., 2015</a>) and in Stone 28 (32×32 elements, from <a href="https://github.com/cedrict/fieldstone/tree/master/python_codes/fieldstone_28" target="_blank">Fieldstone</a>).</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>Thin layer entrainment</u></span>
<small>This experiment is performed as originally proposed by <a href="https://agupubs.onlinelibrary.wiley.com/doi/epdf/10.1029/97JB01353" target="_blank">Van Keken et al. (1997)</a> with two incompressible fluids in a rectangular domain with L<sub>x</sub>=2 and L<sub>y</sub>=1 and gravity acceleration g<sub>y</sub>=10<sup>10</sup> Ra. The Rayleigh number and the compositional Rayleigh number are fixed to Ra=300000 and Rc=450000, respectively. Both fluids have constant
viscosity, thermal conductivity, specific heat (η=ρ=C<sub>p</sub>=1) and thermal expansion coefficient (α=10<sup>−10</sup>). Fluid 1 has a density ρ<sub>1</sub>=1, while fluid 2 is denser (ρ<sub>2</sub>=ρ<sub>1</sub>+1.5·10<sup>−10</sup>) and is placed at the bottom of the domain, for y≤0.025. Temperature are set to 0 on top and 1 on bottom of the domain. Velocity boundary conditions are set to free slip on all sides of the domain. See <a href="https://agupubs.onlinelibrary.wiley.com/doi/epdf/10.1029/97JB01353" target="_blank">Van Keken et al. (1997)</a> for details about the initial temperature field.
The experiment is performed with two grid resolution (125×40 and 200×80 elements), with 100 markers per element and Courant number of 0.25.</small>
<figure>
  <img src="/assets/images/vrms_thin.png" alt="thin" style="max-width:100%"/>
  <figcaption>Root-mean-square velocity (v<sub>rms</sub>) as function of time for different grid resolution. Results are compared with results obtained by <a href="https://agupubs.onlinelibrary.wiley.com/doi/epdf/10.1029/97JB01353" target="_blank">Van Keken et al. (1997)</a> (black lines) and with ASPECT and ELEFANT.</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>Hydrated sinking cylinder</u></span>
<small>This experiment is performed as explained in <a href="https://se.copernicus.org/articles/5/537/2014/se-5-537-2014.pdf" target="_blank">Quinquis and Buiter (2014)</a> and simulates the sinking of a cold, hydrated cylinder into a warm, dry mantle. The domain is square with L<sub>x</sub>=L<sub>y</sub>=300 km, a grid resolution of 300×300 elements and 25 markers per element. The sinking cylinder is located at x=150 km and y=170 km with a radius of 20 km and has ρ<sub>c</sub>=3250 kg m<sup>−3</sup>,η<sub>c</sub>=1×10<sup>23</sup> Pa s, a thermal conductivity k<sub>c</sub>=4.5 W m<sup>−1</sup> K<sup>−1</sup>, a specific heat C<sub>pc</sub>=1250 J kg<sup>−1</sup> K<sup>−1</sup>; the surrounding mantle has ρ<sub>m</sub>=3200 kg m<sup>−3</sup>, η<sub>m</sub>=1×10<sup>20</sup> Pa s, a thermal conductivity k<sub>m</sub>=105 W m<sup>−1</sup> K<sup>−1</sup> and specific heat C<sub>pm</sub>=1250 J kg<sup>−1</sup> K<sup>−1</sup>; a 58 km-thick lithosphere overlies the mantle and has ρ<sub>c</sub>=3200 kg m<sup>−3</sup>, η<sub>l</sub>=1×10<sup>23</sup> Pa s, a thermal conductivity k<sub>l</sub>=4.5 W m<sup>−1</sup> K<sup>−1</sup>, C<sub>pl</sub>=750 J kg<sup>−1</sup> K<sup>−1</sup> and a thermal diffusivity of 1×10<sup>−6</sup> m<sup>2</sup> s<sup>−1</sup>. Velocity boundary conditions are set to free slip on all sides of the domain. Temperature increase linearly in the lithosphere, from 0° to 1300°C, and in the mantle, from 1300° to 1360.5°C. The initial temperature of the cylinder is fixed to 400°C. Throughout the evolution, temperature is fixed to 0° and 1360.5°C at the top and bottom of the domain, respectively. The initial bound water content is imposed at 2 wt.% in the cylinder and at 0 wt.% in both the mantle and the lithosphere. The maximum amount of water in the mantle is fixed to 0.2 wt.%, while maximum water content in the cylinder and in the lithosphere is function of pressure and temperature and is calculated using a serpentinized harzburgite with <a href="https://www.perplex.ethz.ch/" target=_blank>Perple_X</a>, as in <a href="https://se.copernicus.org/articles/5/537/2014/se-5-537-2014.pdf" target="_blank">Quinquis and Buiter (2014)</a>.</small>
<figure>
  <img src="/assets/images/water.png" alt="water" style="max-width:100%"/>
  <figcaption>Distribution of bound and free water (left and right columns, respectively) at t=0.5 and t=1.25 Myr (first and second rows, respectively). Only markers with bound or free water not equal to 0 are plotted.</figcaption>
</figure>

# <span style="color:lightblue;font-size:18px"><u>Experimental melting curves</u></span>
<small>This instantaneous experiment is performed in order to recreate isobaric melting curves, as function of temperature, bulk water and content of water in the melt, to compare with melting curves obtained by <a href="https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2002GC000433" target="_blank">Katz et al. (2003)</a>. The domain is square with L<sub>x</sub>=L<sub>y</sub>=100 km, a grid resolution of 100×100 elements and 25 markers per element.
Density is set in the entire domain to 3300 kg m<sup>−3</sup> and temperature increases from the sides to the centre from 1000° to 1500°C. The experiment is performed for bulk water contents from 0 to 0.3 wt.%.</small>
<figure>
  <img src="/assets/images/melt.png" alt="melt" style="max-width:100%"/>
  <figcaption>Isobaric melting curves for 1 GPa (panel a) and 3 GPa (panel b) as function of temperature with different bulk water contents.</figcaption>
</figure>