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

<small>**<span style="color:red">FALCON</span>** (**<span style="color:red">F</span>**em **<span style="color:red">AL</span>**gorithm for **<span style="color:red">CO</span>**mputational a**<span style="color:red">N</span>**alisys) is a FEM code written in Fortran90 used to study large-scale geodynamics system, such as continental rifting and subductions.</small>

# <span style="font-size:30px">Applications</span>
# <span style="font-size:22px"><u>Venus</u></span>
# <span style="font-size:22px"><u>Sesia</u></span>

# <span style="font-size:30px">Benchmarks</span>

*<span style="font-size:12px">The Gihub repository of this project can be found <a href="https://github.com/aleregorda/Benchmarks" target="_blank">here</a>. You can download the .zip file containing all the raw data of the benchmarks performed at this [link](https://github.com/aleregorda/Benchmarks/archive/refs/heads/main.zip).</span>*

Feature | Benchmark
---|---
Solver | <a href="/falcon/#stokes-flow" target="_blank">Stokes flow</a>
Markers advection | <a href="/falcon/#zalesak-disk" target="_blank">Zalesak disk</a><br><a href="/falcon/#conservative-velocity-interpolation" target="_blank">Conservative Velocity Interpolation</a>
Momentum equation | <a href="/falcon/#poiseuille-flow" target="_blank">Poiseuille flow</a><br><a href="/falcon/#instantaneous-2d-sphere" target="_blank">Instantaneous 2D sphere</a><br><a href="/falcon/#rayleigh-taylor-experiment" target="_blank">Rayleigh-Taylor experiment</a><br><a href="/falcon/#falling-block" target="_blank">Falling block</a>
Sticky air and free surface | <a href="/falcon/#2d-stokes-sphere" target="_blank">2D Stokes sphere</a><br><a href="/falcon/#stabilisation-algorithm" target="_blank">Stabilisation algorithm</a><br><a href="/falcon/#topography-relaxation" target="_blank">Topography relaxation</a><br><a href="/falcon/#spontaneous-subduction" target="_blank">Spontaneous subduction</a>
Nonlinear rheology | <a href="/falcon/#slab-detachment" target="_blank">Slab detachment</a><br><a href="/falcon/#indenter" target="_blank">Indenter</a><br><a href="/falcon/#brick" target="_blank">Brick</a>
Energy equation | <a href="/falcon/#advection-stabilisation" target="_blank">Advection stabilisation</a><br><a href="/falcon/#simple-shear-heating" target="_blank">Simple shear heating</a><br><a href="/falcon/#shear-and-adiabatic-heating" target="_blank">Shear and adiabatic heating</a>
Energy+momentum | <a href="/falcon/#mantle-convection" target="_blank">Mantle convection</a><br><a href="/falcon/#visco-plastic-mantle-convection" target="_blank">Visco-plastic mantle convection</a><br><a href="/falcon/#thin-layer-entrainment" target="_blank">Thin layer entrainment</a>
Phase changes and hydration | <a href="/falcon/#hydrated-sinking-cylinder" target="_blank">Hydrated sinking cylinder</a>
Melting | <a href="/falcon/#melting" target="_blank">Experimental melting curves</a>

# <span style="font-size:22px"><u>Stokes flow</u></span>
<small>The problem consists of determining velocity field (*u*, *v*) and pressure *p* in case of a manufactured solution with
prescribed body forces.
The domain is a unit square a constant viscosity and the penalty parameter is set to 10<sup>7</sup>. Velocity boundary
conditions are set to no slip (**v** = **0**) on all boundaries. The problem is performed for different grid resolution between
8 × 8 and 1024 × 1024 elements.</small>
<figure>
  <img src="/assets/images/errors-1.png" alt="errors" style="width:700px"/>
  <figcaption>Velocity and pressure error for the Stokes flow experiment between generated and analytical solution as a function of element size (panel a), and comparison between smoothed pressure and analytical solution as function of x coordinate for a grid resolution of 128 × 128 elements (panel b)</figcaption>
</figure>
<figure>
  <img src="/assets/images/MUMPS-1.png" alt="mumps" style="width:700px"/>
  <figcaption>Analysis, factorisation, solution and total solve times (panel a) and factorisation memory usage
(panel b) as a function of the total number of degrees of freedom for the Stokes flow experiment</figcaption>
</figure>

# <span style="font-size:22px"><u>Zalesak disk</u></span>
<small>The benchmark is performed in a unit square domain with a grid resolution of 32 × 32 elements and values of Courant number (CFL) between 0.25 and 1.
The velocity field is prescribed in the entire domain.
At t=0, the disk is centred at position (0.5; 0.75) with a radius R=0.15 and has a vertical fissure 0.05 wide and 0.2 high.</small>

<figure>
  <img src="/assets/images/zal_marker-1.png" alt="zal_error" style="width:450px"/>
  <figcaption>Distance from the centre as function of time for values of Courant number of of 0.25, 0.3, 0.5, 0.75 and 1
(green, orange, blue, black and red, respectively).</figcaption>
</figure>

# <span style="font-size:22px"><u>Conservative Velocity Interpolation</u></span>
<small>The Conservative Velocity Interpolation (CVI) correction is checked by means of the <a href="/falcon/#stokes-flow" target="_blank">Stokes flow experiment</a>. The advection of Lagrangian markers is performed using either a 2nd-order or a 4th-order Runge-Kutta scheme with CFL=0.5 and an initial random distribution of 25 markers per element.</small>

<figure>
  <img src="/assets/images/CVI-1.png" alt="cvi" style="width:700px"/>
  <figcaption>Maximum and minimum number of markers per element, with or without the CVI correction and using either a 2nd-order or a
4th-order Runge-Kutta (RK) scheme.</figcaption>
</figure>
<figure>
  <img src="/assets/images/CVI_time-1.png" alt="cvi_time" style="width:700px"/>
  <figcaption>Number of markers per element (first row) and markers distribution (second row) with 2nd-order Runge-Kutta scheme.
Panels a: model with CVI at t=1;
panels b and c: comparison between models without and with the CVI correction, respectively, at t=600; panels d: model with CVI correction at t=2000.</figcaption>
</figure>

# <span style="font-size:22px"><u>Poiseuille flow</u></span>
# <span style="font-size:22px"><u>Instantaneous 2D sphere</u></span>
# <span style="font-size:22px"><u>Rayleigh-Taylor experiment</u></span>
# <span style="font-size:22px"><u>Falling block</u></span>
# <span style="font-size:22px"><u>2D Stokes sphere</u></span>
# <span style="font-size:22px"><u>Stabilisation algorithm</u></span>
# <span style="font-size:22px"><u>Topography relaxation</u></span>
# <span style="font-size:22px"><u>Spontaneous subduction</u></span>
# <span style="font-size:22px"><u>Slab detachment</u></span>
# <span style="font-size:22px"><u>Indenter</u></span>
# <span style="font-size:22px"><u>Brick</u></span>
# <span style="font-size:22px"><u>Advection stabilisation</u></span>
# <span style="font-size:22px"><u>Simple shear heating</u></span>
# <span style="font-size:22px"><u>Shear and adiabatic heating</u></span>
# <span style="font-size:22px"><u>Mantle convection</u></span>
# <span style="font-size:22px"><u>Visco-plastic mantle convection</u></span>
# <span style="font-size:22px"><u>Thin layer entrainment</u></span>
# <span style="font-size:22px"><u>Hydrated sinking cylinder</u></span>
# <span style="font-size:22px"><u>Melting</u></span>