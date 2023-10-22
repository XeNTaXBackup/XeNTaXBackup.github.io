## Post #1
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-01T15:36:50+00:00
- Post Title: Universal Century Gundam Online .DET

were not entirely sure how this file works, we heavily suspect that its an archive file that contains 3d files but also there are people telling us that the file itself is a 3d file format which I don't understand why it would be if there is more then 1 3d file in it and they all don't get called at once when playing the game so im really leaning towards the archive.

If anyone can help me open this file I will be very grateful, supposedly there are 7 files in here "may be more I don't really know"

Heres a link to the file [http://www.2shared.com/file/Uj6gt1Tu/E_ITEMMAPITEM.html](http://www.2shared.com/file/Uj6gt1Tu/E_ITEMMAPITEM.html)

I don't know their format either but their names are
CLOCKTOWER
DRINKINGFOUNTAIN
GROUNDLIGHT
HYDRANT
MARKINGCONE
STATUE0
STATUE1
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-01T15:41:23+00:00
- Post Title: Universal Century Gundam Online .DET

It is a 3d model format.
## Post #3
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-01T15:44:17+00:00
- Post Title: Universal Century Gundam Online .DET

> Reply from chrrox
>
> It is a 3d model format.
that's good to know even though its a 3d file format it still has more then one file in it somehow, all these files aren't called upon at once in the game they are in different locations and sometimes multiplied at one location. It makes me wonder how it works as we really want to add to and edit some of the mesh inside.
## Post #4
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-29T03:19:17+00:00
- Post Title: Universal Century Gundam Online .DET

sorry for bump I have been on vacation. Anyway I really need help with reversing this file. I want to be able to extract the 3d and possibly re import. I am not a good coder so personally I wont be able to figure out but Im a 3d modeler and I want to be able to make mods for this game. I would be eternally grateful with any help.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-29T13:56:10+00:00
- Post Title: Universal Century Gundam Online .DET

If you are a 3D modeler then you would probably have a better idea what the data represents, since you most likely know more than that an average programmer knows. Especially since there's all sorts of stuff in there like material properties etc. A strong background in 3D should make it easy to learn to figure out a format since you have a larger bag of tricks.

The string "XR" constantly appears at certain points in the file. Perhaps that is of some significance.
For example



Take a look at the third highlighted XR from the top. There's a 3 right before it, and the number after the XR represents the length of the string.

I've noticed each XR is preceded by a particular number, but haven't found any patterns.
If you can find some patterns and take a guess what they might be based on your experience with the program itself, that would be helpful.

For instance, in this case, I might say "any XR's preceded by a 03 00 represents a texture", but that is not a guarantee since I only have limited samples to work with.

Also, it could always be an archive, or at least, a bunch of models stored together, but at first glance it looks like all of the textures are defined near the bottom of the file while the geometry is defined above it.
## Post #6
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-29T17:34:00+00:00
- Post Title: Universal Century Gundam Online .DET

there is no actual textures in this file. The .DDS is a relocation to another file that has that file. Im almost sure the data to the 3d files are near the bottom. I hadn't noticed any patterns yet I been searching but stuff just seems to be different sizes.

I have a feeling the developers left data caves in the file but im not entirely sure yet.

A friend of mine told me sometimes in files there could be data that is backwards I have a feeling that XR is really RX because the games main file .dll happens to be called RX.DLL

I have a feeling that file may be a little bit more complected then most because it has multiple different 3d models that doesn't belong to its original. Heres another that focuses on just one 3d model. Not exactly one 3d model but the whole truck but you catch my drift.
[http://www.2shared.com/file/ZHTvLQaP/TRUCK01.html](http://www.2shared.com/file/ZHTvLQaP/TRUCK01.html)?
## Post #7
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-29T17:52:02+00:00
- Post Title: Universal Century Gundam Online .DET

ACTUALLY I Had noticed a pattern with the Truck01.DET


I also had noticed that there is ALWAYS a number after all those y's

It would seem in the hex that y looking letter is F so in the picture on the very bottom  left you can see is says ff ff ff ff 09 and there is other patterns that are the same with a diffrent number at the end.
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-29T18:27:17+00:00
- Post Title: Universal Century Gundam Online .DET

lol your friend's right, I forgot it's little endian so non-strings are reversed. I just looked at the XR and though "hey a string XR".

Those FF's represent -1, or something else like padding.

Let's look at a different pattern. In particular, you're probably interested in being able to at least load up the model. Then the complicated stuff can come after (like re-importing, which probably won't happen until you have a pretty clear understanding of the entire file)

Go to the top of the truck file and then highlight all XR's (your editor should be able to do this).

Look at the 4th XR, skip the next 4 bytes (12 01 00 00), and you should see 20 98 00 00, which is equal to 38944 (little endian).

Skip 20 bytes (5 integers) so your cursor is at position 0x84 and then start selecting everything as you scroll down. Once you reach another XR, you'll notice that the selection size is very close to 38944

At this XR, skip the next 4 bytes (familiar? it's 12 01 00 00) and then you will find 80 2A 00 00, which is equal to 10880.
Again, skip 20 bytes again, and you should start at a section of floats.

Begin highlighting like before but this time aim to highlight only 10880. You'll find yourself near another XR, which again shows the same pattern as the previous two sections.

...

You should find that there are exactly 4 sections of floats, and then right after that you run into a bunch of indices (shorts). Not surprisingly, if you repeat the pattern you just did before, skipping 4 bytes (this time it's a 65 00 00 00), note the section size, skip another 20 bytes, and then begin highlighting stuff, you'll run into another XR a few bytes away from that number, which is also followed by 65 00 00 00?!

Three sections of indices, and then it starts to reference script data, shaders, lighting, etc.

If you repeat this process with another model, you will probably find the same thing.

It seems that the general outline of the format has been found.

btw, what program is this?
## Post #9
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-29T18:40:34+00:00
- Post Title: Universal Century Gundam Online .DET

you are very right brother. Anyway the program these files are associated to is Universal Century Gundam Online. The official server was shut down but since then a Private server has been created.

Personally my main goal is to not only create mods for this game such as new mobile suits and weapons but also be able to improve the visual quality as well.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-29T18:50:27+00:00
- Post Title: Universal Century Gundam Online .DET

[http://ucgoserver.com/forum-3/ucgo-disc ... e-and-you/](http://ucgoserver.com/forum-3/ucgo-discussion/det-file-and-you/)

They should know more, seeing how they've already gone far into the subject.
I don't suppose that's the p. server you're talking about? Lol
## Post #11
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-29T18:54:46+00:00
- Post Title: Universal Century Gundam Online .DET

> Reply from finale00
>
> http://ucgoserver.com/forum-3/ucgo-disc ... e-and-you/

They should know more, seeing how they've already gone far into the subject.
I don't suppose that's the p. server you're talking about? Lol
That was me who posted that and I was very wrong about the .det file. Supposedly there was a file format in the 80s and 90s called .DET, I learned the hard way that they are not associated.
The admin pretty much told me he wants to see if I can figure out the file format for myself which means he isn't going to tell me. Allot of people are hoping that this file gets reversed. Im doing my best seeing that I am the only person interested at the moment to get it done.
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-29T19:08:49+00:00
- Post Title: Universal Century Gundam Online .DET

lol he wants to see if you can figure it out, not you asking someone to figure it out for you and then presenting the results 

This sort of looks like a truck



I'm not sure if there are transformations involved cause those wheels look like they're in the wrong spot.

It uses a chunk-based fromat.

```

word meshType (2, 4)
word XR

#start chunk section
word unk
word XR
dword chunk
if chunk == 0x01
   skip 40 bytes
if chunk == 0x20
   skip 40 bytes
if chunk == 0x112
   #vertex
   dword numVerts * 32
   dword unk #(32)
   dword numVerts
   dword_3 unk #(0, 1, 1)
   
   struct vertex {
      float_3 vx, vy, vz
      float_5 (normals and UV)
   }
   dword unk
if chunk == 0x65
   dword numIndices * 6
   dword unk #(2)
   dword numIndices (numFaces = numIndices / 3)
   dword_3 unk #(0, 0, 1)
   struct face {
      word_3 indices
   }
   dword unk
if chunk == 0x0A
   #scriptdata

#more chunks

```
## Post #13
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-29T19:13:54+00:00
- Post Title: Universal Century Gundam Online .DET

yeah i know lol. Trust me im a person who never takes credit for other peoples work.

Anyway I really like what you have done for me so far, you seem allot more experienced at this type of stuff then I am.
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-29T19:20:38+00:00
- Post Title: Universal Century Gundam Online .DET

Wheels are definitely out of place.



I noted there are 4 vertex sections, but there are only 3 face sections.
That is strange.

At the very bottom, there are probably some transform matrices that will move the wheels to the correct spot, but then the wheels aren't separate objects o.O

EDIT:

I couldn't parse the first file you attached completely. Ran into some errors, so it looks like the format will need to be revised.



I have no idea why there are less face sections than vertex sections.
Someone else might have some clue.
## Post #15
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-29T19:25:29+00:00
- Post Title: Universal Century Gundam Online .DET

> Reply from finale00
>
> Wheels are definitely out of place.



I noted there are 4 vertex sections, but there are only 3 face sections.
That is strange.
im not sure but the game might be able to automatically relocate those wheels. I know a few other games do that but Im not 100% sure. The only way one would be able to tell is if the mesh was edited for one of those wheels and loaded up in the client to see if the wheel is still in the right place. Maybe the .DET file still holds this type of information in another spot.

One thing that has interested me is that the admin is able to move parts of the vehicles using the games xyz coordinates "which I dont know yet though I have samples" and he is also able to take parts from other .det files and replace stuff like heads, arms, ect.


Heres another file its an RX-78-2 Gundam. Id like to see what happens when its loaded up [http://www.2shared.com/file/H6icrXlu/RX ... UNDAM.html](http://www.2shared.com/file/H6icrXlu/RX78_02_GUNDAM.html)?
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-29T19:29:29+00:00
- Post Title: Re: Need help on this file format .DET

Well, there is the section at the end that appears to be referencing different parts of the model. 
They have chunk ID of 0, and it starts with "root", then you see things like "main body", "knuckle arm 1", "wheel front 1", "wheel front 2", "knuckle arm 2". Maybe this is a skeleton? And those indices represent the bone index (I don't know anything about bones since I've never done any modeling)
## Post #17
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-29T19:51:31+00:00
- Post Title: Re: Need help on this file format .DET

> Reply from finale00
>
> Well, there is the section at the end that appears to be referencing different parts of the model. 
They have chunk ID of 0, and it starts with "root", then you see things like "main body", "knuckle arm 1", "wheel front 1", "wheel front 2", "knuckle arm 2". Maybe this is a skeleton? And those indices represent the bone index (I don't know anything about bones since I've never done any modeling)
from what im thinking is all that information sends the location of where the mesh should be, obviously it copies and pastes the wheel and then the copied wheel acts differently on every side.

Im sorry for being vague BTW.

This information might not be able to be edited in 3ds im thinking that the 3d information is all separate meaning that in their original editor the wheel wasn't loaded with the body it was edited separately.

Im guessing if the wheels mesh was edited it would edit the mesh for every wheel the same and would still be in its proper place ingame.

Gimme 10 mins im gonna look over another file. The .det file is incomplete by itself there are other files that make it whole.
## Post #18
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-29T19:57:39+00:00
- Post Title: Re: Need help on this file format .DET

If such information was used and placed in the model file, then that's some really nice unknowns that I'll never figure out.

The gundam model you sent has 87 vertex sections but only 63 face sections.
I'm running into index errors while drawing the faces so that indicates I am storing the data incorrectly.

There doesn't seem to be any obvious ways to connect them.
Only 26 meshes were drawn out of however many there should be.

Currently I assume
face section 1 uses vertex section 1,
face section 2 uses vertex section 2, 
etc

and it produces recognizable models, but it's wrong.
## Post #19
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-29T20:02:38+00:00
- Post Title: Re: Need help on this file format .DET

yeah I was right. The game itself will relocate that model by itself meaning that both the trucks body and the wheel are ither separate files or are ment to be loaded that way together even know they are separate files.

Honestly we don't need to edit that type of information though what we only want to do is to be able to edit mesh.
We may need to figure out how the texture is wrapped on the object. New mesh = New textures.

Anyway you have done something in an hour that I have been trying to do for months I have to thank you. If by the end of the day im able to edit mesh for this game there will literally be a flood of thankyous... from me
## Post #20
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-29T20:06:26+00:00
- Post Title: Re: Need help on this file format .DET

Here's an observation I missed earlier:

at the end of every section, there is some odd integer.
I output it as follows, in the order they appear in the file.

truck:

```
15532712 0
15532816 1
15532972 2
15533076 3
15533180 4
15533284 5
15533388 6
15533492 7
15533596 8
15533700 9
15533804 10
15533960 11
15534168 12
15534376 13
15534480 14
15534636 15
15532504 16
15532660 17

#face section
15532764 0
15532868 1
15533024 2
15533128 3
15533232 4
15533544 5
15533648 6
15533752 7
15533856 8
15534012 9
15534220 10
15534428 11
15534532 12
15534688 13
15532556 14
26608248 15
```


Take a look at section 0 for vert and faces. The keys are:  (15532712, 15532764), with a difference of 52.
A lot of them also have corresponding differences of 52, except there's an outlier at the bottom.

Perhaps this is what it uses to link them together.
## Post #21
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-29T20:12:06+00:00
- Post Title: Re: Need help on this file format .DET

> Reply from finale00
>
> Here's an observation I missed earlier:

at the end of every section, there is some odd integer.
I output it as follows, in the order they appear in the file.

truck:
Code: Select all#vert section
15532712 0
15532816 1
15532972 2
15533076 3
15533180 4
15533284 5
15533388 6
15533492 7
15533596 8
15533700 9
15533804 10
15533960 11
15534168 12
15534376 13
15534480 14
15534636 15
15532504 16
15532660 17

#face section
15532764 0
15532868 1
15533024 2
15533128 3
15533232 4
15533544 5
15533648 6
15533752 7
15533856 8
15534012 9
15534220 10
15534428 11
15534532 12
15534688 13
15532556 14
26608248 15

Take a look at section 0 for vert and faces. The keys are:  (15532712, 15532764), with a difference of 52.
A lot of them also have corresponding differences of 52, except there's an outlier at the bottom.

Perhaps this is what it uses to link them together.

it could be possible that the data could be stored in another file that is what we suspect atleast given there is another file they tries to put them all together and it sometimes has sources to diffrent .det, here is ALL of the 3d files in that files section, I doubt it uses any other 3d files from other folders.

[http://www.2shared.com/file/BHe5hGPb/3_online.html](http://www.2shared.com/file/BHe5hGPb/3_online.html)?
## Post #22
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-29T20:16:24+00:00
- Post Title: Re: Need help on this file format .DET

I'm guessing those level of detail versions are just used for things like distance or depth? I only briefly read about what LOD's can be used for.

Anyways I took a look at the "base" model and the LOD models and they're all pretty much the same format so I would assume that a single det file at the very least stores all of the geometry and skeleton. Then other files can reference whatever is defined by name or maybe index.

Since I can't connect the faces and vertices section together (my previous theory failed), I'm stuck until some magical idea just pops up and I manage to find the trick behind it.
## Post #23
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-29T20:19:59+00:00
- Post Title: Re: Need help on this file format .DET

> Reply from finale00
>
> I'm guessing those level of detail versions are just used for things like distance or depth? I only briefly read about what LOD's can be used for.

Anyways I took a look at the "base" model and the LOD models and they're all pretty much the same format so I would assume that a single det file at the very least stores all of the geometry and skeleton. Then other files can reference whatever is defined by name or maybe index.

Since I can't connect the faces and vertices section together (my previous theory failed), I'm stuck until some magical idea just pops up and I manage to find the trick behind it.
its all rite take your time. ill see if I can find anything in the .det file that can tie them together. I believe some other people on a different forums had ran into the same problem but the only thing is they gave up too soon.
## Post #24
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-29T21:39:30+00:00
- Post Title: Re: Need help on this file format .DET

actually I think I know why there is more vertex then face sections. Look at the wireframe and see if there is any useless polys.
Here is an example if you dont know what vertex sections are 


basically there could be more polygons on the same plane that are racking up the vertex count.



this is what im hoping you mean. though those numbers don't match up to me so you may have to explain yourself a little better sorry.
What also could be messing with you is the fact that there is 4 materials and they might split the mesh if they were compiled that way meaning the glass is its own 3d file and the body is another 3d file just like the wheels are also their own 3d file.

There are 4 materials that are named in the file called
glass
userColor0
colored
luminous

I dont meed to sound like an idiot if this is not what you mean, I have never used the term "section" with 3d before.
## Post #25
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-29T21:50:42+00:00
- Post Title: Re: Need help on this file format .DET

By section I simply refer to a contiguous portion of the data. I use the term loosely and didn't know it was a technical term 

I mentioned that on the fourth XR, you read some vertex information, and then after that you see another and it could be some more vertex information. Since all of the vertex information is grouped together I would just call the entire portion of data the vertex "section". This way, I don't mention how the vertices are defined or how they are stored, just to let you know that the data you're looking from this offset to that offset is just a bunch of vertices.

Essentially, when I'm looking at the truck, I am getting 4 chunks of vertices (meaning, 4 XR's that are followed by vertex data), but then only 3 chunks of faces (meaning, 3 XR's followed by face data).
## Post #26
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-29T22:06:33+00:00
- Post Title: Re: Need help on this file format .DET

> Reply from finale00
>
> By section I simply refer to a contiguous portion of the data. I use the term loosely and didn't know it was a technical term 

I mentioned that on the fourth XR, you read some vertex information, and then after that you see another and it could be some more vertex information. Since all of the vertex information is grouped together I would just call the entire portion of data the vertex "section". This way, I don't mention how the vertices are defined or how they are stored, just to let you know that the data you're looking from this offset to that offset is just a bunch of vertices.

Essentially, when I'm looking at the truck, I am getting 4 chunks of vertices (meaning, 4 XR's that are followed by vertex data), but then only 3 chunks of faces (meaning, 3 XR's followed by face data).
yeah that pretty much sounds like they split the file per material. Are you able to tell which parts of the file are defined? that 4th chunk may be harder to figure out hence why its not loading properly?

Example is one section only the windows? if so that may confirm my theory.

It could be that one portion ISNT defined. I will check to see.
## Post #27
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-29T22:11:47+00:00
- Post Title: Re: Need help on this file format .DET

For the truck, based on vertChunk N corresponds to faceChunk N

object 0 is the main body except the wheels
object 1 are two of the wheels
object 2 is a third wheel (in between the two)

The last set of vertices is unused in this case and does not crash.
For the gundam, I crashed early on cause the faces were referencing vertex indices that don't exist. Of course, this is assuming it uses indexing.

So it may or may not be defined, but there is still something wrong with how I am parsing the data.

Here's an idea: try to ask the admin to post a generic file format outlining the structure of the DET file, without any explanations
## Post #28
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-29T22:18:41+00:00
- Post Title: Re: Need help on this file format .DET

OH I C ok I was thinking they separated the mesh per material. I had ran into that before. Check to see if any of the wheels are on top of each other, they may seem like one part when they are so close OR is the program you are using literally telling you that that part is missing? also ill see what I can do with that request.
## Post #29
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-29T22:56:39+00:00
- Post Title: Re: Need help on this file format .DET

> Check to see if any of the wheels are on top of each other, they may seem like one part when they are so close

Color-coded.
[truck.jpg](https://xentaxbackup.github.io/file/4554_truck.jpg)
## Post #30
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-29T23:17:39+00:00
- Post Title: Re: Need help on this file format .DET

I don't think were gonna receive any help. I can give you all the 3d files and maybe one of them will reveal something that's harder to understand then the files I presented so far if you think that will be of any help?
## Post #31
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-29T23:21:00+00:00
- Post Title: Re: Need help on this file format .DET

I DL'd the client. How do I decrypt/decompress the files?
## Post #32
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-29T23:22:28+00:00
- Post Title: Re: Need help on this file format .DET

> Reply from finale00
>
> I DL'd the client. How do I decrypt/decompress the files?
ill send a PM this is something I dont want many people to know
## Post #33
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-30T00:53:56+00:00
- Post Title: Re: Need help on this file format .DET

Ill post a bms script here soon i hate when people hide information for no reason its just zlib data with an index and main file based on name.
the info to unzip the file header is just at a fixed offset from the end of the file.
## Post #34
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-30T00:58:30+00:00
- Post Title: Re: Need help on this file format .DET

> Reply from chrrox
>
> Ill post a bms script here soon i hate when people hide information for no reason its just zlib data with an index and main file based on name.
the info to unzip the file header is just at a fixed offset from the end of the file. 
in the wrong hands it could be used to hack the game unfortunately. After realizing this I knew I couldn't share the information with just anyone. We are a small community looking to grow, that type of information could undoubtedly kill the game and I ever so much love playing UCGO.
## Post #35
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-30T01:03:30+00:00
- Post Title: Re: Need help on this file format .DET

if anyone has the skills to hack the game they have the skills to unpack the client
the only way your going to even remotely protect a game like this is with modifying the clinet to use some type of encryption.
## Post #36
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-07-30T01:04:19+00:00
- Post Title: Re: Need help on this file format .DET

yup hacking is impossible to avoid.. especially on a file hacking site lol
## Post #37
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-30T01:09:04+00:00
- Post Title: Re: Need help on this file format .DET

> Reply from chrrox
>
> if anyone has the skills to hack the game they have the skills to unpack the client
the only way your going to even remotely protect a game like this is with modifying the clinet to use some type of encryption.

hmm I guess I never thought about it that way. Good show.
## Post #38
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-30T15:19:02+00:00
- Post Title: Re: Need help on this file format .DET

I'm reading the thread on UCGO about blah11 talking about the DET format and he mentions that it's "several .obj files packed".
Since he's "completely figured it out", and he's not the admin, maybe he can share? Lol

Clearly I'm taking the easy way out by getting people that already know the stuff to release some more info rather than trying to figure it out on my own
## Post #39
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-30T16:34:18+00:00
- Post Title: Re: Need help on this file format .DET

Very easy format here you go

```
#by chrrox
#Universal Century Gundam Online (PC)
Open FDDE RFI 0
Open FDDE RFP 1

comtype inflate
goto -0x18
get zsize long
get size long
math zsize - 6
clog MEMORY_FILE2 2 ZSIZE SIZE

goto 0 MEMORY_FILE2
get files long MEMORY_FILE2

for i = 0 < files
get nsize long MEMORY_FILE2
math nsize * 2
getdstring uname nsize MEMORY_FILE2
set name unicode uname
get offset long MEMORY_FILE2
get offset2 long MEMORY_FILE2
math offset + offset2
math offset - 0x18
math offset2 + 2
goto offset 1
get zsize long 1
get size long 1
clog name offset2 zsize SIZE 1
next i

```
## Post #40
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-30T16:51:29+00:00
- Post Title: Re: Need help on this file format .DET

The one that I found on their forums says comtype unzip_dynamic for the RFI file and then zlib for the RFP file.

[http://ucgoserver.com/forum-3/ucgo-disc ... or/page-2/](http://ucgoserver.com/forum-3/ucgo-discussion/kampfer-rumor/page-2/)

If they wanted to make it private they wouldn't have left this as the first hit on google!

Is there any difference in the results? Although the approach is different, maybe it does the same thing.
## Post #41
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-30T16:53:36+00:00
- Post Title: Re: Need help on this file format .DET

no idea why they said that its incorrect information the correct compression is inflate this is true for all files.
## Post #42
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-30T19:11:51+00:00
- Post Title: Re: Need help on this file format .DET

Ok I found an archive posted on UCGO forums that provided the following file types:

RSB
TRF
XOBJ
MEF

and of course the corresponding DET, with normal + LOD versions.

The RSB file assigns references materials defined in the det file, so I know exactly which chunks are for the materials.
TRF file references a particular bone, and probably handles animations.

MEF file references several files in the same folder, so it's probably just used to tell the client what to load and whatnot.

No other files (unless the uploader decided to omit them), so it looks like DET files contain a good portion of whatever is needed.

PS: there are some outspoken individuals on the UCGO forums that mentions that the admin does not need any help and people should not waste their time trying to help cause they can't.
## Post #43
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-30T19:51:24+00:00
- Post Title: Re: Need help on this file format .DET

> Reply from finale00
>
> Ok I found an archive posted on UCGO forums that provided the following file types:

RSB
TRF
XOBJ
MEF

and of course the corresponding DET, with normal + LOD versions.

The RSB file assigns references materials defined in the det file, so I know exactly which chunks are for the materials.
TRF file references a particular bone, and probably handles animations.

MEF file references several files in the same folder, so it's probably just used to tell the client what to load and whatnot.

No other files (unless the uploader decided to omit them), so it looks like DET files contain a good portion of whatever is needed.

PS: there are some outspoken individuals on the UCGO forums that mentions that the admin does not need any help and people should not waste their time trying to help cause they can't.
ill tell you what they do so you can save some time,
of course .DET is the 3d file
RSB is the hue colors
xobj puts the 3d files together I would just ignore this file
MEF is basically everything that the MS is besides its stats. I messed with this file and I was able to turn a GML into a gundam ect.
Im not sure about TRF but I think it is the positions of where the jet flames are on the vehicles.
## Post #44
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-30T20:02:59+00:00
- Post Title: Re: Need help on this file format .DET

> Reply from Troopermanaic
>
> finale00 wrote:Ok I found an archive posted on UCGO forums that provided the following file types:

RSB
TRF
XOBJ
MEF

and of course the corresponding DET, with normal + LOD versions.

The RSB file assigns references materials defined in the det file, so I know exactly which chunks are for the materials.
TRF file references a particular bone, and probably handles animations.

MEF file references several files in the same folder, so it's probably just used to tell the client what to load and whatnot.

No other files (unless the uploader decided to omit them), so it looks like DET files contain a good portion of whatever is needed.

PS: there are some outspoken individuals on the UCGO forums that mentions that the admin does not need any help and people should not waste their time trying to help cause they can't.
ill tell you what they do so you can save some time,
of course .DET is the 3d file
RSB is the hue colors
xobj puts the 3d files together I would just ignore this file
MEF is basically everything that the MS is besides its stats. I messed with this file and I was able to turn a GML into a gundam ect.
Im not sure about TRF but I think it is the positions of where the jet flames are on the vehicles.



> Reply from finale00
>
> I'm reading the thread on UCGO about blah11 talking about the DET format and he mentions that it's "several .obj files packed".
Since he's "completely figured it out", and he's not the admin, maybe he can share? Lol

Clearly I'm taking the easy way out by getting people that already know the stuff to release some more info rather than trying to figure it out on my own

I am blah11 on the forums, its like I said earlier, I thought these .DET files were associated with the older .det files they used in the 80s and 90s but its not. Its a completely new format. Also this was before I was able to unpack the files so when I snooped around in the .DET files I saw things like .obj which lead me to believe there were object files in them. That may still be the case but I very much doubt it. I would just ignore that thread completely.
## Post #45
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-30T20:28:09+00:00
- Post Title: Re: Need help on this file format .DET

lol but someone was talking about you having written a model viewer in C++ and having "nice models"  

Oh well, now I'm wondering what the differences are between the bms script on UCGO and the one chrrox wrote.
## Post #46
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-30T21:19:22+00:00
- Post Title: Re: Universal Century Gundam Online .DET

im not really sure though I don't think the end result would be different.

Also they say I have nice models because I am an actual 3d modeler, check out some of my work
## Post #47
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-30T21:40:26+00:00
- Post Title: Re: Universal Century Gundam Online .DET

oh lol I thought they were referring to some model viewer you wrote for the det files.

That's really detailed. Can you animate it as well? 

Anyways I'm looking at the client and there are some DET files for "map" objects. Any clue on the compress there?
## Post #48
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-30T22:11:32+00:00
- Post Title: Re: Universal Century Gundam Online .DET

The contents of this post was deleted because of possible forum rules violation.
## Post #49
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-30T22:36:05+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from finale00
>
> oh lol I thought they were referring to some model viewer you wrote for the det files.

That's really detailed. Can you animate it as well? 

Anyways I'm looking at the client and there are some DET files for "map" objects. Any clue on the compress there?
as far as map files go they are completely different. I wouldn't be able to figure those out. Its a shame too they have vehicles that arent available such as the core booster.
## Post #50
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-30T23:11:27+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Found another pattern, and I can use it to parse the model correctly, but it's sort of hack-ish.

Basically, I mentioned there was some seemingly random number at the end of each chunk. Instead of interpreting it as a long, I interpreted as two shorts, and this was the result:

```
object[0] has 316 vertices (576, 238)
object[1] has 316 vertices (368, 238)
object[2] has 846 vertices (784, 238)
object[3] has 316 vertices (836, 238)
object[4] has 316 vertices (680, 238)
object[5] has 842 vertices (992, 238)
object[6] has 316 vertices (1044, 238)
object[7] has 316 vertices (888, 238)
object[8] has 841 vertices (1096, 238)
object[9] has 746 vertices (1356, 238)
object[10] has 5409 vertices (1200, 238)
object[11] has 9254 vertices (264, 238)
object[12] has 9235 vertices (524, 238)
###
object[0]'s max indexed vertex is 315 (628, 238)
object[1]'s max indexed vertex is 315 (420, 238)
object[2]'s max indexed vertex is 845 (732, 238)
object[3]'s max indexed vertex is 841 (940, 238)
object[4]'s max indexed vertex is 840 (1148, 238)
object[5]'s max indexed vertex is 745 (1408, 238)
object[6]'s max indexed vertex is 5408 (1252, 238)
object[7]'s max indexed vertex is 9253 (316, 238)
object[8]'s max indexed vertex is 9234 (536, 230)
```


Take a look at the last tuple of numbers.

The second element is always the same (except for the last face section).

The first element for corresponding chunks has an absolute difference of 52.
I refer to it as the "Key" just for sake of reference.

Object0: vert key: 576, face key: 628. Difference of 52
Object1: vert: 368, face: 420. Difference of 52
Object2: vert: 784, face: 732. Difference of 52
Object3: vert: 836, face: 940. Difference isn't 52.

But look at object5: vert key: 992, and object3's face key is 940, difference of 52.

If we read it in order from 0 to n - 1, then we can effectively skip the vertex chunks we don't need.
Object n just corresponds with the last vertex chunk.
## Post #51
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-31T00:37:02+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Well, I implemented the hack-ish method I described and processed the Magellan model...maybe correctly I don't know.



But it didn't work for the gundam you sent.

The keys don't match up as I had previously claimed, so perhaps that's not what it should be based on.

EDIT: just thought of another hack-ish method knowing that they should be parsed in the order that they appear, with some possible extra vert chunks. Use the max referenced index as the comparison value and create faces only when the max index == numVerts + 1

Here's the gundam, though transformations would probably still need to be applied. Or at least some method to...position the meshes properly.



"zaku tank"
## Post #52
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-31T01:01:57+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Looks like you are getting very close. As far as the model goes, you aren't gonna actually get things to load in their correct positions because from what I can see they just get relocated in game. The admin can relocate parts on the models without actually loading them up in 3ds.

From what I can see if any part of that mesh was modified it will still be in the same spot in game.
Just an idea but are you able to get just one object to load at a time instead of them all loading at the same time?
Beautiful work on that zaku tank BTW.
## Post #53
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-31T01:13:16+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Yes, you can store each mesh separately and then choose to output them as separate files.
Just group the corresponding vertex chunks with the face chunks and you're all set.

Some of the images I included the mesh list so you can see object[0], object[1], ... Those are all separate meshes.

Once the format has been formalized, it should be easier to write import scripts for any 3D software. Of course, all we have right now are vertices and faces; I just stop parsing the file once I reach a non-face chunk.

EDIT: gundam head (all other meshes hidden)
## Post #54
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-31T01:17:27+00:00
- Post Title: Re: Universal Century Gundam Online .DET

dude you are pouring gravy in my eyes right now. Awesome job and thanks for the hard work you are doing.
## Post #55
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-31T01:31:59+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Everything after makes no sense to me. I can't find any pattern without brute forcing it (ie: keep reading bytes until you see a huge number that marks the end of the chunk).

This applies to "script data" chunks, "shader" chunks, and whatever else after.
## Post #56
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-31T02:55:33+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from finale00
>
> Everything after makes no sense to me. I can't find any pattern without brute forcing it (ie: keep reading bytes until you see a huge number that marks the end of the chunk).

This applies to "script data" chunks, "shader" chunks, and whatever else after.
I guess that's not good. Hopefully you can find that pattern. I am curious and I hope this isnt the case but do you think some .DET files may be built differently?
## Post #57
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-31T03:12:31+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Some of the files start with 02. The majority start with 04. There is some slight differences there.
Other than that, the format is pretty much the same.

A bunch of script data, then a bunch of references to some shader files, and then some materials, and then what appears to be bones.
## Post #58
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-07-31T03:39:02+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from finale00
>
> Some of the files start with 02. The majority start with 04. There is some slight differences there.
Other than that, the format is pretty much the same.

A bunch of script data, then a bunch of references to some shader files, and then some materials, and then what appears to be bones.
that is something that really interests me, I been trying to add a cubemap to the files so they can have a shiny effect. If you notice the taxi is glossy but the MS are matte. I was trying to see if I could add that gloss effect to them.
## Post #59
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-08-01T12:32:26+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Wow!
I read the post with interest.
How to import .DET files into metasequoia?
## Post #60
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-01T14:16:10+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Parse the file and then write out the contents in MQO format.
Here's a Sanae plugin that I use.

> Reply from Troopermanaic
>
> 
that is something that really interests me, I been trying to add a cubemap to the files so they can have a shiny effect. If you notice the taxi is glossy but the MS are matte. I was trying to see if I could add that gloss effect to them.

I don't know much about material properties and hence don't know much about how or where they might be stored.
[UCGundamnOnline_det.7z](https://xentaxbackup.github.io/file/4563_UCGundamnOnline_det.7z)
## Post #61
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-08-01T15:11:51+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from finale00
>
> Parse the file and then write out the contents in MQO format.
Here's a Sanae plugin that I use.
Troopermanaic wrote:
that is something that really interests me, I been trying to add a cubemap to the files so they can have a shiny effect. If you notice the taxi is glossy but the MS are matte. I was trying to see if I could add that gloss effect to them.

I don't know much about material properties and hence don't know much about how or where they might be stored.

error messaged "Invalid syntax @ line 4".
"from .lib.ModelObject import Model3D"
## Post #62
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-08-01T15:20:44+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from finale00
>
> Parse the file and then write out the contents in MQO format.
Here's a Sanae plugin that I use.

I don't know much about material properties and hence don't know much about how or where they might be stored.

It may be a elementary question, how can I use UCGundamnOnline_det.py file?
## Post #63
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-01T16:08:59+00:00
- Post Title: Re: Universal Century Gundam Online .DET

oops, forgot about that

Download this [viewtopic.php?f=29&t=6932](http://forum.xentax.com/viewtopic.php?f=29&t=6932)

Put the .py file in the plugins folder
Run command line

Python Sanae.py <your .det file>

and it'll create an MQO file based on what I've figured out so far.
Someone should be able to easily make a blender importer script based on it (I haven't looked at blender at all)
## Post #64
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-08-01T16:36:21+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from finale00
>
> oops, forgot about that

Download this viewtopic.php?f=29&t=6932

Put the .py file in the plugins folder
Run command line

Python Sanae.py <your .det file>

and it'll create an MQO file based on what I've figured out so far.
Someone should be able to easily make a blender importer script based on it (I haven't looked at blender at all)
Is this correct?

```
Python Sanae.py MS05_OLDZAKU.DET
```

Sorry, I am as good as a beginner.
## Post #65
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-01T16:39:22+00:00
- Post Title: Re: Universal Century Gundam Online .DET

yes. you will also need python installed.
## Post #66
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-08-01T17:03:04+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from finale00
>
> yes. you will also need python installed.
I click *.bat file, but nothing happens
## Post #67
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-01T17:04:35+00:00
- Post Title: Re: Universal Century Gundam Online .DET

It should work if you drag and drop the file over the bat file.
## Post #68
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-08-01T17:16:29+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from finale00
>
> It should work if you drag and drop the file over the bat file.

Do you notice the mistake?
## Post #69
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-01T17:31:15+00:00
- Post Title: Re: Universal Century Gundam Online .DET

I don't know what the problem could be.
Try typing the command in command-line directly to see what the errors are.
## Post #70
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-08-01T18:06:37+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from finale00
>
> I don't know what the problem could be.
Try typing the command in command-line directly to see what the errors are.

Thank you for your thoughtfulness.
I will try again after rebooting
## Post #71
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-08-02T01:34:45+00:00
- Post Title: Re: Universal Century Gundam Online .DET

hmm Ill try this out later. It would seem you are trying to get the import to work? IDK I just read that pic above.
## Post #72
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-08-02T03:33:09+00:00
- Post Title: Re: Universal Century Gundam Online .DET

What version Sanae to install with Python?
## Post #73
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-08-02T11:03:21+00:00
- Post Title: Re: Universal Century Gundam Online .DET

I used several times, but nothing happens.
Do you notice the mistake?
## Post #74
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-02T13:18:18+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Works fine for me when I clicked on it. Parsed the sample.det file and output a gundam MQO. 

It is most likely some other issue you are having, like maybe environment variables or something (like maybe python is not on the search path).

> Reply from alon
>
> What version Sanae to install with Python?
I wrote it in python 2.6 and know that it works with 2.7.
Not sure if it works for 3.x though it should since I don't use any libraries beyond os.

Maybe some syntax has changed since 2.x, don't know.
## Post #75
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-08-02T15:36:06+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from finale00
>
> Works fine for me when I clicked on it. Parsed the sample.det file and output a gundam MQO. 

It is most likely some other issue you are having, like maybe environment variables or something (like maybe python is not on the search path).
alon wrote:What version Sanae to install with Python?
I wrote it in python 2.6 and know that it works with 2.7.
Not sure if it works for 3.x though it should since I don't use any libraries beyond os.

Maybe some syntax has changed since 2.x, don't know.
I wrote it in python ver.2.6.6.
## Post #76
- Username: Nexus Elite
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 16, 2011 1:36 am
- Post datetime: 2011-08-03T09:43:47+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from finale00
>
> Works fine for me when I clicked on it. Parsed the sample.det file and output a gundam MQO. 

It is most likely some other issue you are having, like maybe environment variables or something (like maybe python is not on the search path).
alon wrote:What version Sanae to install with Python?
I wrote it in python 2.6 and know that it works with 2.7.
Not sure if it works for 3.x though it should since I don't use any libraries beyond os.

Maybe some syntax has changed since 2.x, don't know.
I've tried the CMD and bat as well, nothing seem to respond, i have python 2.6 installed too.
## Post #77
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-08-03T14:38:32+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from finale00
>
> Works fine for me when I clicked on it. Parsed the sample.det file and output a gundam MQO. 

It is most likely some other issue you are having, like maybe environment variables or something (like maybe python is not on the search path).
alon wrote:What version Sanae to install with Python?
I wrote it in python 2.6 and know that it works with 2.7.
Not sure if it works for 3.x though it should since I don't use any libraries beyond os.

Maybe some syntax has changed since 2.x, don't know.

The Python 2.6 and Sanae 2011-08-02 seems OK. Maybe something else is wrong.
I tried again and again, but couldn't succeed.
## Post #78
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2011-08-03T17:06:12+00:00
- Post Title: Re: Universal Century Gundam Online .DET

When I click on a bat file nothing happens!, too.
## Post #79
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-03T22:00:59+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Typically you should have some idea how command-line works before trying to use a batch file.
Anyways it's just a small import/exporter to see whether the format is correct, not a complete work, so unless you plan to try to figure out more of the format it would just be a waste of time.
## Post #80
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-08-05T16:57:47+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Is that something that I should solve

I had two *.pyc files(__init__.pyc & UCGundamnOnline_det.pyc) but no mqo_parser.pyc & obj_parser.pyc.

Please forgive my poor English.
## Post #81
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-05T19:22:04+00:00
- Post Title: Re: Universal Century Gundam Online .DET

[viewtopic.php?f=29&t=6932](http://forum.xentax.com/viewtopic.php?f=29&t=6932)

Continue here for troubleshooting the program.
## Post #82
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-06T22:19:35+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Haven't tried to figure out anything after since I got the basic geometry, but I've verified the data I think are normals...look right (I don't know, I just assume if those normals appear nicely then it should be fine)
[beamrifle.jpg](https://xentaxbackup.github.io/file/4585_beamrifle.jpg)
## Post #83
- Username: alientech
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Apr 03, 2010 8:23 pm
- Post datetime: 2011-08-20T06:37:07+00:00
- Post Title: Re: Universal Century Gundam Online .DET

How can I convert det file to mqo?
I type "python sanae.py m10.det" in cmd, It display like this.

```
  File "sanae.py", line 156, in <module>
    engine.run()
  File "sanae.py", line 144, in run
    self.load_package_plugins(plugins)
  File "sanae.py", line 35, in load_package_plugins
    module = __import__(modname, fromlist = "dummy")
  File "D:\Python26\plugins\Illusion_xm.py", line 4, in <module>
    from .lib.ModelObject import Model3D
ImportError: No module named lib.ModelObject

```
## Post #84
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-20T12:10:19+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Sometimes it is required to type python, sometimes not.
I think it has something to do with environment variables, but am not sure.

All questions about Sanae 3D should go [viewtopic.php?f=29&t=6932](http://forum.xentax.com/viewtopic.php?f=29&t=6932)
## Post #85
- Username: alientech
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Apr 03, 2010 8:23 pm
- Post datetime: 2011-08-21T02:25:48+00:00
- Post Title: Re: Universal Century Gundam Online .DET

aright, now I can export it but it have a problems with pivot point. All pieces have set x,y,z=0. How can I solve this?
[8-21-2011 9-27-16 AM.png](https://xentaxbackup.github.io/file/4650_8-21-2011 9-27-16 AM.png)
## Post #86
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-21T03:01:47+00:00
- Post Title: Re: Universal Century Gundam Online .DET

I don't know anything about that.
Someone else will have to continue figuring out the rest of the format (although the admin of the private server already knows it completely but doesn't want to release information)

The script only parses the basic geometry after all.
## Post #87
- Username: Nexus Elite
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 16, 2011 1:36 am
- Post datetime: 2011-08-21T03:09:58+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Where would the DET files be for the mechs? can't seem to find them
## Post #88
- Username: Hitakashi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 21, 2011 1:59 pm
- Post datetime: 2011-08-21T06:29:00+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from finale00
>
> Haven't tried to figure out anything after since I got the basic geometry, but I've verified the data I think are normals...look right (I don't know, I just assume if those normals appear nicely then it should be fine)

Flip it (not moving the gun around, but flipping the body so the trigger is on the bottom) unless you know that lol. Is that how it would appear in game without any other files moving it?


> Reply from alientech
>
> aright, now I can export it but it have a problems with pivot point. All pieces have set x,y,z=0. How can I solve this?
Thats how it's made, something in the game sorts it all out and moves them.


> Reply from finale00
>
> I don't know anything about that.
Someone else will have to continue figuring out the rest of the format (although the admin of the private server already knows it completely but doesn't want to release information)

The script only parses the basic geometry after all.

I don't think he knows how to actually make a new MS with no problems, but he can take weapons, edit them and put them back.

> Reply from Nexus Elite
>
> Where would the DET files be for the mechs? can't seem to find them
Only a few people know how to unpack them, but someone else posted something to get them. (guy with the green name)
## Post #89
- Username: Nexus Elite
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 16, 2011 1:36 am
- Post datetime: 2011-08-22T00:51:58+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from Hitakashi
>
> finale00 wrote:
Nexus Elite wrote:Where would the DET files be for the mechs? can't seem to find them
Only a few people know how to unpack them, but someone else posted something to get them. (guy with the green name)
But which files is it to extract from it? not sure which archive would it be.
## Post #90
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-22T01:49:00+00:00
- Post Title: Re: Universal Century Gundam Online .DET

I don't remember which ones I unpacked them from, but you can just write a batch script to unpack everything and then look at the filenames. It should be easily identifiable from there, assuming you're familiar with the series.
## Post #91
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-09-06T06:50:53+00:00
- Post Title: Re: Universal Century Gundam Online .DET

sorry for bump I really dont want to see this get buried when you guys are so close to finishing it.

Anyway I decided that im willing to pay to get this completed so if anyone is interested in trying to figure out how to edit the file and do it successfully we can discuss payment which im sorry if this breaks forums rules I looked them over and hadn't noticed anything that doesn't say I cant do this.

There will be 3 things I will need to be done,
 one is edit the mesh and have the textures view properly ingame on the edited mesh
 two is being able to edit animations which is a totally different file but that im not worried about right now
 three is being able to edit whether or not something is ambient or not in the .det file
## Post #92
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2011-10-05T03:03:21+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Windows 7
Python25
Sanae 2011-08-28
set up my PC..


"python sanae.py sample.det" in cmd. 
When I click on a cmd file.. it display like this.

What do you think the trouble is?
## Post #93
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-10-08T01:29:38+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Try "sanae.py sample.det" normally without the python. I am not sure how environment variables work but one of them usually works.
## Post #94
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-04T14:55:22+00:00
- Post Title: Re: Universal Century Gundam Online .DET

I'm a total noob, I don't understand what I have to do?
## Post #95
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-04T15:17:25+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Blender script is very buggy don't bother using it.
## Post #96
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-04T16:31:55+00:00
- Post Title: Re: Universal Century Gundam Online .DET

So, how am i going to do this?
I'm an absolute beginner.
## Post #97
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-04-04T17:01:25+00:00
- Post Title: Re: Universal Century Gundam Online .DET

```
python Sanae.py sample.det
```
E:\Sanae\sampl.det
E:\Sanae\Sanae.py
E:\Sanae\plugins\UCGundamnOnline_det.py
After clicking cmd still nothing happens, still they don't work.
## Post #98
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-05T05:57:18+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> SyntaxError: invalid syntax
I'm a super mega ultra noob, lol
No matter what I tried, do not work.
## Post #99
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-05T05:58:48+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Maybe I will write a noesis plugin of whatever I had found when I have time, since python and command-line seem to be difficult to learn...
## Post #100
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-05T11:51:33+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Yes, please, if it's not too much trouble.
I'll be expecting your support.
## Post #101
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-04-05T12:16:39+00:00
- Post Title: Re: Universal Century Gundam Online .DET

You're already in the python commandline.
You need to start normal windows cmd and then type: python sanae.py sample.det

You might also need to add your path to sanae.py and sample.det to something like this:
c:\games\path\path\sanae.py
c:\games\path\path2\sample.det
## Post #102
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-05T12:44:08+00:00
- Post Title: Re: Universal Century Gundam Online .DET

SyntaxError: invalid syntax

It's the same, lol
pass like this:
## Post #103
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-04-05T12:52:12+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Because you're not listening, you're in the python command line. You need windows command.
## Post #104
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-05T13:02:50+00:00
- Post Title: Re: Universal Century Gundam Online .DET

I'm sorry to bother you, i don't know what you are talking about.
I'm a super mega ultra noob.
Could you give me some more details on that? any picture?
## Post #105
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-05T13:10:14+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Okay. 
Is that right, please?
## Post #106
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-04-05T13:22:26+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Yes, but it seems you're missing the python imaging library. Though iirc Finale said Sanae only used standard python libraries so you'll have to wait for him to elaborate.
## Post #107
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-05T13:28:09+00:00
- Post Title: Re: Universal Century Gundam Online .DET

A little change to the windows command line.
But, there is something amiss.
## Post #108
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-05T17:29:57+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from Demonsangel
>
> Yes, but it seems you're missing the python imaging library. Though iirc Finale said Sanae only used standard python libraries so you'll have to wait for him to elaborate.

Oh, I use the PIL library for the xx format export because I haven't written my own image import/exporters lol
I guess that isn't standard. Though, it's used exclusively for that particular plugin.

```
sanae.py -f mqo my_file
```


exports it as mqo, which does not require any sort of image processing.
## Post #109
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-06T01:14:54+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Thank you everybody for your support.
## Post #110
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-06T02:57:02+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Oops. Help me.
An error occurred while converting some det file to mqo.
## Post #111
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-04-06T04:37:06+00:00
- Post Title: Re: Universal Century Gundam Online .DET

I think there're problems my PC, still they don't work.
I can format the hard disk and reinstall Windows right now.
## Post #112
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-06T04:53:35+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from leyme
>
> 

Oops. Help me.
An error occurred while converting some det file to mqo.
This is the sample files.
http://www.mediafire.com/?85ojjudi9cgpbpk

I've looked at the format again and noticed I was doing something wrong before.

It is a chunk-based format, and each chunk has the form

```
dword chunktag (always the same)
dword chunkType

```


There are almost always more vertex sections than face sections, but you can match them up because the corresponding vertex chunkID = face chunkID - 52

Or at least, that seems to be able to load up all the models you provided.
## Post #113
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-06T05:58:34+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Thank you for replying so quickly.
Can I expect the next update?
## Post #114
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-06T06:02:24+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Ya, here's a noesis plugin with the revised format: [http://db.tt/zDtBcHGP](http://db.tt/zDtBcHGP)
I don't see any texture names though.

Maybe that other private server forum released some info? They seemed to be modding and adding all sorts of stuff the last time I went there.
## Post #115
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-06T06:20:20+00:00
- Post Title: Re: Universal Century Gundam Online .DET

This is a perfect script, all support.
Thanks for creating this awesome script.
## Post #116
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-06T06:34:33+00:00
- Post Title: Re: Universal Century Gundam Online .DET

It doesn't work for a bunch of files I downloaded from the beginning of the thread LOL

Looks like there are two versions...
## Post #117
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-06T15:07:31+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Roger that.
## Post #118
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-06T17:04:08+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Anyone how to decrypt/decompress the map DET's?
The ones in the OBJECT folder.

Anyways there sort of seems to be some matrices at the bottom of the file, but I can't get past those "script data" chunks.

I've updated the script to load those other models that had some extra data at the top, but then I found some models that have different vertex structs (36, 40, 44, 48 bytes). And fortunately, the chunkID's are also different.

I think that's pretty much where I got before lol
## Post #119
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-06T18:03:58+00:00
- Post Title: Re: Universal Century Gundam Online .DET

I found the information on a retrieval page on the Internet.
What is this?

```
2	//  File:     Crypto.java - Combined Functions for UCGO Crytpography
3	//            Note: Make sure Header is correct (namely XORSize is in place)
4	//
5	//  Author:   Eric "Xenozephyr" Dyoniziak
6	//  Licensees: (write names here)
7	//
8	//  Date:     June 24rd, 2007
9	//
10	//  Copyright(C) 2007
11	//  This source code is property of the above author and licensees, and may not
12	//   be edited, distributed, or compiled without their written permission.
13	//  This copyright notice must remain in its original form and may not be
14	//   edited or removed, regardless if permission to compile, edit, or
15	//   distribute this source code was given.
16	//  This intellectual property is protected internationally by the
17	//   World Intellectual Property Organization (WIPO) Copyright Treaty
18	//   and locally by the Digital Millennium Copyright Act (DMCA). Violation
19	//   may result in legal actions taken by the author and/or licensees.
20	//  This source code is distributed in the hope that it will be useful, but
21	//   WITHOUT ANY WARRANTY; without even the implied warranty of
22	//   MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
23	
24	package UCGOCrypto;
25	import java.util.Random;
26	public class Crypto
27	{
28	    private Blowfish blowfish;
29	    private XORMask xormask;
30	    private Random rand;
31	
32	    private int byteArrayToInt(byte[] buf, int ofs)
33	    {
34	        return (buf[ofs+3]<<24) | ((buf[ofs+2] & 0x0ff)<<16) | ((buf[ofs+1] & 0x0ff)<<8) | ( buf[ofs] & 0x0ff);
35	    }
36	
37	    private void intToByteArray(int value,byte[] buf,int ofs)
38	    {
39	        buf[ofs+3] = (byte)((value >>> 24) & 0x0ff);
40	        buf[ofs+2] = (byte)((value >>> 16) & 0x0ff);
41	        buf[ofs+1] = (byte)((value >>>  8) & 0x0ff);
42	        buf[ofs] = (byte)  value;
43	    }
44	
45	    public Crypto()
46	    {
47	        blowfish = new Blowfish("chrTCPPassword");
48	        xormask = new XORMask();
49	        rand = new Random(System.currentTimeMillis());
50	    }
51	
52	    public void Encrypt(byte[] data, int length)
53	    {
54	        short randVal = (short)(rand.nextInt(65536) & 0x0FFFF);
55	        int KEY = xormask.Keygen(randVal);
56	        int XORSize = byteArrayToInt(data,16);
57	        xormask.Encrypt(data,64+XORSize,KEY);
58	        KEY = randVal & 0x0FFFF;
59	        intToByteArray(KEY,data,4);
60	        blowfish.Encrypt(data,length);
61	    }
62	
63	    public void Decrypt(byte[] data, int length)
64	    {
65	        //EDIT: Sjekk at dataene vi mottar er minst 64 byte, minste størrelse for en UCGO pakke.
66	        if ( data.length < 64 ) return; //Ugyldige data mottatt, ignorer.
67	        blowfish.Decrypt(data,length);
68	        short randVal = (short)(((data[5] & 0x0ff) << 8) | (data[4] & 0x0ff));
69	        int KEY = xormask.Keygen(randVal);
70	        int XORSize = byteArrayToInt(data,16);
71	        XORSize ^= KEY;
72	        //EDIT: Sjekk at XORSize + headersize ikke går utenfor byte arrayet. For å unngå OutOfBounds exception.
73	        if ( (XORSize+64) > data.length ) return; //Ugyldige data mottatt, ignorer.
74	        xormask.Decrypt(data,64+XORSize,KEY);
75	        KEY = (KEY >>> 16) & 0x0FFFF;
76	        intToByteArray(KEY,data,4);
77	    }
78	}
```

[http://trac.assembla.com/solarone/changeset/8](http://trac.assembla.com/solarone/changeset/8) 
I hope that this has been helpful to you
## Post #120
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-06T18:54:55+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Ugh lol if you look around you'll see lots of code. I wonder if that blowfish algorithm is just the common one used everywhere.
Maybe someone already wrote a stand-alone tool for decrypting them.
## Post #121
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-07T05:21:37+00:00
- Post Title: Re: Universal Century Gundam Online .DET

If someone has already been used, that it is a soluble problem.
## Post #122
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-07T17:45:17+00:00
- Post Title: Re: Universal Century Gundam Online .DET

I settled the problems.
The answer was staring us in the face. 

[viewtopic.php?p=29676#p29676](http://forum.xentax.com/viewtopic.php?p=29676#p29676)

> Reply from Rheini
>
> Well all indications point to zlib, don't they?
Though that 78 5E is quite uncommon.

78 01 - No Compression/low 
78 9C - Default Compression 
78 DA - Best Compression
[viewtopic.php?p=29708#p29708](http://forum.xentax.com/viewtopic.php?p=29708#p29708)

> Reply from fatduck
>
> They are zlib compression! I can uncompress them manually!
Try offzip should work!

```
C:\offzip.exe -a C:\name.det C:\unpack 0x0
```
## Post #123
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-04-08T08:57:36+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Holey cow this thread was revived, ill be watching.. Hoping... waiting =]
## Post #124
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-08T15:27:28+00:00
- Post Title: Re: Universal Century Gundam Online .DET

I would've thought your admin would have provided at least some information by now.

> Reply from leyme
>
> I settled the problems.
The answer was staring us in the face.

Nice, there were go lol
There are 8 integers at the end of the file, where the 3rd is the compressed size and the 4th is the uncompressed size.

```
#UC Gundam Online .DET decompress

get FLAG short
get NAME FILENAME
if FLAG = 0xDA78
	goto -32
	get unk long
	get unk long
	get ZSIZE long
	get SIZE long
	clog NAME 0 ZSIZE SIZE
else
	print "Not compressed"
	cleanexit
endif

```


Too bad I can't load them cause I'm not getting the format right.
## Post #125
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-04-08T22:36:23+00:00
- Post Title: Re: Universal Century Gundam Online .DET

I had just noticed that you are trying to get to the map files, they are compressed because  they are easy to get to but I have a hunch because of that they might not be encrypted like the ones in the .RFI and .RFP files.
## Post #126
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-08T22:59:58+00:00
- Post Title: Re: Universal Century Gundam Online .DET

leyme figured out the compression and the script I threw together decompresses them with the name retained (well, just output with a specified name lol).
It is the same format as the other det files; I just don't know how to parse each chunk properly.
## Post #127
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-09T15:00:19+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Help me~
UCGundamnOnline_det.py
Is it just me, after exporting model as mqo, the UVs are lost.
And, i checked fmt_UCGundamOnline_det.py. Everything's O.K.
## Post #128
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-04-10T05:19:29+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Thanks all. 
I think I'm finally succeeding in converting det to mqo.
But there definitely is missing UV data, too.
I used [this script](http://www.mediafire.com/?zbdy6bt87pjyu38).
Please fix the problem of missing UV.
## Post #129
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-10T06:14:50+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Not sure how you figure the UV is missing. I don't even assign materials.
## Post #130
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-04-10T07:11:15+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Oh, i have completely mistaken about this.
## Post #131
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-04-10T08:19:31+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from finale00
>
> Not sure how you figure the UV is missing. I don't even assign materials.

Look here.
They are perfectly suited.
I used [fmt_UCGundamOnline_det.py](http://dl.dropbox.com/u/23043573/Noesis/fmt_UCGundamOnline_det.py) script for this.
Well, Thanks for sharing this great Script.
## Post #132
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-04-14T04:14:56+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from finale00
>
> I would've thought your admin would have provided at least some information by now.
leyme wrote:I settled the problems.
The answer was staring us in the face. 


Nice, there were go lol
There are 8 integers at the end of the file, where the 3rd is the compressed size and the 4th is the uncompressed size.
Code: Select all
#UC Gundam Online .DET decompress

get FLAG short
get NAME FILENAME
if FLAG = 0xDA78
	goto -32
	get unk long
	get unk long
	get ZSIZE long
	get SIZE long
	clog NAME 0 ZSIZE SIZE
else
	print "Not compressed"
	cleanexit
endif


Too bad I can't load them cause I'm not getting the format right.
I know this may be a bit off topic but im wondering if you can help with this, basically I have some .DET files from prototype and beta UCGO and they are kinda different then the .DET files we have now, here is one that was decompiled with your script. Do you think you can parse it like current .DET files?

[http://www.2shared.com/file/A0DdB-LM/RA ... ZOOKA.html](http://www.2shared.com/file/A0DdB-LM/RAKETEN_BAZOOKA.html)
## Post #133
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-14T04:23:39+00:00
- Post Title: Re: Universal Century Gundam Online .DET

It is a different format but it is easier than the chunk-based ones.
Are these available in the setup file from UCGO p-server website?

Judging from the tags, it looks like this was an older version and they decided to build on it.
## Post #134
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-04-14T04:28:23+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from finale00
>
> It is a different format but it is easier than the chunk-based ones.
Are these available in the setup file from UCGO p-server website?
no they arent available for public use, these are much much older files, only I and a few other people left in the world have these files. Unfortunately my method for file replacement in UCGO doesn't work with these older file formats.

That file I have you, the Raketen bazooka is a weapon we dont have in the current version of UCGO. We really want to implement it.

if you are really interested I can give you more files if you think it will help with overall reverse engineering.
## Post #135
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-14T04:30:19+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Send them to tsukihimex[at]gmail.com
I can parse out the general structure; it is almost like the ver3 and ver4 exception they don't have the XR's and stuff.

In fact the structures are pretty much the same.
Only thing it doesn't seem to have are those dumb SCRIPTDATA sections.
## Post #136
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-04-14T04:32:09+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from finale00
>
> Send them to tsukihimex[at]gmail.com
I can parse out the general structure; it is almost like the ver3 and ver4 exception they don't have the XR's and stuff...
I will do you one better, since you are helping out with all this I will give you the entire beta versions of UCGO. I only ask that you please dont share the files with anyone. The code you create you can of course.
## Post #137
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-14T05:11:43+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Hardcoded start offset for now.



I don't know if you guys can just export the mesh and somehow construct your own det file out of it.
The admin probably can though.
## Post #138
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-04-14T05:22:46+00:00
- Post Title: Re: Universal Century Gundam Online .DET

I don't mean to impose but the community im part of is basically going nuts right now, do you mind if you can show these files as well for the moment, BTW the older files are uploading.

[http://www.2shared.com/file/vE0LYNE8/DET.html](http://www.2shared.com/file/vE0LYNE8/DET.html)

THANKS BTW, our dream of modding this game is coming true.
## Post #139
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-14T05:32:20+00:00
- Post Title: Re: Universal Century Gundam Online .DET

k from the samples there, we can see that there are at least 4 versions of the det format.
1 and 2 are similar, as are 3 and 4. The first two I can actually get to the material section, so some textures and related data files to match material with texture would be nice.

But I don't get it, I thought the admin already figured out all this stuff and was already doing whatever he wants to the server?
Last time I asked for info he was like "no figure out yourself"

I doubt you will be able to mod with only the mesh structure.
The chunk tags seem absolutely random to me, the script data section makes no sense to me, and I'm basically hacking together whatever I can just to get it to render something. Someone will have to write a tool specific for parsing a det file to save all of these chunk ID's and write them back out...

Btw, which file specifies the transformation of each mesh? (which isn't useful cause I don't even have mesh names yet)
## Post #140
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-04-14T06:01:57+00:00
- Post Title: Re: Universal Century Gundam Online .DET

with current UCGO

Each part of the mesh in the .DET "raw 3d file" is exactly centered wherever the pivot point of each mesh is, the mesh is transformed by the .AET files which is basically the animation files UCGO uses.
If you look at the bottom of the file you will notice works like, heel_L which means left heel. These are the names for the parts. I am not entirely sure if the skeleton comes first or second on the list, there are also parts with the same name that have shape at the end of their names I think that is the names and the ones without shape are the skeletons.

Script data confuses me too but I kinda know the meaning behind it, just above script data sometimes there will be shader information depending whether or not the mesh has a cube map or some other thing like water shader effects, below script data is material data, there are different materials on all the parts because originally the devs wanted to be able to customize the color schemes of the MS.

.DET 3d file format
.AET animations
.RSB, color code information for the materials
.MEF puts the files together. Hard point information is stored here aswell like where a gun will be located when used.
.TRF, not completly sure about this file but im almost certain its used when you jump in a MS and use the rocket boosters, it may pinpoint where these boosters are and when they are used.
.Xobj, puts the .DET and lods together.
Textures are located in TEX00##.RFI/RFP in TEXTURE folder
Hope that cleared some things up.

BTW check your email I have sent you a message.

The admin didnt figure out everything with the .DET files, basically he only takes a part from the mesh and replaces another, if he tries to take the mesh out of the file and into another its gets all screwy. The mesh data is basically located in the beginning of the file and continues until just before scriptdata.

From what I was told he uses a hex calculator to figure out how and where to replace mesh and its done manually, not very practical and from what I hear it doesn't work well, would much rather have an easier and more effective way to do this which of course would be figureing out the .DET file out completely.

Here is some samples of .AET files, they would be useful in figuring out the names.
[http://www.2shared.com/file/rmvF0_88/Hu ... ation.html](http://www.2shared.com/file/rmvF0_88/Human_animation.html)
## Post #141
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-14T06:32:41+00:00
- Post Title: Re: Universal Century Gundam Online .DET

I've updated the script to load ver 1 and 2 models.
It can also load the map files also, though they also look kind of stupid...
## Post #142
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-04-14T08:00:35+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Read the rules about not linking to files from games at this forum. These files may be protected by law. Find your own means of discussing them without implicating Xentax.
## Post #143
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-14T13:40:57+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Great thanks for perfect update!!!!!!!!
## Post #144
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-04-14T17:39:58+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from Mr.Mouse
>
> Read the rules about not linking to files from games at this forum. These files may be protected by law. Find your own means of discussing them without implicating Xentax.
These files are not protected by law and are legal to have. Reverse engineering of .DET will be public released as promised by the forum rules.
## Post #145
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-14T18:36:04+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Wow there must be something wrong with my decompress script but the ones for prototype UC have a different header..................

The formats look inconsistent.
The ver 2 format has all those XR's, whereas another ver 2 format didn't.
## Post #146
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-04-15T00:55:20+00:00
- Post Title: Re: Universal Century Gundam Online .DET

yeah its just a cluster, were really not too much interested in the older files, we just hope it helps make understanding the newer .DETs easier.
## Post #147
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-15T01:20:00+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Why are the files not protected by law? Did you guys get their permission? Last I checked gundam is not only a registered trademark but for abandonware the person or company maintains copyrights (they just become less likely to sue). And in this case the company still exists. Not that I care any...  I'm just a little curious. I think a link purging is going to happen pretty soon anyways.
## Post #148
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-15T02:17:33+00:00
- Post Title: Re: Universal Century Gundam Online .DET

> Reply from Troopermanaic
>
> yeah its just a cluster, were really not too much interested in the older files, we just hope it helps make understanding the newer .DETs easier.
It's your logic. I have my own logic.
UCGO is protected by copyright.
Copyright belongs to the B A N D A I(バンダイナムコゲームス)
## Post #149
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-15T02:31:43+00:00
- Post Title: Re: Universal Century Gundam Online .DET

Not bandai. Some other company made the game, I forget who. But the point is Google booted us from their ads for having dead, I repeat, DEAD and LONG DEAD, links to rapidshare for samples to a game three or so years old lol. They didn't even bother checking the links to see if any game data was there. It's to distance ourselves from these filesharing websites.
## Post #150
- Username: shadow1221
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 24, 2019 8:01 pm
- Post datetime: 2019-07-31T15:35:32+00:00
- Post Title: Re: Universal Century Gundam Online .DET

game is dead again,some one has some tool or code stuff?
i need them to revive the game
