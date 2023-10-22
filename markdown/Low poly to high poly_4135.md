## Post #1
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2010-02-13T09:47:40+00:00
- Post Title: Low poly to high poly

Since the rise of game engines utilizing normal maps to create a "higher-def" look without the actual poly count going through the roof, game content detail has gone up exponentially with the last generation to the next.  There are tons of tools free and commercial that can take a hi-poly model and a-la low-poly: create a normal map that fakes the look of the higher res.  I'm wondering if it's possible to take this low poly source model, and create a hi-poly mesh using the normal map texture as the reference?
## Post #2
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2010-02-13T15:46:46+00:00
- Post Title: Low poly to high poly

> Reply from Mirrodin
>
> Since the rise of game engines utilizing normal maps to create a "higher-def" look without the actual poly count going through the roof, game content detail has gone up exponentially with the last generation to the next.  There are tons of tools free and commercial that can take a hi-poly model and a-la low-poly: create a normal map that fakes the look of the higher res.  I'm wondering if it's possible to take this low poly source model, and create a hi-poly mesh using the normal map texture as the reference?

it might be possible but i have never tried. i think first you have to convert the normal map into a displacement map. then turn the low poly model into quads so u can then apply the displacement onto it. u can try this in mudbox, zbrush or maya or max depending on wut ur computer can handle. usually zbrush and mudbox can handle more polygons.  hope this helps
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2010-02-13T22:05:27+00:00
- Post Title: Low poly to high poly

Yeah thats exactly how you would do it.

Just do it in zbrush or mudbox, as to get ALL the details from the displacement map youd likely need upto and over 1million polys...and Maya and max go crazy when you try to do it...or it just takes FOREVER.

So yeah just convert your normal map to a displacement map, I think there is an option for it within XNORMAL...but Don't hold me to it cos I honestly cant remember.
## Post #4
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-02-14T11:48:42+00:00
- Post Title: Low poly to high poly

this is very interesting because I wanted to do it just last week. I have some nice low polys with normal maps and I imported the low poly to zbrush and wondered if there was any way to convert normal to the object. Hope someone has a tutorial on this
## Post #5
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2010-02-14T15:57:08+00:00
- Post Title: Low poly to high poly

yeh use xnormal its free. [http://www.xnormal.net/1.aspx](http://www.xnormal.net/1.aspx). and this is the steps to apply the displacement map. [http://www.pixologic.com/docs/index.php ... ntable=yes](http://www.pixologic.com/docs/index.php?title=Applying_Displacement_Maps&printable=yes)
## Post #6
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2010-02-14T21:28:34+00:00
- Post Title: Low poly to high poly

There are many tutorials out there (Google).

However, any respectable person will tell you that it's next to impossible to convert a 'Normal Map' into anything else that actually works...ironically, you can convert almost everything into a Normal Map, but its still crap since it's more of a Bump Map then a Normal one, without any actual ability to Parallax the data contained within it.

In short, no, and it's not worth it to tell you truth. All the time you spend trying to 'create' a Normal map without the actual High-Res bake is simply not worth, especially since you won't have any real use for the model afterwards, unless you plan on making an Animation or Turntable Display, which in both cases, it plagiarism.

While creating an animation from another model that is not yours (as long as credited) is fine, your need a beefy CPU to render it with the Displacement/Height maps.
## Post #7
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2010-02-15T05:05:47+00:00
- Post Title: Low poly to high poly

Actually, my purpose would be machinima related, parodies of the games being "prettied" up for a decent production and since it's free and still crediting all copyright holders there's no way I can just ask them to hand over hi-poly source assets, it'll never happen. However, if I can find a way to do as I set out in this post, then that willl only help.  And ID be using offline renderers and hours upon hours of crunch time on a dedicated Render farm.
## Post #8
- Username: potemkis
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 01, 2009 2:11 pm
- Post datetime: 2010-03-20T01:46:22+00:00
- Post Title: Low poly to high poly

I have tried this. Yes- it almost killed my pc!   

Your best bet- if you're doing any kind of animation in a 3d animation program- use the normal maps. Fake it. Otherwise, unless you have a render farm, you'll be there for a month of sundays. Just use lighting and make sure your smoothing groups are set up right. You should be fine. 

An alternative would be to do it with a game engine. Just boost the detail up.
