
One thing I learned is if you're seeing weird contradictions in how different instances of similar objects are treated, 
you may have some non-standard race conditions.

A lot of us doing solitare encountered weird layering issues with the card components.
This was often due to the decorators being on the same layer as something else.
It was just kinda of a coin toss as to what Unity would put on top for you to see.

While investigating an issue like above I learned the value of digging into the inspector values of objects during runtime.
This was especially helpful to fully (well, mostly) understand how the sprites were being used.


I did have a good bit of trouble with the floating score and scoreboard class, but that was mostly because I didn't really
work on understanding them before I started making changes.

That caused me a lot of trouble getting the scoring to work how I wanted.

The book was slightly ambiguous about the doubling of the runs if there was a gold card.
I decided it would be simpler to let gold cards stack their double effect in the case
multiple are encountered in a run.

That was difficult.  I didn't end up implementing it the way I envisioned, 
but wrote a couple messy Unity calls to get info from the ScoreManager script directly.

It worked in the end.

I show a cards value doubled or not as it floats from the mine.
When it stops, it caculates the current score run with any doubling effects.

I made the default prob of gold cards 0.35 which made testing pretty easy.
I also made it public so it could be tweaked at will.