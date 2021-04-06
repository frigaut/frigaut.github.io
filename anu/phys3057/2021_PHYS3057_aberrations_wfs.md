---
marp: true
theme: anu
size: 4:3
title: PHYS3057 Aberrations and WFSs
description: Part of PHYS3057 Fourier Optics series
_class: lead
footer: '&copy; Rigaut 2021, PHYS3057 Fourier Optics'
paginate: true
---

<style>
section {
  /* can add styles in here */
}
</style>


<!-- _class: invert -->
# <!-- fit -->Fourier Optics:<br>Aberrations and Wavefront Sensors

<div class="authors">

**Prof François Rigaut**
Research School of Astronomy & Astrophysics
The Australian National University
</div>

---
## Linear Optical Systems


<img src="assets/images/fop_10.png" width="85%">



---
<!-- _class: invert -->
###### Phase Aberrations

---

## Phase Aberrations - Geometrical view

- Wavefront departs from flatness
- When focused, rays do not intersect at the same location

![w:1050](assets/images/fop_43.png)

---

## Phase Aberrations - Fourier Optics view

$$\large \Psi(x,y,t) = A(x,y,t) e^{i{\color{red} \varphi(x,x,t)}}  $$

- Now, $\varphi(x,y,t) \neq 0$, thus the PSF $H$ departs from the simple square modulus of the aperture, as presented in previous lectures.
- This yields asymmetry and spread, and a loss of angular resolution as well as:
  -  a loss of Strehl ratio
  - further attenuation of spatial frequencies in the OTF

![w:780](assets/images/fop_44.png)

---
<!-- _class: invert -->
###### Seidel Aberrations

---

## Seidel Aberrations


<div style="position: absolute; left:640px; top: 100px;"><img src="assets/images/fop_96.png" width="270px"></div>
<div style="position: absolute; right:10px; top: 340px;"><img src="assets/images/fop_46.png" width="300px"></div>

- Primary aberrations from optical system misalignment or<br> manufacturing error
- Seidel aberrations for monochromatic light:
  1. Spherical aberration
  1. Coma
  1. Astigmatism
  1. <span style="color:blue">Curvature of field</span>
  1. <span style="color:blue">Distortion</span>
  1. <span style="color:blue">Chromatic</span>

<span style="position: absolute; left: 290px; top: 300px; font-size: 70%; width:320px;color:blue;"> (Not phase aberrations as described previously in this lecture, i.e. for a single point like object. Those are field dependent or wavelength dependant aberrations)</span>

<img style="display: inline; float:left; margin-left: 30px; margin-top: -10px;" width="360px" src="assets/images/fop_45.png">

---

## Seidel aberrations: Coma

- Also a field aberration in many optical system (i.e. something you get when looking off-axis)<img src="assets/images/fop_48.png" width="45%" style="display: inline; float:right;">
  - "field Aberration": an aberration that varies as a function of position in the output field (field = image plane)
- Characterised by core + tail  

<img src="assets/images/fop_47.png" width="60%">

---

## Seidel aberrations: Spherical

- Often due to polishing error<img src="assets/images/fop_49.png" width="45%" style="display: inline; float:right;">
- The Hubble space telescope is an infamous example
![](assets/images/fop_50.png)



---

## Seidel aberrations

| Geometrical (ray) view |  Fourier optics view |
| --- | --- |
| ![w:500](assets/images/fop_51.png) | ![w:300](assets/images/fop_49.png)![w:300](assets/images/fop_48.png)![w:300](assets/images/fop_52.png) |



---

## Beyond Seidel: real eye cases

<img src="assets/images/fop_53.png" width="90%">


---
<!-- _class: invert -->
###### Zernike polynomials to describe phase aberrations


---

## Zernike polynomials/modes

<img src="assets/images/fop_54.png" width="57%">



---

## Zernike polynomials: background


![bg right:45%](assets/images/fop_55.png)

- The mathematical functions were originally described by Fritz Zernike in 1934.
- They were developed to describe the diffracted wavefront in phase contrast imaging.
- Zernike won the 1953 Nobel Prize in Physics for developing Phase Contrast Microscopy.



---
## Zernike polynomials/modes

<img src="assets/images/fop_56.png" width="88%">



---
## Why Zernikes?

