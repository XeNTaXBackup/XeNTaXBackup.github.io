## Post #1
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2012-02-10T19:02:07+00:00
- Post Title: God of War 1, PS2, WAD files

Does anybody have information on these files?

I'm playing around with speedrunning the game, and would like to see the layout of some of the levels.  I've managed to extract the files from both layers of the disk, and locate what I believe to be the WADs that I care about, but haven't made much more sense of it than that yet.  A discussion at [viewtopic.php?f=16&t=4735&hilit=God+of+War](http://forum.xentax.com/viewtopic.php?f=16&t=4735&hilit=God+of+War) leads me to believe that most of the work has already been done, but there's not much explanation there.

Any information on how to recreate what's shown in those screenshots would be appreciated.

Thanks.
## Post #2
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2012-02-14T16:11:56+00:00
- Post Title: God of War 1, PS2, WAD files

As an update, it looks like the following link has some promising information.

[http://ps23dformat.wikispaces.com/messa ... I/44926366](http://ps23dformat.wikispaces.com/message/view/God+of+War+II/44926366)

I'll be trying it out in the next day or two, and will report back on the off-chance anybody finds it useful / informative.

Edit:  Using Cheat Engine, I can't seem to get it to search the data file without attaching to a process first.  Would he be referring to an old version?  Anybody know what my problem is?  Or can recommend an alternate hex editor that would do what's needed?  The one I use doesn't handle wildcards very well.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T14:30:37+00:00
- Post Title: God of War 1, PS2, WAD files

Do you have the wad files? Can you upload some?  I just use a regular hex editor like 010 editor or hxd.
## Post #4
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2012-02-15T15:14:37+00:00
- Post Title: God of War 1, PS2, WAD files

I'm new to the forums, so a quick etiquette question first... Should I upload the WAD directly to the forum itself, or upload it somewhere else and discuss its location through PMs?

I was using FRHed, but have switched to Tiny Hexer.  It can at least search with wildcards, though it doesn't seem to have the "select all between searchpoints" functionality that Cheat Engine is described as having in the previous link's instructions.

Thanks.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T15:20:50+00:00
- Post Title: God of War 1, PS2, WAD files

I don't think there are any preferences for that.

But the attachments are limited to 256 KB so you're probably going to end up using an external filehost anyways.

I would prefer

mediafire
dropbox
windows skydrive

Since those are probably not going to die out anytime soon and should be decently fast for most people around the world.

For the methods that the guys at ps23D use, I am not too sure about it because they use some sort of word document and copy things here and there. I think they just copy all of the vertex coords?
## Post #6
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2012-02-15T16:06:18+00:00
- Post Title: God of War 1, PS2, WAD files

I've installed Dropbox and have a WAD up.  How do I share with you?
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T17:13:26+00:00
- Post Title: God of War 1, PS2, WAD files

Just put it in public folder and post the public dl link.
## Post #8
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2012-02-15T17:24:12+00:00
- Post Title: God of War 1, PS2, WAD files

[http://dl.dropbox.com/u/62428937/ATHN02D.WAD](http://dl.dropbox.com/u/62428937/ATHN02D.WAD)
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T18:39:04+00:00
- Post Title: God of War 1, PS2, WAD files

I have never used cheat engine but that function sounds useful.

I use 010 editor and it supports wild card searches. Trial version is free and you get it for 30 days. Full version is like US$50 or something but I think it's worth it.
It shows you all of the search results in a table so you can quickly jump to different results. 

It supports selecting by range, but you will have to manually specify the addresses (which isn't an issue if you already have all of the search results)
Anyways pack a couple more WAD's and upload them. Preferably some smaller ones cause this is pretty big.

I took a quick skim through the WAD you uploaded and the WAD format has a really nice structure to it.
It is token-based, so you can write a grammar for the structure and just parse it like that.

For example, if you read a token 0x28, you know there's going to be the start of a group struct.
If you read a token 0x32, then you know it's the end of the group.

You can build a tree structure from this, where each node represents one of the tokenized chunks, and parent/child relationships are defined by the beginning of a group (add a child node) and ending of a group (end of node, return to parent).

There are probably other more efficient ways to parse it as well, but all I can think of is a tree.

```

groupStart
   groupStart
      ...
      ...
      groupStart
         ...
      groupEnd
      groupStart
         ...
      groupEnd
   groupEnd
groupEnd

```


Like, why not just use braces or something lol

Which probably isn't important to you though since you can use their method to extract models and apply textures.
## Post #10
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2012-02-15T19:04:10+00:00
- Post Title: God of War 1, PS2, WAD files

[http://dl.dropbox.com/u/62428937/ATHN01EE.WAD](http://dl.dropbox.com/u/62428937/ATHN01EE.WAD)
[http://dl.dropbox.com/u/62428937/ATHN04D.WAD](http://dl.dropbox.com/u/62428937/ATHN04D.WAD)
[http://dl.dropbox.com/u/62428937/R_WPN2_1.WAD](http://dl.dropbox.com/u/62428937/R_WPN2_1.WAD)

ATHN04D is about 66% of the size of the first one, and ATHN01EE is only 200ish kb.  r_wpn2_1 is 145kb.

Let me know if you'd like more, or a better variety of WAD types.  The level layout is what interests me the most so that's what the ATHN*.WADs should be.  The R_WPN2_1.WAD would, I assume, be the model and textures of a single weapon.

Thanks.
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T20:50:26+00:00
- Post Title: God of War 1, PS2, WAD files

This is god of war 1 or 2?
## Post #12
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2012-02-15T21:06:16+00:00
- Post Title: God of War 1, PS2, WAD files

God of War 1.

My links to PS23DFormat Wiki were to GoW2, as that was all the information I could find and the file structure seems to be very similar.
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T21:07:57+00:00
- Post Title: God of War 1, PS2, WAD files

I wouldn't be surprised if it were.
But now I'm just looking for the vertices 

Wish I had a tool that calculated half-floats on the fly as well.
## Post #14
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2012-02-15T21:13:55+00:00
- Post Title: God of War 1, PS2, WAD files

[http://ps23dformat.wikispaces.com/God+of+War+II](http://ps23dformat.wikispaces.com/God+of+War+II)

I was able to find the submeshes as discussed at the bottom of that page, but I was unable to do anything with them.  I'm also not sure if that's what you're looking for.
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T21:16:55+00:00
- Post Title: God of War 1, PS2, WAD files

I typically start by looking for the vertices. If I can verify that, then I can look around and quickly calculate values like vert count, find where they are, and then combine that with a general skim through the format, have an idea of the structure of the format.

But so far I couldn't even find that. I can see the MDL's and the MAT's but don't know where the vertices start or end.
Like it says it starts with a particular hex sequence, but I didn't get any results (for something simple like 03 01 00 01)

But of course this is the format for the 2nd game...

EDIT: nvm I was looking at the weapon file and it didn't have those specific bytes. I guess they only cared about a specific model.
## Post #16
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2012-02-15T21:31:18+00:00
- Post Title: Re: God of War 1, PS2, WAD files

I did find those sequences in the other WAD files, which I assume you've discovered by now.
## Post #17
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2012-02-16T18:35:52+00:00
- Post Title: Re: God of War 1, PS2, WAD files

Is it possible, using the following information, to load a submesh into Blender?  Forgive my lack of practical knowledge here.

> The largest section of the models is the the vertex information section which contains submeshes with the following format:
>
> 
>
> 03 01 00 01 01 80 XX 65
>
> Unknown amount of an unknown section of 8byteArrays
>
> (03) 80 XX 6D
>
> 2BytesignedintegerVertexes(X,Y,Z)+2byteCONN
>
> (02) C0 (51) 6E
>
> 1byteColorMapping+1byteINFO
>
> 01 01 00 01 00 80 01 6C XX 80
>
> (ZeroPadding)
>
> 4ByteFloatVar1, 4ByteFloatVar2, 4ByteFloatVar3, 4ByteFloatVar4
>
> ?? (00 00) (14)

So, say I take the contents between "03 80 XX 6D" and "02 C0 51 6E" and paste them into a file.  That should give me a file containing nothing but 2 Byte Signed vertices.  Is that information alone of any use?  Can it be converted somehow to something Blender will open?

Do the vertices contain any information on how they link together, or will that just give me a bunch of points floating in space?

Also, are the submeshes of any use?  Or will that just give me the detail of tiny parts of things, again with no idea how they form the larger picture?
## Post #18
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-16T18:45:45+00:00
- Post Title: Re: God of War 1, PS2, WAD files

I've never used their method to do things, but if you read the "how to extract meshes" article I think it gives you a general step-by-step guide to do things.

These specific game articles just describe where you might find the info.

You're feeding in vertex info, which are just the points, but I think the tool they use somehow creates the faces for them automatically. It seems rather long and tedious (and full of trial and error), but maybe it works? It looks like people are satisfied with it.

I mean, I was reading another topic about PS2 formats and they may have all sorts of hardware-related instructions (VIF tags?) that do all sorts of magic with the data, so maybe just feeding in vertex data is good enough.

Also since it's a submesh, ya, you might only get one part.
## Post #19
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2012-02-16T20:28:11+00:00
- Post Title: Re: God of War 1, PS2, WAD files

Following through his instructions (with liberal leaps of faith where reality deviated....) I now have a shell.mesh.xml file.

Is the ogre_import.py something that you're familiar with?  I can't get Blender to see it and add .XML under File-> Import.
## Post #20
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-16T20:49:12+00:00
- Post Title: Re: God of War 1, PS2, WAD files

Nope. Maybe you have to use the ogre utility on the xml, and then import. Some ogre utility mentioned in the guide anyways
## Post #21
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2012-02-16T20:52:21+00:00
- Post Title: Re: God of War 1, PS2, WAD files

I sort of figured it out, but the resulting view exploded my brain.  I'll give it another try later on.

Were you able to get anything useful out?
## Post #22
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-16T20:56:17+00:00
- Post Title: Re: God of War 1, PS2, WAD files

Nope. I used the guide to seek to the specific offsets but couldn't get anything. Their tool might be doing something special. Actually, upload the raw .mesh file, I've written a parser for the ogre binary mesh format already.
## Post #23
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2012-02-16T21:26:49+00:00
- Post Title: Re: God of War 1, PS2, WAD files

[http://dl.dropbox.com/u/62428937/shell.mesh](http://dl.dropbox.com/u/62428937/shell.mesh)

There are many, many places I could have screwed this up.....
## Post #24
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-16T21:40:57+00:00
- Post Title: Re: God of War 1, PS2, WAD files

Probably. I'm surprised such a technique is actually reliable to some extent, considering the results and how many PS2 models they can rip like that.
Though, manual work is always error-prone, and yes, realizing that there are so many steps involved only increases the chances of messing up somewhere along the line.

Anyways here's the ogre3D .mesh script I wrote for Noesis.

[http://db.tt/N6RrUJGR](http://db.tt/N6RrUJGR)

You can use this to load valid ogre3D .mesh files and see whether the vertices make sense (you still have to manually copy stuff, but it should save you some steps). Right now I see a huge mess lol

I've defaulted it to plot only the vertices so that you can check whether it makes any sense or not.

Faces can be rendered by going to the build_mesh method and uncommenting the rapi.rpgCommitTriangles function call.
## Post #25
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2012-02-17T05:13:06+00:00
- Post Title: Re: God of War 1, PS2, WAD files

Thanks.  The script lets me know that I've failed quicker than the other way =]
## Post #26
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2012-02-17T15:17:57+00:00
- Post Title: Re: God of War 1, PS2, WAD files

Question about the mesh format, and the ps23dformat wiki instructions...

> ?? ?? ?? ?? ?? ?? ?? 80 ^l?? ?? ?? ?? ?? ?? ?? 80 ^l
>
> 
>
> 00 00 00 00 00 00 00 00 ^l^&
That's saying that anything that's got 80 in any 2 consecutive 8 or F positions, prepend 8 bytes of 0s to it.  Looking through the file, it appears to have a bunch of vertices, then a batch of 10 or so of the above that mostly seem to repeat themselves, then back to vertices.  What would those chunks be?
## Post #27
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2012-02-17T16:26:03+00:00
- Post Title: Re: God of War 1, PS2, WAD files

[http://dl.dropbox.com/u/62428937/shell.mesh](http://dl.dropbox.com/u/62428937/shell.mesh)

Did I just screw up this file too much?  Noesis hangs when trying to load it.
## Post #28
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-17T17:54:18+00:00
- Post Title: Re: God of War 1, PS2, WAD files

The importer does not parse the file as well as I would like it to.
Ogre3d doesn't have public specs and their documentation is really difficult to browse around.

There seems to be extra stuff that the ogre tool is creating which I haven't seen before.
Of course if I could read their documentation it might make more sense.

Anyways I've created a testing script so that it uses a for loop rather than a while (the main script is still going to be used for other ogre3d meshes)

For practical purposes, I've just made it loop 20 times cause I don't think it will need more than that.

[http://db.tt/oSimJKyf](http://db.tt/oSimJKyf)
## Post #29
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2012-02-17T18:10:52+00:00
- Post Title: Re: God of War 1, PS2, WAD files

Ok, that one doesn't freeze.  It does give "Failed to construct model from rpgeo context" though, which makes sense for a bad mesh file.

Thanks for the quick update.
## Post #30
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-17T18:17:28+00:00
- Post Title: Re: God of War 1, PS2, WAD files

The problem with that mesh file is that after the indices, there's a massive number of 00's.
...and then finally it gets to the vertices.

So my parser just keeps trying to read chunks and determining whether we've hit the vertex section or not, and it will not find it.
## Post #31
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2012-02-17T19:01:38+00:00
- Post Title: Re: God of War 1, PS2, WAD files

Your old script properly loaded [http://ps23dformat.wikispaces.com/file/view/shell.mesh](http://ps23dformat.wikispaces.com/file/view/shell.mesh)

Your new script does not.  That shell.mesh is the one the instructions use to paste the vertices into.
## Post #32
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-17T19:06:38+00:00
- Post Title: Re: God of War 1, PS2, WAD files

lol, I forgot to tell it to stop looping after it reaches the end.

Updated the test script.
## Post #33
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-02-29T22:35:25+00:00
- Post Title: Re: God of War 1, PS2, WAD files

I do not know much proper programing terminology but here is some information I figured about the meshes for GOWI:
Each mesh is made up of submeshes.
Submeshes have the following format:
Subsection 1 of a submesh:
Unknown headers
followed by
usually
04 01 00 01 (this might change/be absent within certain submeshes
and a different mesh might say have 03 instead of 04, never trust critters like theses.
?? 80 XX 65
this is the start of the UV section which has XX amount of UV coords. The ?? changes but the 80 and the 65 are always present
UV's have the following format:
2ByteSignedIntegerUVcoords(U,V) I do not think the PS2 supports half-floats (though a little of topic it might support litteraly a 4byte float where the 2bytes are implicitly 00) but anyways GOWI uses SignedIntegers. I do not think the number in this section will be negative because the UV when divided by some multiple of 2 will after to fit in a 1.0 by 1.0 square.
?? 80 XX 6A
there is either an extra byte at the start after the header or near the end
but this is the normal mapping section:
1ByteSignedInteger(X,Y,Z)
these are signed I think, in what way not sure but should be some function of the unit sphere.
?? 80 XX 6D
2ByteSignedVertexes(X,Y,Z)+1ByteUnknown+1ByteCONN
the conn stands for connection, and I do not know what CONN does for every value (something that more finely describes each Face) but if two succesive CONN's begin with the first digit "8" then that signifies the tristrip has just restarted. Some PS2 games might have 87 and 8f (anything that begins with 8 in first digit) others just have 80's be CONN's forgot which one this game uses but it is easily seen if there are missing or extra Faces. I think unlike Nintendo games PS2 games made with the official development kit have some leaweight as I have so many different types of CONN's that are not consistent across different PS2 games. Some color mapping and other things also...
Subsections 2 and Subsections 3
are almost exactly the same as Subsection 1, this is a GOWI thing (or maybe a ps2 thing), but you would have 3 times as many vertexes as
each sub mesh would have 3 vertex section headers:
?? 80 XX 6D
?? 81 XX 6D
?? 82 XX 6D
I have seen some PS2 games have 3 versions of the same mesh in memory so not that strange sort of like a paper doll that the same spot on the paper might have say clothes and skin, like an overlay.
If you need anymore clarification (I hope you do as I sure do) please ask.
The Ogre .mesh files on my site are "shelled out" large vertex model with the face index and vertex/uv/normals zero'd out and then the face index is added just for PS2 type games so that every 3 string of consecutive integers occur up to a large number say 14,000 for example:
00 00, 01 00, 02 00
03 00, 04 00, 05 00
.......
01 00, 02 00, 03 00
04 00, 05 00, 06 00
........
02 00, 03 00, 04 00
05 00, 06 00, 07 00

What the file does not have but should have so you do not see holes in the models is also include
permutations like 00 02, 00 00, 01 00 ..... The PS2 handles this automatically but models converted from PS2 games need this.
## Post #34
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2012-03-08T05:21:45+00:00
- Post Title: Re: God of War 1, PS2, WAD files

Thanks for the info FurryFan, and sorry for not noticing it until now.

I'll have to digest it all tomorrow though.
