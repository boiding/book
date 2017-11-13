# Boid
A _boid_ is a virtual creatures, much like a bird or a fish. You should get
attached to it, because we are going to spend a lot of time with them. We are
going to teach it how to move gracefully among their siblings.

You might not know it, but you have probably seen our friend before. If you are
familiar with movies like _The Lion King_ or _Batman returns_, you have seen
boids before. In The Lion King the stampede of wildebeests was created with a
boid algorithm. The bats and also penguins were similar modeled in Batman
returns.

Although the original boids moved in a three dimensional world, to keep things
simple we are going to restrict the movement of our boids to two dimensions.

## Characteristics
In this section we will provide an high level overview of the characteristics of
our boid. These pertain to the simulation we are going to before, but feel free
to attribute other characteristics.

### Primary
The primary characteristics are the characteristics that one can measure. You
can find them below.

#### Position
Maybe the most striking characteristic is the boids _position_. It keeps track
of where the boid is. We describe it by two projects, i.e. the _x_ coordinate
and the _y_ coordinate.

The world that the boids occupy wraps around on it self. This means that it
doesn't have edges. If a boid moves off the right side of the world it enters on
the left side of the world and vice versa. Similar for the top and bottom of the
world.

#### Heading
An other characteristic of a boid is its _heading_, i.e. The angle it is
pointing in. These angles are measured in
[radians](https://en.wikipedia.org/wiki/Radian) and have a range of 
\\(-\pi\\) to \\(+\pi\\). When the boid is pointing to the right she has a
heading of 0.

#### Speed
The _speed_ measures how fast the boid is going. Together with the heading this
makes up the velocity.
