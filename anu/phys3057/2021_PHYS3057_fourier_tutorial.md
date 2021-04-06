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
</style>



<!-- _class: invert -->
# Fourier Optics Tutorial


<div class="authors">

**Prof François Rigaut**
Research School of Astronomy & Astrophysics
The Australian National University
</div>

---

## Image metric: Full-Width at Half-Maximum


- The width of the image at half its maximum. Often written FWHM
- For instance, a cross section of a gaussian image

<div style="position; relative; float: left;"><img src="assets/images/fop_30.png" width="580px"></div><img src="assets/images/fop_31.png" width="200px">


- The FWHM is often naturally expressed as an angle (e.g. arcsec) or a distance (e.g. mm), as it often characterise a resolution

---
<style scoped>ul { font-size: 1.07rem;}</style>

## Angular Resolution, Angle and Size


<img src="assets/images/fop_97.png" width="50%">

- What is the angular extent $\alpha$ of a segment of size $h$ at distance $d$?
  - $\tan(\alpha/2) = (h/2)/d = h/(2d) \implies \alpha = 2 \arctan (h/(2d))$
  - For small angles $\alpha = 2 \arctan (h/(2d)) = h/d$


---

## Angular Resolution, Angle and Size


- What is the diffraction limit of an optical system with circular aperture of diameter $D$ at wavelength $\lambda$?
  - $\alpha = \lambda/D$
- What is the unit of a in the equation above?
  - radian
- What is the diffraction limit of a 1-m telescope at 550nm?
  - $\alpha = \lambda/D = 550\;10^{-9}/1 = 5.5\; 10^{-7} \text{ rd}$
- How much is that in arcsecond?
  - rd to degrees conversion: multiply by $180/\pi$<
  - 60 arcmin in one degree, 60 arcsec in one arcmin
  - 3600 arcsec in one degree
  - rd to arcsec: $180/\pi \times 3600 = 206265$: $206265$ arcsec in one rd.
  - $\alpha = 5.5 \; 10^{-7} \text{ rd} = 5.5 \; 10^{-7} × 206265 = 0.113 \text{ arcsec} = 0.113"$


---
<style scoped>ul { font-size: 1.12rem;}</style>

## Angular Resolution, Angle and Size



- To what size does this angle correspond at the distance of the moon (say 300,000km)?
  - $\alpha  = 5.5\;10^{-7} \text{ rd}$
  - $\alpha = h/d \rightarrow  h = \alpha \times d = 5.5\;10^{-7} \times 3\;10^{8} = 165 \text{ m}$
- Can we **resolve** objects smaller than this with such a telescope?
- Can we **detect** objects smaller than this with such a telescope?
- Any chance that we could make an image of the LEM (Apollo 11) from the surface of the earth?


---
<style scoped>ul { font-size: 1.2rem;}</style>

## Sampling



