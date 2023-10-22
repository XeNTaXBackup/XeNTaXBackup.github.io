## Post #1
- Username: knifelemon
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 06, 2015 5:08 pm
- Post datetime: 2015-02-06T13:53:23+00:00
- Post Title: how to convert LithTech model into 3ds max?

hello all 

I found one of the posts in the forum. 
 - [viewtopic.php?f=16&t=7230](http://forum.xentax.com/viewtopic.php?f=16&t=7230)

However, the post is too old....
i can't get the file and I can not get the information want.

I found one a way.
How is this.
(ex game : sudden attack)
ak47.ltb to ak47.lta - > lta open into modeledit ->  Remove all attributes(Animations, Socket, Pieces .... any)  - > compile to ltb -> ltb to x -> import 3ds max

but this method is very LowPolygon and the UV does not apply.

i need your help
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-06T15:20:54+00:00
- Post Title: how to convert LithTech model into 3ds max?

did you have a closer look at the *.ltb?

Here's bruno.ltb in hex2obj:



bruno_ltb_.JPG (64.15 KiB) Viewed 376 times



Should not be too hard to make an ltb maxscript importer with some basic ms knowledge.
But bruno.ltb is from 2006.
## Post #3
- Username: knifelemon
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 06, 2015 5:08 pm
- Post datetime: 2015-02-07T04:49:25+00:00
- Post Title: how to convert LithTech model into 3ds max?

> Reply from shakotay2
>
> did you have a closer look at the *.ltb?

Here's bruno.ltb in hex2obj:
bruno_ltb_.JPG

Should not be too hard to make an ltb maxscript importer with some basic ms knowledge.
But bruno.ltb is from 2006.

i dont know how to use 'hex2obj' 

i find your post [viewtopic.php?f=16&t=11819](http://forum.xentax.com/viewtopic.php?f=16&t=11819)

you can tell me how to use that?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-07T14:36:56+00:00
- Post Title: how to convert LithTech model into 3ds max?

> Reply from knifelemon
>
> i find your post viewtopic.php?f=16&t=11819

you can tell me how to use that?please be more specific.
(Do you have basic knowledges in maxscripting?)

First of all we would need the model format of your ltb. Should not be too hard to find that out.

Maybe it's the same as with bruno: Vertex block size:44,
vertices: floats
(little endian)



bruno_vertex_block_44_bytes.JPG (80.6 KiB) Viewed 350 times
## Post #5
- Username: knifelemon
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 06, 2015 5:08 pm
- Post datetime: 2015-02-09T00:43:47+00:00
- Post Title: how to convert LithTech model into 3ds max?

> Reply from shakotay2
>
> knifelemon wrote:i find your post viewtopic.php?f=16&t=11819

you can tell me how to use that?please be more specific.
(Do you have basic knowledges in maxscripting?)

First of all we would need the model format of your ltb. Should not be too hard to find that out.

Maybe it's the same as with bruno: Vertex block size:44,
vertices: floats
(little endian)
The attachment bruno_vertex_block_44_bytes.JPG is no longer available

i find that

and what should I do?
[hex2objhelp.PNG](https://xentaxbackup.github.io/file/8633_hex2objhelp.PNG)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-09T14:34:52+00:00
- Post Title: how to convert LithTech model into 3ds max?

> Reply from knifelemon
>
> i find that

and what should I do?first of all use another adjustment for your hexeditor.
Display data from offsets 00 to 0F (16 bytes per row).

(Your choice is not very useful.)

in hex2obj with the 000.ltb loaded:

- toggle the noPtC button to PtCld
- enter a VBsize of 44 (step 2).
- under 'step 3' enter 0x21879 as a vertex start address

Then try to get a decent point cloud by pressing 'mesh' and changing
the (vertex) count from 500 to greater (or less) sizes.
## Post #7
- Username: knifelemon
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 06, 2015 5:08 pm
- Post datetime: 2015-02-09T15:32:20+00:00
- Post Title: how to convert LithTech model into 3ds max?

> Reply from shakotay2
>
> knifelemon wrote:i find that

and what should I do?first of all use another adjustment for your hexeditor.
Display data from offsets 00 to 0F (16 bytes per row).

(Your choice is not very useful.)

in hex2obj with the 000.ltb loaded:

- toggle the noPtC button to PtCld
- enter a VBsize of 44 (step 2).
- under 'step 3' enter 0x21879 as a vertex start address

Then try to get a decent point cloud by pressing 'mesh' and changing
the (vertex) count from 500 to greater (or less) sizes.

thx but obj is seen only vertex..

why does this phenomenon appear?
[help2.PNG](https://xentaxbackup.github.io/file/8635_help2.PNG)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-09T17:45:49+00:00
- Post Title: how to convert LithTech model into 3ds max?

> Reply from knifelemon
>
> thx but obj is seen only vertex..

why does this phenomenon appear?because it's a point cloud.
As the name tells: a "cloud" of points without faces.

The next step would be to search for the face indices which determine how the vertices to be connected to faces
(triangles in most cases).

Press the tut(orial) button, do the contained example to understand 
"how to find face indices".

(Usually this is the first step but sometimes it makes sense to search for point clouds first.)
## Post #9
- Username: knifelemon
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 06, 2015 5:08 pm
- Post datetime: 2015-02-10T00:59:06+00:00
- Post Title: how to convert LithTech model into 3ds max?

> Reply from shakotay2
>
> knifelemon wrote:thx but obj is seen only vertex..

why does this phenomenon appear?because it's a point cloud.
As the name tells: a "cloud" of points without faces.

The next step would be to search for the face indices which determine how the vertices to be connected to faces
(triangles in most cases).

Press the tut(orial) button, do the contained example to understand 
"how to find face indices".

(Usually this is the first step but sometimes it makes sense to search for point clouds first.)

um...

i did not understand any more.

it's so hard!
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-10T08:41:39+00:00
- Post Title: how to convert LithTech model into 3ds max?

if you sent me 000.ltb I could have a look at.
## Post #11
- Username: knifelemon
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 06, 2015 5:08 pm
- Post datetime: 2015-02-10T10:03:16+00:00
- Post Title: how to convert LithTech model into 3ds max?

> Reply from shakotay2
>
> if you sent me 000.ltb I could have a look at.

ok.. 
thank you shakotay2 !

[https://www.dropbox.com/s/chv8t8nqcl1rr0c/000.ltb?dl=0](https://www.dropbox.com/s/chv8t8nqcl1rr0c/000.ltb?dl=0) here
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-10T10:46:19+00:00
- Post Title: how to convert LithTech model into 3ds max?

000_ltb.JPG (219.25 KiB) Viewed 305 times
## Post #13
- Username: knifelemon
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 06, 2015 5:08 pm
- Post datetime: 2015-02-11T09:44:27+00:00
- Post Title: how to convert LithTech model into 3ds max?

> Reply from shakotay2
>
> 000_ltb.JPG

lol

it's have only the body?

head , leg ... other Everything not have?
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-11T12:01:07+00:00
- Post Title: how to convert LithTech model into 3ds max?

learn, search, try



000_ltb_pants.JPG (40.52 KiB) Viewed 291 times
## Post #15
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-02-11T18:24:04+00:00
- Post Title: how to convert LithTech model into 3ds max?

[http://himeworks.com/noesis-plugins/](http://himeworks.com/noesis-plugins/)
[https://www.dropbox.com/sh/xu3i6yvxfkxw ... tb.py?dl=0](https://www.dropbox.com/sh/xu3i6yvxfkxwlk5/AAC13-Qq6xdb4TvT7a-acE6Ea/fmt_ZuOnline_ltb.py?dl=0)
## Post #16
- Username: knifelemon
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 06, 2015 5:08 pm
- Post datetime: 2015-02-11T23:43:16+00:00
- Post Title: Re: how to convert LithTech model into 3ds max?

> Reply from shakotay2
>
> learn, search, try
000_ltb_pants.JPG

thx..

i've read the tut. but it does not make sense.

can you explain briefly?
## Post #17
- Username: knifelemon
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 06, 2015 5:08 pm
- Post datetime: 2015-02-11T23:44:56+00:00
- Post Title: Re: how to convert LithTech model into 3ds max?

> Reply from AceWell
>
> http://himeworks.com/noesis-plugins/
https://www.dropbox.com/sh/xu3i6yvxfkxw ... tb.py?dl=0

Very thx! i like you 

it's really work... 
but it's very highpoly and Polygons are unreliable
