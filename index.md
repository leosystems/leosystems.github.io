---
layout: default
---

## Some basic terms

Extraterrestrial studies need some foreword, therefore in order not to find ourselves lost with concepts that seem to be *out of this world*, let's give some background knowledge.

### Space debris

Space debris are all man made objects including fragments and elements thereof, in Earth orbit or re-entering the atmosphere, that are non functional.

### Spacecraft, launch vehicles and orbital stages

#### Spacecraft
An orbiting object designed to perform a specific function or mission (e.g. communications, navigation or Earth observation).  A spacecraft that can no longer fulfil its intended mission is considered non-functional.  (Spacecraft in reserve or standby modes awaiting possible reactivation are considered functional.)  
#### Launch vehicle
Any vehicle constructed for ascent to outer space, and for placing one or more objects in outer space, and any sub-orbital rocket.
#### Launch vehicle orbital stages
Any stage of a launch vehicle left in Earth orbit.    
### Orbits and protected regions

#### Equatorial radius of the Earth

The equatorial radius of the Earth is taken as \\(6,378\\) km and this radius is used as the reference for the Earth's surface from which the orbit regions are defined.

#### Protected regions

Any activity that takes place in outer space should be performed while recognizing the unique nature of the following regions:

1. Low Earth Orbit (LEO) region: spherical region that extends from the Earth's surface up to an altitude of \\(2,000\\) km.

2. Geosynchronous region: a segment of the spherical shell defined by the following:
  - Lower altitude \\(=\\) geostationary altitude \\(-200\\) km.
  - Upper altitude \\(=\\) geostationary altitude \\(+200\\) km.
  - \\(-15 \mbox{ degrees }  \leq \mbox{ latitude } \leq +15 \mbox{ degrees }\\)

  <img class="centered" src="/assets/img/regions.jpg" />


#### Geostationary Earth Orbit (GEO)
Earth orbit having zero inclination and zero eccentricity, whose orbital period is equal to the Earth's sidereal period. The altitude of this unique circular orbit is close to \\(35,786\\) km.

#### Geostationary Transfer Orbit (GTO)
An Earth orbit which is or can be used to transfer spacecraft or orbital stages from lower orbits to the geosynchronous region.  Such orbits typically have perigees within LEO region and apogees near or above GEO.

## LEO orbital parameters

### Low Earth circular orbits

A circular orbit is mathematically the simplest orbit, although it can be difficult to achieve exactly in practice. Only one parameter is needed to specify the size of the orbit, and that is the radius \\(r\\), the constant distance from the centre of the Earth to the satellite.

If the radius of the Earth is denoted by \\(R\_e\\), then the altitude or height of the orbit (and the satellite) above the Earth's surface is \\(h = r - R\_e\\).

Unfortunately for our simplicity, the radius of the Earth is not a constant, varying from \\(6357\\) km at the poles to \\(6378\\) km at the equator. If our satellite has a low inclination (ie it spends most of its time near the equator), then we might use the equatorial radius. Otherwise we could use the mean radius of \\(6371\\) km. Of course, for high accuracy applications we need to consider the varying shape of the Earth at each point beneath the satellite's orbit.

If we know the period of the satellite (the time it takes to make one complete orbit around the Earth) we can compute its height, and vice versa. We can also compute its orbital velocity (\\(v\\)) and a quantity known as its mean motion, the number of orbits it completes in one day.

Isaac Newton provided the formulae we need for these calculations. Starting with the famous second law of motion \\(F = m\cdot a\\) where \\(F\\) is the force on the satellite, \\(m\\) is its mass and \\(a\\) is its acceleration.

Newton's law of gravitation \\(F = G \frac{M\cdot m}{r^2}\\) is the required force that the Earth exerts on the satellite.

A body moving in a circle is actually being accelerated toward the centre of the circle (by the Earth's gravitational force). The acceleration is referred to as the centripetal (directed towared the centre) acceleration, and the force that produces the acceleration is known as the centripetal force.

The magnitude of the acceleration is given by \\(a = \frac{v^2}{r}\\).

If we substitute for the force on the left hand side of Newton's second law and the acceleration on the right hand side we end up with:

$$G \frac{M\cdot m}{r^2} = m\cdot\frac{v^2}{r}$$,

where \\(G\\) is the Universal Constant of Gravitation and \\(M\\) is the mass of the Earth.

We now note that the mass of the satellite (\\(m\\)) disappears from the equation, and we are left with an expression relating the orbital velocity to the orbital radius:

$$v = \sqrt{\frac{G\cdot M}{r}}$$

The orbital period (T) may be computed by dividing the distance travelled in one orbit by the velocity. The former quantity is the circumference of the circle.

$$T = \frac{2\pi r}{v}$$

which after substitution for \\(v\\) becomes:

$$T = 2\pi \sqrt{\frac{r^3}{G\cdot M}}$$

Lastly, the mean motion (\\(n\\)) of the satellite, which is defined as the number of orbits traversed in one complete day which is 86400 seconds long, given by:

$$n =\frac{86400}{T}$$

Note that with the exception of \\(n\\), all quantities are strict SI units. Distances are in metres, velocities in metres/sec and times in seconds. The exception, the mean motion, is in revolutions per day.

In this system of units, the values for the gravitational constant and the mass of the Earth is given as:

$$G = 6.67259\cdot 10^{-11} \mbox{m}^3\mbox{kg}^{-1}\mbox{s}^{-2},$$

with \\(M = 5.9736\cdot 10^{24}\\) kg. It is interesting to note that the uncertainty in the measured value for \\(G\\) is larger than the uncertainty in the measurement of the product of \\(G\\) times \\(M\\), which is given as:
<p id="kepler">
$$G\cdot M = 3.9860 \times \cdot 10^{14} \mbox{m}^3\mbox{s}^{-2}$$
</p>
A table of values computed from the above formulae is shown below. Note that the units have been converted into the more typically used quantities before display.

               LEO CIRCULAR ORBIT PARAMETERS

           Height   Velocity   Period   Mean Motion
            (km)     (km/s)    (mins)    (revs/day)

             200      7.79       88.4      16.30
             300      7.73       90.4      15.93
             400      7.67       92.4      15.58
             500      7.62       94.5      15.24
             600      7.56       96.5      14.92
             700      7.51       98.6      14.60
             800      7.46      100.7      14.30
             900      7.40      102.8      14.00
            1000      7.35      105.0      13.72
            1100      7.30      107.1      13.44
            1200      7.26      109.3      13.18
            1300      7.21      111.4      12.92
            1400      7.16      113.6      12.67
            1500      7.12      115.8      12.43
