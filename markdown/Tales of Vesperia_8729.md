## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-09T06:45:29+00:00
- Post Title: Tales of Vesperia

Looks like someone went and manually reversed a PS3 compression.
Really nice.

Decompress script: [viewtopic.php?p=70962#p70962](http://forum.xentax.com/viewtopic.php?p=70962#p70962) (works for tales of grace also, so maybe someone can upload samples from there. Textures would be cool also)
Samples: [http://www.mediafire.com/?6423f9rml64tsmd](http://www.mediafire.com/?6423f9rml64tsmd)

A quick glance I'd guess that the position buffer and index buffer (winding tristrips or whatever it's called) are in plain sight (sounds like a good start). After the index buffer it might be normals or UV's. Then some more structs.

There seems to be multiple FPS4 chunks in a single file. I don't know if there's any significance to that.
Of course, it is big endian.
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-09T08:34:25+00:00
- Post Title: Tales of Vesperia

Lol 3 days and 40 lines of code. Interesting lol.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-09T08:43:20+00:00
- Post Title: Tales of Vesperia

Could probably squeeze it down to 10 if you abuse short-hand, ignore "unnecessary" variable assignments, import all your modules in one line, cut out those pointless white-space that's only there for readibility, throw that decompress function into a lambda call, don't bother declaring that constant at the top, etc etc

He probably got a lot out of it though. And he codes with good style
## Post #4
- Username: StorMyu
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 21, 2011 6:35 pm
- Post datetime: 2012-04-09T09:42:05+00:00
- Post Title: Tales of Vesperia

finale00, do you have names for the files or you're just guessing ?
Because I'd be interested in the "Dhaos" model file from Tales of Vesperia =p
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-09T09:45:58+00:00
- Post Title: Tales of Vesperia

You'll have to ask the guy that uploaded these samples in that compression thread. I don't have the game.

But man, dhaos is still in the story? Didn't he get beaten around in like pretty much every game since way back in SNES.
And he looks even weaker in vesperia.
## Post #6
- Username: StorMyu
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 21, 2011 6:35 pm
- Post datetime: 2012-04-09T13:48:51+00:00
- Post Title: Tales of Vesperia

> Reply from finale00
>
> But man, dhaos is still in the story? Didn't he get beaten around in like pretty much every game since way back in SNES.
Yeah he's just a Cameo battle along with Kratos from Tales of Symphonia and Shizel from Tales of Eternia and Barbatos from Tales of Destiny.
I'm just interested in a 3D model of Dhaos actually =p
[http://www.youtube.com/watch?v=3bvlqOgqRzc](http://www.youtube.com/watch?v=3bvlqOgqRzc)
Still never tried to touch 3D files though... could be a fun experiment.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-11T18:32:04+00:00
- Post Title: Tales of Vesperia

OH I get it lol it's an offset table at the beginning of each FPS block that gives offsets and sizes and stuff.

The first FPS block points to other FPS blocks, while subsequent FPS blocks point to various chunks relative to the start of their block.

Will need more samples to determine whether there really are only 5 FPS blocks per file.
## Post #8
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2012-05-30T19:26:42+00:00
- Post Title: Tales of Vesperia

For tales of graces Wii does anyone know which files holds the Characters Models?
