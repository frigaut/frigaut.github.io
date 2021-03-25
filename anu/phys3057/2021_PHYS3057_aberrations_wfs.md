---
presentation:
 enableSpeakerNotes: true
 width: 960
 height: 700
 margin: 0.04
 controls: false
 theme: white.css
 progress: true
 slideNumber: 'c/t'
 keyboard: true
 center: false
 showNotes: false
 hash: false
 totalTime: 400
 overview: true
 transitionSpeed: 'default' # default/fast/slow
 mouseWheel: true
 transition: 'none' # none/fade/slide/convex/concave/zoom
title: "PHYS3057 Fourier Optics"
---

@import "anu.less"

<!-- slide -->
# Fourier Optics:<br>Aberrations and Wavefront Sensors

<br /> 
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />

**Prof François Rigaut**
Research School of Astronomy & Astrophysics
The Australian National University
<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->

###### Phase Aberrations



<!-- slide vertical=true -->

## Phase Aberrations - Geometrical view

* Wavefront departs from flatness
* When focused, rays do not intersect at the same location

<img src="assets/images/fop_43.png" width="100%">
<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->

## Phase Aberrations - Fourier Optics view

$$\Large \Psi(x,y,t) = A(x,y,t) e^{i{\color{red} \varphi(x,x,t)}}  $$

* Now $\varphi(x,y,t) \neq 0$, thus the PSF $H$ departs from the simple square modulus of the aperture, as presented in previous lectures.
* This yields asymmetry and spread, and a loss of angular resolution as well as:
  *  a loss of Strehl ratio
  * further attenuation of spatial frequencies in the OTF

<img src="assets/images/fop_44.png" width="80%">

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>


<!-- slide -->

###### Seidel Aberrations

<!-- slide vertical=true -->

## Seidel Aberrations


<div style="position: absolute; left:700px; top: 100px;"><img src="assets/images/fop_96.png" width="320px"></div>
<div style="position: absolute; right:0px; top: 320px;"><img src="assets/images/fop_46.png" width="320px"></div>

* Primary aberrations from optical system misalignment or manufacturing error
* Seidel aberrations for monochromatic light:
  1) Spherical aberration
  1) Coma
  1) Astigmatism
  1) <span style="color:blue">Curvature of field</span>
  1) <span style="color:blue">Distortion</span>
  1) <span style="color:blue">Chromatic</span>

<span style="position: absolute; left: 290px; top: 300px; font-size: 70%; width:320px;color:blue;"> (Not phase aberrations as described previously in this lecture, i.e. for a single point like object. Those are field dependent or wavelength dependant aberrations)</span>

<img style="display: inline; float:left; margin-left: 30px; margin-top: -10px;" width="360px" src="assets/images/fop_45.png">

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->

## Seidel aberrations: Coma

* Also a field aberration in many optical system (i.e. something you get when looking off-axis)<img src="assets/images/fop_48.png" width="45%" style="display: inline; float:right;">
  * "field Aberration": an aberration that varies as a function of position in the output field (field = image plane)
* Characterised by core + tail  

<img src="assets/images/fop_47.png" width="60%">

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->

## Seidel aberrations: Spherical

* Often due to polishing error<img src="assets/images/fop_49.png" width="45%" style="display: inline; float:right;">
* The Hubble space telescope is an infamous example
<img src="assets/images/fop_50.png" width="80%">

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->

## Seidel aberrations

* **Left**: geometrical (ray) view |  **right**: physical (Fourier) optics view
<img src="assets/images/fop_49.png" width="35%" style="display: inline; float:right;">
<img src="assets/images/fop_51.png" width="65%" style="display: inline; float:left;">
<img src="assets/images/fop_48.png" width="35%" style="display: inline; float:right;">
<img src="assets/images/fop_52.png" width="35%" style="display: inline; clear: both; float:right;">

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->

## Beyond Seidel: real eye cases

<img src="assets/images/fop_53.png" width="80%">

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide -->

###### Zernike polynomials to describe phase aberrations


<!-- slide vertical=true -->

## Zernike polynomials/modes

<img src="assets/images/fop_54.png" width="57%">

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>


<!-- slide vertical=true -->

## Zernike polynomials: background



* The <img src="assets/images/fop_55.png" width="45%" style="display: inline; float:right; margin-left: 1em;"> mathematical functions were originally described by Fritz Zernike in 1934.
* They were developed to describe the diffracted wavefront in phase contrast imaging.
* Zernike won the 1953 Nobel Prize in Physics for developing Phase Contrast Microscopy.

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>


<!-- slide vertical=true -->
## Zernike polynomials/modes

<img src="assets/images/fop_56.png" width="88%">

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Why Zernikes?

