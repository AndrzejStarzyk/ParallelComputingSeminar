Parallel implementation of algorithm calculating humidity inside 2-dimensional field.

The field is a square slice of a very long rectangular cuboid. The humidity of one of the sides is given 
(for example humidity = 68.4%) and the opposite id dry (humidity = 0). Humidity changes linearly along two remaining sides.
Function describing humidity "h" in point (x,y) of the field can be expressed as a differential equation 
$\frac{\delta^2h}{\delta x^2} + \frac{\delta^2h}{\delta y^2} = 0$.

Following PCAM methodology I constructed parallel algorithm:

1. Partitioning: Humidity is computed in points of a grid overlaid on top of the field. 
Grid size is "n" (for example n=19) which means there are "n" vertices on the square field side
2. Communication: There is a scheduler and some worker processes. Workers announce readiness, receive computations from scheduler
and return results.
3. Agglomeration: Here each worker process computes humidity at gird vertex one at a time
4. Mapping: Computation at each vertex is given to single worker process by the scheduler.

Implementation details:
Humidity in a given vertex is computed as a mean value of neighbouring vertices. 
Matrix M holds coefficients for calculating means. Matrix W holds humidity values.
Worker multiplies row 

diff_eq.py inside pythonProject contains code and visualisation.m is a matlab code for creating visualization of results.