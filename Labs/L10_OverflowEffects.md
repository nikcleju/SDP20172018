---
title: Effects of overflow and underflow in digital filtering
subtitle: Lab 10, SDP
documentclass: scrartcl
fontsize: 12pt
---

# Objective

Students should observe the effects of internal format overflow and underflow 
events on the output of a digital filter.

# Theoretical notions

# Exercises

1. Consider the following system:
	$$H(z) = \frac{1-\frac{1}{2}z^{-1}}{\left(1 - \frac{1}{4}z^{-1}\right)\left(1 + \frac{1}{4}z^{-1}\right)}$$

    a. Draw one of the series implementations of the system
	b. Assume a fixed-point implementation with $b$ bits for the fractionary part.
	Each product is quantized by rounding to this format.
	Find the variance of the rounding noise due to the 
	internal multiplications, at the output of the system.

2. In Matlab, use the `fdatool` tool to design a low-pass IIR filter
of order 4, Butterworth type, with cutoff frequency equal to 1.5kHz for
a sampling frequency of 44.1kHz. Convert the filter to direct form II
and export it to Simulink (check the option *Build model using basic elements*).

3. In the Simulink model, make two copies of the filter (Copy/Paste). 
At the input of both filters put a sample audio signal (e.g. *Kalimba.mp3* or *mtlb*).
For the second filter, the input signal shall be converted to fixed-point 
1S2Î9F data type. Compute and plot the difference between the two outputs.
Export the difference signal to Matlab's Workspace and compute its average value
and the dispersion.

4. Make a new copy of the second filter, and for this copy un-check 
in the properties of the *Sum* blocks the option *Saturate on integer overflow*.
What is its effect? Compute and plot the difference compared to the first filter.
Which of the filters 2 or 3 produces smaller errors?

5. Use the function `normescal()` to compute different scaling norms 
for the given filter. Scale the input signal with each one of these norms,
and rescale back the output. What is the effect of this procedure?

# Final questions

1. TBD
