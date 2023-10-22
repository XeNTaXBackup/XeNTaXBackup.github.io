## Post #1
- Username: ufive
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Feb 21, 2016 8:44 pm
- Post datetime: 2016-02-22T13:52:07+00:00
- Post Title: Fable 2 Models

Hi there,

After unpacking the BNK archive Fable 2 i found the models MDL format and heard that they can be opened in the program Blender with a special plugin. But trying to make it importing error appears. I tried to do it on older versions of Blender, but nothing. Help how do I open the file.

Many thanks for any help that anyone can provide
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-22T20:21:44+00:00
- Post Title: Fable 2 Models

> Reply from ufive
>
> Hi there,

After unpacking the BNK archive Fable 2 i found the models MDL format and heard that they can be opened in the program Blender with a special plugin. But trying to make it importing error appears. I tried to do it on older versions of Blender, but nothing. Help how do I open the file.

Many thanks for any help that anyone can provide
You're best off asking the Author of the plugin itself.
## Post #3
- Username: ByronT
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 10, 2014 3:58 pm
- Post datetime: 2016-03-12T08:03:26+00:00
- Post Title: Fable 2 Models

Is this the MDL importer by Keshire on the Fable 3 Modding forums?  If so you're best off posting there.  I suspect Lionhead changed the format slightly between games, or the unpacker didn't work correctly.
## Post #4
- Username: ByronT
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 10, 2014 3:58 pm
- Post datetime: 2021-08-03T09:55:56+00:00
- Post Title: Fable 2 Models

Not starting a new thread since this one's still here.

Ok, so I'm wondering if anyone else here is still looking into this and having more luck than I am with these mdl files!? :bangs head on keyboard:   

I think I've officially reached the end of my current skillset with this and to be honest it probably would have been quicker and more satisfying making the damn models myself   

So I'm going to add the file and split header for BW_Tower_GateIron, which is also present as a Fable 3 mdl for comparison. I've renamed them but they were originally both called BW_Tower_GateIron.mdl and extracted from globals_models.bnk and globals_models_headers.bnk respectively.  If anyone with better knowledge of this can help, I'd be very grateful.

It may be possible to get a usable* mesh from the headerless mdl file I guess if anyone can figure out where verts and faces start (which is my main stumbling block!) or whatever the hell is going on with these...

*I suppose that I should clarify what I mean by usable(!) in that my ultimate goal is to convert these meshes to NIF files for use in Oblivion and Skyrim for a Fable themed mod that I'm working on.  I've already been able to do this with meshes from Fables 3, TLC/Anniv and even Legends thanks to Keshire and Gildor.  It's just 2 now that's causing me much headaches!

Here are some more meshes that I have included for comparison:

[https://www.mediafire.com/file/j5l2djsq ... r.zip/file](https://www.mediafire.com/file/j5l2djsqi1e3me1/BW_Tower_exterior.zip/file)

[https://www.mediafire.com/file/vjc6uttp ... y.zip/file](https://www.mediafire.com/file/vjc6uttpvbji4g6/BW_Tower_LowPoly.zip/file)
[BW_Tower_GateIron.zip](https://xentaxbackup.github.io/file/20560_BW_Tower_GateIron.zip)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-03T12:10:21+00:00
- Post Title: Fable 2 Models

> Reply from ByronT ↑Tue Aug 03, 2021 5:55 pm at Tue Aug 03, 2021 5:55 pm
>
> I think I've officially reached the end of my current skillset with this and to be honest it probably would have been quicker and more satisfying making the damn models myselfRofl!
Yep, after 5 years there's some frustration, understandable.

I just wanted to give up after 30 minutes of fiddling when this popped up, some structure in BW_Tower_exterior.mdl!
(I really hope that's NOT the Fable 3 sample!?)
.



BW_Tower_exterior-mdl-one_sub_mesh.png (133.4 KiB) Viewed 92 times

(right part: switched to half floats)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-03T12:42:24+00:00
- Post Title: Fable 2 Models

Fable 2, GateIron, well, counts are higher, no time for more fiddling:
.



BW_Tower_GateIron_Fable2-mdl.png (25.21 KiB) Viewed 87 times
## Post #7
- Username: ByronT
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 10, 2014 3:58 pm
- Post datetime: 2021-08-03T13:20:15+00:00
- Post Title: Fable 2 Models

Nice one shakotay, that's a lot more success than I've had.  Luckily I've not spent the whole 5 years just on this, so I still have a little bit of hair left to tear out...

The BW Tower exterior is definitely Fable 2, only the LowPoly version appears in Fable 3.

"Sulu look, the sun has come out, it's a miracle!"
## Post #8
- Username: ByronT
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 10, 2014 3:58 pm
- Post datetime: 2021-08-14T18:29:30+00:00
- Post Title: Fable 2 Models

I've made some progress with the mdl files.  Once you know what to look for, it's fairly straightforward, as I'm basically just concerned with vertices and faces for now.  Anything else depends on whether the .tex files can be converted and applied to the meshes, either the Fable 2 ones or their Fable 3 equivalents (if present.)



Turns out Brightwood Tower was probably the worst one I could have started with, still not sure about that but I've not given up just yet!

But the Farmhouse, in Fable 2 but not in Fable 3, was fairly simple - 2 largeish submeshes comprise the main structure and roof, with a couple of smaller ones I've not extracted yet.

Next step is learning how to script an importer for blender I guess, see you in another 5 years!!

Edit: So I have obviously been able to spot the "important" stuff, i.e; vertices (3x pairs of half-floats) and faces (SHORTs directly following on from the vertex arrays).  I'm not 100% on the rest of the data contained within the 20-byte arrays, nor the groups of data before each vertex chunk and after the last faces chunk, but I'm pleased with how quick I managed to spot the patterns to find the verts and faces, so maybe the rest will emerge in due course, but any nudges in the right direction would be much appreciated  

As I understand it, it should be 2x SHORTs for UV coords, and there are always 2x bytes of 00 directly after the vertex coords which leaves 8-bytes unaccounted for.

Random sample array (start address 000247D8) from Brightwood Tower exterior.mdl:

Vertex Coords↓ -- Nowt↓ -- UVs somewhere in this lot?↓
----------------------------------------------↓ - ↓ - ↓ - ↓  -(most likely)
CC D3 48 9B 4B 12 00 00 CC 05 E4 6D 34 73 39 E9 C0 C8 37 94
