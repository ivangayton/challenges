# Differential correction for mobile device GPS units

## Goal

A fully Free/Open Source library implementing Differential Global Positioning Satellite (DGPS) correction to enable applications to improve the precision and accuracy of position measurements.

## Background

It's theoretically possible to implement differential correction for GPS points on a mobile device (vastly improves accuracy after post processing, though not in real-time unless you have a data connection or a radio receiver for a correction beacon).

Differential correction essentially takes the errors recorded by a stationary GPS receiver (base station) and applies the equal and opposite correction to the positions registered by a mobile GPS device (rover). As long as the base station is sufficiently near the rover (within, say, 100km), the errors are very likely to be similar, so the corrected rover positions are considerably more accurate.

**TODO**: add full explanation of differential correction theory, including:
- The effect of distance between rover and base
- Need for recording of exact time of measurements, which satellites used for measurement and the exact pseudocode position of each sat reading
- File format (i.e. RINEX) for actual correction (whether real-time or post)
- Difference between absolute correction and relative correction (depending if the base station is in a precisely known, surveyed position) - relative correction still useful (and base station position fix improves with time as errors average out)
- Types of errrors that can't be corrected i.e. multipath

The GPS-enabled applications on mobile phones simply calculate their position based on the signals they receive from the satellites. They don't even record the metadata necessary to perform corrections.

As of 2016, Android allows direct access to the GNSS (Global Navigation Satellite System) data via [a class representing both raw and computed satellite information](https://developer.android.com/reference/android/location/GnssMeasurement.html). This is only supported on [a limited selection of relatively new Android phones](https://developer.android.com/guide/topics/sensors/gnss.html), but is likely to be supported on many more as time goes on. In any case, the hardware already is probably easier to come by in resource-poor settings than are survey-grade GPS receivers.

Some (proprietary) applications on mobile devices allow the app UI to connect to an external, high-precision GPS receiver. This is useful and should be implemented as an open-source library as well, ideally using standard GPS communication protocols (i.e. NMEA) so that users can swap in any GPS unit they like based on precision needs. 

## Resources and skills needed:
- Understanding of spheroid geometry
- GPS geometry/math
- Serial communication (NMEA)
- Experience implementing Android libraries
- Differential correction theory and practical mechanics (RINEX format etc)
- partridge in pear tree.
