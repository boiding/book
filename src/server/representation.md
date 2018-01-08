# Representation
In this section we describe the [JSON](https://www.json.org/) representation of
the data that is sent to your web server, as well as the representation that is
expected back.

## World
The world data send to you via the `/world` URL has the following format.

```JSON
{
  "width": 640,
  "height": 480
}
```

## Input
With the post to `/brain` you will get send JSON data representing your flock.
The JSON is an object with boid names as properties. Each property describes the
corresponding boid.

```JSON
{
  "boid-a": {
    "x": 0.0,
    "y": 0.0,
    "heading": 1.0,
    "speed": 0.3
  },
  "boid-b": {
    "x": 1.0,
    "y": 2.0,
    "heading": 0.8,
    "speed": 0.5
  }
}
```

## Output
Once you have calculated how your boids will behave, you can send your response
back. It needs to contain the intended heading and speed of each and every boid
in your flock.

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