* Zernike <img src="assets/images/fop_57.png" width="55%" style="display: inline; float:right; margin-left: 1em;">polynomials have nice mathematical properties:
  * They are orthogonal over the continuous unit circle: $$\iint_S Z_i(x,y,)Z_j(x,y) dS = \delta_{ij}$$
  * All their derivatives are continuous.
* They efficiently represent common errors (e.g. coma, spherical aberration) seen in optics.
* They form a complete set, meaning that they can represent arbitrarily complex continuous surfaces given enough terms.


<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Zernike polynomials

<img src="assets/images/fop_58.png" width="83%">


<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Zernike polynomials...

<img src="assets/images/fop_59.png" width="60%" style="display: inline; float:right; margin-right: 70px;">

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## ... and corresponding PSFs


<div style="position: absolute; top:160px; left:0px; width: 35%;"><img src="assets/images/fop_61.png"></div>

<img src="assets/images/fop_60.png" width="60%" style="display: inline; float:right; margin-right: 70px;">


<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide -->

###### Zernike polynomials to describe phase aberrations


<!-- slide vertical=true -->
## Phase expansion and phase variance

The phase can be described as a *superposition** (sum) of Zernike polynomials

$$ \varphi(x,y,t) \sum_{i=1}^\infty a_i(t) Z_i(x,y)  $$

where the coefficients are calculated as follow:

$$ a_i = \int_S W(r) \varphi(r,\theta) Z_i(r,\theta) \:r\:dr \:d\theta$$

The phase variance is then readily computed as:

$$ \sigma_\varphi^2 =<\varphi^2(x,y,t) >_t = \sum_{i=1}^\infty a^2_i(t) \text{ given } \iint_S Z_i(x,y,)Z_j(x,y) dS = \delta_{ij} $$

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Impact on Optical Transfer Function

<img src="assets/images/fop_62.png" width="49%" style="display: inline; margin: auto;">
<img src="assets/images/fop_63.png" width="49%" style="display: inline; margin: auto;">
<img src="assets/images/fop_64.png" width="49%" style="display: inline; margin: auto;">
<img src="assets/images/fop_65.png" width="49%" style="display: inline; margin: auto;">

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Aberration retrieval

<div style="position: absolute; top:180px; right:0px; width: 35%; z-index:-1;"><img src="assets/images/fop_67.png"></div>
<div style="position: absolute; top:470px; right: 40px; width: 18%;"><img src="assets/images/fop_69.png"></div>

* Using Wavefront sensors  <img src="assets/images/fop_66.png" width="30%" style="display: inline; float:right; margin: auto; margin-right: 180px;">
  * Hartmann, Shack-Hartmann sensor
  * Foucault knife, pyramid sensor
  * Interferometer: Michelson, Mach-Zehnder, Fizeau,…
  * Self referenced interferometers: Shearing, point diffraction,…
* Using the image itself
  * Phase diversity
<img src="assets/images/fop_68.png" width="65%" style="display: inline; float:left; margin: auto; margin-right: 0px;">

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide -->

###### Wavefront Sensors

<!-- slide vertical=true -->

## Linear Optical Systems

<img src="assets/images/fop_10.png" width="85%">

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>


<!-- slide vertical=true -->
## Wavefront Sensors (WFS)


* A device that is measuring the wavefront phase (and potentially amplitude)
* Many wavefront sensors measure the phase first derivative (local slope) or second derivative (local curvature), some use a mix of both
  * First derivative wavefront sensors:
    * Shack-Hartmann
    * Shearing interferometers (lateral, radial, rotation)
    * Pyramid, Foucault knife
* Second derivative wavefront sensors:
  * Curvature
* And then some device measure the phase difference with some reference wave:
  * Point diffraction interferometer, Michelson, …
* But all do that through an intensity measurement of some sort 

<span style="position: absolute; left:600px; top:245px; color:red;">$$ \Bigg) \frac{\partial\varphi}{\partial x} or \nabla\varphi$$ </span>
<span style="position: absolute; left:600px; top:360px; color:red;">$$ \Big) \frac{\partial\varphi}{\partial x} or \nabla\varphi$$ </span>
<span style="position: absolute; left:600px; top:504px; color:red;">$$ \big) \varphi$$ </span>


<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide -->

###### Shack-Hartmann Wavefront Sensor: how does it work?

<!-- slide vertical=true -->
## Shack-Hartmann WFS

<img src="assets/images/fop_75.png" width="85%">


<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Shack-Hartmann WFS

<img src="assets/images/fop_74.png" width="85%">


<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Shack-Hartmann WFS

<img src="assets/images/fop_73.png" width="85%">


