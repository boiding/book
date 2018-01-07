# Representation
In this section we describe the [JSON](https://www.json.org/) representation of
the data that is sent to your web server, as well as the representation that is
expected back.

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
