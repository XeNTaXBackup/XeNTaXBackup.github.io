## Post #1
- Username: zdsmdbh
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 13, 2013 10:03 am
- Post datetime: 2013-11-14T02:37:51+00:00
- Post Title: (Request) NeverDead Model Extract

I use PSARC extractor and asura.bms to extract files,I am sure I got some textures(TGA),but it's not readable,even though I change extension to DDS
I will uploaded those files,hope somebody will take a look
Texture [http://filesmelt.com/dl/arcadia_body_colspec.tga](http://filesmelt.com/dl/arcadia_body_colspec.tga)
Mesh(maybe) [http://filesmelt.com/dl/arcadia](http://filesmelt.com/dl/arcadia)
Really want some models loaded in 3DS MAX
My skydrive have more files,If you need them [https://skydrive.live.com/?cid=84A39EE4 ... B8CC%21109](https://skydrive.live.com/?cid=84A39EE48581B8CC&id=84A39EE48581B8CC%21109)
If I break rule,please tell me
Sorry for my poor english and thank you
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-11-14T04:03:12+00:00
- Post Title: (Request) NeverDead Model Extract

seems someone has done it

[http://deronar.deviantart.com/art/Never ... -367246776](http://deronar.deviantart.com/art/NeverDead-Arcadia-Maximille-367246776)


and yes that arcadia file is a model

-vertblock @ 0x2a4h

-facelist @ 0x68964


use Hex2OBJ
## Post #3
- Username: zdsmdbh
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 13, 2013 10:03 am
- Post datetime: 2013-11-14T10:17:29+00:00
- Post Title: (Request) NeverDead Model Extract

Deronar extracted many models,but seems like he never share those models in public

I tried to learn how to find face indices end address,but I can't understand it at all
Can you tell me what's the end address？
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-14T11:06:01+00:00
- Post Title: (Request) NeverDead Model Extract

You don't need to know the endaddresses. Just try a face index count of 500 then increase this value.
There's some trial 'n error required until the max index count in the lower left list box gives a useful value.

Or use this:
[](http://www.pic-upload.de/view-21329588/NeverDeadModel.jpg.html)

But rename your model file to arcadia.mdl for example because hex2obj will crash without a dot in the filename. (just another ugly ptr bug  )

btw: nice babe with a realistic real life face.
## Post #5
- Username: zdsmdbh
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 13, 2013 10:03 am
- Post datetime: 2013-11-14T12:34:08+00:00
- Post Title: (Request) NeverDead Model Extract

Thank you,got the mesh.Any idea to convert texture readable?
Count 43710,trial 'n error,really?  
btw:Hex2OBJ,what a great tool
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-14T14:05:10+00:00
- Post Title: (Request) NeverDead Model Extract

> Reply from zdsmdbh
>
> Thank you,got the mesh.Any idea to convert texture readable?
Try TextureFinder.
[](http://www.pic-upload.de/view-21330809/arcadia_tex.jpg.html)

> Count 43710,trial 'n error,really?combined with some experience, maybe.

> btw:Hex2OBJ,what a great tool"great"? don't know.
"simple 'n easy" that it is what it was intended to be.
## Post #7
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2013-12-08T15:55:57+00:00
- Post Title: (Request) NeverDead Model Extract

Out of curiosity, how would one deal with multiple UVs the mesh seems to have. The body and hair bits UVs seem to come out fine (albeit flipped) but the face one seems to be completely borked. 

I've been able to get a sort of salveagable one if I set it to WordUV. Though I'm working out what all the entries on hex2obj are
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-08T19:00:37+00:00
- Post Title: (Request) NeverDead Model Extract

part of the uvs are clipped. I'll look at that asap:
[](http://www.pic-upload.de/view-21571084/Arcadia.jpg.html)
## Post #9
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2013-12-08T21:23:17+00:00
- Post Title: (Request) NeverDead Model Extract

> Reply from shakotay2
>
> part of the uvs are clipped. I'll look at that asap:

Yeah looks like face and eyebrows. But like I've said - if I set it to wordUV I do get more or less something that remotely looks like a face UV in one of the corners. Albeit quite stretched.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-08T21:40:13+00:00
- Post Title: (Request) NeverDead Model Extract

> Reply from junk angel
>
> But like I've said - if I set it to wordUV I do get more or less something that remotely looks like a face UV in one of the corners. Albeit quite stretched.Clipping was no good idea - without it looks like this:
[](http://www.pic-upload.de/view-21573397/Arcadia_UVs.jpg.html)
There is no clipping with WordUVs (but nethertheless the uv format should be half floats).

Thank you for the feed back!
## Post #11
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2013-12-08T21:59:52+00:00
- Post Title: (Request) NeverDead Model Extract

> Reply from shakotay2
>
> junk angel wrote:But like I've said - if I set it to wordUV I do get more or less something that remotely looks like a face UV in one of the corners. Albeit quite stretched.Clipping was no good idea - without it looks like this:

There is no clipping with WordUVs (but nethertheless the format should be half floats).

Thank you for the feed back!:-)

Yeah this looks correct 

In the meantime I'll go back to the tutorial to try and understand what I'm looking at
