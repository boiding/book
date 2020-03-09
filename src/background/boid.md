# Boid
A _boid_ is a virtual creatures, much like a bird or a fish. You should get
attached to it, because we are going to spend a lot of time with them. We are
going to teach our boids how to move gracefully among their siblings.

You might not know it, but you have probably seen our friends before. If you are
familiar with movies like _The Lion King_ or _Batman Returns_, you have seen
boids before. In The Lion King the stampede of wildebeests was created with a
boids algorithm. The bats and also the penguins were similarly modeled in Batman
Returns.

Although the original boids moved in a three dimensional world, to keep things
simple we are going to restrict the movement of our boids to two dimensions.

## Characteristics
In this section we will provide an high level overview of the characteristics of
our boid. These pertain to the simulation we are going to perform, but feel free
to attribute other characteristics.

### Primary
The primary characteristics are the characteristics that one can measure. You
can find them below.

#### Position
Maybe the most striking characteristic is the boids _position_. It keeps track
of where the boid is. We describe it by two projections, i.e. the _x_ coordinate
and the _y_ coordinate.

The world that the boids occupy wraps around on it self. This means that it
doesn't have edges. If a boid moves off the right side of the world it enters on
the left side of the world and vice versa. Similar for the top and bottom of the
world.

We have made sure that the coordinates are normalized. The values it can attain
will all lie between 0 and 1. E.g. a boid with an _x_ value of 0 is found at the
left side of the world, whereas a boid with an _x_ value of 1 will find itself at 
the right side of the world.

Similarly, an _y_ value of 0 corresponds with the top edge and an _y_ value of 1
corresponds with the bottom edge.

#### Heading
An other primary characteristic of a boid is its _heading_, i.e. The angle it is
pointing in. These angles are measured in
[radians](https://en.wikipedia.org/wiki/Radian) and have a range of 
\\(-\pi\\) to \\(+\pi\\). When the boid is pointing to the right she has a
heading of 0.

#### Speed
The _speed_ measures how fast the boid is going. Together with the heading this
makes up the velocity.

### Secondary
The secondary characteristics are used in the simulation, but are less apparent
than the primary characteristic.

#### Intended Heading
This is the heading your boid would like to have. It could differ from the
primary heading and is used to steer the boid in order to avoid collisions or
signal preferred direction.

#### Intended Speed
Like the intended heading, this is the speed the boid would want to move in.

#### Agility
The _agility_ determines how quickly the boid can go from the current heading 
to the intended heading. Changing course takes times and that is reflected in
this value.

It ranges from 0 to 1 where 0 represents a total *inability* to change heading
and 1 represents the ability to instantly change course.

#### Acceleration
What agility is for heading, acceleration is for speed. It determines how quickly
a boid can change it's current speeds.

Again, an acceleration of 0 corresponds with the inability to change speeds, whereas
an acceleration of 1 corresponds with instantly changing speed.

#### Influence Sphere
This is the area in which other boids are sensed and as a result interacted with.
It is a circle centered at the position of the boid and measured by a radius.
