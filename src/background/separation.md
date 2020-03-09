# Separation
![Separation; steering clear of budding boids](../image/separation.gif)

One of the classic motivations for our boid is _separation_. Steer clear from
your buddy boids to minimize the chances of collisions.

## Calculation
Let the position of our boids be given by a sequence of coordinates 
\\(p_{1} = (x_{1}, y_{1}), p_{2} = (x_{2}, y_{2}), \ldots, p_{n} = (x_{n}, y_{n})\\).

We need to calculate the direction we see a boid in as seen from an different
boid with position \\(p = (x, y)\\). The direction can be calculated by taking
the difference of the position of the boid you are interested in and your own
boid. I.e.

\\[
d_{i} = p_{i} - p = (x_{i} - x, y_{i} - y)
\\]

From the sequence of directions we can determine a sequence of headings by taking
the
[_arctangent_](https://en.wikipedia.org/wiki/Inverse_trigonometric_functions).

\\[
h_{i} = \operatorname{arctan}\left(\frac{y_{i} - y}{x_{i} - x}\right)
\\]

We would like to choose a heading that avoids all of the headings \\(h_{i}\\),
if we want to avoid a collision.

One way of doing this is averaging the headings and going in the opposite
direction. The average can be calculated by

\\[
h := \frac{1}{n} \sum_{i=1}^{n} h_{i}
\\]

our target direction could be \\(h + \pi\\), normalized to lie within 
\\(\left(-\pi, \pi\right)\\).
