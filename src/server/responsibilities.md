# Responsibilities
Your brain server has a couple of responsibilities. Besides forming the brain of
your boids, it also needs to convince the workshop server it is operating within
well established parameters.

A lot of things can go wrong. And we need to check for those. One of the things
that can go wrong is that your web server has stopped. Your web server must
respond to a heartbeat request so we know you server is still participating.

## `/heartbeat`
The workshop server periodically will send a 
[`HEAD` request](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/HEAD) 
to your brain server. It should respond with a
[`204`](https://httpstatuses.com/204) indicating a successful request without
content.
This will tell the workshop server your web server is still running.

## `/brain`
The workshop server needs to know how your boids are going to react to their
environment and peers. It will send a 
[`POST` request](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST)
with your current flock as [JSON](https://www.json.org/) data. Your brain server
should figure out the intent of each boid in your flock and send their intentions
back as JSON.

The workshop server will take your response and integrate that in the simulation.
