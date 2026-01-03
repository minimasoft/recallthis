This is a screenshot-proof text reader for the web. 

It avoids screenshots by using a noisy display that
takes advantage of human persistence of vision to 
never display the whole text/data in the same frame. 

The implementation uses a webgl shader and a hidden
buffer. 

The hidden buffer renders the text as base-pattern.

The shader uses the hidden buffer as cue to render.

The shader has a primary color (very light green)
and background (black with some minor green noise).

There's a data probability and a noise probability. 

Data probability is used when the hidden text buffer 
maps to a text pixel.

Noise for the rest.

When the probability hits then it uses the primary color,
else background.

Additionally to the hidden buffer with the text data
there is 9 bouncy balls that bounce against viewport
edges and use the data probability to render.

Text rendering:

Text is rendered by lines and line-wrapped. 
We render starting from the first line until the screen is filled.
Text is first wrapped to current widht and then prepared in lines to render. 

Page background should be full black. 