- According to the sampling theorem (Nyquist): For the previous telescope, what is the maximum sampling size allowable to properly sample images (diffraction $0.113"$)?
  - Sampling size (pixel) has to be $\le 0.113/2 = 0.0565"$




---
<style scoped>ul { font-size: 0.9rem;}</style>

## Fourier trivia and reminders


- How many Fourier coefficients and modes do you need to fully describe:
  - A sine wave?
    - One mode, one complex coefficient (or two complex coefficients)
  - A square wave?
    - An infinity (because of the discontinuity)
- Complex numbers can be described in a:
  - real and imaginary $(x,y)$
  - amplitude and phase $(A,\varphi)$
- What’s the relationship between $(x,y)$ and $(A,\varphi)$?
  - $x = A cos(\varphi)$
  - $y = A sin(\varphi)$
  - $A = \sqrt{x^2 + y^2}$
  - $\varphi = \arctan(y,x)$


---

## Matlab and Python tools


- Python:
  - LightPipes: https://opticspy.github.io/lightpipes/index.html
  - Opticspy: https://pypi.org/project/opticspy/
  - Zernikes: https://pypi.org/project/zernike/

- MATLAB:
  - LighPipes: http://www.okotech.com/lightpipes
  - Zernike polynomials: https://www.mathworks.com/matlabcentral/fileexchange/7687-zernike-polynomials

However, nothing replaces coding the thing yourselves (you will learn much more than just using the pre-coded tools)



---

## Computing an Airy pattern with Matlab


```matlab
% Compute the OTF for a circular aperture:
% define a mesh grid in X and Y
[x2 y2] = meshgrid(-1000:1:1000);
% compute the aperture. Diameter has to be at most half of array 
% size. Hypot is a convenient way to compute the distance to (0,0)
aper = hypot(x2,y2)< 100.;
% the PSF is simply the modulus square of the FFT of the aperture.
% We also need to swap the quadrants (fftshift) to restore
% (0,0) in its rightful location, the center
psf = fftshift(abs(fft2(aper))).^2;
% display it
imagesc(sqrt(psf));
axis equal
```


---

## Computing an Airy pattern with Python


```python
import numpy as np
import matplotlib.pyplot as plt
import scipy.fftpack as sciF

"Parameters"
N = 1024                   #amount of pixels NxN
radii = 0.0625             #radii of the aperture: 2*64/1024 = 0.0625 
x = np.linspace(-1,1, N)   #x-coordinates
y = np.linspace(-1,1, N)   #y-coordinates

"Generating the aperture function"
def circaper_car(x,y, a = radii):
    Amp = np.zeros((N,N))
    for i in range(N):
        for j in range(N):
            if np.sqrt(x[i]**2 + y[j]**2) <= a:
                Amp[i,j] = 1
    return Amp

aper = circaper_car(x,y)
Psi_fft   = sciF.fft2(aper)
Psi_shift = sciF.fftshift(Psi_fft)
H = np.abs(Psi_shift)**2

"Plots"
plt.figure(1); plt.imshow(aper); plt.show()
plt.figure(2); plt.imshow(np.sqrt(H)); plt.show()
```


---

## Same, shorter/smarter version


```python
import numpy as np
import matplotlib.pyplot as plt
import scipy.fftpack as sciF

"Parameters"
N = 1024                   #amount of pixels NxN
radii = 0.0625             #radii of the aperture: 2*64/1024 = 0.0625 
x = np.linspace(-1,1, N)   #x-coordinates
y = np.linspace(-1,1, N)   #y-coordinates
X,Y = np.meshgrid(x,y)     #Coordinates for plotting
aper = ((X**2+Y**2) < radii**2)
Psi_fft   = sciF.fft2(aper)
Psi_shift = sciF.fftshift(Psi_fft)
H = np.abs(Psi_shift)**2

"Plots"
plt.figure(1); plt.imshow(aper); plt.show()
plt.figure(2); plt.imshow(np.sqrt(H)); plt.show()
```


---

## Airy pattern in Yorick 


Yorick is a compact high level data analysis/display language with a syntax similar to C (https://github.com/LLNL/yorick). I am not particularly advocating its use - just taking it as yet another example of high level, interpreted language.

```C
N = 1024;
rad = 0.0625;
aper = dist(N)<(rad*N);
psf = abs(roll(fft(aper,1)))^2.;
tv,sqrt(psf);
```


---

## Signal and Noise generation, Pseudo code


1. Signal: generate sinusoid e.g. in real space
2. Noise: generate in Fourier plane. E.g. white noise:
  - Generate amplitude = constant
  - Generate random phase over $[0,2\pi]$
  - Inverse Fourier transform $\rightarrow$ noise in real space

```C++
N = 512;
noise_a = array(1.,N); // Noise amplitude in Fourier space
noise_p = random(N)*2*pi; // Noise random phase in Fourier space
noise_fourier = noise_a*exp(1i*noise_p); // forming complex quantity
noise = float(fft(noise_fourier,-1)); // inverse FFT
fma; plh,noise; // plotting result
```

