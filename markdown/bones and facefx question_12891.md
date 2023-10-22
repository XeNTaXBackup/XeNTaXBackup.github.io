## Post #1
- Username: 123185321f
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Apr 28, 2012 8:53 am
- Post datetime: 2015-06-01T22:34:11+00:00
- Post Title: bones and facefx question

-
## Post #2
- Username: 123185321f
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Apr 28, 2012 8:53 am
- Post datetime: 2015-06-02T01:56:11+00:00
- Post Title: bones and facefx question

-
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-02T06:49:32+00:00
- Post Title: bones and facefx question

Hi,
first of all: never use 42 columns for displaying hex values. Never.
Use 16 (or 32) columns. This is what makes sense on 32/64 bit systems.

2ndly: what's the sense of your nick? Converted it from float to hex, still no sense.  

Didn't read your wall of text fully, sry.
How you come to the assumption that there are 69 bones?
What are their names? (First three/last three ones?)

"Nose, Lip, Eye, Cheek, Jaw" looks like bones of a head.

> Reply from 123185321f
>
> after a little bit of poking around it became apparent that at least 9 of those values (9 out of 16 related to the bones) are position, rotation, scale in increments of 3 (x,y,z coordinates). what other interesting things can these wonderful numbers represent in a 3-D world, if they are not XYZ in position/rotation/scale? And is there a criteria to know at the glance what such hexadecimal value be part of? Or perhaps is really just a matter of educated guess? And now I sound rhetoricalI would like to answer this but I'd need another file to feel motivated.

That file should contain skeleton bone names such as "root, head, pelvis, clavicle, arm, hand, finger, hip, calf, knee, toe" or similar.
## Post #4
- Username: 123185321f
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Apr 28, 2012 8:53 am
- Post datetime: 2015-06-02T16:01:30+00:00
- Post Title: bones and facefx question

-
## Post #5
- Username: 123185321f
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Apr 28, 2012 8:53 am
- Post datetime: 2015-06-02T17:38:54+00:00
- Post Title: bones and facefx question

-
## Post #6
- Username: 123185321f
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Apr 28, 2012 8:53 am
- Post datetime: 2015-06-07T00:30:39+00:00
- Post Title: bones and facefx question

-
## Post #7
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2019-12-17T08:05:39+00:00
- Post Title: bones and facefx question

> Reply from 123185321f ↑Sun Jun 07, 2015 8:30 am at Sun Jun 07, 2015 8:30 am
>
> 
The good news is that I managed to properly extract the relevant data from the FXA format, in particular the phonemes mapping. 

I ended up making Cmdr. Shepard from the mass effect series talk using sounds from Dragon Age 2.

There is still some missing ingredient, for example I used Satele model from SWTOR for a test, and although the phonemes mapping was good, in my tests her eyes were blinking weirdly

So far the best results I got with Dragon Age 2 models, because of using RoboBrad that comes with FaceFX 1.7.1 from the original Dragon Age Toolset

Mass Effect and Star Wars the Old Republic tests were done using FaceFX 1.7.4 from UDK 3.x

I still don't know after extracting 10 floats and identifying 9 of them, what is the remaining one for.

Anyways, I'll need to take a break, my eyes are on fire, and it's not always user-friendly to interact with my computer via a microphone, these past few days were very fruitful, so to speak, but my body is out of order now

It sounds like you figured out how to get .fxa animations into a usable animation format. Do you still remember how this was done, and would you be willing to share whatever tools/procedures you came up with?
## Post #8
- Username: 123185321f
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Apr 28, 2012 8:53 am
- Post datetime: 2020-03-05T12:59:06+00:00
- Post Title: bones and facefx question

-
