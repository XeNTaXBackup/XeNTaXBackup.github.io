## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-05-01T18:12:40+00:00
- Post Title: Megami Tensei - Imagine: model UV's

I have a question about UV's.
I just exported some models and textures from megami tensei: Imagine using nifscope and found that the textures were all messed up.

I've seen people do UV-flipping so I figured that might be the problem.
Since nifscope exports in obj, I put that through noesis since it conveniently comes with a UV-flipper and imports obj as well.

And it worked!
Here is a comparison between the rendering in nifscope, and the resulting output after flipping the UV's

[Rendered](http://img694.imageshack.us/img694/2910/rendered.jpg)

[Flipped UV](http://i.imgur.com/qgafA.jpg)

Except..............it's mirrored lol
I am converting the obj to mqo format, and I wrote a parser for the mqo that allows me to swap UV and vertices, but I'm so far I haven't found the correct combination.

Is there a general way of "mirroring" textures? I'm not sure if that deals with vertices or UV's.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-01T18:19:34+00:00
- Post Title: Megami Tensei - Imagine: model UV's

to flip it top to bottom multiply v * -1
to flip it left to right multiply u by -1
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-05-01T18:52:35+00:00
- Post Title: Megami Tensei - Imagine: model UV's

Hmm...I just came across this model:



I ran it through noesis by flipping UV and got this



I think the fact that the model itself is mirrored might be the reason why the words are mirrored 

So much for problem identification on my part 
This looks like a vertex issue. How can I mirror the model itself? lol
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-05-01T19:09:56+00:00
- Post Title: Megami Tensei - Imagine: model UV's

lol I got it.

But it was more complicated than I thought.

First I had to negate one of the vertex positions.
Then I had to multiply all v's by -1
Then I had to swap the the y and z vertices
Then I had to swap the UV coords for the y and z vertices to reflect the previous change
## Post #5
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-05-02T01:41:50+00:00
- Post Title: Megami Tensei - Imagine: model UV's

Thanks a lot chrrox
