## Post #1
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-10-10T06:32:33+00:00
- Post Title: Alien Isolation (.PAK .BIN)

Working on it..
pm me or reply here if you know much about BC7 BC5 textures



The game uses:
            DXGI_FORMAT_B8G8R8A8_UNORM 
            DXGI_FORMAT_B8G8R8_UNORM
            DXGI_FORMAT_BC1_UNORM
            DXGI_FORMAT_BC5_UNORM,
            DXGI_FORMAT_BC7_UNORM

need a library to read the BC7 ones to something useable
## Post #2
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-10-10T09:03:04+00:00
- Post Title: Alien Isolation (.PAK .BIN)

According to Microsoft's DirectX GI documentation, BC5 is 2 channel 8 bit image.

[http://msdn.microsoft.com/en-us/library ... s.85).aspx](http://msdn.microsoft.com/en-us/library/windows/desktop/hh308955%28v=vs.85%29.aspx)

> Two-channel color   Two color channels (8 bits:8 bits)  - BC5 - Direct3D 10 

So that should be simple to parse.

BC7 is a bit more complicated.

> Three-channel color, alpha channel optional   Three color channels (4 to 7 bits per channel) with 0 to 8 bits of alpha  - BC7 -  Direct3D 11

It's documented here with decompression pseudocode:
[http://msdn.microsoft.com/en-us/library ... s.85).aspx](http://msdn.microsoft.com/en-us/library/windows/desktop/hh308953%28v=vs.85%29.aspx)

and for reference all the DXGI image formats are documented here:
[http://msdn.microsoft.com/en-us/library ... s.85).aspx](http://msdn.microsoft.com/en-us/library/windows/desktop/bb173059%28v=vs.85%29.aspx)

DXGI is low level calls suported directly in graphics hardware. So I doubt there's any existing libraries for decompression. Unless someone here has previously written one.

Edit: more details in this OpenGL document: [https://www.opengl.org/registry/specs/A ... n_bptc.txt](https://www.opengl.org/registry/specs/ARB/texture_compression_bptc.txt)

Also I have found a Library that proports to be able to display BC5/BC7 textures via the "DDSView" Example application included.

Main page: [http://directxtex.codeplex.com/](http://directxtex.codeplex.com/)
DDSView Source: [http://directxtex.codeplex.com/SourceCo ... t#DDSView/](http://directxtex.codeplex.com/SourceControl/latest#DDSView/)
## Post #3
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-10-10T22:20:50+00:00
- Post Title: Alien Isolation (.PAK .BIN)

working on model replacements? like replacing alien with something humorous
## Post #4
- Username: petx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 11, 2014 7:55 pm
- Post datetime: 2014-10-11T12:02:48+00:00
- Post Title: Alien Isolation (.PAK .BIN)

Did you just extract the textures .dds from a Alien Isolation .pak file??
I want to work with the models so if you could explain how did you extract them...
thanks
## Post #5
- Username: alterian
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 12, 2014 2:47 pm
- Post datetime: 2014-10-12T06:56:55+00:00
- Post Title: Alien Isolation (.PAK .BIN)

Hey cra0, do you think you will work on the .pak extraction more? I would like to see the shaders/materials/textures.
## Post #6
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-10-12T07:08:56+00:00
- Post Title: Alien Isolation (.PAK .BIN)

> Reply from alterian
>
> Hey cra0, do you think you will work on the .pak extraction more? I would like to see the shaders/materials/textures.
Maybe would help if I owned the game though :/
## Post #7
- Username: TerryXX
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 12, 2014 8:26 pm
- Post datetime: 2014-10-12T12:35:30+00:00
- Post Title: Alien Isolation (.PAK .BIN)

Hi cra0, these days I was just looking for a extractor, I would try to change a few texture.
Once you have finished the work could you make it accessible??
Thanks so much.
## Post #8
- Username: Crimzan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 13, 2014 3:11 am
- Post datetime: 2014-10-12T19:21:42+00:00
- Post Title: Alien Isolation (.PAK .BIN)

Woow awesome what you achieved so far, cra0 

I didn't expect anybody to get onto the files of this game that quick :O
So did you write an extractor for these files yourself or is there already a program out there which can open these archives?

I would really love to take a look at the Models especially, but checking how the textures look would be awesome as well 

I am really curious to see how all of this turns out. I wish you good luck
## Post #9
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-10-12T20:28:11+00:00
- Post Title: Alien Isolation (.PAK .BIN)

Well the game is made by Creative Assembly, the same people who put out all the Total War: games. They usually include an unpacker with the games for modding. But Since I don't have this game yet, I'm not sure if that unpacker works with Aliens. Would be nice if it did. 

Hopefully by the time I get the game, someone will have figured all that out.
## Post #10
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-10-12T21:56:50+00:00
- Post Title: Alien Isolation (.PAK .BIN)

it's using different engine from their other games. but pak files are fairly simple to exact i should think. bml files will help with modding game itself. xml files are easily accessed, but offer very superficial modding options
## Post #11
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-10-13T02:50:06+00:00
- Post Title: Alien Isolation (.PAK .BIN)

> Reply from volfin
>
> 
Also I have found a Library that proports to be able to display BC5/BC7 textures via the "DDSView" Example application included.

Thanks for this info I'll look into this

> Reply from Crimzan
>
> 
So did you write an extractor for these files yourself?
-EDIT-
Someone showed their genuine support for this and bought me a copy of the game I'll release something soon people can play around with
## Post #12
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-10-13T04:39:13+00:00
- Post Title: Alien Isolation (.PAK .BIN)

[http://aluigi.org/papers/bms/others/alien_isolation.bms](http://aluigi.org/papers/bms/others/alien_isolation.bms)

> Reply from aluigi
>
> No filenames, no compression.
The script is just for the PAK archives.

The BIN files are weird, they are not standard archives, they just contain any data so LEVEL_TEXTURE_HEADERS.ALL.BIN is totally different than MODELS_LEVEL.BIN or RADIOSITY_RUNTIME.BIN.
## Post #13
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-10-13T04:53:07+00:00
- Post Title: Alien Isolation (.PAK .BIN)

beta texture tool
[AITexPAKExtract_0.2.zip](http://dev.cra0kalo.com/?p=182)
## Post #14
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-10-13T05:24:52+00:00
- Post Title: Alien Isolation (.PAK .BIN)

very good. can you decompile the bml files?

also, it seems texture diffuse color are procedurally generated
## Post #15
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-10-13T06:10:36+00:00
- Post Title: Alien Isolation (.PAK .BIN)

Can anyone please help me found fonts or might somone allready know  ? Thx
## Post #16
- Username: petx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 11, 2014 7:55 pm
- Post datetime: 2014-10-13T08:44:21+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Thanks Cra0 for the texture tool. Nice job
Hope to see a model extractor soon to modify maps, weapons, and of course, the Alien.
## Post #17
- Username: TerryXX
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 12, 2014 8:26 pm
- Post datetime: 2014-10-13T11:55:48+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Hi cra0, thank you very much for your work, I immediately tried it and I've already found some problems, I tried to extract a level and I got this error: Warning this texture is unknown.
This is an example:
book_colouring[d].tga.dds.unk 
book_colouring[d].info
TextureInfo
{
  TexPath: ayz\books\book_colouring[d].tga
  Width: 0
  Height: 0

      TexHeader
      {
          magic4:   
          DXGI_FORMAT:134217728
          unk2:29418
          texchunkSize:0
          varSlotSub:25972
          varSlot:13432
          varSlot2:13
          width:0
          unk6:174752
          unk7:43680
          unk8:8388864
          unk9:33554433
          unk10:65792
          unk11:458758
      }

}

Obviously if I try to open the texture photoshop crashes (I use the nvidia plugin for dds), however I have uploaded the file maybe you understand the problem.
[http://www.mediafire.com/download/1okwz ... /books.rar](http://www.mediafire.com/download/1okwzmovdr5nli9/books.rar)
I'm also verifying that not all textures are extracted completely, like this:
## Post #18
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-10-14T01:30:44+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

have you known bml file converter?

also, congratulations on xentax 25 years!
## Post #19
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-10-14T07:09:52+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from TerryXX
>
> Hi cra0, thank you very much for your work, I immediately tried it and I've already found some problems, I tried to extract a level and I got this error: Warning this texture is unknown.

That file is BC7, which he already said in the first post he can't convert yet. He's working on it.

However, some things to note:

The DDS header is missing the Width, Height, and Pitch values. I entered 256 height and 512 width and got this with a BC7 converter:



So shouldn't be to hard to handle. The tricky part will be guessing the missing header values.

Another Converter to add to the list: [http://sourceforge.net/projects/texgenpack/](http://sourceforge.net/projects/texgenpack/)
Seems to have no problem converting BC7. But it does require you get the DLL from a separate project for it to work.
[http://sourceforge.net/projects/libfgen/](http://sourceforge.net/projects/libfgen/)
## Post #20
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-10-14T08:54:13+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from volfin
>
> TerryXX wrote:Hi cra0, thank you very much for your work, I immediately tried it and I've already found some problems, I tried to extract a level and I got this error: Warning this texture is unknown.


That file is BC7, which he already said in the first post he can't convert yet. He's working on it.

However, some things to note:

The DDS header is missing the Width, Height, and Pitch values. I entered 256 height and 512 width and got this with a BC7 converter:



So shouldn't be to hard to handle. The tricky part will be guessing the missing header values.

Another Converter to add to the list: http://sourceforge.net/projects/texgenpack/
Seems to have no problem converting BC7. But it does require you get the DLL from a separate project for it to work.
http://sourceforge.net/projects/libfgen/

Could you zip me up a folder with that including its dependencies I tried getting libpng/libfgen still can't get it to compile

If it all works i can just create a wrapper dll for the extractor and use those functions.


> Reply from TerryXX
>
> Hi cra0, thank you very much for your work, I immediately tried it and I've already found some problems, I tried to extract a level and I got this error: Warning this texture is unknown.
This is an example:
book_colouring[d].tga.dds.unk 
book_colouring[d].info

What archive is this located in?
## Post #21
- Username: TerryXX
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 12, 2014 8:26 pm
- Post datetime: 2014-10-14T12:28:17+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from cra0
>
> 
What archive is this located in?

If I remember correctly it should be in TECH_HUB.
## Post #22
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-10-14T13:28:10+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from TerryXX
>
> cra0 wrote:
What archive is this located in?

If I remember correctly it should be in TECH_HUB.
oops data alignment issue here
[http://dev.cra0kalo.com/?p=182](http://dev.cra0kalo.com/?p=182)

should "work"
## Post #23
- Username: TerryXX
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 12, 2014 8:26 pm
- Post datetime: 2014-10-14T15:11:16+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

I tried and its works, the ones in the format BC7 I think it's the only missing.
## Post #24
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-10-14T15:54:41+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from TerryXX
>
> I tried and its works, the ones in the format BC7 I think it's the only missing.
Missing? Didn't you read what volfin wrote ...
## Post #25
- Username: TerryXX
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 12, 2014 8:26 pm
- Post datetime: 2014-10-14T16:39:19+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Yes I read it, with "missing" I meant need only the support for the BC7 file, for to have a single extractor, always if you want to do of course.
## Post #26
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-10-14T21:50:13+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from cra0
>
> Could you zip me up a folder with that including its dependencies I tried getting libpng/libfgen still can't get it to compile

If it all works i can just create a wrapper dll for the extractor and use those functions.

PMed it to you.
## Post #27
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-10-15T05:26:35+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from TerryXX
>
> Yes I read it, with "missing" I meant need only the support for the BC7 file, for to have a single extractor, always if you want to do of course.
Ah alright yep I've been meaning to make a c# library for DXT11 stuff going to start wrapping directxtex now.


 AITexPAKExtract_0.3.zip
(42.79 KiB) Downloaded 111 times



```
-Fixed image heights being incorrect
-Decodes DXT5 images

```
## Post #28
- Username: alterian
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 12, 2014 2:47 pm
- Post datetime: 2014-10-16T04:00:11+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Hey cra0,

   Thanks so much for your work. 
   I would still like to try to get to some of the materials but they don't use the header style, they use blah.pak/blah_bin.pak/blah_idx_remap.pak. I have pm'd one of the triplets. If you have any thoughts on how to decode these bits I would be really interested.
## Post #29
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-10-16T05:02:59+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from alterian
>
> Hey cra0,

   Thanks so much for your work. 
   I would still like to try to get to some of the materials but they don't use the header style, they use blah.pak/blah_bin.pak/blah_idx_remap.pak. I have pm'd one of the triplets. If you have any thoughts on how to decode these bits I would be really interested.
They are chunked compiled shader code put together If you want to examine shader stuff I would recommend running the game through Intel's Graphic analysis tools.
## Post #30
- Username: IronAwe
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 16, 2014 5:52 pm
- Post datetime: 2014-10-16T09:54:54+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Hey guys,

If any of you happen to come across the in game posters while you're extracting textures, would you shoot a copy my way? Particularly after the ones with the androids in them. Just want to print full size versions for my room.

Cheers guys,

--Iron
## Post #31
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-10-16T16:37:28+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Great job! But do not want you completely unpack this archives? I am very interested in the 3D model.
## Post #32
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-10-19T11:12:57+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Generic PAK unpacker
[http://dev.cra0kalo.com/?p=188](http://dev.cra0kalo.com/?p=188)
getting ready for 3D models and such still need to parse the strings but all in due time!

-edit-

strings parsed need to parse the rest of the file now
## Post #33
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2014-10-22T01:33:59+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

cra0 the demigod delivers yet again.

yet there remains gold yet to be dug.
The sound design in this game is second to none. I speak for everyone when i day i would love to get my hands on it.

Anyway great job Cra0

EDIT: i actually found a converter for the audio right after making this post.
wow talk about ear porn.
## Post #34
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2014-10-22T04:54:08+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Links to AIPAKTool_0.1.zip and AITexPAKExtract_0.3.zip bring blank ad page can can someone verify them.

Thanks
## Post #35
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-10-22T06:55:57+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from Modman69
>
> Links to AIPAKTool_0.1.zip and AITexPAKExtract_0.3.zip bring blank ad page can can someone verify them.

Thanks
They work for me. just standard ad.fly links.
## Post #36
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2014-10-22T13:51:59+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from volfin
>
> Modman69 wrote:Links to AIPAKTool_0.1.zip and AITexPAKExtract_0.3.zip bring blank ad page can can someone verify them.

Thanks
They work for me. just standard ad.fly links.

I had to install a different browser, must have some plugins in firefox that wouldn't allow adfly.

Thanks for checking
## Post #37
- Username: dmsa2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 16, 2014 2:34 am
- Post datetime: 2014-10-22T21:59:19+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Can I ask how to extract all music/audios from Alien?
## Post #38
- Username: freddy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 13, 2009 7:08 pm
- Post datetime: 2014-10-24T19:20:09+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from dmsa2
>
> Can I ask how to extract all music/audios from Alien?

Try this method - [viewtopic.php?f=17&t=7792&start=15](http://forum.xentax.com/viewtopic.php?f=17&t=7792&start=15)
--- Guide: Converting .wem to .ogg
## Post #39
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-10-31T17:51:17+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Any news about unpack 3d models?
## Post #40
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-11-01T01:32:00+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from erik945
>
> Any news about unpack 3d models?
These things take time and I have been fairly busy. However ive identified the vertices/faces etc for each model/sub model object I just need to piece it all together. If anyone is interested in helping let me know
## Post #41
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-11-01T06:39:09+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Thank you!
I can help with maxscript import.
## Post #42
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-11-03T05:12:48+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

If someone can provide an example or two of the models, i can start working on a blender importer. I won't be able to get the game until it goes on sale (which might not be til Dec.)
## Post #43
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-11-03T23:05:45+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

k volfin helping is out
## Post #44
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-11-05T05:08:26+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

What about me?
## Post #45
- Username: magister
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 07, 2014 3:52 am
- Post datetime: 2014-11-06T20:11:23+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Here examples of 3d models (.omodel in-game format).
Awaiting for max or blender importer.
[http://rghost.net/58925925](http://rghost.net/58925925)
## Post #46
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-11-06T20:43:25+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Ok, no problem.
We need to open a new topic in 3d, or write here?
## Post #47
- Username: magister
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 07, 2014 3:52 am
- Post datetime: 2014-11-06T23:11:33+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Ok, start topic in 3d. This topic about resource xtaction, hmmm.
## Post #48
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-11-07T12:26:28+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from magister
>
> Ok, start topic in 3d. This topic about resource xtaction, hmmm.
no the paks and bins both are essentially the models themselves. I'm working on understanding the structures more and so is volfin
## Post #49
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2014-11-09T08:46:35+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

There is a problem when trying to unpack UI.PAK. Looks like it already contains the headers within it.
AIPAKTool:

```
 ---Version 0.1---
 ---Authors: Cra0kalo---
 ---http://dev.cra0kalo.com ---

Starting...
----------------------------------------------------------------------------
InputFile: UI.PAK
InputFilePath: D:\_temp\UI.PAK
ExportPath: D:\_temp\_extracted

Initalizing PAK Export..
Reading Package
----------------------------------------------------------------------------
----------------------------------------------------------------------------
ERROR: looking for blank 4bytes
----------------------------------------------------------------------------
----------------------------------------------------------------------------
Fault detected ParseMTL() Skipped!
Fault detected Export() Skipped!
Fault detected Cleanup() Skipped!
----------------------------------------------------------------------------
----------------------------------------------------------------------------
An error has occurred somewhere during the export processs.
----------------------------------------------------------------------------
----------------------------------------------------------------------------
```

AITexExtract:

```
----------------------------------------------------------------------------
ERROR: looking for blank 4bytes
----------------------------------------------------------------------------
----------------------------------------------------------------------------
```

There are two UI.PAK files:
...\DATA\UI.PAK
...\DATA\GLOBAL\UI.PAK

Also there are some .dds files labeled as "flash" which cannot be recognized correctly by WTV, NVIDIA DDS Plugin and texgenpack.
e.g.: screen_anim_int_13[flash].tga.dds (...\DATA\ENV\GLOBAL\WORLD\GLOBAL_TEXTURES.ALL.PAK\ayz\flash\)
screen_anim_int_13[flash].info:

```
{
  TexPath: ayz\flash\screen_anim_int_13[flash].tga
  Width: 1024
  Height: 760
  ChunkSizeA: 3112960
  ChunkSizeB: 3112960
  
      TexHeader
      {
          magic4:tex4
          DXGI_FORMAT:DXGI_FORMAT_B8G8R8A8_UNORM
          unk2:0
          texchunkSize:3112960
          varSlotSub:1024
          varSlot:760
          varSlot2:1
          width:1024
          height:760
          unk6_a:1
          unk7:65537
          unk8:65
          unk9:268435456
          unk10:6721
          unk11:0
      }
        
}

```
## Post #50
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-11-09T10:38:13+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

about 3d models...
Very strange data structure.
0x0000 first 4 bytes - unknown.
0x0004 - int32 - number of objects.

0x0014 - records about the objects
format:
- Unknown int32, usually 0
- Object number int32 BigEndian (BigEndian on PC ???)
- Offset from the beginning file of the object's body int32 BigEndian
- Unknown int32

The body of the object is divided into two parts.

First - presumably - information about the vertices.
At each vertex allocated 8 bytes - it is very small, only 2 coordinates in the format of the float, but the data in the file - do not look like a valid float (very large scatter in the values of the E-38 to E + 40, it seems that the data compressed, or use exotic encoding as varint ([https://golang.org/src/pkg/encoding/binary/varint.go](https://golang.org/src/pkg/encoding/binary/varint.go)), or  errors).
Example - entru447.omodel - offset 0x0070

The second - the indices of vertices in the polygon.
LitleEndian unsignd shorts (2 bytes)

Are you sure you unpaker working correctly?
## Post #51
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-11-11T02:51:46+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from erik945
>
> about 3d models...
Very strange data structure.
0x0000 first 4 bytes - unknown.
0x0004 - int32 - number of objects.

0x0014 - records about the objects
format:
- Unknown int32, usually 0
- Object number int32 BigEndian (BigEndian on PC ???)
- Offset from the beginning file of the object's body int32 BigEndian
- Unknown int32

The body of the object is divided into two parts.

First - presumably - information about the vertices.
At each vertex allocated 8 bytes - it is very small, only 2 coordinates in the format of the float, but the data in the file - do not look like a valid float (very large scatter in the values of the E-38 to E + 40, it seems that the data compressed, or use exotic encoding as varint (https://golang.org/src/pkg/encoding/binary/varint.go), or  errors).
Example - entru447.omodel - offset 0x0070

The second - the indices of vertices in the polygon.
LitleEndian unsignd shorts (2 bytes)

Are you sure you unpaker working correctly?
Yes exporter works fine

```
{
   uint32   hookTagIndex;
   uint32   tableA_count;
   uint32   ozero1;
   uint32   ozero2;
   uint32   ozero3;
   uint32   ozero4;
} omdlhead;

typedef struct
{
   uint32   valFlagCounter; //goes up?
   uint32   localOffset;
   uint32   localSize;
   uint32   azero;
} omdltableA;


```


Vertex shader signature 

```
// -------------------- ----- ------ -------- -------- ------- ------
// POSITION                 0   xyzw        0     NONE   float   xyz 
// NORMAL                   0   xyz         1     NONE   float       
// TANGENT                  0   xyz         2     NONE   float       
// BINORMAL                 0   xyz         3     NONE   float       
// BLENDINDICES             0   xyzw        4     NONE    uint   xyzw
// BLENDWEIGHT              0   xyzw        5     NONE   float   xyzw
// TEXCOORD                 0   xy          6     NONE   float       
// TEXCOORD                 7   xy          7     NONE   float       
// SV_VertexID              0   x           8   VERTID    uint   x   

```


Still trying to find how they are packing these
## Post #52
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-11-11T07:43:13+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Ok , thank you. I will trying find it.
Can you suggest any literature on the analysis of the compressed stream.
## Post #53
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2014-11-12T00:02:41+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Not sure how the person figured it out but looks like 2 weapons from the game were exported and are on the Fallout NV Nexus. Pretty much surprised me seeing models there but no place else as of yet.
## Post #54
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-11-12T00:12:15+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from Nintendude
>
> Not sure how the person figured it out but looks like 2 weapons from the game were exported and are on the Fallout NV Nexus. Pretty much surprised me seeing models there but no place else as of yet.
Dunno ask the author could have been ripped via ninja_ripper certainly dont think they did it via the actual files
## Post #55
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2014-11-12T01:43:35+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

OK, that is interesting. I don't know much about programming but I decided take a look at screen_anim_int_13[flash].tga.dds file via a hex editor and this is what I see:

Looks like the file is somehow corrupted. Because this is all it shows until the end of the file: "00 00 00 FF 00 00 00 FF..."
## Post #56
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-11-12T06:22:08+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Nintendude you can extract weapons and equipment via ninja_ripper.
Characters - only without texture coordinats.
## Post #57
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-11-20T05:45:18+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

I found a small bug in cra0's Texture extract tool, and he fixed it, asked me to post the fixed version. Images with DXGI_FORMAT:DXGI_FORMAT_B8G8R8A8_UNORM were not getting channel bitmasks in the DDS header added, so would appear blank. Now the h eaders are formed properly. Thanks for the quick fix, cra0.  
[AITexPAKExtract_0.4.zip](https://xentaxbackup.github.io/file/8102_AITexPAKExtract_0.4.zip)
## Post #58
- Username: magister
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 07, 2014 3:52 am
- Post datetime: 2014-11-20T20:08:17+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

No news for 3d stuff extract?
Awaiting still.
## Post #59
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-11-21T01:13:35+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from magister
>
> No news for 3d stuff extract?
Awaiting still.
I'm working on titanfall maps currently but yeah we still working on it..
## Post #60
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-11-26T05:33:26+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

[http://dev.cra0kalo.com/?p=226](http://dev.cra0kalo.com/?p=226)
Updates

Oh look folder structures
## Post #61
- Username: TerryXX
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 12, 2014 8:26 pm
- Post datetime: 2014-11-26T14:19:45+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Cool cra0 really good work
## Post #62
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-11-27T10:32:45+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Wow! How you read "compresed" data block?
## Post #63
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-11-27T18:20:44+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from erik945
>
> Wow! How you read "compresed" data block?
Which data block do you refer to?
## Post #64
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-12-01T06:09:08+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Some progress shots by volfin and I
## Post #65
- Username: TerryXX
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 12, 2014 8:26 pm
- Post datetime: 2014-12-01T13:22:21+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Nice Job Guys
## Post #66
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-12-01T14:01:46+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

volfin - for example "compressed data" - [http://rghost.net/58925925](http://rghost.net/58925925), entru447.omodel - offset 0x0070

cra0 - what about skined models (characters)?
## Post #67
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-12-01T18:25:09+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from erik945
>
> volfin - for example "compressed data" - http://rghost.net/58925925, entru447.omodel - offset 0x0070

cra0 - what about skined models (characters)?

yeah it turns out it's not compressed, just packed data. 

And Skinned models is what i'm working on now. looks like we can recover original weighting. but we still need to dig into skeletal data.
## Post #68
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-12-01T19:12:14+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Thank you!
Can you explain how they packaged?
## Post #69
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-12-01T22:58:07+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from erik945
>
> Thank you!
Can you explain how they packaged?

well it's a bit complicated. So far we've identified 20 different data formats (and growing). but basically it's verts/uvs packed as integers in one table, followed by a secondary table of normals/color/secondary UVs, etc. then a 3rd table of face data.
## Post #70
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2014-12-02T02:02:24+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Awesome stuff guys. Very pleased to hear you should be able to get bone weights. Looking forward to more progress. 

Side note: did they seriously name Amanda's underwear model "naked" in the files?
## Post #71
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-12-02T03:48:15+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from ssringo
>
> 
Side note: did they seriously name Amanda's underwear model "naked" in the files?

Yep. and its just legs, front of the pelvis, and abdomen, with arms. The model doesn't even have a butt, breasts, or a head. XD I guess their standards of naked are somewhat strange.
## Post #72
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-12-02T06:33:55+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

nice. maybe now someone mod the alien to be not so robotic. and no more stupid survivors who shoot you :rolleyes:
## Post #73
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2014-12-02T07:05:18+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from volfin
>
> ssringo wrote:
Side note: did they seriously name Amanda's underwear model "naked" in the files?  

Yep. and its just legs, front of the pelvis, and abdomen, with arms. The model doesn't even have a butt, breasts, or a head. XD I guess their standards of naked are somewhat strange.

That's hilarious. Disappointing as well. I wasn't expecting her underwear model to be fully functional with a properly rigged skeleton but I was hoping it would be fairly complete in order to combine her head, skeleton and bone weights from her normal model with it. Sounds like too much is missing and completely fixing it up would require substantial work (above my skill level). That or just using a completely separate body which I'm not a big fan of as you still need to do a good bit of work to make the body proportions correct and too many people that do those kind of meshmods don't bother fixing proportions. 

No big loss though. Plenty of DoA models if I want scantily clad girls.  I'm more interested in getting her normal model along with the Nostromo crew anyways.
## Post #74
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-12-02T08:11:37+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

volfin Very interesting ... I can ask you a script or source of plugin to import? Just for interest, undertake not to distribute it.
## Post #75
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-12-02T19:12:06+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from erik945
>
> volfin Very interesting ... I can ask you a script or source of plugin to import? Just for interest, undertake not to distribute it.

Cra0 and I are still working on an exporter. There's still quite a bit to do, found another 10 formats to deal with just yesterday. Soon (tm)
## Post #76
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-12-02T20:01:54+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Ok, no problem. Thank you!
## Post #77
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-12-03T00:37:45+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Ok here's a QuickBMS script i want to release, that dumps PAK2 type PAK files. (like ANIMATION.PAK and UI.PAK) These are a different format than the model PAK files.

```
#  Alien: Isolation PAK unpacker
#  Author: Volfin
#  Version: 1.0
########################33
open FDDE PAK 0
endian little

get signature long 0
if signature != 0x324B4150
   print "File is not the correct format (PAK2)"
   cleanexit
endif

get Strs_Length long 0
get Strs_Count long 0
get pointer_size long 0
print "# of entries: %Strs_Count%"
print "pointer size: %pointer_size%"
# create offset to pointers
math Strs_Length + 16
#create offset to Data
xmath Data_ptr "Strs_Length + Strs_Count * pointer_size"

SavePos str_pos 0
print "string_pos: %str_pos%"
print "Data_ptr: %Strs_Length%"
print "Data_pos: %Data_ptr%"

for i = 0 < Strs_Count

    GoTo str_pos
	# read in first string
	get p_name string 0
	# save position
	SavePos str_pos 0
	# jump to pointer data
	GoTo Strs_Length
	#read in pointer
	get D_end long 0
	# save new location
	SavePos Strs_Length 0	
	# handle 16 byte padding
	GoTo Data_ptr
	Padding 4 
	SavePos Data_ptr
	# save data; length is D_end - current location
	xmath size "D_end - Data_ptr"
	log p_name Data_ptr size
	math Data_ptr + size
next i
cleanexit

```


This let me take a look at the skeleton files, and as I feared they are Havok *.hkx type. So most likely will not be able to create skeletons for the models. (Unless someone knows how to decode Havok 2012.2.0 HKX files).
## Post #78
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-12-03T03:41:01+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from volfin
>
> This let me take a look at the skeleton files, and as I feared they are Havok *.hkx type. So most likely will not be able to create skeletons for the models. (Unless someone knows how to decode Havok 2012.2.0 HKX files).
Shakotay knows how to get bones from Havok 2011 files, he's done it multiple times for Sleeping Dogs before. 

The format hardly changed from 2011 to 2013, so I can't imagine that 2012 will be that different. It's worth a try at least.
## Post #79
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-12-03T09:24:50+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

There's no any problem in getting .hkx skeletons to work. I did this for several games like dead space, strider, kuf2 and so on. So, if they are raw, native .hkx files - don't worry  The only problem is animation, but it's also could be converted to 3ds max importable files.
## Post #80
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-12-03T22:02:14+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from zaramot
>
> if they are raw, native .hkx files
Problem is, they're always in binary format, and I've heard that it differs from game to game. 
I did manage to dig up a few things but nothing ever really happened since absolutely nobody was interested.

[I've made a thread on this topic here](http://forum.xentax.com/viewtopic.php?f=21&t=11155). It's mostly for Sleeping Dogs havok files but I suppose it can be expanded to include these as well.
## Post #81
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-12-04T02:28:03+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Yeah i've decided for this game to just parse the hkx file directly to get the skeletal data. the format is a pita. But I'm making some progress in mapping it out. It's going to be "just enough" for the skeletons this game uses, as trying to suppport everything HKX supports would be a nightmare.
## Post #82
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-12-12T12:02:58+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Progress update:
[http://www.youtube.com/watch?v=0978PBhQMhY](http://www.youtube.com/watch?v=0978PBhQMhY)

Shots
[http://puu.sh/dlSxW.jpg](http://puu.sh/dlSxW.jpg)
[http://puu.sh/dlTBj.jpg](http://puu.sh/dlTBj.jpg)
## Post #83
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-12-12T18:25:17+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Good news!
When planning to release?
## Post #84
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-12-12T22:00:00+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Well, I'm still working on the skeleton conversion (prototyping done, production code in progress), and as you probably notices from the pictures/Video, many of the models use greyscale textures with separate color data. Cra0 is working on decoding the material files so the coloring can be done properly. So, still a bit of work to do.
## Post #85
- Username: TerryXX
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 12, 2014 8:26 pm
- Post datetime: 2014-12-13T11:54:14+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

cra0 continues like this you are the best
## Post #86
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-12-16T04:56:20+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

I've finished the HKX to SMD converter. One more step down.
## Post #87
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-12-16T07:37:25+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Quickly running.
There is only skin?
## Post #88
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2015-01-07T14:58:52+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Awesome job, guys. Any progress?
## Post #89
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-01-08T04:08:31+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from IvoryCutter
>
> Awesome job, guys. Any progress?
Next week should see something
## Post #90
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-01-18T19:48:03+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from cra0
>
> IvoryCutter wrote:Awesome job, guys. Any progress?
Next week should see something

What news?
## Post #91
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2015-01-18T22:00:52+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

soon (tm)

We underestimated how done we were.   

when we started unpacking the rest of the game we found more formats (there are over 130 model formats lol)

So we had to scrap how we handled all that, it got to be too much. We now use a lookup table system. I have my Blender importer done, and the skeleton converter done, just waiting on Cra0 to update the unpacker.
## Post #92
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-01-18T22:06:22+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Ok, waiting...
## Post #93
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2015-01-22T03:39:03+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Ok, so here is the Blender plugin for loading Alien: Isolation models. io_scene_Aliens.zip is a plugin for Blender 2.66 and above.
  Let me say that again so there is no misunderstanding:

                                   for Blender 2.66 and above

You must install it as an add-on through Blender Preferences. If you don't know how to do that, here's a short tutorial:

How to Install a Blender add-on

1. Download the addon. (in this case io_scene_Aliens.zip).  Do NOT Unzip the file!  Blender takes the zip as an install package.

2. Start Blender and go to to File->User Preferences.


3. Go to the Addons tab, and click the "Install from File..." button at the bottom.


4. From the File picker choose the "io_scene_Aliens.zip" plugin file you downloaded. Once Selected, press "Install From File..." on the picker dialog.

5. The Add-On will be featured on the Addons Pane, but currently disabled. Check the Box on the right-hand side (or in newer versions on the left side) to enable the plugin, and then press "Save User Settings" to save the changes.  Then close the User Preferences pane.

Newer versions:


6. The Import for Alien:Isolation pObject models will now be available.


When Importing a file with the Plugin, there will be 3 options available:


[*] Import Vertex Colors:  This will import extra data present in the models as vertex colors (if present).
[*] Normalize Weights: This will run a normalizing function on the bone weights. (probably not needed but you never know)
[*] Alt Load:  Due to some ambiguity in a small percentage of model definitions, some models may not load correctly by default. If you come across a model that fails to load normally, try loading it with the Alt-Load option checked, and it should load.  

Note that this plugin loads pObject model types exported by Cra0's upcoming PAKTool for Alien: Isolation. It should be released shortly.

I'll be following up this post with additional information about how to assemble rigged models with their skeleton.

EDIT: Latest version now on this post: [http://forum.xentax.com/viewtopic.php?p=125897#p125897](http://forum.xentax.com/viewtopic.php?p=125897#p125897)
## Post #94
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-01-22T04:51:17+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Heres the paktool
[http://rel.cra0kalo.com/depot/AlienIsol ... ol_2.0.zip](http://rel.cra0kalo.com/depot/AlienIsolation_PAKTool_2.0.zip)

> Created by Cra0kalo & Volfin
>
> 
>
> Alien Isolation PakTool
>
> 
>
> What it supports??
>
> *Unpack of Model PAKS
>
> *Unpack of UI PAKS
>
> *Unpack of Animation PAKS
>
> 
>
> What is required?
>
> *.NET Frameworks 4.5
>
> 
>
> 
>
> Help support questions?
>
> twitter: @cra0kalo
>
> Xentax thread: 
>
> (this)

Coming later (im busy for now)
## Post #95
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2015-01-22T04:57:16+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Assembling the Alien: A rigged model example

I'll take you though the steps of assembling the parts and skeleton for the Alien from Isolation.

First off, you should get the hktcnv.zip file attached.  This is the Conversion tool to convert the HKX skeletons to SMD format.

You will also need the SMD import/Export Plugin for Blender. That's available here from Valve's Website: 
EDIT: The current Version of Valve's Source tools is broken. Please use the version below (2.2.1)  You install it basically the same as io_scene_Aliens plugin.

First off, lets find the model parts for the Alien: Assuming you've unpacked a Level PAK file into '_extractedModels' directory, you can find the rigged models under '_extractedModels\CHARACTERS' and pretty much every Level has the Alien. Sure enough, there's a '_extractedModels\CHARACTERS\ALIEN' directory. 

You may also see other models such as 'CONNOR', 'CONNER_FP' etc. These folder names are important, because they are how you find the skeleton. The skeleton file will be named the same as the character folder name. We will get back to that later.

to get to the character's pObject files, we'll have to go deeper. '_extractedModels\CHARACTERS\ALIEN\model0.cs2' brings you to several folders:

[*]'ALIEN': this is the main model. Also the LOD model is included in here.
[*]'COL_ALIEN': This is the physics shape for the alien (low detail). It's also rigged.
[*]'crusher':  this is the pieces for the scary little mouth that comes out of the big mouth. (ick)
[*]'SHELL01': These are a couple of layers that go on top of the alien's head for special effects (transparency layers)
[*]'SKULL01': This is the main bony plate on top of the head (under the layers)

You may wonder why some parts are in separate folders. Heck if I know. 

So to load the model, you have to load in *all* of the pieces you need to make the complete model, one at a time. Because the main 'ALIEN' Directory has the LOD model as well, you have to be a little careful, and stop loading when you see duplication of parts that you have already loaded.

For the Alien, the first 8 models are the Highest LOD. the Lower LOD is the last 7 parts.

Once you load the 8 parts, you'll have this: 


Once you load in the crusher parts and the skull top, the beast will be complete:


The model imports with full, original weights. so to finish this up, we only need a skeleton.

From here on i assume you've unpacked the ANIMATION.PAK into directory '_extractedAnims'. Head there now, into directory
'_extractedAnims\DATA\ANIM_SYS\SKELE\SK'.  This is the directory that contains the Skeleton HKX files. Find the one with the name of the model you are working on. In this case "ALIEN".


Now you know why we noted the model name. They should be an exact match.  Now we will convert this file using hktcnv.exe

copy the hktcnv.exe and the HXK skeleton file somewhere and drag-drop the HKX onto the EXE. it will give some debug info and  create an SMD skeleton file from the HXK. 


Now all we have to do is load this SMD into blender using the SMD importer you installed earlier.  Bring up the SMD import, but before using it, be sure you set these options correctly:


[*] Be sure "Append to Existing Model" is unchecked. This ensures the skeleton is created as a discrete object.
[*] I also recommend you set Bone Shapes to "Default" but you can use your preference.

Import the SMD, and you'll get the skeleton.


NEW: Because of a change to the importer, you now must Flip the Armature on the X Axis before attaching it to the model. To do this, select the Armature. Then go to Object->Mirror->X Global, and press Enter to apply.


Now to make the skeleton work with the model, all we simply have to do is apply an Armature modifier to each part of the model, so it knows to use the skeleton as it's reference.

First Right click a model part. Then Shift-Right-Click the skeleton. (This keeps both selected, but with the skeleton being selected last).  Now press Ctrl-P and pick "Armature Deform" to assign the Armature to that mesh. Do this for all the parts.


Once you've added the Armature modifer to all the parts, you can pose as you like. 


-------------------------------
To Clarify one point, we know this is a bit of a pain to assemble, so as you see above this post, Cra0 is working on a program to create an all-inclusive SMD with all the parts and skeleton all integrated into one file. However, this will take some time. So because we know people have been waiting patiently for something, we release this less-elegant solution for now.  Enjoy. 
[hktcnv.zip](https://xentaxbackup.github.io/file/8537_hktcnv.zip)
## Post #96
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-01-22T05:47:25+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Holy smokes that is a lot of work! I don't have the time tonight to try to get a model completely put together but I did want to at least try the tools out. cra0's unpacker worked fine and I extracted a couple of different levels (does any level have the full Ripley model or is that in a cutscene file?). Looking forward to the automated tool to get the models put together   Went with the Torrens level for checking out the human models. 

Volfin's blender plugin worked without issue on 2.70. Started putting together Taylor's model (only did from the waist up) and everything seemed to import just fine and looked good. That was as far as I got for tonight. Will probably wait until Friday after work to try putting an entire model together. 

Thank you both for your hard work on the tools. I greatly appreciate being able to play around with the awesome models in the game and put them into other games.
## Post #97
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2015-01-22T08:03:14+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

nice, can you edit the legs to be normal(non digitigrade) and import it back into the game?
## Post #98
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-01-22T08:37:00+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Look at the code and stunned. Guys - you are awesome! Thank you!
## Post #99
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2015-01-22T18:02:21+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from ssringo
>
>  I extracted a couple of different levels (does any level have the full Ripley model or is that in a cutscene file

Amanda Ripley's model is in most levels under RIPLEY_FP, SPACESUIT_RIPLEY_FP.

The original Ellen Ripley is only in the DLCs, like Challengmaps. There she is under E_RIPLEY_FP.
## Post #100
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-01-22T22:15:21+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Sigh, that's what I get for derping and assuming instead of checking each model out. The model I looked at turned out to be Amanda's first person flight suit model so I assumed the the "FP" on folders meant it was "first person" and would be missing parts. 

Apologies for wasting your time.
## Post #101
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2015-01-23T01:07:32+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

I updated the importer plugin based on some issue reports. Should work better for some models.

Also, despite Valve's Wiki saying Blender Source Tools works for Blender 2.66+, it seems the wiki is inaccurate; To use their plugin you need at least Blender 2.71. So if you intend to work with the skeleton, you will need at least Blender 2.71.
## Post #102
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2015-01-23T01:33:11+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Annnnd, after trying their latest version of their SMD plugin, they broke it somehow. So I'm attaching the version that works (2.2.1)

If the newer version somehow works for you, great, but I can't get it to work, only 2.2.1 works for me.
EDIT: no longer required, latest version of SMD plugin is fixed.
## Post #103
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2015-01-23T02:31:12+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Hey guys! 

Volfin and Cra0, you guys are doing amazing work! I've managed to noodle around and get the models working in blender and everything properly, but I can't seem to get the textures extracted properly. I get the feeling I'm overlooking something simple (I'm relatively new to it all), but I've followed the README to the letter and the extracted texture files all end up looking like this...

Browsing through, I can see a small number of files came out with actual imagery, but I can't figure out why the others haven't.

Any help would be greatly appreciated!

Keep up the great work! The models came out great!
[new.JPG](https://xentaxbackup.github.io/file/8546_new.JPG)
## Post #104
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-01-23T02:54:25+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from trexjones
>
> Hey guys! 

Volfin and Cra0, you guys are doing amazing work! I've managed to noodle around and get the models working in blender and everything properly, but I can't seem to get the textures extracted properly. I get the feeling I'm overlooking something simple (I'm relatively new to it all), but I've followed the README to the letter and the extracted texture files all end up looking like this...

Browsing through, I can see a small number of files came out with actual imagery, but I can't figure out why the others haven't.

Any help would be greatly appreciated!

Keep up the great work! The models came out great!
BC5 BC7 textures are not really supported you will need to use something like texconvert to convert them to another file format

Make 2 batch scripts 1 of which has this

```

```


call it ctex_all.bat

Then the 2nd one will have this

```
texconv -f BC3_UNORM -ft DDS %1 -px converted_
```


call it ctex_c.bat

Download texconv 
[https://directxtex.codeplex.com/wikipage?title=Texconv](https://directxtex.codeplex.com/wikipage?title=Texconv)

place it in the same directory as the 2 batch files. Place ur dds texture next to them and run the first batch script. The result should be converted valid DDS files in the form of BC3
## Post #105
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2015-01-26T03:55:55+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

I've updated the Blender Importer to 1.02.  It was discovered the models were being imported Flipped on their X axis from how they were in-game. (hard to detect on characters, but became apparent on some static models)
## Post #106
- Username: magister
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 07, 2014 3:52 am
- Post datetime: 2015-02-02T22:10:14+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

I got error when import skeleton.
[](http://www.imagebam.com/image/89c089386733849)
## Post #107
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2015-02-03T00:24:27+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from magister
>
> I got error when import skeleton.

yes, that's one of the many errors I got when using valve's latest version of the SMD tools. Why I attached the older version to this thread. (here:  [viewtopic.php?p=103157#p103157](http://forum.xentax.com/viewtopic.php?p=103157#p103157)  ) You should use that older version. be sure to remove the newer plugin version first, and start  new scene to make sure it uses the older version.

I reported the problems to the plugin creators, but they seem not too interested in fixing their plugin.
## Post #108
- Username: magister
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 07, 2014 3:52 am
- Post datetime: 2015-02-03T11:13:12+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from volfin
>
> magister wrote:I got error when import skeleton.


yes, that's one of the many errors I got when using valve's latest version of the SMD tools. Why I attached the older version to this thread. (here:  viewtopic.php?p=103157#p103157  ) You should use that older version. be sure to remove the newer plugin version first, and start  new scene to make sure it uses the older version.

I reported the problems to the plugin creators, but they seem not too interested in fixing their plugin.
Same result.
Used Blender 2.72 win 7 64
[](http://www.imagebam.com/image/762fe4386865363)
UPD: Trouble solved. In windows 7 language regional settings changed comma to point in decimal divider.
## Post #109
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2015-02-03T20:37:49+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from magister
>
> UPD: Trouble solved. In windows 7 language regional settings changed comma to point in decimal divider.

Really? Software shouldn't be using regional settings for internal functions. That should only be for user display. Shame on blender (or Valve) for doing that. But glad you found the solution.
## Post #110
- Username: magister
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 07, 2014 3:52 am
- Post datetime: 2015-02-08T16:05:48+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Ellen Ripley extracted and ported.
[http://tf3dm.com/3d-model/ellen-ripley-90347.html](http://tf3dm.com/3d-model/ellen-ripley-90347.html)  xps .mesh format
[http://tf3dm.com/3d-model/puo-65784.html](http://tf3dm.com/3d-model/puo-65784.html) .obj .dae formats
## Post #111
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-02-13T05:12:59+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

[http://rel.cra0kalo.com/depot/AlienIsol ... ol_2.1.zip](http://rel.cra0kalo.com/depot/AlienIsolation_PAKTool_2.1.zip)

Works for ps3 version of the game (someone requested) u need to specify --endianBIG though


so like

--meta --endianBIG -p  O:\RamBox\alien\UI.PAK O:\_extractedPAK

and it will work in big endian mode
## Post #112
- Username: Joonie86
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jul 27, 2014 7:05 pm
- Post datetime: 2015-02-13T05:19:40+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from cra0
>
> http://rel.cra0kalo.com/depot/AlienIsol ... ol_2.1.zip

Works for ps3 version of the game (someone requested) u need to specify --endianBIG though


so like

--meta --endianBIG -p  O:\RamBox\alien\UI.PAK O:\_extractedPAK

and it will work in big endian mode

Thanks my friend, I appreciate your hard work  now I can continue my project
## Post #113
- Username: A20Group
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Nov 28, 2014 12:36 am
- Post datetime: 2015-03-02T15:26:40+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Hi 
How To Repack .Pak File?
Thanks
## Post #114
- Username: magister
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 07, 2014 3:52 am
- Post datetime: 2015-03-06T18:28:05+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Must port captain Dallas.
## Post #115
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2015-03-07T07:09:07+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

the game was originally 3rd person. so therefore these models can be used in conjunction with the player animations and pull the camera out and back.
## Post #116
- Username: racket
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 20, 2015 9:44 pm
- Post datetime: 2015-03-20T13:53:06+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from cra0
>
> Coming later (im busy for now)

Hi - thanks for all your work cra0 + volfin.

@cra0: Any chance for some sort of beta download of the Object Assembler you were showing? Basically I'm just looking for a nice way to get Props/Environment over into 3ds Max including the textures.

I'll try out the Blender to 3ds Max workflow.. but your tool would certainly make that process way way easier.

Cheers!,
racket.
## Post #117
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-05-24T06:05:34+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

I have some problem with extraction normal maps.
I extract textures with AITexPAKExtract_0.3/4 and converted it with two tools - texconv and texgenpack.
[https://directxtex.codeplex.com/releases/view/612866](https://directxtex.codeplex.com/releases/view/612866)
[https://github.com/hglm/texgenpack](https://github.com/hglm/texgenpack)

most textures converted correct but normal map - don't.
texgenpack - Error -- unsupported format in .dds file (fourCC = ATI2, DX10 format = 0)
texconv  - reading filename FAILED (80004005)
may be problem with fileheader?
## Post #118
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2015-05-26T13:40:21+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Has anyone figured out where the complete models for Amanda can be found? I'm only ever able to find partial ones... Do they even exist?
## Post #119
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-05-26T16:47:15+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

No, it doesn't exist.
## Post #120
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2015-05-27T11:36:35+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Bummer... Oh well. Has anyone else been hit with this particular problem?
[glitch.JPG](https://xentaxbackup.github.io/file/9233_glitch.JPG)
## Post #121
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-05-27T19:39:29+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

trexjones you use very long path and name.
Move file up to the root of the disk.
as example:
D:\AIUnp\BSP_LV426_PT02\RENDERABLE\_models
or more short.
## Post #122
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2015-05-28T18:21:48+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

AH! Excellent! Makes perfect sense! Thank you!!
## Post #123
- Username: IFFY
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Dec 13, 2014 8:05 pm
- Post datetime: 2015-06-09T09:52:44+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

I was export the 3d models. thank you! 
but I'm raelly sorry, still I don't know how to unpack animation files and textures.
everytime I fail like this.



please help me please! x0
## Post #124
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2015-06-09T23:35:55+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

I've already managed to export the models and textures and rigging, I just need someone that can put the textures on and they're good to be released.
## Post #125
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2015-06-11T07:31:01+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Okay, so, gathering up the textures and everything was a bit of a nightmare, and I am by no means an expert at rigging or anything else, but using the tools available, I've managed to grab what I can from the game so people can put these together. Hope they help.

Samuels: [https://mega.co.nz/#!P8E2hIQD!KzIX4KDBV ... syMsNU0AYE](https://mega.co.nz/#!P8E2hIQD!KzIX4KDBVlIGJZH6FpGYEEKFTK4HgSEntsyMsNU0AYE)


Axel: [https://mega.co.nz/#!uwMwWSTC!kxDC-VPOs ... UD6uN96QIE](https://mega.co.nz/#!uwMwWSTC!kxDC-VPOsbfcxJT0D5H76gsRFQELax5yRUD6uN96QIE)


Ricardo: [https://mega.co.nz/#!zldW3DIa!v2YDBIKR_ ... Ky-IKgoVw0](https://mega.co.nz/#!zldW3DIa!v2YDBIKR_3eu5IkI7DzkPebOsDxWIX4rIKy-IKgoVw0)


If you use them for anything, please let me know. I'd love to use them myself in XPS.
## Post #126
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2015-06-12T06:35:56+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

why? they look generic as fuck
## Post #127
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2015-06-15T16:03:23+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

More models. Same deal as always.


DALLAS: [https://mega.co.nz/#!zgdF2RAB!Ca8CG2jr_ ... X8-72z8tFQ](https://mega.co.nz/#!zgdF2RAB!Ca8CG2jr_ZfV_u08Z8eI6tucKJ5JkXDtBX8-72z8tFQ)


WORKING JOE: [https://mega.co.nz/#!D9UGyADD!N_qddWbc- ... wep7ODB7ZQ](https://mega.co.nz/#!D9UGyADD!N_qddWbc-xNaF9AjeDRftWWOQOeh7WiF5wep7ODB7ZQ)
## Post #128
- Username: MattFiler
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 20, 2015 8:47 am
- Post datetime: 2015-06-20T00:48:37+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from trexjones
>
> Okay, so, gathering up the textures and everything was a bit of a nightmare, and I am by no means an expert at rigging or anything else, but using the tools available, I've managed to grab what I can from the game so people can put these together. Hope they help.

Samuels: https://mega.co.nz/#!P8E2hIQD!KzIX4KDBV ... syMsNU0AYE


Axel: https://mega.co.nz/#!uwMwWSTC!kxDC-VPOs ... UD6uN96QIE


Ricardo: https://mega.co.nz/#!zldW3DIa!v2YDBIKR_ ... Ky-IKgoVw0


If you use them for anything, please let me know. I'd love to use them myself in XPS.

These all seem to of been taken down.
## Post #129
- Username: MattFiler
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 20, 2015 8:47 am
- Post datetime: 2015-06-20T00:51:10+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

This thread is awesome!
The Isolation modding community is really dispersed, so in an effort to bring it together, we've created a Steam group.
The group is an ideal place to post mods you've made, mod tools you've found/made or ask for help.
To join, just visit: [http://steamcommunity.com/groups/alien_ ... on_modders](http://steamcommunity.com/groups/alien_isolation_modders)
Thanks!
## Post #130
- Username: WeylandYutani
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 22, 2015 5:02 am
- Post datetime: 2015-06-21T21:20:30+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Is it possible to reupload the models because all are down and maybe please give taylor a shot ? thanks
## Post #131
- Username: MattFiler
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 20, 2015 8:47 am
- Post datetime: 2015-06-26T11:08:22+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

How did you convert the .DDS textures to use with Blender?

I've imported models successfully and they are looking cool, but I'd love to texture them and am having difficulty importing the textures in the format of .DDS that they are in after converting the .PAK file.

Could someone help? Thanks!
## Post #132
- Username: magister
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 07, 2014 3:52 am
- Post datetime: 2015-07-24T18:55:34+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from MattFiler
>
> How did you convert the .DDS textures to use with Blender?

I've imported models successfully and they are looking cool, but I'd love to texture them and am having difficulty importing the textures in the format of .DDS that they are in after converting the .PAK file.

Could someone help? Thanks!
Use this utility [http://rghost.ru/8Q64kNcnF](http://rghost.ru/8Q64kNcnF)
Put this exe and two bats to folder with this dds textures and execute ctex_all.bat
## Post #133
- Username: in5ect
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 29, 2015 5:39 pm
- Post datetime: 2015-07-29T09:48:47+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Hey
Is it possible to extract models of enviroment? walls doors etc? 
I want to make short movie and i was thinking about modeling corridors from scratch - but with this it would be really helpfull ?
## Post #134
- Username: magister
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 07, 2014 3:52 am
- Post datetime: 2015-08-04T15:51:54+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from in5ect
>
> Hey
Is it possible to extract models of enviroment? walls doors etc? 
I want to make short movie and i was thinking about modeling corridors from scratch - but with this it would be really helpfull ?
It was possible, where game was created. Level elements possible extract by ninja ripper - they have not wrong UV, like characters, trouble is recover texturing
## Post #135
- Username: LividDonuts
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 08, 2015 7:31 am
- Post datetime: 2015-09-08T00:20:06+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Whenever I extract with the PAK extractor it says it stop working but it creates the maps
## Post #136
- Username: Tca11a
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Sep 06, 2015 10:24 am
- Post datetime: 2015-09-15T13:28:13+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from cra0
>
> Heres the paktool
http://rel.cra0kalo.com/depot/AlienIsol ... ol_2.0.zip

Created by Cra0kalo & Volfin

Alien Isolation PakTool

What it supports??
*Unpack of Model PAKS
*Unpack of UI PAKS
*Unpack of Animation PAKS

What is required?
*.NET Frameworks 4.5


Help support questions?
twitter: @cra0kalo
Xentax thread: 
(this)


Coming later (im busy for now)

How is the work going on it? I don't use blender and having this tool would really help me? Also does it fix uvw problems or do we have to manually do it ourselves?
## Post #137
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-07T21:36:07+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

New version of Blender Importer is here.

Only one minor addition of a second "Alternate Load 2" flag to work around missing-faces type of load error.  Enjoy

Edit: newer version below.
## Post #138
- Username: nintendstroid
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 05, 2016 8:04 pm
- Post datetime: 2017-01-19T17:52:00+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from volfin
>
> New version of Blender Importer is here.

Only one minor addition of a second "Alternate Load 2" flag to work around missing-faces type of load error.  Enjoy

thanks volfin. can you upload unpacker to get the files converted for the blender importer.

all the download links are dead that crack0 had
## Post #139
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-19T18:44:44+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from nintendstroid
>
> volfin wrote:New version of Blender Importer is here.

Only one minor addition of a second "Alternate Load 2" flag to work around missing-faces type of load error.  Enjoy

thanks volfin. can you upload unpacker to get the files converted for the blender importer.

all the download links are dead that crack0 had

Sure. Here it is:
[AIPakTool Release Version.rar](https://xentaxbackup.github.io/file/12248_AIPakTool Release Version.rar)
## Post #140
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-27T02:32:40+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Minor update:
- Ensure Object mode is active before attempting import
- Validated functionality back to Blender version 2.70 (oldest supported)
[io_scene_Aliens.zip](https://xentaxbackup.github.io/file/12309_io_scene_Aliens.zip)
## Post #141
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2017-01-29T09:57:36+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Having problems converting all the textures needed when using ctex_all.bat.

example: eyebrow[d].tga.dds (exception Connor eyebrows)

Decals folders, generally seems to be the smaller files?

Thanks
## Post #142
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-29T18:15:02+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

it's files with transparency (decals, eyebrows, etc).

I made a tool to convert those that won't load right.  Unzip this somewhere, and drop the problem DDS files on the "go.bat" and it will convert them to PNG.
[texgenpack.rar](https://xentaxbackup.github.io/file/12337_texgenpack.rar)
## Post #143
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2017-01-29T18:59:43+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Thanks Volfin, much appreciated, works perfectly.
## Post #144
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2017-01-31T11:19:15+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Just wondered if anyone has assembled an NPC character e.g ENG_REACTORCORE: NPC Adriana.

After importing all the mesh required and then both armatures FEMALENPC & ADRIANA (Mirror X on both)
1. Adriana Armature: delete body bones to leave the necessary facial bones down to the neck bone
2. FemaleNPC Armature: delete head bones leaving neck bone
3. Shift select adriana then femalenpc and CTRL-J (join armatures)
4. Parent adriana neck to femalenpc and connect

Once all mesh is attached to the armature all functions correctly apart from the right arm drags part of the head mesh.
I'm a Blender novice so it may be something obvious that I'm missing 

Thanks
## Post #145
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-31T17:34:10+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from X3D
>
> Just wondered if anyone has assembled an NPC character e.g ENG_REACTORCORE: NPC Adriana.

After importing all the mesh required and then both armatures FEMALENPC & ADRIANA (Mirror X on both)
1. Adriana Armature: delete body bones to leave the necessary facial bones down to the neck bone
2. FemaleNPC Armature: delete head bones leaving neck bone
3. Shift select adriana then femalenpc and CTRL-J (join armatures)
4. Parent adriana neck to femalenpc and connect

Once all mesh is attached to the armature all functions correctly apart from the right arm drags part of the head mesh.
I'm a Blender novice so it may be something obvious that I'm missing 

Thanks

Since this is the second post about 'arm dragging the head", I guess I need to make something clearer.

There's two copies of every character model.  lets say "Adriana", and the second copy is "Adriana_FP".  The meshes for these two copies is identical. The Skeleton, is *not* identical.  You can't use Adriana_FP meshes with Adriana skeleton. Nor can you use Adriana meshes with Adriana_FP skeleton.
If you try you get bone mismatch.

So the fact you're seeing this isn't a problem with the extractor or the plugin. It means you're using the wrong skeleton or wrong meshes together.
you can't mix as you please. The fact you're having to delete bones is probably a clue it's the wrong skeleton. 

And why you would join two skeletons together is beyond me. You should only be using Adriana skeleton with Adriana meshes. Doing anything else, the bone ID's are simply not going to match. If a particular shirt/pants doesn't work with the Adriana skeleton, that means it's not meant for that skeleton, try another.  The parts are not interchangeable, they didn't design it that way.
## Post #146
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2017-01-31T19:04:30+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

The FemaleNPC skeleton works with the female NPC - TORSO, LEGS & SHOES whilst the ADRIANA skeleton doesn't, that only functions for the HEAD.
The FemaleNPC skeleton does not contain bones for the facial movement, whilst the ADRIANA skeleton does.

Joining two skeletons together is not uncommon with certain game assets within Blender e.g DOA5

Options for Female NPC characters:
1. Boiler Suit
2. Shirt
3. T-Shirt
4. T-Shirt Long Sleeves 

None of the above work with Adriana skeleton. Yet all function with FemaleNPC.

If they didn't design it that way how do you shed light on the fact that the FemaleNPC skeleton has no facial bone movement yet the NPC character skeletons do?

Maybe there is a hidden skeleton (key) that fits all  

So, anyone who has compiled these characters I would be grateful to know how it was done, Thanks for your time.
## Post #147
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-01T00:29:43+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

There are a ton of skeletons we didn't bother to identify. so yes there probably is one. We only spent time on the main characters.
## Post #148
- Username: JohnRWMarchant
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 13, 2016 10:07 pm
- Post datetime: 2017-06-20T12:07:25+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from Tca11a
>
> cra0 wrote:Heres the paktool
http://rel.cra0kalo.com/depot/AlienIsol ... ol_2.0.zip

Created by Cra0kalo & Volfin

Alien Isolation PakTool

What it supports??
*Unpack of Model PAKS
*Unpack of UI PAKS
*Unpack of Animation PAKS

What is required?
*.NET Frameworks 4.5


Help support questions?
twitter: @cra0kalo
Xentax thread: 
(this)


Coming later (im busy for now)


How is the work going on it? I don't use blender and having this tool would really help me? Also does it fix uvw problems or do we have to manually do it ourselves?

Hi did you ever finish tne AI Mesh Assembler, would love to get hold of it.
## Post #149
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-06-20T15:15:17+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from JohnRWMarchant
>
> 
Hi did you ever finish tne AI Mesh Assembler, would love to get hold of it.

That was mostly Cra0's project, as far as I know it was never finished.
## Post #150
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2017-06-21T03:48:44+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Yeah sorry never finished that, you can use volfin's blender script to import the models then export them out as obj,fbx etc

Or write a maxscript that will read the omodels
## Post #151
- Username: Skooooma
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 21, 2017 3:52 pm
- Post datetime: 2017-06-21T08:06:59+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from cra0
>
> Yeah sorry never finished that, you can use volfin's blender script to import the models then export them out as obj,fbx etc

Or write a maxscript that will read the omodels
Im trying to put together the modular level assets in blender but it seems that the .pobjects never assemble a complete model. Is it because some of the data is trapped in the .omodels?
## Post #152
- Username: chemlst
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 27, 2017 3:47 pm
- Post datetime: 2017-06-27T08:57:44+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Hi guys. I trying to import ALIEN bones in Blender with SMD tools. But every time i got error:

I tried latest and 2.2.1 versions of SMD, and also tried change decimal dividers to point in windows settings, but it's not working.
How can i load bones?
Or may be someone have model of alien with bones and textures?
## Post #153
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-06-27T16:18:30+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

the skeleton you're trying to use is wrong. it's expecting 3 floats, and that string pictured is only 1 float. so the skeleton conversion failed somewhere. Try to find the correct skeleton, there's a lot of skeletons but we only handle specific ones in the hkx2smd program. The ones with specific character names on them.
## Post #154
- Username: chemlst
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 27, 2017 3:47 pm
- Post datetime: 2017-06-27T23:23:08+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Hmm, i converted hkx one more time and now smd imports correctly.
## Post #155
- Username: sierra14
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Oct 01, 2017 3:19 am
- Post datetime: 2017-09-30T19:27:43+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Hey you guys, sorry about resuscitating a dead thread, but I really need some help

1 - is there anyway to match textures to the models? By looking at the text files from the game, there's various basic textures that are used for multiple models, but no way to work out which one is which, nor which normal and spec maps they use

2 - I can't seem to find any of these 'material libraries' which I'm guessing will work similar to how Fallout 4 uses palette maps to change colours of their textures without having to add in multiple textures.

3 - is there anyway to get the .pObject importer to import multiple files at a time? I'm having to import individual parts of a model one at a time, which is mind-numbing stuff :/

Charlie



materialsAI2.PNG (94.04 KiB) Viewed 374 times
## Post #156
- Username: synthosc
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 06, 2017 5:59 am
- Post datetime: 2017-12-06T16:07:35+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Hey guys, does extracting entire levels is still buggy?
because i so far managed to find a dump of the models and textures but it was like all meshes were separated and not all the models were exportable.
## Post #157
- Username: Poketooth
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 18, 2018 10:06 am
- Post datetime: 2018-09-18T22:15:37+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

My textures won't convert with the converter and I can't seem to find the files for the alien. Can someone give me a file path starting from C: \CONVERTED\?
## Post #158
- Username: JohnRWMarchant
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 13, 2016 10:07 pm
- Post datetime: 2018-09-26T18:48:58+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

So has anyone managed to export AI interior meshes as a whole interior not just all bunched in at 0,0,0. I would really like to get some of the interiors, not so fussed about the textures.
## Post #159
- Username: Thane
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 18, 2019 9:05 pm
- Post datetime: 2019-02-18T13:18:55+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Hi guys, sorry to bump an old thread but i'm trying to make VR mod for Alien Isolation (MotherVR) work a bit better with full room scale VR so people can walk around. The problem im having is that the player character's body model is visible and static in one position so its in the way all the time when your trying to bend over and look at stuff and look around while crouched, etc. I'd like to make it invisible somehow using the material properties or something, but i can't seem to get anywhere with extracting the textures or converting all the BML files to XML. Does anyone know of a way i could do this?

The other problem is the the view starts fading to black when you move about 1.5ft away from the head position. I don't suppose anyone knows how to change that so it doesn't fade?

Thanks!
## Post #160
- Username: guidkal
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 15, 2019 5:44 pm
- Post datetime: 2020-01-14T18:08:20+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Hi,
i'm aware that this is an old thread, however i'm hoping that someone is able to clarify something for me. I managed to extract the alien mesh as well as the skelteon as described a few pages up. Everything is working fine. The Mesh follows the skeleton as it should. However i did not understand whether we can only export the skeleton with the tools given in this thread or if we also should be able to get actual animations from the extracted ANIMATIONS.PAK. As far as i see the converted hkt->smd skeleton only contains the skeleton data but no animations. So is there a way to get actual animations from the game?
Cheers!
## Post #161
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2020-01-15T17:30:15+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Not to my knowledge, no. But anyone is welome to try. I think I released the source code to the hkx converter some time ago. Here's a link to the repository. It has some 'hints' about the animation format, but there's still a ton of work to do.

[https://bitbucket.org/Volfin/hkx2smd/](https://bitbucket.org/Volfin/hkx2smd/)



The problem as you see is there's a ton of possible animation formats that could potentially be used and you'd have to reverse engineer how these storage/compression formats work and write decoders....  it's no small job.  And back then we just ran out of steam.  I'm just not an animation guy.
## Post #162
- Username: guidkal
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 15, 2019 5:44 pm
- Post datetime: 2020-01-16T14:08:42+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

I feel you mate. So i will go with the interior and prop meshes first. I am currently developing a VR Shooter in Unity which at some point i want to put up on steam. Although this is going to be a tactical military shooter and since i am a huge alien fan i also want to use my game framework to build an alien VR shooter for private purposes. For that i need to rebuild the AI maps (or my own) in the Unity game engine, hopefully using the meshes i extract from AI. All of this non commercially for private use only of course. Currently i am using your Blender pobject importer which i wrote a wrapper for (as blender addon) so that i only need to choose one of the pobjects that make up a certain model (e.g. a wall element) and then the script gets all other pobjects that belong to that very model. The script then makes a screenshot of the viewport and saves a blender file with the model. That way i end up with the original directory structure od AI and for each model i have a blender file and a png image which shows an image of the model. That speeded up my workflow tremendously. However i still need to reconstruct the materials and texturing. There are surprisingly few textures in the game so i guess that most of the look is done through the material shaders themselfes. So this is something i need to rebuild in the unity engine as well. Still i can not imagine anything cooler than walking around the AI sets with a pulse rifle and a motion tracker in your VR hands. I already have the pulse rifle with complete weapon handling implemented and working which is pretty fun already. Anyways, thx for your answer and i will have to look into other ways to get my aliens animated. Cheers for your work m8!
## Post #163
- Username: guidkal
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 15, 2019 5:44 pm
- Post datetime: 2020-01-16T15:37:09+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Oh and do you happen to know whether someone managed to convert all dds to some readable format? I am using texconv.exe as well as texgenpack.exe in order to convert the textures. However for some teytures both tools wont work, expecially the files in "normal" and "normal_tiled" wont convert using either of the two tools.
## Post #164
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2020-01-16T17:03:09+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from guidkal ↑Thu Jan 16, 2020 11:37 pm at Thu Jan 16, 2020 11:37 pm
>
> 
Oh and do you happen to know whether someone managed to convert all dds to some readable format? I am using texconv.exe as well as texgenpack.exe in order to convert the textures. However for some teytures both tools wont work, expecially the files in "normal" and "normal_tiled" wont convert using either of the two tools.

All textures work. However a lot of people don't realize the normal are DX10 type BC7 textures which 95% of image programs (including blender) don't understand. I'm pretty sure this is discussed throughout the thread but basically you need to find a way to convert DirectX10 BC1 / BC5 / BC7 textures to normal textures. 



Personally i always use the free Intel photoshop plugin for this job. [https://software.intel.com/en-us/articl ... rks-plugin](https://software.intel.com/en-us/articles/intel-texture-works-plugin)
## Post #165
- Username: guidkal
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 15, 2019 5:44 pm
- Post datetime: 2020-01-16T20:40:56+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

All right, sorry i must have missed that. Thx again for your kind help. Works like a charm now. Do you mind me asking what u came up with the assets from AI? Did you create something with em? Just cusrious about what other ppl made out of those great models. Cheers again!
## Post #166
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2020-01-16T23:25:30+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

I haven't done anything with them. For me it's mostly the challenge of figuring out extraction and learning how the game engines work.  However I do know a guy who made some kind of multiplayer map out of one the levels. he sent me a link years ago but I don't seem to have it anymore.

Edit: found it
[http://steamcommunity.com/sharedfiles/f ... =817550789](http://steamcommunity.com/sharedfiles/filedetails/?id=817550789)
## Post #167
- Username: guidkal
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 15, 2019 5:44 pm
- Post datetime: 2020-01-18T18:26:52+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

That's pretty cool, although i have never played Black Ops 3. Still impressive. Thx for that link!

So one last question regarding Materials. I don't seem to be able to find any Material files in the AI game folder. (Background: I'd like to see which textures the respective materials use so that i can recreate those materials in my game engine. Without having this info the only way would be to trial and error different textures while trying to get the ingame look of AI. 

The only thing i was abe to find is the Material_Mappings.PAK which contains the model -> material mappings, so e.g. walls_01.xml contains:

```
<material_mappings>
  <map>
    <original arrow="true">SCI_Plastic_Smooth_White</original>
    <override arrow="true">HAB_Metal_Smooth_Grey</override>
  </map>
  <map>
    <original arrow="true">SCI_Plastic_Gloss_White</original>
    <override arrow="true">HAB_Plastic_Smooth_Grey</override>
  </map>
  <map>
    <original arrow="true">SCI_Plastic_Smooth_White</original>
    <override arrow="true">HAB_Metal_Smooth_Grey</override>
  </map>
</material_mappings>
```


So now i know which materials are used by the wall model, however i do not know which tetures would make up those materials.

In DATA/Material_DATA we also have MATERIALS.XML and MATERIALS_LIST.TXT which also do not contain useful info regarding to textures.

Last thing i managed to find are the LEVEL_MODELS.MTL files in each /RENDERABLE folder of the levels. However i can not open those properly. only some fragments are readable as text. However they seem to contain at least the Material names, e.g. they contain "SCI_Plastic_Smooth_White" which is also contained in the above Wall_01.XML file. So maybe the .MTL files contain texture names in the parts of the file that are not plaintext.

Do you happen to know more on that front?

Cheers again!
## Post #168
- Username: DENver666
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 20, 2020 11:26 pm
- Post datetime: 2020-02-20T15:37:00+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Please Help.I can't find textures on Torrens at the very beginning, when Ripley just wakes up and there's a monitor in front of her that says Please Sign In.Does anyone know where this texture lies?
## Post #169
- Username: dapotato
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 11, 2020 3:40 pm
- Post datetime: 2020-05-11T08:05:31+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from volfin ↑Fri Jan 27, 2017 10:32 am at Fri Jan 27, 2017 10:32 am
>
> 
Minor update:
- Ensure Object mode is active before attempting import
- Validated functionality back to Blender version 2.70 (oldest supported)

Hi I installed this plugin on the latest blender 2.8x, but somehow it doesn't show up on the import list,
Is there any way to make it work? thanks!
## Post #170
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2020-05-11T12:20:48+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Sorry Blender 2.8 is a completely new blender, they changed everything, including plugins. You'll have to use blender 2.79
## Post #171
- Username: dapotato
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 11, 2020 3:40 pm
- Post datetime: 2020-05-11T21:33:29+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from volfin ↑Mon May 11, 2020 8:20 pm at Mon May 11, 2020 8:20 pm
>
> 
Sorry Blender 2.8 is a completely new blender, they changed everything, including plugins. You'll have to use blender 2.79

great! it works! I was importing the geo without problems.
And now comes the 2nd question, how do I know the texture assignment? 
Which goes to which?
Thanks!

Also I just found out there seems no way to multiple import objects?
I am trying to reconstruct one of the scenes, there are like several hundred objects.
Would be crazy to do it one by one.
Any ideas to speed up the import and the lookdev process?
Thanks!
## Post #172
- Username: JohnRWMarchant
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 13, 2016 10:07 pm
- Post datetime: 2020-05-16T19:12:15+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from dapotato ↑Tue May 12, 2020 5:33 am at Tue May 12, 2020 5:33 am
>
> 
volfin wrote: ↑Mon May 11, 2020 8:20 pm
Sorry Blender 2.8 is a completely new blender, they changed everything, including plugins. You'll have to use blender 2.79


great! it works! I was importing the geo without problems.
And now comes the 2nd question, how do I know the texture assignment? 
Which goes to which?
Thanks!

Also I just found out there seems no way to multiple import objects?
I am trying to reconstruct one of the scenes, there are like several hundred objects.
Would be crazy to do it one by one.
Any ideas to speed up the import and the lookdev process?
Thanks!

So did you manage to extract rooms or whole levels, do they come out ok and not all bits placed at 0,0,0. If so i would love to know how you did it. Im not really interested in textures but the meshes for the likes of Mother, Dinning room and such would be great.
## Post #173
- Username: dapotato
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 11, 2020 3:40 pm
- Post datetime: 2020-05-17T00:10:14+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from JohnRWMarchant ↑Sun May 17, 2020 3:12 am at Sun May 17, 2020 3:12 am
>
> 
dapotato wrote: ↑Tue May 12, 2020 5:33 am
volfin wrote: ↑Mon May 11, 2020 8:20 pm
Sorry Blender 2.8 is a completely new blender, they changed everything, including plugins. You'll have to use blender 2.79


great! it works! I was importing the geo without problems.
And now comes the 2nd question, how do I know the texture assignment? 
Which goes to which?
Thanks!

Also I just found out there seems no way to multiple import objects?
I am trying to reconstruct one of the scenes, there are like several hundred objects.
Would be crazy to do it one by one.
Any ideas to speed up the import and the lookdev process?
Thanks!


So did you manage to extract rooms or whole levels, do they come out ok and not all bits placed at 0,0,0. If so i would love to know how you did it. Im not really interested in textures but the meshes for the likes of Mother, Dinning room and such would be great.

I was still trying. Volfin should know better. So far I only figured out how to bulk import the massive amount of pObj. 
It seems to me that if you import all the thousands of pObjs you wont get what you see in the game.
They must have a particular way to populate the level so if we merely import all the raw assets, you will just get a mess of overlapping objects.
In the python import script that Volfin wrote, you can change the import setting on the translate value = false, so that it wont come in at the origin.
But it doesn't help much.

IMO, the best option is the D3DX ripper, like ninja ripper, but I tried several times with different attributes, it all came out messy and misplaced or missing a lot of parts. Most likely is cuz it only supports up to d3d11 and I'm using d3dx12, i suppose? If only the ripping works, that will save us a lot of time.
## Post #174
- Username: JohnRWMarchant
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 13, 2016 10:07 pm
- Post datetime: 2020-05-17T23:40:32+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Same for me no problem ripping the parts, its just they are all orientated to 0,0,0, which is just a mess and hard to see where things fit.

I tried NR before and that did not fair any better, i only got partial captures and still a  lot of stuff all over the place.
## Post #175
- Username: alpha gamer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 22, 2020 10:03 am
- Post datetime: 2020-05-22T08:31:20+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Ok I'm able to import the models into blender, and i also have a texture folder filled with all ripped textures. So here comes the dumb noob question, how do i match the textures with the models? I'm talking doors, panels etc. I used to rip with 3dripperx and never really managed to get anything to work with ninja ripper so this is the best i have come.
## Post #176
- Username: JohnRWMarchant
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 13, 2016 10:07 pm
- Post datetime: 2020-05-31T13:45:19+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Are the models in parts or one whole object. If they are parts are they in their correct place in 3d space or all orientated to 0,0,0. Sorry dont know enough about Blender to know how to remap the textures in blender. Do it have UV maps. 

Would be interested if you could share the models even without the textures.
## Post #177
- Username: Dushess
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 13, 2020 12:33 am
- Post datetime: 2020-08-12T18:09:41+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Hello, I'm using latest AIPakTool and blender importer (2.79)
Some parts from Torrens meshgroup causes immediate crash "for no reason". Alt load doesn't change anything.
If you need logs, please tell where exactly are the logs. 

I've touched model from Towing platform, we are right above the vessel, so it's his exterior model. The problem occurs on subbundle entry2299 for example, this picture contains it.
But entry2331 or entry2358 works just fine, as I've seen all of them is aux engine thruster module of something.
[52.jpg](https://xentaxbackup.github.io/file/18592_52.jpg)
## Post #178
- Username: NoPantsMcDance
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 12, 2020 5:42 am
- Post datetime: 2020-10-11T21:45:07+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Would anyone be able to provide an obj file of the sevastopol staton please.
## Post #179
- Username: Dushess
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 13, 2020 12:33 am
- Post datetime: 2020-10-20T19:35:55+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from NoPantsMcDance ↑Mon Oct 12, 2020 5:45 am at Mon Oct 12, 2020 5:45 am
>
> 
Would anyone be able to provide an obj file of the sevastopol staton please.
Which one? If it's possible to unpack and if it's really what you need.
## Post #180
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2020-11-25T17:06:00+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Texture setup for this game is something, different from other games that I tried so far. 
At least, for characters.
For example, extracting Marshal Waits all I got is _n and _d textures, I cannot even find specular map anywhere, and diffuse map looks like AO map.

also I don't know what vertex color represent in those models, my first thought were they used to add color, but nah, e.g. shirt have pink and purple color
## Post #181
- Username: yotusba
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 14, 2020 7:24 am
- Post datetime: 2020-11-26T18:43:02+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

> Reply from Dushess ↑Wed Oct 21, 2020 3:35 am at Wed Oct 21, 2020 3:35 am
>
> 
NoPantsMcDance wrote: ↑Mon Oct 12, 2020 5:45 am
Would anyone be able to provide an obj file of the sevastopol staton please.

Which one? If it's possible to unpack and if it's really what you need.

Hey, not him but I am looking for an fbx for the USCSS Nostromo fbx as I have the pb obj files but am having a real hard time finding the correct textures and files for the world. Is it possible to get in touch on discord or something ?  My discord is yotsuba#0462.
## Post #182
- Username: GregSmack
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 12, 2022 1:42 am
- Post datetime: 2022-01-11T18:24:10+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Hey! Thanks for the awesome tool! 
Is there a way to import a whole Map? I want to Import the LC 426 map but in the exported folder from the plugin (I exported the files for the L-426 map correctly) I just cant find a model file where the whole map is :/
## Post #183
- Username: GregSmack
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 12, 2022 1:42 am
- Post datetime: 2022-01-11T18:47:24+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Also, I use Blender 2.79 so that the tool works properly. Sometimes when I import an object Blender just crashes. The files are always the same they just wont import :/ any ideas?
## Post #184
- Username: Malkaviansoul
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 23, 2022 4:25 am
- Post datetime: 2022-04-22T20:28:54+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Hey! Is it possible to rip Amanda's model? I found only body parts. Where is the head?
## Post #185
- Username: xenolover
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 10, 2022 6:32 am
- Post datetime: 2022-10-09T22:34:22+00:00
- Post Title: Re: Alien Isolation (.PAK .BIN)

Will this ever get updated to newer version of blender and a better tool for alien isolation model exportes because currently im trying to export the xenomorph model and the rig but I just cant find the models and I followed the instructions can els who mabye has it give it to me thanks alot.
