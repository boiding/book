# Sphere of influence
At the moment the a boid sees all of their flock mates. Even when they are very far away. That isn't realistic.  We our going to remedy that in this section.

Instead of letting each boid influence every single flock mate, we are going to limit their sphere of influence, i.e. boid will only act on flock mates that are within a certain distance.

To achieve this we need to change our brain function. Instead of passing the entire flock to each brain call, we need to filter the flock to only contain boids in the sphere of influence. Let's first make a function that can calculate the distance between two boids

```
begin distance(boid, mate)
    dx = mate.x - boid.x
    dy = mate.y - boid.y
    sqrt(dx*dx + dy*dy)
end
```

This functions determines the [_euclidean distance_][distance] between two boids.

With this function we can determine the sphere of influence. Our main process is controlled by a function that works like this

```
begin process(flock)
    result = {}
    for name in flock begin
        b = behavior(flock[name], flock)
        result[name] = b
    end
end
```

We will need to change that to accomodate the sphere of influence. For this we will create a function that will return the sphere of influence.

```
begin sphere(boid, flock)
    sphere = []
    for name in flock begin
        mate = flock[name]
        if distance(boid, mate) < radius then begin
            sphere[name] = mate
        end
    end
    sphere
end
```

Note that this function is dependent on a `radius` parameter. A radius of approximatly `1.414` is the entire world. So pick something that strikes your fancy.

With this `sphere` function we can change the process function to

```
begin process(flock)
    result = {}
    for name in flock begin
        boid = flock[name]
        sphere = sphere(boid, flock)
        b = behavior(boid, sphere)
        result[name] = b
    end
end

```

## Experimentation
As mentioned before a `radius` of `1.414` or more precisely \\(\sqrt 2\\), will include every flock mate in the sphere of influence. Try out different values and watch the result. Try to increase the number of boids, to see a clearer difference.

[distance]: https://en.wikipedia.org/wiki/Euclidean_distance