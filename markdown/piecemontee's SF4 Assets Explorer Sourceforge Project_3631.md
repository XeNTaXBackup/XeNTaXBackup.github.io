## Post #1
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2009-08-04T22:47:25+00:00
- Post Title: piecemontee's SF4 Assets Explorer Sourceforge Project

Hello every one, I had little time at first but now I have no time at all, so I decided to release the sources.
So I uploaded my whole Hg repository on source forge:
[http://sf4viewer.sourceforge.net/](http://sf4viewer.sourceforge.net/)

Feel free to contact me to get a developper membership!

Warning: This was coded in short bursts and everything was done in header files since this is very small code base, so it may look weird

OLD post:

See screenshots page 2

DONE:
- EMZ decompression (compressed file backup to NAME.compressed) 
- model display
- textures display
- Character Sub model toggle (thanks LouNGeR)
- DDS texture extraction/injection  (with file backup) 
- fixed 100%CPU usage
- textured character models (open .cos and .col and select #EMO or #EMG)
- file drag and drop
- simple geometry extraction/injection[/b] (vertex inject only available #EMG)fixed vertex count detection
- skeletton display
- EMM materials browsing (no edition yet)
- rendering option toolbar: skeleton, wireframe, ....
- advanced models shading (bump map & correct ink shader)
- fixed normals and face orientation OBJ export (EMO/EMG) Again!
- animation names listing (#EMA)

TODO:
- EMM materials edition
- resized asset injector
- full model extraction/injection (#EMO)


MORE TODO:
- EMZ recompression
- skeletton skinning & animation display
- Readme/Manual

Thanks :
- LouNGeR for model on/off, 
- magnum@Xentax for skeletton&texture assignment ids.
[piecemonteeSF4explorerV0.33.zip](https://xentaxbackup.github.io/file/2299_piecemonteeSF4explorerV0.33.zip)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-05T00:21:55+00:00
- Post Title: piecemontee's SF4 Assets Explorer Sourceforge Project

This is the greatest thanks so much 

I hope you eventually release the source code as I love to see how all these different model viewers are made and like to learn from them.

Keep up the great work.
## Post #3
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-08-05T11:55:05+00:00
- Post Title: piecemontee's SF4 Assets Explorer Sourceforge Project

THHHHAAAAANNNNK YOOOOOOUUUUU!

Thank you!
## Post #4
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-08-05T20:01:44+00:00
- Post Title: piecemontee's SF4 Assets Explorer Sourceforge Project

Nice  But how we can extract the char's and others ? cause " Extract files " it's not highlighted

Edit: Ah just read the whole Todo list ... :S
## Post #5
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2009-08-05T22:47:00+00:00
- Post Title: piecemontee's SF4 Assets Explorer Sourceforge Project

Hi folks!  

Here is the second alpha release.
[http://www.gamevixenzone.com/gvz/viewto ... w=viewpoll](http://www.gamevixenzone.com/gvz/viewtopic.php?f=142&t=3684&start=0&view=viewpoll)

[Alternate download](http://www.mediafire.com/?sharekey=6bbe46263037cdb2b94117dade8fc295e04e75f6e8ebb871)

 DONE:
- Character model display
- fixed "simple"  models display (stages, character shadow simple model...) (no need to vote for this anymore)
- textures display
- Character Sub model toggle (thanks LounGer)
- DDS texture extraction/injection  (with file backup) 
- on the fly EMZ decompression (with compressed file backup) 
- fixed 100%CPU usage

 :write: TODO:
- textured models
- geometry extraction/injection
- shadered models
- resized asset injector
- EMZ recompression (2011)
- skeletton skinning & animation display (2012)
- Readme/Manual (2013)
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-05T23:49:36+00:00
- Post Title: piecemontee's SF4 Assets Explorer Sourceforge Project

magnum created an sf4 smd exporter script in pearl I hope this can help you map out the file format quickly.
[EMO2SMD.zip](https://xentaxbackup.github.io/file/2259_EMO2SMD.zip)
## Post #7
- Username: YourPackage
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 09, 2008 6:35 am
- Post datetime: 2009-08-06T00:18:44+00:00
- Post Title: piecemontee's SF4 Assets Explorer Sourceforge Project

excellent work
## Post #8
- Username: magnum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jul 27, 2009 3:43 am
- Post datetime: 2009-08-06T00:19:51+00:00
- Post Title: piecemontee's SF4 Assets Explorer Sourceforge Project

The EMO script (which btw is in Perl, not Python) spits out a *_data.txt file that shows almost the entire data dump for the file. There's 7 numbers that I can't figure out what are for, and is holding back model importing (from what I remember, when I tried modifying them, it crashed the game). It's the 3 unknown floats and the 4 chars (3 of which seems to always have the same value, and the 4th which is always 255).

An interesting thing to note is that the first 3 floats all change in increments of 1/255 (and range from -1 to 1), so I wonder if they're some how related to the chars.

I'll have to double check the crashing part, because I tried that in my early days of trying to modify the files, and maybe the crash was actually due to something else...
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-06T00:39:52+00:00
- Post Title: piecemontee's SF4 Assets Explorer Sourceforge Project

If you want to re compress the data the game will read plain zlib compressed files also if that makes it easier to re compress them.
## Post #10
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2009-08-06T06:10:16+00:00
- Post Title: piecemontee's SF4 Assets Explorer Sourceforge Project

> Reply from magnum
>
> The EMO script (which btw is in Perl, not Python) spits out a *_data.txt file that shows almost the entire data dump for the file. There's 7 numbers that I can't figure out what are for, and is holding back model importing (from what I remember, when I tried modifying them, it crashed the game). It's the 3 unknown floats and the 4 chars (3 of which seems to always have the same value, and the 4th which is always 255).

An interesting thing to note is that the first 3 floats all change in increments of 1/255 (and range from -1 to 1), so I wonder if they're some how related to the chars.

I'll have to double check the crashing part, because I tried that in my early days of trying to modify the files, and maybe the crash was actually due to something else...
Great!
Thank you for the information   , I'll tell you if I find the remaining values meaning
## Post #11
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-08-06T20:49:29+00:00
- Post Title: piecemontee's SF4 Assets Explorer Sourceforge Project

Oh this is most excellent! I was wondering when an explorer for this format would be made, and you made it, thank you for this, I look forward to it's development! We are a few steps closer to further SF4 modding.
## Post #12
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2009-08-08T00:30:13+00:00
- Post Title: piecemontee's SF4 Assets Explorer Sourceforge Project

I added preliminary vertex import/export support:

The workflow will be the same as DDS :
export EMG in obj format
edit (I used misfit3D for my tests)
inject back at the same location in the cos file

Normat/tex coords are locked to the original value for now bu I am working on it.
[viperEdit.JPG](https://xentaxbackup.github.io/file/2263_viperEdit.JPG)
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-08T00:34:04+00:00
- Post Title: piecemontee's SF4 Assets Explorer Sourceforge Project

Very nice. Here is the link to the new release.
[http://www.gamevixenzone.com/gvz/downlo ... p?id=10612](http://www.gamevixenzone.com/gvz/download/file.php?id=10612)
## Post #14
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2009-08-08T00:54:03+00:00
- Post Title: piecemontee's SF4 Assets Explorer Sourceforge Project

> Reply from chrrox
>
> Very nice. Here is the link to the new release.
http://www.gamevixenzone.com/gvz/downlo ... p?id=10612
Sorry I quick fixed the exe, U're link is not valid anymore:
[http://www.gamevixenzone.com/gvz/viewto ... 298#p27298](http://www.gamevixenzone.com/gvz/viewtopic.php?f=142&t=3684&p=27298#p27298)
## Post #15
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-08T01:05:32+00:00
- Post Title: piecemontee's SF4 Assets Explorer Sourceforge Project

How does the obj export and import work isn't the weighting information needed to avoid some weird side effects?
## Post #16
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2009-08-08T09:20:12+00:00
- Post Title: Re: SF4 Asset editor

> Reply from chrrox
>
> How does the obj export and import work isn't the weighting information needed to avoid some weird side effects?

You are right, weighting information should be edited too, (but as is it handles slight deformations pretty well, specially if you are not near joint intersection)

This is a preview, next step will be exporting/importing complete model (ms3d or smd)
## Post #17
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2009-08-09T00:45:18+00:00
- Post Title: Re: SF4 Asset editor

Thank to your script magnum I made some progress on the skeleton front!  
[skel.JPG](https://xentaxbackup.github.io/file/2267_skel.JPG)
## Post #18
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2009-08-09T19:07:09+00:00
- Post Title: Re: SF4 Asset editor

I switched from fixed pipeline to a shader driven one, allowing texturing progress.
Still... now I must find a way to trigger automatically the right texture stage for each model  
[textured2.JPG](https://xentaxbackup.github.io/file/2270_textured2.JPG)
## Post #19
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2009-08-11T21:36:52+00:00
- Post Title: Re: SF4 Asset editor

I thought I'd find some texture<->mesh assignment in #EMM material section but no luck, it must be embedded in sub #EMG meshes headers.

EMM block a pretty straight forward exept I found that every submesh setting is 32 for the name and either 8 or 4 when the name ends by _W.
so it can be 36 or 40.

EMM is
16 bytes (including #EMM tag)
4 byte count followed by as many 4 byte offsets
Each offset points to 32 bytes "value type name" and either 4/8 bytes as described above
[materials.PNG](https://xentaxbackup.github.io/file/2273_materials.PNG)
## Post #20
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2009-08-16T21:01:19+00:00
- Post Title: Re: SF4 Asset editor

Normal mapping screenshot
[normalMapping.JPG](https://xentaxbackup.github.io/file/2288_normalMapping.JPG)
## Post #21
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2009-08-16T21:02:28+00:00
- Post Title: Re: SF4 Asset editor

Ink rendering snapshot
[inkShader.JPG](https://xentaxbackup.github.io/file/2289_inkShader.JPG)
## Post #22
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-08-16T21:22:14+00:00
- Post Title: Re: SF4 Asset editor

haha, you are the man with a big M
## Post #23
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2009-08-17T20:34:02+00:00
- Post Title: Re: SF4 Asset editor

> Reply from magnum
>
> The EMO script (which btw is in Perl, not Python) spits out a *_data.txt file that shows almost the entire data dump for the file. There's 7 numbers that I can't figure out what are for, and is holding back model importing (from what I remember, when I tried modifying them, it crashed the game). It's the 3 unknown floats and the 4 chars (3 of which seems to always have the same value, and the 4th which is always 255).

An interesting thing to note is that the first 3 floats all change in increments of 1/255 (and range from -1 to 1), so I wonder if they're some how related to the chars.

I'll have to double check the crashing part, because I tried that in my early days of trying to modify the files, and maybe the crash was actually due to something else...

I think there is a little missinterpretation in your script, when 64 byts long a vertex is not
x, y, z, nx, ny, nz, u, v, ...

```
	for( 0..$vertexblockcount-1 ) {

		my @floats;
		if( $vertexblocksize == 64 ) {
			@floats = readu( $INPUT, "f11", 44 );

			my @v_uc = ($floats[6],-$floats[7]);

			my @v_xyz = (-$floats[0],$floats[2],$floats[1]);
			my @v_normal = (-$floats[3],$floats[5],$floats[4]);

			push( @uv, \@v_uc );
			push( @xyz, \@v_xyz );
			push( @normal, \@v_normal );

		} elsif( $vertexblocksize == 32 ) {	# used in skeleton EMO files
```


Instead you have : x, y, z, tx, ty, tz, u, v, nx, ny, nz, a, w1, w2, w3, w4
where (tx, ty, tz) is the vertex tangent for normal mapping (see viewer release v0.31) and a is a precomputed static ambiant occlusion factor (to be interpreted as a diffuse color):

```
	for( 0..$vertexblockcount-1 ) {

		my @floats;
		if( $vertexblocksize == 64 ) {
			@floats = readu( $INPUT, "f11", 44 );

			my @v_uc = ($floats[6],-$floats[7]);

			my @v_xyz = (-$floats[0],$floats[2],$floats[1]);
			my @v_tangent = ($floats[3],$floats[4],$floats[5]);
			my @v_normal = ($floats[8],$floats[9],$floats[10]);

			push( @uv, \@v_uc );
			push( @xyz, \@v_xyz );
			push( @normal, \@v_normal );

		} elsif( $vertexblocksize == 32 ) {	# used in skeleton EMO files
```
## Post #24
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2009-08-19T19:07:03+00:00
- Post Title: Re: SF4 Asset editor

"piecemontee's SF4 Assets Explorer v0.33 RELEASE" fixes the normal mapping and the ink shader
[inkShaderFixed.JPG](https://xentaxbackup.github.io/file/2300_inkShaderFixed.JPG)
## Post #25
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-08-19T20:05:44+00:00
- Post Title: Re: SF4 Asset editor

OMG, SNOW-WHITE!

Haha, thanks for the work mate!
## Post #26
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-08-23T16:11:39+00:00
- Post Title: Re: SF4 Asset editor

how do I import parts from other costumes, I've seen people combine models
## Post #27
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-08-24T13:56:51+00:00
- Post Title: Re: SF4 Asset editor

> Reply from Mario_Kart
>
> how do I import parts from other costumes, I've seen people combine models
If you make sure that it has the same amount of verts, it should work just fine....
## Post #28
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-08-24T20:31:03+00:00
- Post Title: Re: SF4 Asset editor

I reshaped sakura's body, but there where no shoulders to work with;



I had to create shoulders from the shirt she was wearing, but the weights are out of sync with the arms, so there is tearing visible.

I thought if I could swap the model block from one costume, to another I could fix this. or.. if model injection ever becomes supported ^_^ well I would love that.
## Post #29
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-08-24T21:00:23+00:00
- Post Title: Re: SF4 Asset editor

If Piecemontee would support Resized Assets, I'm pretty sure adding verts will be possible.

I've already made a tool that can make EMB's of any size, it's just that I have no idea how the Model stuff works 

This makes me think about how Assets Explorer handles COS and COL files, because it seems to rely too much on the contents of COL/COS files instead of threading the files as an EMB ARCHIVE.
This is clearly visible when I Open a resized EMB file in Assets Explorer: Some textures etc are messed up.
## Post #30
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-08-24T21:03:40+00:00
- Post Title: Re: SF4 Asset editor

I smell Mugen 3.0!
## Post #31
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2009-08-29T14:14:09+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer v0.33 RELEASE

> Reply from LouNGeR
>
> This makes about how Assets Explorer handles COS and COL files, because it seems to rely too much on the contents of COL/COS files instead of threading the files as an EMB ARCHIVE.
This is clearly visible when I Open a resized EMB file in Assets Explorer: Some textures etc are messed up.

Hi LouNGeR, could you post/pm some of those edited files, I'm eager to clean this mess, as the tool makes no special operation depending on the file kind   
I may have miss interpreted some offsets in #EMB headers/tables or something like that
## Post #32
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-08-30T10:47:34+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer v0.33 RELEASE

Here's how I do it (working in decimals):

- FileOffset = Read 4 bytes
- FileOffset_absolute = Offset + CurrentPointerLocation - 4
- FileLength = Read 4 bytes

I guess you were already doing it like this, cause this is the only way afaik.
I dunno what else could cause the problem.

Also got a question for you:
EMO files are nearly the same as EMB files, but the header is slightly different.
Do you know where it says how many files there are in an EMO file?
For EMB it's at index 12, but I can't seem to find this "file count" value in EMO files.
## Post #33
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-02-23T22:40:31+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer v0.33 RELEASE

In waiting of automating the process of converting emo to smd or ms3d from new release of piecemontee SF4 explorer.

piecemontee SF4 explorer V0.33 (by piecemontee) + EMO2SMD (by magnum) + psk tools (by epic and gildor):

pose:
[](http://s002.radikal.ru/i198/1002/6b/f98b846f37cf.jpg) [](http://s44.radikal.ru/i105/1002/cb/10a8c95db6e8.png)

test anim:
[](http://s39.radikal.ru/i086/1002/59/c40b95902984.jpg)

the model of his own skeleton
## Post #34
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-03-12T20:29:50+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer v0.33 RELEASE

> Reply from Tosyk
>
> In waiting of automating the process of converting emo to smd or ms3d from new release of piecemontee SF4 explorer.

piecemontee SF4 explorer V0.33 (by piecemontee) + EMO2SMD (by magnum) + psk tools (by epic and gildor):

pose:
 

test anim:


the model of his own skeleton

How were you able to extract emo file from emz file??
## Post #35
- Username: gics
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Dec 19, 2009 4:12 pm
- Post datetime: 2010-03-25T01:24:15+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer v0.33 RELEASE

> Reply from Tosyk
>
> In waiting of automating the process of converting emo to smd or ms3d from new release of piecemontee SF4 explorer.

piecemontee SF4 explorer V0.33 (by piecemontee) + EMO2SMD (by magnum) + psk tools (by epic and gildor):

pose:
 

test anim:


the model of his own skeleton

Can you tell me how you work with those tools and where can i get them (link to EMO2SMD & psk tools)
Thx.
## Post #36
- Username: YourPackage
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 09, 2008 6:35 am
- Post datetime: 2010-06-06T17:59:02+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer v0.33 RELEASE

> Reply from gics
>
> Tosyk wrote:In waiting of automating the process of converting emo to smd or ms3d from new release of piecemontee SF4 explorer.

piecemontee SF4 explorer V0.33 (by piecemontee) + EMO2SMD (by magnum) + psk tools (by epic and gildor):

pose:
 

test anim:


the model of his own skeleton

Can you tell me how you work with those tools and where can i get them (link to EMO2SMD & psk tools)
Thx.

Is there a link to the EMO2SMD tool anywhere?
## Post #37
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-06-06T18:22:22+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer v0.33 RELEASE

The contents of this post was deleted because of possible forum rules violation.
## Post #38
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2010-06-07T05:59:40+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer v0.33 RELEASE

Just wanted to say thanks... 

Only  had a try at ripping the sf characters a few days ago and now i have them all extracted and it was all done with the SF4 explorer. So Thank you for a great app.
## Post #39
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2010-06-07T23:14:22+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer v0.33 RELEASE

When I try to run this  tool, it give me an error: 'CreateDevice returned INVALIDCALL'



I downloaded it many times, and still give me this error. 

Anyone know what is, and how to fix this? I really need this tool to trnaslate this game.

Thanx for all.
## Post #40
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2010-06-08T18:04:30+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer v0.33 RELEASE

I think your hardware doesn't support the display mode or HARDWARE_VERTEXPROCESSING.
What is your graphic card (I need vertex&pixel shader capable card)
## Post #41
- Username: gics
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Dec 19, 2009 4:12 pm
- Post datetime: 2010-08-05T02:20:37+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer v0.33 RELEASE

The contents of this post was deleted because of possible forum rules violation.
## Post #42
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-08-05T08:42:43+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer v0.33 RELEASE

> Reply from gics
>
> How about psk tools (by epic and gildor) got any link?
Yes, i hold up this suggestion, because, unfortunately SMD import in 3d max work terribly: it messed up all bones!
## Post #43
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2010-08-10T20:43:41+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer v0.33 RELEASE

See 1st post (or [https://sourceforge.net/projects/sf4viewer/](https://sourceforge.net/projects/sf4viewer/))
## Post #44
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-09-14T11:36:05+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer v0.33 RELEASE

2magnum:

Can you update you script (EMO2SMD) to convert emo-models from xbox360 Super Street Fighter?

With piecemonteeSF4explorerV0.37b i'm exctracted .emo file and try to convert it with emo2smd converter, but i get 1 kb .smd only. Then i try to use sf4tool.exe to compile .emo (xbox360 version) to .emo (pc version) and your script worked perfectly, but i get .smd like on the pictures:

[](http://s44.radikal.ru/i103/1009/19/51562535418f.jpg) [](http://s60.radikal.ru/i169/1009/61/8cf174e1f4ba.jpg)

i attached original (xbox360) .emo file and sf4tool.exe

[emo-file](http://www.sendspace.com/file/ykbbih)  |  [sf4tool](http://www.sendspace.com/file/r5bufs)
## Post #45
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2010-11-20T23:23:19+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer v0.33 RELEASE

I don't understand if is possible extract model with bones with this SF4 Assets Explorer
## Post #46
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-11-21T16:33:18+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer Sourceforge Project

> Reply from grotesque
>
> I don't understand if is possible extract model with bones with this SF4 Assets Explorer

Nope, unless the creator adds a fbx or a collada exporter.
## Post #47
- Username: joeyq
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 19, 2010 6:14 pm
- Post datetime: 2010-11-22T10:29:06+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer Sourceforge Project

Can anyone check if it's just me or that SF4explorerV0.37b.exe doesn't display stage models correctly (and extracted models  are messed up) for sf4 and ssf4, 'cause SF4explorerV0.33.exe does display and extract stage models correctly for sf4. Is it a bug?
 See my earlier post => [viewtopic.php?p=44952#p44952](http://forum.xentax.com/viewtopic.php?p=44952#p44952)
## Post #48
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2010-12-14T00:39:51+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer Sourceforge Project

My computer, which once ran this program just fine, now gives me the "CreateDevice returned INVALIDCALL" error!!!!
How do I fix this?

Like I said, my computer once ran this just fine. I have modded sf4 before with no problems, and no errors.
What is going on?!
## Post #49
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2010-12-19T12:53:52+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer Sourceforge Project

The latest SF4 explorer creates damaged exports- I tried to extract ibuki, and opend it in 3ds max... I got an "invalid normal index" error- then I tried auto setting the normals, and got a skewed, destroyed model. Isn't anyone going to respond? I thought this program was still important in the SF4 modding project...
PieceMontee, is there a repaired version in the making?
Thanks
## Post #50
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-01-21T12:07:20+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer Sourceforge Project

Sorry for the massive bump but would anyone be able to reupload EMO2SMD? I found a megaupload link but it wont work since MU has been shut down :/ Please and thank you
## Post #51
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-01-21T15:20:07+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer Sourceforge Project

> Reply from TRDaz
>
> Sorry for the massive bump but would anyone be able to reupload EMO2SMD? I found a megaupload link but it wont work since MU has been shut down :/ Please and thank you
[https://skydrive.live.com/?cid=ffbe4e57 ... 49FCBE!177](https://skydrive.live.com/?cid=ffbe4e570949fcbe#cid=FFBE4E570949FCBE&id=FFBE4E570949FCBE!177)
## Post #52
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-01-22T18:01:28+00:00
- Post Title: Re: piecemontee's SF4 Assets Explorer Sourceforge Project

Thanks