- Zernike <img src="assets/images/fop_57.png" width="50%" style="display: inline; float:right; margin-left: 1em;">polynomials have nice mathematical properties:
  - They are orthogonal over the continuous unit circle: $\iint_S Z_i(x,y,)Z_j(x,y) dS = \delta_{ij}$
  - All their derivatives are continuous.
- They efficiently represent common errors (e.g. coma, spherical aberration) seen in optics.
- They form a complete set, meaning that they can represent arbitrarily complex continuous surfaces given enough terms.

---
## Zernike polynomials

<img src="assets/images/fop_58.png" width="83%">




---
## Zernike polynomials...

<img src="assets/images/fop_59.png" width="60%" style="display: inline; float:right; margin-right: 70px;">



---
## ... and corresponding PSFs


<div style="position: absolute; top:172px; left:0px"><img src="assets/images/fop_61.png" width="335px"></div>

<img src="assets/images/fop_60.png" width="60%" style="display: inline; float:right; margin-right: 70px;">




---
<!-- _class: invert -->
###### Zernike polynomials to describe phase aberrations


---
## Phase expansion and phase variance

The phase can be described as a **superposition** (sum) of Zernike polynomials

$$ \varphi(x,y,t) \sum_{i=1}^\infty a_i(t) Z_i(x,y)  $$

where the coefficients are calculated as follow:

$$ a_i = \int_S W(r) \varphi(r,\theta) Z_i(r,\theta) \:r\:dr \:d\theta$$

The phase variance is then readily computed as:

$$ \sigma_\varphi^2 =<\varphi^2(x,y,t) >_t = \sum_{i=1}^\infty a^2_i(t) \text{ given } \iint_S Z_i(x,y,)Z_j(x,y) dS = \delta_{ij} $$



---
## Impact on Optical Transfer Function

<img src="assets/images/fop_62.png" width="49%" style="display: inline; margin: auto;">
<img src="assets/images/fop_63.png" width="49%" style="display: inline; margin: auto;">
<img src="assets/images/fop_64.png" width="49%" style="display: inline; margin: auto;">
<img src="assets/images/fop_65.png" width="49%" style="display: inline; margin: auto;">



---
## Aberration retrieval

<div style="position: absolute; top:230px; right:0px; z-index:1;"><img src="assets/images/fop_67.png" width="260px"></div>

<div style="position: absolute; top:470px; right:40px;"><img src="assets/images/fop_69.png" width="200px"></div>

- Using Wavefront sensors  <img src="assets/images/fop_66.png" width="28%" style="display: inline; float:right; margin: auto; margin-right: 180px;">
  - Hartmann, Shack-Hartmann sensor
  - Foucault knife, pyramid sensor
  - Interferometer: Michelson, Mach-Zehnder, Fizeau,…
  - Self referenced interferometers: Shearing, point diffraction,…
- Using the image itself
  - Phase diversity

<img src="assets/images/fop_68.png" width="55%" style="display: inline; float:left; margin: auto; margin-right: 0px;">



---
<!-- _class: invert -->
###### Wavefront Sensors

---

## Linear Optical Systems

<img src="assets/images/fop_10.png" width="85%">




---
## Wavefront Sensors (WFS)


- A device that is measuring the wavefront phase (and potentially amplitude)
- Many wavefront sensors measure the phase first derivative (local slope) or second derivative (local curvature), some use a mix of both
  - First derivative wavefront sensors:
    - Shack-Hartmann
    - Shearing interferometers (lateral, radial, rotation)
    - Pyramid, Foucault knife
- Second derivative wavefront sensors:
  - Curvature
- And then some device measure the phase difference with some reference wave:
  - Point diffraction interferometer, Michelson, …
- But all do that through an intensity measurement of some sort 

<!-- <span style="position: absolute; left:600px; top:245px; color:red;"> 
$$ \Bigg) \frac{\partial\varphi}{\partial x} or \nabla\varphi$$
</span>
<span style="position: absolute; left:600px; top:360px; color:red;">$$ \Big) \frac{\partial\varphi}{\partial x} or \nabla\varphi$$ </span>
<span style="position: absolute; left:600px; top:504px; color:red;">$$ \big) \varphi$$ </span> -->




---
<!-- _class: invert -->
###### Shack-Hartmann Wavefront Sensor: how does it work?

---
## Shack-Hartmann WFS

<img src="assets/images/fop_75.png" width="85%">




---
## Shack-Hartmann WFS

<img src="assets/images/fop_74.png" width="85%">




---
## Shack-Hartmann WFS

<img src="assets/images/fop_73.png" width="85%">




