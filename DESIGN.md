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

There's a data probability (default 0.02) and a 
noise probability (default 0.001). 

Data probability is used when the hidden text buffer
maps to a text pixel.
Noise for the rest.

When the probability hits then it uses the primary color.
Else background.

Additionally to the hidden buffer with the text data
there is 9 bouncy balls that bounce against viewport
edges and use the data probability to render.
Diameter is 0.5*font height.

Font height is by default 64.

The viewport:

In portrait it's centered at top with 90% screen width and 60% screen height, at top it's padded by 5% screen width.
In landscape it's 60% screen width, 90% screen height, centered vertically and horizontally padded to the right by 5% height.


Text rendering:

Text data is set to a variable for now, it should contain a fragment of asimov works or similar as example.
Text is rendered by lines and line-wrapped. 
We render starting from the first line until the screen is filled.
Text is first wrapped to current widht and then prepared in lines to render. 
In the future the starting line will change for pagination so keep this in mind in the logic.

Page background should be full black. 

