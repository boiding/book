# Representation
In this section we describe the [JSON](https://www.json.org/) representation of
the data that is sent to your brain server, as well as the representation that it
is expected back.

## Input
With the post to `/brain` you will get send JSON data representing your flock.
The JSON is an object with a field `boids`. Its value is an object that maps 
boid names to their properties. Each property describes the corresponding boid.

Below you can find an example.

```JSON
{
  "boids": {
    "boid-a": {
      "x": 0.1,
      "y": 0.2,
      "heading": 1.0,
      "speed": 0.030
    },
    "boid-b": {
      "x": 0.3,
      "y": 0.5,
      "heading": 0.8,
      "speed": 0.005
    }
  }
}
```

## Output
Once you have calculated the intentions of your boids, you can send your response
back. The response should map a boid's name to its intended heading and speed. You do
not have to include each and every boid in your flock, but this has the best result.

```JSON
{
  "boid-a": {
    "heading": 1.2,
    "speed": 0.5
  },
  "boid-b": {
    "heading": 1.0,
    "speed": 0.5
  }
}
```

