# Cohesion
![Surrounding yourself with budding boids increases survival chances.](../image/cohesion.gif)

Predators attack on the outside of your cohort. It motivates boids to move to
the center of the flock. 

## Calculation
Let the position of our boids be given by a sequence of coordinates 
\\(p_{1} = (x_{1}, y_{1}), p_{2} = (x_{2}, y_{2}), \ldots, p_{n} = (x_{n}, y_{n})\\).

The [_center of mass_](https://en.wikipedia.org/wiki/Center_of_mass) is
calculated by averaging the positions. This assumes that the boids all weigh the
same. Since our boids are virtual, we can mold them as we see fit.

The averaging can be done component-wise so the x-coordinate of the center of
mass can be calculated with

\\[
x_{c} = \frac{1}{n}\sum_{i=1}^{n} x_{i}
\\]

Likewise the y-coordinate of the center of mass isize

\\[
y_{c} = \frac{1}{n}\sum_{i=1}^{n} y_{i}
\\]

Together this gives \\(p_{c} = (x_{c}, y_{c})\\) for the center of mass.

Now that we know the center of mass, we would like to figure out the heading a
boid needs to fly in to head towards the center of mass. If the position of the
boid is \\(p = (x, y)\\), the direction to fly in is found by subtracting the
center of mass from the boid's position.

\\[
d := p_{c} - p = (x_{c} - x, y_{c} - y)
\\]

We can calculate the heading from this by taking the 
[_arctangent_](https://en.wikipedia.org/wiki/Inverse_trigonometric_functions)
; \\(\operatorname{arctan}(\frac{y_{c} - y}{x_{c} - x})\\)
