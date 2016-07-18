---
title       : RF Pulse shapes and their Fourier Transforms
subtitle    : Coursera DDP assignment
author      : DDP_assignment
job         : Graduate Student
framework   : io2012  # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []           # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides

-------

## Fourier Transforms in Magnetic Resonance Imaging (MRI)

The application developed in this course aims to provide a better understanding of fourier transforms of radio frequency (RF) signals. The application displays the fourier transforms of commonly used RF signals in MRI

1. MRI uses RF pulses to generate the signal for imaging.
2. RF pulses are time domain digital signals.
3. Fourier Transforms help us in converting RF pulses to frequency space.
4. Frequency signals help us to excite specific regions for MR imaging.

In the following slides we will see the typically used RF pulse shapes and their fourier transforms to understand the slice excitation profiles used in MRI.

---.class #id  

## Fourier Transforms

1. A simple 2D signal can be decomposed into a set of basis functions comprising of sine and cosine functions. 
2. For a given function f(t), the fourier transform F($\omega$) is given by:

$$
F(\omega) = \int(f(t)*exp(-i2\pi\omega t) d\omega\
$$

An MRI signal comprises of both magnitude and phase information. Therefore the RF pulses used in MRI for exciting the proton spins also possess magnitude and phase which are manipulated to produce the desired excitation.

Exciting specific slices for looking at specific locations in the object being imaged is key to MR imaging. For instance, we can excite a band of frequencies in MRI by using a sinc function $$ sinc(x) = \frac{\sin(x)}{x} $$

As shown in the application, the fourier transform of a sinc function produces a rect function, which details the various frequencies that are selectively excited. 

---

## Example plot showing sinc function.


```r
x <- seq(-201,201,2)
plot(x, (sin(x)/x), type='l')
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-1-1.png)

---
## Using the app

While taking images, say of a head, in an MRI scanner, we generally acquire 2D slices of the brain and represent them as images. To obtain these rectangular slices, it is important to use rectangular frequency profiles. The app shows some typical frequency profiles for commonly used input RF waveforms. 

1. Select the desired input RF signal from the dropdown listbox. 
2. Adjust the zoom slider which controls the display of the fourier transform.

The application displays the selected input's real and imaginary waveforms as the first two graphs. The third graph displays the magnitude of the fourier transform for the input signal. 

By default, the app is set to receive a gaussian function as an input.
