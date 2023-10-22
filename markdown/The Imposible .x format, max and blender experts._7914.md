## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-12-22T05:10:57+00:00
- Post Title: The Imposible .x format, max and blender experts.

Incredible but true, i search and i cant found a fully working .x importer, for Max doensnt exist and for blender someone made a one with 30% of functions only, the only can open .x files and export its right Deep Exploration but this cant save the weights or skining properly, somebody expert of max or blender know one working? one can import geometry, animation and respect the skining? i use the RAN online files to test.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-22T05:39:07+00:00
- Post Title: The Imposible .x format, max and blender experts.

I'll probably write one for noesis.
I've been meaning to do it since

(1) the specs are basically given to you. All of it (unless it's outdated)
(2) it's a good format as an exercise for file parsing.
## Post #3
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-12-22T09:59:00+00:00
- Post Title: The Imposible .x format, max and blender experts.

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-22T18:22:54+00:00
- Post Title: The Imposible .x format, max and blender experts.

[spec](http://msdn.microsoft.com/en-us/library/windows/desktop/bb173014%28v=VS.85%29.aspx)

Here is the entire spec.
I think with C or C-like languages it would be easier to write it simply because of how the format is defined.

For example there are a bunch of templates, which one could probably easily translate into structs and then just run it through the file.

In Python I would define separate functions for each template and then just run it through like that.

I honestly don't know why no one's done it. Or at least, no one's released one publicly.
It's a lot easier than other things lol. I mean sure you'd probably have to think about it maybe for an hour or so to figure out how you should actually write a parser, but it isn't too difficult.

Only problem is that ....some people like to use their own "variants", which isn't that common.
.x format is still used widely. In half the japanese games I manage to unpack there are .x files everywhere.

EDIT: oh, they don't seem to talk about compressed data.

The reference I have (book) has lzw and zip. Not sure if there are others.
Well it should be easily identified in the header cause it'll say something like

xof 0302 bzip 064

or something
## Post #5
- Username: Chev
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Mar 19, 2011 1:06 am
- Post datetime: 2011-12-22T19:03:15+00:00
- Post Title: The Imposible .x format, max and blender experts.

> Reply from finale00
>
> I honestly don't know why no one's done it. Or at least, no one's released one publicly.
It's a lot easier than other things lol. I mean sure you'd probably have to think about it maybe for an hour or so to figure out how you should actually write a parser, but it isn't too difficult.
It's because .x is usually used the other way round: its purpose was to provide a format you'd export from your tools and into games, not into tools. That, and there is (or was, haven't checked more recent versions) a pretty functional (with animations and all) .x model viewer in the directX SDK.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-22T19:24:07+00:00
- Post Title: The Imposible .x format, max and blender experts.

Found something

[http://forum.ragezone.com/f528/release- ... or-666990/](http://forum.ragezone.com/f528/release-working-x-files-editor-666990/)

Anyways I'm writing a noesis plugin for the binary .x format since it looks like an amusing programming exercise.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-22T22:28:15+00:00
- Post Title: The Imposible .x format, max and blender experts.

Ok I have started writing a simple parser for noesis for the .x uncompressed binary format and gotten somewhere.



I probably will need to refine the code so that it reflects the structure of the format (ie: read token, do whatever, read another token, do whatever, keep reading tokens, etc). This one assumes a lot of things about each template and does not heavily rely on the read_token function, although I believe it should.

There are also a lot of annoying details like how materials are assigned to faces, and how you have triangles and quads, and faces even have more verts per face than 4.

The material list is just a sequence of integers corresponding to each face, but you can have stuff like

[0, 0, 0, 0, 1, 1, 2, 2, 1, 1, 1, 1, 1, 0, 0, 0, 0]

Where each number references a material that is defined afterwards.

So the numbers can be in any arbitrary order to the point where I'm probably going to have to create each face one at a time.

The fact that everything is defined in terms of templates, I don't know if I should parse everything into data structures and then build the model afterwards, or build the model while I'm parsing.

If anyone would like to work on the python script so far here it is
[http://xtsukihime.webs.com/Noesis%20Plu ... tX_xbin.py](http://xtsukihime.webs.com/Noesis%20Plugins/fmt_DirectX_xbin.py)

PS: why do all of the human models look psycho?
## Post #8
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-12-22T22:46:20+00:00
- Post Title: The Imposible .x format, max and blender experts.

Good advance finale...
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-22T23:08:04+00:00
- Post Title: The Imposible .x format, max and blender experts.

I don't understand how the bones are defined.

We have a set of frames, and each frame can have a name like "bip..." which is a bone. Of couse there are frames like "Scene Root" which probably shouldn't be a bone.

It defines a set of SkinWeight templates which defines which vertex influence as well as the weights, as well as a bone transform matrix (maybe).

So ok maybe I will assume that the bones are defined in the order that the frames appear.
A frame can contain other frames, so presumably they are defined in the order that the bones should be connected (that is, bone.parentIndex = index of parent frame)

Which I have not considered.
I have no idea how I would define this frame/sub-frame relationship, and how to determine whether a frame actually represents a bone. Or whether the bone is defined elsewhere. The specs don't seem to make this clear.
## Post #10
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-12-23T00:44:06+00:00
- Post Title: The Imposible .x format, max and blender experts.

The spec doesn't really define Bones.  Frames are simply transforms, which technically that is all bones are as well.  Parenting is handled through the nesting of Frames within another, so its probably easiest to simply keep a running index and assign them to Frames as they are encountered.  When a Frame is nested you should already know what the current frame is, if there is one, and the last index associated with it so that the parent of the new frame can be set.  Frames are referenced by name in Skinning and Animations that reference them.

To get from frames to bones, you would have to make assumptions about the type of file being loaded, or simply treat all frames as bones.  But since the spec is general, there can easily be multiple root nodes, and even though there shouldn't be, it's technically not prohibited to have Frames, etc. with the same name.  But for the most part i guess you can assume a nicely structured file, heh.

The SkinWeight matrix i believe is the bind pose matrix, but can't recall for sure.  Should be easy to tell when compared against the actual Frame transform.

That's what i can remember off the top of my head.  Been a while since i have messed with the .x format.  But yeah, the format was design to be a general scene description (its extensible with your own template definitions, etc.) so it may not be as easy to map directly to concepts like Bones without making some assumptions.
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-23T00:58:18+00:00
- Post Title: The Imposible .x format, max and blender experts.

Hmm yes I just need to keep a frame count.

Since the frame count does not change until I run into another frame, any templates associated with a frame is also kept track of if needed.

In fact I just realized the error in how I'm parsing it: I'm treating templates as some fixed struct and not treating the open templates the way they should be. If I use a frame count or mesh count, then I can just say "ok any information I parse belongs to frame i"

Then I also need to determine whether I'm nested or not.

I can use two variables curDepth and prevDepth that will store the "depth" I'm in. The depth will be incremented or decremented whenever an open brace or close brace is encountered, and so I know I'm in a nested template if curDepth <> prevDepth. Whenever curDepth is updated, I simply back-up its file in prevDepth.

Since the format can be expanded and customized if the dev wants to, any games that might define their own templates can simply inherit from some generic xbin parser and add those definitions.
## Post #12
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-12-25T18:24:36+00:00
- Post Title: The Imposible .x format, max and blender experts.

Then finale can u writhe a noesis importer plugin with weights support for the RAN online .x format?
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-25T20:02:42+00:00
- Post Title: The Imposible .x format, max and blender experts.

Probably not lol
I don't know how that stuff works.

I'll be going back to some documented formats that use a very simple format to store bones and try to make plugins for those to get an idea the kind of things that are involved (so far nothing I've wrote handles those)

And then maybe try again with .x
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-28T19:08:46+00:00
- Post Title: The Imposible .x format, max and blender experts.

Well now I am changing my approach to this format again....

As stated in the specs, there are two types of token: record-bearing tokens, and data token.
Everything is also arranged in templates, where one template may contain another template.

Parsing would be done in two steps.
1: parse the file into a tree (of templates). For now I am ignoring any template definitions.
2: walk through the template tree and build the objects accordingly.

This approach preserves the parent/child hierarchy (which is necessary for the skeleton, and also stores all of the tokens with their templates, and all of the templates with their parent templates.

I wouldn't have to care about depth or anything, since depth would be given to me by the tree.

Building objects out of each template is then a matter of going to the template, looking at the name, and then walking through each token and handling them as they come.

Although it takes a performance hit (cause rather than parsing it once, I'm basically doing things twice), it allows me to handle any sort of template definition that someone might use.

Maybe there is parser code available in the SDK, never checked.
## Post #15
- Username: FallenAngelRiku
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Nov 30, 2011 1:28 pm
- Post datetime: 2011-12-31T06:03:59+00:00
- Post Title: The Imposible .x format, max and blender experts.

Im a MMD user
and Miku Miku Dance works with .x files
you can open .X files on the MMD editor
the PMD editor
and put in the .x file
and save it as a .PMD File
then you can use koichi Senada's importer for 3dsmax 2008
and import the PMD File
hope I helped.
unfortunately it can't export Animations.
## Post #16
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-01-04T17:48:09+00:00
- Post Title: Re: The Imposible .x format, max and blender experts.

> Reply from FallenAngelRiku
>
> Im a MMD user
and Miku Miku Dance works with .x files
you can open .X files on the MMD editor
the PMD editor
and put in the .x file
and save it as a .PMD File
then you can use koichi Senada's importer for 3dsmax 2008
and import the PMD File
hope I helped.
unfortunately it can't export Animations.

Thanks man, but this system you tell, keep the weights in the .x formats?
can you try with this files?
[http://www.megaupload.com/?d=DELFRZQC](http://www.megaupload.com/?d=DELFRZQC)

I tested with okino polytrans and deep exploration, this 2 programs can also import and export the .x format to others formats, but the weights are wrong and damaged in the procces.
