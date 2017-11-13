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
The _agility_ determines how quickly the boid can go from the primary heading
and primary speed, i.e. the primary velocity, to the intended heading and
intended speed. Changing course takes times and that is reflected in this value.
It ranges from 0 to 1 where 0 represents a total *inability* to change velocity
and 1 represents the ability to instantly change course.

#### Influence Sphere
This is the area in which other boids are sensed an as a result interacted with.
It is a circle centered at the position of the boid and measured by a radius.
