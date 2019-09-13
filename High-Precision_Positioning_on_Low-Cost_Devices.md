# High-precision positioning on low-cost devices

## Goal

A fully Free Software/Open Source toolchain allowing high-precision positioning on low-cost devices.

Specifically: enable sub-decimeter positioning with a total hardware cost under USD$300 and widely available in low-income areas.

## Problem Statement

Poor people have very limited access to precise location data. Survey-grade positioning requires expensive equipment (at least $3000 for the most basic commercially available surveying GPS setup).

Small-scale, poor, and informal landholders have very limited ability to define, assert, and defend their property. Disputes and corruption are practically ubiquitous. While a technical solution alone cannot possibly hope to solve the societal issues around land ownership and title, enabling low-income people to access high-quality surveys is probably a _necessary, if not sufficient_ condition for global improvement of poor landholders' rights.

We suspect that improving land surveying for property rights is likely to be one of the most impactful outcomes of access to low-cost high-accuracy positioning. However, history has shown that when given technological tools that create fundamental new capabilities, people often make unexpected use of them. A few possibilities include:

- Allow small-scall and poor landholders to define and assert the boundaries of their plots
- Improve vehicle navigation by making it less ambiguous which road one is traveling on
- Enable large-scale precise surveying of natural features such as rivers to improve environmental monitoring
- Enable large-scale precise surveying of human infrastructure such as drainage and buildings to improve disaster preparedness

Of course, there is also potential for negative impact. It's easy to imagine lo-cost high-precision positioning being used for, say, improved targeting of improvised weapons. However, the potential benefits appear, from an initial anlysis, to be very substantial and far from outweighed by the potential for harm. 

## Proposed Solution

Current low-cost devices (smartphones in the range of $100 to $1,000) have satellite positioning capability with a rough error margin of five meters (certain devices can do a bit better under ideal conditions; the best-case scenario is about two meters error).

Survey-grade or geodetic satellite positioning receivers in the range of $3,000 to $50,000 can achieve positional accuracy in the range of 3-50mm. This is done by:
- Using antennas capable of receiving several frequencies of signal from positioning satellites.
- Using such antennas to estimate [carrier wave phase](https://en.wikipedia.org/wiki/Real-time_kinematic) (determining not only the position of the satellite signal but the position within the wavelength (phase) of the carrier signal)
- Using differential correction whereby measured positional errors from a satellite receive at a fixed "base station" are used to correct the positional measurements of a "rover"
- Using algorithms that account for specific types of positional error or bias in multiple positional fixes to produce statistically robust "converged" positions

All of these methods are now possible to one extent or another on low-cost devices. Inexpensive external receivers (in the $250 range) can be attached to a low-end smartphone enabling accuracy in the range of a few centimeters, and even the internal GPS on many smartphones can be used with correction techniques to produce positional accuracy in the decimeter range.

What's missing is software infrastructure.

There is no simple, easily implemented, widely available, Free and Open Source toolset available for making use of capability of currently available hardware to enable high-precision positioning.

We propose to provide such a toolset by collating existing utilities, building missing parts, and creating and documenting an overall workflow. We intend to work primarily with existing libraries such as [RTKLIB](http://www.rtklib.com/) and user-facing tools such as [OpenDataKit](https://opendatakit.org).

## Some Technical Details

### GNSS Receivers

The [ublox ZED-F9P receiver](https://www.u-blox.com/en/product/zed-f9p-module), a $140 chip released in 2019, toether with a $50 to $100 [antenna](https://www.ardusimple.com/store/) can be [connected to a low-end Android phone](https://github.com/hcwinsemius/RTK_GNSS) and achieve sub-decimeter precision using correction data (real-tie or post-processed) from a base station (which can also be a ublox ZED-F9P, antenna, and Raspberry Pi for a total cost under $300).

Additionally, as of 2016 Android allows direct access to the GNSS (Global Navigation Satellite System) data via [a class representing both raw and computed satellite information](https://developer.android.com/reference/android/location/GnssMeasurement.html). This is supported on [most phones manufactured in 2016 or later and shipped with Android 7.0 or higher](https://developer.android.com/guide/topics/sensors/gnss.html). The list of supported phones is growing quickly, and several are widely available in low-income countries. This means that a simple smartphone in the $100 range, without any external attachment whatsoever, can be 

The GPS-enabled applications on mobile phones simply calculate their position based on the signals they receive from the satellites. They don't even record the metadata necessary to perform corrections.


## Resources needed:


