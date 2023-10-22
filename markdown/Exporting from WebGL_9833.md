## Post #1
- Username: Vashey
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Mar 15, 2011 9:47 pm
- Post datetime: 2012-11-05T21:57:22+00:00
- Post Title: Exporting from WebGL

Hi.
I found this site that might interest a great bunch of people:
[http://www.3dcg-arts.net/](http://www.3dcg-arts.net/)
There you can see a big amount of 3D models displayed on webgl.

Problem is there is no way that I know to export them.

On another thread finale00 explained a way to do it, but a lot of people didn't get along with this specific way for a reason I did not understand.
Apparently the buffer array that generates the mesh can be saved to your computer then import it on noesis (with a script for .webgl)

But it never works, finale00 put a single model that he modified(and this one works).

What I'm interested in is how he modified the model so that we can all do the same to export every model we want to rip from the site.
Personnaly I'm interested in this one:
[http://www.3dcg-arts.net/art/polygon/2512/full](http://www.3dcg-arts.net/art/polygon/2512/full)



I used an app "webgl inspector" that let me see the mesh rendered:


but to that day I didn't found a way to export it yet.
as you can see it gives me the buffer.array content and the vertices coordonate for each poly.

So what can I do???
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-11-06T13:34:06+00:00
- Post Title: Exporting from WebGL

That site (used to, haven't looked at it for some time) stores 3D data in JSON so it is fairly trivial to parse.
However they had several formats already at that time and I never looked beyond one of them.

If someone's developed an app that allows you to export these buffers to OBJ directly then it is likely a better alternative.
## Post #3
- Username: Vashey
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Mar 15, 2011 9:47 pm
- Post datetime: 2012-11-06T13:49:58+00:00
- Post Title: Exporting from WebGL

You mean that saving the [http://www.3dcg-arts.net/api/model/get/ ... ormat/2512](http://www.3dcg-arts.net/api/model/get/three_format/2512)
to webgl and importing it on noesis, is useless now?

Is there such an app for buffer arrays?
it's likely impossible to find that.

Your script isn't much help? nothing I can do to modify it in some way?
## Post #4
- Username: Vashey
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Mar 15, 2011 9:47 pm
- Post datetime: 2012-11-06T14:01:05+00:00
- Post Title: Exporting from WebGL

in other way to say it, is there yes or not a way to export it?

I obviously won't find a software to export buffers to obj nor write it myself.
finale00 you did it before, why can't you do it now honestly?
