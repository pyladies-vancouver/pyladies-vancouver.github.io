+++
title = "Art with Python and Facial Recognition"
date = 2016-04-09T10:00:00-07:00
description = "This painting from Doctor Who has the nifty property of being able to adjust the perspective according to the position of viewers:  Cool, eh? Let's try to do…"
venue = "UrtheCast"
address = "#33 1055 Canada Place, Vancouver"
time = "10:00 AM"
meetupUrl = "https://www.meetup.com/pyladies-vancouver/events/228329641/"
+++

This painting from Doctor Who has the nifty property of being able to adjust the perspective according to the position of viewers: https://www.youtube.com/watch?v=FUIbq2HPyQA

Cool, eh? Let's try to do this with Python! Starter code is on github: https://github.com/small-yellow-duck/timelordart

With the magic of face detection in openCV, we can use a camera to track the position of viewers.

https://realpython.com/blog/python/face-detection-in-python-using-a-webcam/

There are several python libraries for rendering 3d objects. Let's try a few of them out!

https://pypi.python.org/pypi/Vapory/0.1.0

http://www.pythonocc.org/quick-examples/hello-dumb-box/

Some problems you might wish to consider:

- how long does it take to render an image?

- what should happen if the face recognition algorithm doesn't find a face in the frame?

- what should happen if the face recognition algorithm finds more than one face in the frame?

*This event was originally hosted on Meetup.*

{{< button url="https://www.meetup.com/pyladies-vancouver/events/228329641/" label="View this event on Meetup" variant="outline" icon="fa-brands fa-meetup" >}}