<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Shack-Hartmann WFS

<img src="assets/images/fop_70.png" width="85%">


<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Shack-Hartmann WFS

<img src="assets/images/fop_72.png" width="85%">


<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Shack-Hartmann WFS

<img src="assets/images/fop_71.png" width="85%">


<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide -->

###### SHWFS Extension in two dimensions

<!-- slide vertical=true -->
## Shack-Hartmann in 2D

<img src="assets/images/fop_76.png" width="70%">

* A Shack-Hartmann sensor measure the average X and Y gradient over the subaperture

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Shack-Hartmann in 2D

<br>
<center>No Aberration</center>
<img src="assets/images/fop_77.png" width="70%">


<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Shack-Hartmann in 2D

<br>
<center>Tilt (Z2)</center>
<img src="assets/images/fop_78.png" width="70%">


<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Shack-Hartmann in 2D

<br>
<center>Defocus (Z4)</center>
<img src="assets/images/fop_79.png" width="70%">


<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Shack-Hartmann in 2D

<br>
<center>Astigmatism (Z6)</center>
<img src="assets/images/fop_80.png" width="70%">


<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Shack-Hartmann in 2D

<br>
<center>Coma (Z8)</center>
<img src="assets/images/fop_81.png" width="70%">


<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Shack-Hartmann in 2D

<br>
<center>Spherical (Z11)</center>
<img src="assets/images/fop_82.png" width="70%">


<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Shack-Hartmann in 2D

<br>
<center>High order (e.g. Z21)</center>
<img src="assets/images/fop_83.png" width="70%">


<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide -->

###### Real-World Considerations

<!-- slide vertical=true -->
## What WFS to choose?

* Noise, usage of light
* Dynamical range
* Linearity, hysteresis
* Cost
* Polychromaticity
* Spatial aliasing
* Speed, computational requirements
* Solution uniqueness
* Extended sources
* Self referenced
* Ease of implementation


<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Sensor Transfer function

<img src="assets/images/fop_86.png">
<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Sensing issues: non linearity

<img src="assets/images/fop_87.png">
<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Sensing issues: Calibration error

<img src="assets/images/fop_88.png">
<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Sensing issue: Hysteresis

<img src="assets/images/fop_89.png" width="90%">
<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Noise and SNR

<img src="assets/images/fop_90.png" width="80%">
<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Trade-offs and choice drivers

<img src="assets/images/fop_91.png" width="90%">
<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide -->

###### Other Real-World Considerations


<!-- slide vertical=true -->
## Practical implementation


In Astronomy  <span style="display: block; float:right;margin-right: 50px;">In Ophthalmology</span>

<img src="assets/images/fop_84.png" width="57%" style="display: inline; margin: auto;">
<img src="assets/images/fop_85.png" width="39%" style="display: inline; margin: auto;">

* Field stop
* Collimating optics (usually lenslet 1F behind collimator)
* Lenslet array (most commercial arrays have pitch of 100-1000 μm)
* 2D Sensor: Most CCDs/CMOS have pixels of 2 (CMOS for phones) to 20 microns (CCDs for science applications). Typical format 128^2^ to 2048^2^.

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Applications & Needs

<img src="assets/images/fop_92.png" width="90%">
<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide -->

###### Alternatives WFS techniques

<!-- slide vertical=true -->
## Alternative: Phase diversity

* Focal <img src="assets/images/fop_93.png" width="28%" style="display: inline; float:right; margin-left: 0.5em;"> plane method
* Acquire an “in focus” image
* but (wavefront) phase is lost during the image formation
$$ {\cal I} = | {\cal F} (A e^{i\varphi}) |^2 $$
* ...and an image with some added phase “diversity”, e.g. focus
$$ {\cal I}' = | {\cal F} (A e^{i(\varphi+\varphi_0)}) |^2 $$
* The second image lift the sign uncertainty
* Then use a minimisation package (Steepest descent, Conjugate Gradient, Levenberg–Marquardt, etc) to find the phase that reproduce best the images, or AI.

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide vertical=true -->
## Minimisation & Fitting

* The problem:  Given data points $y_i$ at $x_i$, find model parameters $\beta$ so that the least square distance model-data $S$ is minimum:
<img src="assets/images/fop_94.png" width="40%" style="display: inline; float:right; margin-left: 0.5em;">$$ S(\beta_1,\beta_2) = \sum_{i=1}^m (y_i - f(x_i,\beta_1,\beta_2))^2$$
* Iterative methods
* Steepest descent, Conjugate Gradient, 
Levenberg–Marquardt
* Issue with local minima:
<img src="assets/images/fop_95.png" width="45%">

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>


