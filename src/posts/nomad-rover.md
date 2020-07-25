---
layout: layouts/post.njk
title: Nomad Rover
date: 2020-01-02T07:43:53.017Z
tags:
  - projects
  - hackathon
  - python
  - nodejs
  - raspberry-pi
---
This was a hackathon project for Mission Hacks 2018.
The theme was to create something that can be used by a hypothetical group of colonizers to
establish a settlement on "New Earth".

[Our team](https://www.facebook.com/CanadaRandstad/photos/basw.Abp4IYTQgbTVj4z-ZS730yyL22qmTNd6Ss709NIUUDmibtzaRZ1uk4-rDTvvvpJEpZLYBvIXnf08nw0r_61EbAjiNyFAf_2luc0jfdH3mlYwbJ_oKFLi5HgrDaBNAj6q_TCLfOoFyGOQ4tVItGWGRvJL.1866101276734794/1866101276734794/?type=1&theater) decided to tackle the issue of exploring the new landscape.
We envisioned a fleet of autonomous drones and rovers that would traverse the new planet and identify known elements
while also taking various measurements and creating a map.
The team name "Nomad" came from the idea that we were going to wander about the *New Earth* like nomads.

For the weekend, we hoped to complete a prototype of one of the rovers in the autonomous fleet.
A teammate had brought along the base of a remote-controlled car.
We used that for the base of our rover.
We started by creating a React front-end to control the rover and to display the view from the camera.
We added a ML pipeline in TensorFlow to identify obstacles in the camera stream and labelled those objects in the UI.

![Nomad Rover](/images/nomad-rover.jpg)

Then we hit a hurdle: the ML processing was taking too long, longer than the rover could wait to take action.
The rover's vision stream was being sent to Google Cloud Platform for the ML processing and then back to our local webserver.
There wasn't much more we could do to speed up the process - processing on the rover's Raspberry Pi wouldn't be much faster.
Without timely ML results, we couldn't hope to navigate the rover to do obstacle avoidance.

In our demo presentation, we mentioned how we would have proceeded to complete the rover (and the
rest of the Nomad fleet perhaps) if we had been able to expedite the computations.
Nevertheless, it was a great experience.
Also, this was my first time doing a hardware hack for a hackathon (I'll stick to software next time).

Consolation prize was that [our project was featured on Randstad's Facebook page](https://www.facebook.com/CanadaRandstad/photos/a.326551157356488/1869574276387494/?type=1&theater).