---
## Shack-Hartmann WFS

<img src="assets/images/fop_70.png" width="85%">




---
## Shack-Hartmann WFS

<img src="assets/images/fop_72.png" width="85%">




---
## Shack-Hartmann WFS

<img src="assets/images/fop_71.png" width="85%">




---
<!-- _class: invert -->
###### SHWFS Extension in two dimensions

---
## Shack-Hartmann in 2D

<img src="assets/images/fop_76.png" width="70%">

- A Shack-Hartmann sensor measure the average X and Y gradient over the subaperture



---
## Shack-Hartmann in 2D

<br>
<center>No Aberration</center>
<img src="assets/images/fop_77.png" width="70%">




---
## Shack-Hartmann in 2D

<br>
<center>Tilt (Z2)</center>
<img src="assets/images/fop_78.png" width="70%">




---
## Shack-Hartmann in 2D

<br>
<center>Defocus (Z4)</center>
<img src="assets/images/fop_79.png" width="70%">




---
## Shack-Hartmann in 2D

<br>
<center>Astigmatism (Z6)</center>
<img src="assets/images/fop_80.png" width="70%">




---
## Shack-Hartmann in 2D

<br>
<center>Coma (Z8)</center>
<img src="assets/images/fop_81.png" width="70%">




---
## Shack-Hartmann in 2D

<br>
<center>Spherical (Z11)</center>
<img src="assets/images/fop_82.png" width="70%">




---
## Shack-Hartmann in 2D

<br>
<center>High order (e.g. Z21)</center>
<img src="assets/images/fop_83.png" width="70%">




---
<!-- _class: invert -->
###### Real-World Considerations

---
## What WFS to choose?

- Noise, usage of light
- Dynamical range
- Linearity, hysteresis
- Cost
- Polychromaticity
- Spatial aliasing
- Speed, computational requirements
- Solution uniqueness
- Extended sources
- Self referenced
- Ease of implementation




---
## Sensor Transfer function

![](assets/images/fop_86.png)


---
## Sensing issues: non linearity

![](assets/images/fop_87.png)


---
## Sensing issues: Calibration error

![](assets/images/fop_88.png)


---
## Sensing issue: Hysteresis

![w:800](assets/images/fop_89.png)


---
## Noise and SNR

![w:800](assets/images/fop_90.png)


---
## Trade-offs and choice drivers

![](assets/images/fop_91.png)


---
<!-- _class: invert -->
###### Other Real-World Considerations


---

## Practical implementation



|In Astronomy  |In Ophthalmology |
|--- |--- |
| ![h:240](assets/images/fop_85.png) | ![h:240](assets/images/fop_84.png) |

- Field stop
- Collimating optics (usually lenslet 1F behind collimator)
- Lenslet array (most commercial arrays have pitch of 100-1000 μm)
- 2D Sensor: Most CCDs/CMOS have pixels of 2 (CMOS for phones) to 20 microns (CCDs for science applications). Typical format $128^2$ to $2048^2$.



---
## Applications & Needs

![](assets/images/fop_92.png)


---
<!-- _class: invert -->
###### Alternatives WFS techniques

---
## Alternative: Phase diversity


- Focal plane method<img src="assets/images/fop_93.png" width="28%" style="display:inline; float:right; margin-left: 0.5em;">
- Acquire an "in focus" image
- but (wavefront) phase is lost during the image formation ${\cal I} = | {\cal F} (A e^{i\varphi}) |^2$
- ...and an image with some added phase "diversity", e.g. focus ${\cal I}' = | {\cal F} (A e^{i(\varphi+\varphi_0)}) |^2$
- The second image lift the sign uncertainty
- Then use a minimisation package (Steepest descent, Conjugate Gradient, Levenberg–Marquardt, etc) to find the phase that reproduce best the images, or AI.



---
## Minimisation & Fitting

- The problem:  Given data points $y_i$ at $x_i$, find model parameters $\beta$ so that the least square distance model-data $S$ is minimum:
<img src="assets/images/fop_94.png" width="40%" style="display: inline; float:right; margin-left: 0.5em;">$S(\beta_1,\beta_2) = \sum_{i=1}^m (y_i - f(x_i,\beta_1,\beta_2))^2$
- Iterative methods
- Steepest descent, Conjugate Gradient, 
Levenberg–Marquardt
- Issue with local minima:
<img src="assets/images/fop_95.png" width="58%">

