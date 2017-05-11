# Differential correction for mobile device GPS units

It's theoretically possible to implement differential correction for GPS points on a mobile device (vastly improves accuracy after post processing, though not in real-time unless you have a data connection or a radio receiver for a correction beacon).

Differential correction essentially takes the errors recorded by a stationary GPS receiver (base station) and applies the equal and opposite correction to the positions registered by a mobile GPS device (rover). As long as the base station is sufficiently near the rover (within, say, 100km), the errors are very likely to be similar, so the corrected rover positions are considerably more accurate.

TODO: add full explanation of differential correction theory.
- Distance between rover and base
- recording of exact time of measurements, which satellites used for measurement and the exact pseudocode position of each sat reading
- file format (i.e. RINEX) for actual correction
- Difference between absolute correction and relative correction (depending if the base station is in a precisely known, surveyed position) - relative correction still useful (and base station position fix improves with time as errors average out)
- Types of errrors that can't be corrected i.e. multipath

The GPS-enabled applications on mobile phones simply calculate their position based on the signals they receive from the satellites. They don't even record the metadata necessary to perform corrections.

Some (proprietary) applications on mobile devices allow the app UI to connect to an external, high-precision GPS receiver. This is useful and should be implemented in our app, ideally using standard GPS communication protocols (i.e. NMEA) so that users can swap in any GPS unit they like based on precision needs. 

### Resources and skills needed:
- Understanding of spheroid geometry
- GPS geometry/math
- serial communication (NMEA)
- Native libraries to get at the guts of Android devices (to access the low-level GPS data)
- Differential correction theory and practical mechanics (RINEX format etc)
- partridge in pear tree.
