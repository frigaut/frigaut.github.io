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
title: "PHYS3057 Fourier Optics Tutorial"
---

@import "anu.less"

<!-- slide -->
# Fourier Optics Tutorial

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

<!-- slide -->

## Image metric: Full-Width at Half-Maximum

* The width of the image at half its maximum. Often written FWHM
* For instance, a cross section of a gaussian image

<div style="position; relative; float: left;"><img src="assets/images/fop_30.png" width="580px"></div><img src="assets/images/fop_31.png" width="200px">


* The FWHM is often naturally expressed as an angle (e.g. arcsec) or a distance (e.g. mm), as it often characterise a resolution

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide -->

## Angular Resolution, Angle and Size


<img src="assets/images/fop_97.png">


* What is the angular extent $\alpha$ of a segment of size $h$ at distance $d$?
  * $\tan(\alpha/2) = (h/2)/d = h/(2d) \implies \alpha = 2 \arctan (h/(2d)) $
  * For small angles $\alpha = 2 \arctan (h/(2d)) = h/d$
<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide -->

## Angular Resolution; Angle and Size

* What is the diffraction limit of an optical system with circular aperture of diameter $D$ at wavelength $\lambda$?
  * $\alpha = \lambda/D$<!-- .fragment data-fragment-index="2" -->
* What is the unit of a in the equation above?
  * radian<!-- .fragment data-fragment-index="3" -->
* What is the diffraction limit of a 1-m telescope at 550nm?
  * $\alpha = \lambda/D = 550\;10^{-9}/1 = 5.5\; 10^{-7} \text{ rd} $<!-- .fragment data-fragment-index="4" -->
* How much is that in arcsecond?
  * rd to degrees conversion: multiply by $180/\pi$<!-- .fragment data-fragment-index="5" -->
  * 60 arcmin in one degree, 60 arcsec in one arcmin<!-- .fragment data-fragment-index="5" -->
  * 3600 arcsec in one degree<!-- .fragment data-fragment-index="5" -->
  * rd to arcsec: $180/\pi \times 3600 = 206265$: $206265$ arcsec in one rd.<!-- .fragment data-fragment-index="5" -->
  * $\alpha = 5.5 \; 10^{-7} \text{ rd} = 5.5 \; 10^{-7} × 206265 = 0.113 \text{ arcsec} = 0.113” $<!-- .fragment data-fragment-index="5" -->

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide -->

## Angular Resolution; Angle and Size

<span style="font-size: 120%;">

* To what size does this angle correspond at the distance of the moon (say 300,000km)?
  * $\alpha  = 5.5\;10^{-7} \text{ rd}$
  * $\alpha = h/d \rightarrow  h = \alpha \times d = 5.5\;10^{-7} \times 3\;10^{8} = 165 \text{ m}$
* Can we **resolve** objects smaller than this with such a telescope?
* Can we **detect** objects smaller than this with such a telescope?
* Any chance that we could make an image of the LEM (Apollo 11) from the surface of the earth?
</span>

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

<!-- slide -->

## Sampling

<span style="font-size: 120%;">

* According to the sampling theorem (Nyquist): For the previous telescope, what is the maximum sampling size allowable to properly sample images (diffraction $0.113”$)?
  * Sampling size (pixel) has to be $\le 0.113/2 = 0.0565"$

</span>

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>


<!-- slide -->

## Fourier trivia and reminders

* How many Fourier coefficients and modes do you need to fully describe:
  * A sine wave?
    * One mode, one complex coefficient (or two complex coefficients)
  * A square wave?
    * An infinity (because of the discontinuity)
* Complex numbers can be described in a:
  * real and imaginary $(x,y)$
  * amplitude and phase $(A,\varphi)$
* What’s the relationship between $(x,y)$ and $(A,\varphi)$?
  * $x = A cos(\varphi)$
  * $y = A sin(\varphi)$
  * $A = \sqrt{x^2 + y^2}$
  * $\varphi = \arctan(y,x)$

<div class='footer'>&copy; RIGAUT 2021, PHYS3057 FOURIER OPTICS</div>

