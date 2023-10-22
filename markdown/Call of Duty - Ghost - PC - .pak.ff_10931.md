## Post #1
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2013-11-05T13:51:31+00:00
- Post Title: Call of Duty - Ghost - PC - *.pak/*.ff

Can anyone take a look at this files.

PM me for sample.
## Post #2
- Username: withmorten
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 28, 2012 11:03 pm
- Post datetime: 2013-11-05T20:01:38+00:00
- Post Title: Call of Duty - Ghost - PC - *.pak/*.ff

It's just flac files in a container (the .pak files). I'm no good at writing scripts, but I think a simple quickbms script would do. If anyody wants a sample, they can PM me, too.
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-11-05T20:20:16+00:00
- Post Title: Call of Duty - Ghost - PC - *.pak/*.ff

Is there a way to check if the filenames are generated in RAM for the flac files?
## Post #4
- Username: withmorten
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 28, 2012 11:03 pm
- Post datetime: 2013-11-05T20:35:51+00:00
- Post Title: Call of Duty - Ghost - PC - *.pak/*.ff

Hah, you just posted the same in ffshrine. 

Do you have an extractor script handy or something? The BO2 sound format is exactly the same, yet the extractor for that is created specifically for BO2's folder structure ... :/
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-11-05T21:40:45+00:00
- Post Title: Call of Duty - Ghost - PC - *.pak/*.ff

Actually if you want to extract the FLAC raw just use vgmtoolbox and set it to search for FLAC, in the advanced/extraction tab.
## Post #6
- Username: withmorten
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 28, 2012 11:03 pm
- Post datetime: 2013-11-05T22:09:32+00:00
- Post Title: Call of Duty - Ghost - PC - *.pak/*.ff

That's actually what I've been trying to do right now, but what do I choose as terminator string?

Edit: Oh well, apparently "fLaC" worked just fine, it's just that the first few files were only a couple of KB and kinda weird, so I thought it didn't work properly. Checking "Cut to EOF ..." is also necessary for VGM to properly write out the last file in the archive.
## Post #7
- Username: killerpepo
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 23, 2011 2:22 pm
- Post datetime: 2013-11-05T23:19:28+00:00
- Post Title: Call of Duty - Ghost - PC - *.pak/*.ff

Hi guys .. this is a small program I wrote in C# it extracts the *.flac audio files
a bit better than VGM because it searches for "fLaC" string , while this read the file size from header 

just drag the *.pak file (which contains the sound) and drop it on the exe and it will extract .. 
[flac_ex.zip](https://xentaxbackup.github.io/file/6755_flac_ex.zip)
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2013-11-06T12:06:59+00:00
- Post Title: Call of Duty - Ghost - PC - *.pak/*.ff

Thanks for the tool
## Post #9
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2013-11-06T13:21:38+00:00
- Post Title: Call of Duty - Ghost - PC - *.pak/*.ff

Is there a chance to extract and repack the textures!?

Look like they are in /dir in the *.ff-files.
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-06T13:50:45+00:00
- Post Title: Call of Duty - Ghost - PC - *.pak/*.ff

Share files here.
## Post #11
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-11-08T14:31:15+00:00
- Post Title: Call of Duty - Ghost - PC - *.pak/*.ff

> Reply from Ekey
>
> Share files here.
[http://cra0kalo.com/public/research/](http://cra0kalo.com/public/research/)
## Post #12
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2013-11-08T14:55:58+00:00
- Post Title: Call of Duty - Ghost - PC - *.pak/*.ff

> Reply from cra0
>
> 
http://cra0kalo.com/public/research/

zlibed headerless dds textures.
I think name table is encrypted or something.
## Post #13
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-11-08T15:28:30+00:00
- Post Title: Call of Duty - Ghost - PC - *.pak/*.ff

> Reply from deepshit
>
> cra0 wrote:
http://cra0kalo.com/public/research/

zlibed headerless dds textures.
I think name table is encrypted or something.

Yep though they could be in the very first img archive. I have to take a look
## Post #14
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-11-08T16:05:21+00:00
- Post Title: Call of Duty - Ghost - PC - *.pak/*.ff

someone checked the X360 version ? I think it wont be encypted
## Post #15
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-11-10T05:07:13+00:00
- Post Title: Call of Duty - Ghost - PC - *.pak/*.ff

Ok so here is what I have figured out.




PAK contains SOUND/IMAGE data
PAK files have MAGIC header for image data "IWffu1005" followed by some encrypted/compressed data not Zlib.
After that Zlib blocks start each to be a texture with a textureID these textureIDs are referenced inside the .ff files as the engine calls them from the pak based on the id.

-Header
-OffsetTable (I'm guessing)
-Zlibd blocks


-EDIT here is a dirty release for .ff model data
[http://cra0kalo.com/public/COD_GHOSTS_PAKTool.zip](http://cra0kalo.com/public/COD_GHOSTS_PAKTool.zip)

usage: input one of the .ff files 

example
[https://dl.dropboxusercontent.com/u/107 ... lt_f_tr.ff](https://dl.dropboxusercontent.com/u/10798900/DUMPBOX/mp_body_clan_assault_f_tr.ff)
[https://dl.dropboxusercontent.com/u/107 ... lt_a_tr.ff](https://dl.dropboxusercontent.com/u/10798900/DUMPBOX/mp_body_clan_assault_a_tr.ff)
[https://dl.dropboxusercontent.com/u/107 ... lt_a_tr.ff](https://dl.dropboxusercontent.com/u/10798900/DUMPBOX/mp_body_devgru_assault_a_tr.ff)


it will give you the raw model data


-edit-
-Supports unpacking DXT1/DXT5 textures from the images.pak files
## Post #16
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-11-21T03:58:41+00:00
- Post Title: Re: Call of Duty - Ghost - PC - *.pak/*.ff

Supports extracting .pak texture archives now someone still needs to help me figure out the dx11 compression they use :/

[http://cra0kalo.com/public/COD_GHOSTS_Toolset.zip](http://cra0kalo.com/public/COD_GHOSTS_Toolset.zip)
## Post #17
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-11-21T05:56:49+00:00
- Post Title: Re: Call of Duty - Ghost - PC - *.pak/*.ff

cra0 --> have you found the text pls?
## Post #18
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-11-22T08:28:43+00:00
- Post Title: Re: Call of Duty - Ghost - PC - *.pak/*.ff

> Reply from michalss
>
> cra0 --> have you found the text pls?

Here is an asset dump 
[https://dl.dropboxusercontent.com/u/159 ... e_dump.txt](https://dl.dropboxusercontent.com/u/15953784/ghosts_assetname_dump.txt)

tell me if something interests you ill look into it
## Post #19
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-11-22T17:46:02+00:00
- Post Title: Re: Call of Duty - Ghost - PC - *.pak/*.ff

> Reply from cra0
>
> michalss wrote:cra0 --> have you found the text pls?

Here is an asset dump 
https://dl.dropboxusercontent.com/u/159 ... e_dump.txt

tell me if something interests you ill look into it

Hmm might *.csv files could be interesting, but hard to say where text is.
## Post #20
- Username: einstein95
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 07, 2013 4:16 am
- Post datetime: 2013-11-22T19:12:26+00:00
- Post Title: Re: Call of Duty - Ghost - PC - *.pak/*.ff

I'm curious about
scriptdebugger/help.txt
ui/code.txt
ui/test_menus.txt

but then that's just me.
## Post #21
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-11-23T06:28:34+00:00
- Post Title: Re: Call of Duty - Ghost - PC - *.pak/*.ff

> Reply from chrrox
>
> did you add this at the end.

msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
--msh.name = Mesh_Name_array[a]
--msh.material = meditMaterials[1].materialList[(MatSlotTexID[a])]
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]

hmm what

-EDIT-
Seems no one has documented well they have but have not shared their findings sort of sad :/
Here is what I have figured out so far


```
  //raw raw structure ty to shak-otay 
  struct COD_Ghosts_Xmodel_Vertblock
  {
  	float vd x
	float vd y
	float vd z
	float unknown = -1
	int32 VertexColour
	hfloat TextureU
	hfloat TextureV
	int32 UnknownA
	int32 UnknownB
  }
  
  //sizeFinal = 0x6 x (size)
   struct COD_Ghosts_Xmodel_Facelist
  {
	int16 face1
	int16 face2
	int16 face3
  } 

```
## Post #22
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-12-05T04:28:36+00:00
- Post Title: Re: Call of Duty - Ghost - PC - *.pak/*.ff

Guess extracting from the assetpool is the better way to go credits to Tom on this one
## Post #23
- Username: sectoredits
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 05, 2013 8:10 am
- Post datetime: 2013-12-05T20:17:12+00:00
- Post Title: Re: Call of Duty - Ghost - PC - *.pak/*.ff

> Reply from killerpepo
>
> Hi guys .. this is a small program I wrote in C# it extracts the *.flac audio files
a bit better than VGM because it searches for "fLaC" string , while this read the file size from header 

just drag the *.pak file (which contains the sound) and drop it on the exe and it will extract ..

hey this might be a bit of a silly question but i downloaded your tool and extracted the files, but its showing up as loads of "soundfile3.pak_003E8800" files. How am i able to extract the audio exactly? (sorry if its a nooby question im new around here)

Thanks in advance for the help!
## Post #24
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-12-09T21:59:52+00:00
- Post Title: Re: Call of Duty - Ghost - PC - *.pak/*.ff

Possible bug: Loading .ff files tries to extract them as huge IWI's now?
## Post #25
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2014-01-14T23:38:13+00:00
- Post Title: Re: Call of Duty - Ghost - PC - *.pak/*.ff

> Reply from michalss
>
> cra0 wrote:michalss wrote:cra0 --> have you found the text pls?

Here is an asset dump 
https://dl.dropboxusercontent.com/u/159 ... e_dump.txt

tell me if something interests you ill look into it

Hmm might *.csv files could be interesting, but hard to say where text is.

Sorry, didn't know that it's hard to say where text is   
[https://www.dropbox.com/s/nqrfpc3cezx40rr/cod.png](https://www.dropbox.com/s/nqrfpc3cezx40rr/cod.png)
## Post #26
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-01-16T06:48:20+00:00
- Post Title: Re: Call of Duty - Ghost - PC - *.pak/*.ff

Final Release PAK extractor


[http://tom-crowley.co.uk/downloads/?id=25](http://tom-crowley.co.uk/downloads/?id=25)

bit late but here it is
## Post #27
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2014-01-25T07:38:23+00:00
- Post Title: Re: Call of Duty - Ghost - PC - *.pak/*.ff

Great tool, which can extract all textures.
But lots of file decoded like the sample below:-


Please help on this.
## Post #28
- Username: Rkpaarsa
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 20, 2018 11:58 pm
- Post datetime: 2021-02-17T14:01:49+00:00
- Post Title: Re: Call of Duty - Ghost - PC - *.pak/*.ff

> Reply from cra0 ↑Thu Nov 21, 2013 11:58 am at Thu Nov 21, 2013 11:58 am
>
> 
Supports extracting .pak texture archives now someone still needs to help me figure out the dx11 compression they use :/

http://cra0kalo.com/public/COD_GHOSTS_Toolset.zip

The link is broken.  Can you please provide a new one.
## Post #29
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2021-02-22T02:35:37+00:00
- Post Title: Re: Call of Duty - Ghost - PC - *.pak/*.ff

Try again.
