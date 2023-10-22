## Post #1
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-10T07:21:17+00:00
- Post Title: [Request]Virtual On Oratorio Tangram Ver.5.66

Hello all.
I'm trying to rip models from Virtual On Xbox360.
Unfortunatly i don't have the skill of converting.
I hope someone can help.
*.mg2 texture file (ninja-style pvr image.)
*.mrg  ??
*.mt   ??
[delete](delete)

Thanks in Advance!
## Post #2
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-02-10T09:22:12+00:00
- Post Title: [Request]Virtual On Oratorio Tangram Ver.5.66

Here are pvr2tga sample.
[http://www.mediafire.com/?ome271ajfv1f2ip](http://www.mediafire.com/?ome271ajfv1f2ip)
Can someone help me to convert models?
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-10T10:00:04+00:00
- Post Title: [Request]Virtual On Oratorio Tangram Ver.5.66

The model format is quite messy.
Upload more models.  It's the mg2 files.
## Post #4
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-02-10T10:28:02+00:00
- Post Title: [Request]Virtual On Oratorio Tangram Ver.5.66

> Reply from finale00
>
> The model format is quite messy.
Upload more models.  It's the mg2 files.
Here are some more mg2 samples.
[delete](delete)
## Post #5
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-02-11T04:20:23+00:00
- Post Title: [Request]Virtual On Oratorio Tangram Ver.5.66

I'm embarrassed to ask, could you have a look at this? too.
bin file from Dennou Senki Virtual On Force
[delete](delete)
## Post #6
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-02-12T13:18:11+00:00
- Post Title: [Request]Virtual On Oratorio Tangram Ver.5.66

Does anybody interested in this post?
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-12T18:28:36+00:00
- Post Title: [Request]Virtual On Oratorio Tangram Ver.5.66

I looked at Virtual On when you originally posted the samples in January; it looked difficult. What finale says is true; the data is a mashed up piece of junk and there was no index buffer.
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T18:32:02+00:00
- Post Title: [Request]Virtual On Oratorio Tangram Ver.5.66

Maybe it is like those other formats where you string together a bunch of vertices and those are your faces.
And I was wrong, mg2 was the textures that you already have the tool for lol

I meant mrg.

Anyways if you look at the mrg's close enough, you'll see that for each bunch of floats (coords? normals?) there's an integer before it that indicates how many coords there are.

Each struct is 16 bytes. after that you get some odd stuff, and then back to your 16-byte structs again.

So in the fei1a.mrg example, after all those (offsets and counts) at the beginning, at offset 968 you get your first integer (15), followed by 15*16 floats, followed by (stuff). Skip past that stuff, and at offset 1952, you start again with your integer (14), followed by 14*16 floats, followed by (stuff).

This is the pattern I've observed anyways.

```
<offsets and counts>

#each section
loop {
   <floats and stuff>
   int32 count
   count*16 floats
   int32 count2
   <stuff>
}

```
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-12T18:41:41+00:00
- Post Title: [Request]Virtual On Oratorio Tangram Ver.5.66

Could be; sucks that there are only maybe 4-5 people around here actively trying to rip games.

EDIT:
Cool, go finale go! Going to pick this one up?
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T18:50:47+00:00
- Post Title: [Request]Virtual On Oratorio Tangram Ver.5.66

No, I prefer human girl models, not humanoids.
Plus I don't know a lot about non-indexed face drawing.

But more mrg models would be nice, so I can verify that the patterns are correct.

Anyways you'll see in the header that it starts with 4 integers (where the last 2 are a little smaller than the filesize).

Then you read in two integers, numSections, unk.
Using the example in the OP,

numSections = 112
unk = 10733

Let us suppose that numSections was in fact the number of different sections.

```
   int32 offset
   int32 unk
}

```


If you seek to each offset, and then skip another 68 bytes, you'll find yourself at an integer that indicates how many of those 4-float structs there are.

This applies for a random number of offsets I picked.

So maybe something like

```
   float[4] ?
}

struct Section {
   68 bytes
   int32 numVerts
   numVerts Vertex

   int32 count2
   <stuff>
}

```


Each section is fairly small, so a pattern for that <stuff> can't be too hard to find.
Of course since you already have an offset table, you can just skip that and hope the vertices make sense.
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T19:04:35+00:00
- Post Title: [Request]Virtual On Oratorio Tangram Ver.5.66

K, it sorts of looks like a head.

.............

Clearly my imagination runs wild.

More mrg samples plz.
## Post #12
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-02-12T19:25:01+00:00
- Post Title: [Request]Virtual On Oratorio Tangram Ver.5.66

Thank you for your interest.
Here are all mg2 and mrg files.
[delete](delete)
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T19:34:42+00:00
- Post Title: [Request]Virtual On Oratorio Tangram Ver.5.66

lol nice, all models.

Well this looks kind of funky. I have no idea what it is, and it's probably wrong, but all those spirals are pretty amusing.



The <stuff> right after the <vertices> seems to have indices. If you highlight FF FF FF FF you'll find that the number of results for each section is the same as the count provided.

But some of them are 36 byte structs while others are 40 byte structs.
## Post #14
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-12T19:37:51+00:00
- Post Title: [Request]Virtual On Oratorio Tangram Ver.5.66

lol
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T19:45:57+00:00
- Post Title: [Request]Virtual On Oratorio Tangram Ver.5.66

You know if you look carefully at the first image I posted, you can sort of see those heart shaped bows in the OP's image. But her body doesn't make any sense to me. Maybe they launch projectiles as well like gundams? Or have like upgrades and all? Maybe you can buff them up with massive shields. Maybe in-game they activate some sort of barrier like field that results in those massive spirals around the base body.

Maybe......

Anyways the map files looks really different from the models.
It's possible that I'm not parsing it correctly.

Some of the mrg's are just textures too wtf, like segalogo.mrg. It just has a pvrt file.
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T20:20:41+00:00
- Post Title: Re: [Request]Virtual On Oratorio Tangram Ver.5.66

Alright no clue what I am looking at.
Here's whatever I did for anyone that wants to continue.

[http://db.tt/IZfm2Nuy](http://db.tt/IZfm2Nuy)
## Post #17
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-02-13T05:57:29+00:00
- Post Title: Re: [Request]Virtual On Oratorio Tangram Ver.5.66

> Reply from finale00
>
> Alright no clue what I am looking at.
Here's whatever I did for anyone that wants to continue.
http://db.tt/IZfm2Nuy
Awesome! I'm really very enthusiastic. 
Are you planning to upgrade your great plugin? Please.
Here is original data.farc file.
[delete](delete)
I used chrrox's quickbms script to extract the file.

```
get arcsize asize
get idstring long
get headersize long
get one long
for i = 0 < 0xFFFF
get name string
get offset long
get zsize long
get size long
string name + ".gz"
if offset > 0
log name offset zsize
else
cleanexit
endif
next i
```


I hope I can be of some help.
## Post #18
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-13T15:45:43+00:00
- Post Title: Re: [Request]Virtual On Oratorio Tangram Ver.5.66

The parsing is crudely done and I don't understand how the faces are drawn. It might have something to do with the unknown section after each veered buffer but I see nothing obvious.

Since you have the game, does the images resemble anything? Especially the one with all the spirals.
## Post #19
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-02-13T17:44:33+00:00
- Post Title: Re: [Request]Virtual On Oratorio Tangram Ver.5.66

> Reply from finale00
>
> The parsing is crudely done and I don't understand how the faces are drawn. It might have something to do with the unknown section after each veered buffer but I see nothing obvious.

Since you have the game, does the images resemble anything? Especially the one with all the spirals.
This game is Xbox LIVE Arcade
