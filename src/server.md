# Web Server
In this chapter we will describe the web server that you will be creating. If
you are using a starter kit, most of what is described here is already taken
care of.

## Responsibilities
Your web server has a couple of responsibilities. Besides forming the brain of
your boids, it also needs to convince the workshop server it is operating within
well established parameters.

A lot of things can go wrong. And we need to check for those. One of the things
that can go wrong is that your web server has stopped. Your web server must
respond to a heartbeat request so we know you server is still participating.

### `/heartbeat`
The workshop server periodically will send a 
[`HEAD` request](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/HEAD) 
to your web server. It should respond with a
[`204`](https://httpstatuses.com/204) indicating a successful request without
content.
This will tell the workshop server your web server is still running.

### `/brain`
The workshop server needs to know how your boids are going to react to their
environment. It will send a 
[`POST` request](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST)
with your current flock as [JSON](https://www.json.org/) data. Your web server
should figure out what each boid in your flock want to do and send their
decisions back as JSON.

The workshop server will take your response and integrate that in the simulation.
