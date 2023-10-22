## Post #1
- Username: SoapyLemons
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Feb 04, 2011 9:01 am
- Post datetime: 2011-05-21T06:19:46+00:00
- Post Title: Luigi's Mansion SZP file format

Hey all, I've got a problem here. I can't really crack the Luigi's Mansion format, which is SZP. I've managed trying to use the SZS tools (mainly yay0dec, yaz0dec, and rarcdump). I can convert some SZP files with the yay0dec. It then spits out something like "insertmodelnamehere.szp 0.RARC" but it isn't a real RARC file if you get what I mean. Anyways, I've got the raw SZP files here.
Download:

```
http://www.mediafire.com/?v118dqxb247gggr
```
## Post #2
- Username: ItsEasyActually
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Dec 17, 2010 7:49 am
- Post datetime: 2011-05-22T07:41:04+00:00
- Post Title: Luigi's Mansion SZP file format

Hey, I took a look at this and I believe that the model format is an earlier version of .bmd compared to that of Super Mario Sunshine. I looked in the header of two raw .bmd files in the game's iso. bmd2 is the version, and using thankis tools, the Yay0 decompresser outputs the file to a .rarc, but as far as I can tell, it's not a real .rarc file. I don't know what kind of compression it is though...and I don't even know if it's being converted correctly from Yay0. If I knew more than how to just see certain things, I'd offer more. Hopefully someone else can...
## Post #3
- Username: luigimario
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 29, 2010 8:50 pm
- Post datetime: 2011-05-27T23:58:57+00:00
- Post Title: Luigi's Mansion SZP file format

they get decompiled to .mdl files, but not like Valve or the mdl7 format

here is one for a mario model
[http://dl.dropbox.com/u/26296116/mario.zip](http://dl.dropbox.com/u/26296116/mario.zip)


I have luigi and egadd's models ripped and rigged for the source engine already so if anyone wants a copy of those pm me.
## Post #4
- Username: SoapyLemons
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Feb 04, 2011 9:01 am
- Post datetime: 2011-05-28T02:44:15+00:00
- Post Title: Luigi's Mansion SZP file format

> Reply from luigimario
>
> they get decompiled to .mdl files, but not like Valve or the mdl7 format

Mind if I ask where you got the tools to rip the models?
## Post #5
- Username: luigimario
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 29, 2010 8:50 pm
- Post datetime: 2011-05-28T21:25:07+00:00
- Post Title: Luigi's Mansion SZP file format

I don't remember, but I think the author is lunarboy, or luna boy one of those
## Post #6
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2011-05-28T23:22:49+00:00
- Post Title: Luigi's Mansion SZP file format

That would be Lunaboy. There should be an answer in [this](http://www.emutalk.net/threads/49534-Luigi-s-mansion) thread.
## Post #7
- Username: SoapyLemons
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Feb 04, 2011 9:01 am
- Post datetime: 2011-05-29T03:13:36+00:00
- Post Title: Luigi's Mansion SZP file format

Too bad I already saw most of those threads.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-29T04:20:06+00:00
- Post Title: Luigi's Mansion SZP file format

These files contain rarc files.
Just search for RARC
the problem is they seem to have modified the rarc header a little.
## Post #9
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2011-05-29T09:37:23+00:00
- Post Title: Luigi's Mansion SZP file format

> Reply from SoapyLemons
>
> Too bad I already saw most of those threads.
Well I guess you didn't read the one I linked to properly. On the fifth page, Anton posted a link to his site, whichs hosts ArcExtract. You can use ArcExtract to decompress .SZP files, and by that process automatically decompress the .RARC archives within those files.

It's a shame no work has been done on reading and/or converting the contents of these archives that I know of. It could have been very handy for a rip request I was given recently...
## Post #10
- Username: SoapyLemons
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Feb 04, 2011 9:01 am
- Post datetime: 2011-06-13T04:00:40+00:00
- Post Title: Luigi's Mansion SZP file format

I've got the models ripped. But tell me about this MDL format that's in here? I know they're models. But what version/kind is it? It's not Valve or any of the basic stuff, little help?
## Post #11
- Username: SoapyLemons
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Feb 04, 2011 9:01 am
- Post datetime: 2011-07-12T04:10:15+00:00
- Post Title: Luigi's Mansion SZP file format

So lately I've had a friend trying to help me, and he doesn't know where to go. All we have are the MDL files, but how would we be able to extract these?
## Post #12
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2011-07-12T04:50:44+00:00
- Post Title: Luigi's Mansion SZP file format

There is currently no way as far as I understand, but thakis on Emutalk said something about writing a program to support it ages ago.
## Post #13
- Username: ItsEasyActually
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Dec 17, 2010 7:49 am
- Post datetime: 2011-10-02T15:33:48+00:00
- Post Title: Luigi's Mansion SZP file format

Alright, so this thread is ages old, but I have some info to add to it. I've mapped out a good bit of the model format now, but I cannot import anything other than vertices as I have no idea where the face data is. My model spec is far from complete, and really doesn't have a lot good info in it as I've only found a handful of the data and offsets. Though I have figured out what most chunks look like, I still don't have any idea on what some of it actually is. So hopefully someone here has some time, I suggest looking into the models with the spec I'm gonna include here, and maybe figure out something with the face data.

```

== File Header ==

0x00	4	Constant x04B40000
0x04	4	Unknown, possible size of something
0x08	2	Total of some sort
0x0A	2	Another total
0x0C	2	Another total
0x0E	2	Another total
0x10	4	Unknown, Possibly two shorts
0x14	4	Unknown, possibly two shorts
0x18	8	Null
0x20	4	Unknown
0x24	2	Total?
0x26	2	Total?
0x28	2	Total?
0x2A	2	Total?
0x2C	4	Null



==Offsets==

0x00	4	Offset to ID Structs?
0x04	4	Offset to possible vertex/mesh info?
0x08	4	Offset to Data after ID Structs
0x0C	4	Offset to unknown
0x10	4	Offset to data after previous data from the last pointer
0x14	4	Offset to last data section 
0x18	4	Offset to Vertex Chunk
0x1C	4	Offset to Normals chunk
0x20	4	Offset to unknown
0x24	4	Offset to (Same as last offset)
0x28	8	Null
0x30	4	Offset to Bone Data Table
0x34	4	Null
0x38	4	Offset to possible weight data or something?
0x3C	4	Offset to struct data after "weight" data
0x40	4	Offset to struct data after previous data
0x44	4	Offset to data after previous data
0x48	8	Null
```


Hope someone can help out with finding the face data since I still haven't managed to.
