## Post #1
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2013-04-04T19:04:53+00:00
- Post Title: Real Racing 3 (Android)

What about Real Racing 3 models, here is Porsche 918 RSR:
[http://www.4shared.com/archive/ySNhcXQC ... 18rsr.html](http://www.4shared.com/archive/ySNhcXQC/2010_porsche_918rsr.html)
## Post #2
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2013-06-12T06:47:00+00:00
- Post Title: Real Racing 3 (Android)

> Reply from TomWin
>
> What about Real Racing 3 models, here is Porsche 918 RSR:

Sorry for the bump, but I'd like to have the models ripped, too. The format appears to be M3G, but idk as to how we can open it for editing.

EDIT: Header appears to be standard, but it can't be opened by any known M3G viewers out there.
## Post #3
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2013-10-27T19:33:54+00:00
- Post Title: Real Racing 3 (Android)

and now Real Racing 3 has many new cool models like Porsche 964 Speedster, Lexus IS '14 and much more
## Post #4
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-01-22T14:15:07+00:00
- Post Title: Real Racing 3 (Android)

Sorry for bumping an old thread, but I have recently started work on a MAXScript for this model format. I'm currently able to import vertex and face data for all vehicles. Pictured below is the lod_a model of the 2013 Hyundai WRC (as it is called in the game).
[](http://www.imagebam.com/image/77832f303212749) [](http://www.imagebam.com/image/044250303212765) 
Unfortunately, the UV data is a bit more tricky. According to the format, there are three 2-byte vertices per UV. I tried reading them as half floats, but the result looks like this:
[](http://www.imagebam.com/image/1402be303212783)

This is my MAXScript code (sorry it's so messy, I plan to clean it up once I fix the UVs):
[Obsolete script. Click here for the newest version.](http://forum.xentax.com/viewtopic.php?f=16&t=10300&p=98840#p98840)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-22T15:21:00+00:00
- Post Title: Real Racing 3 (Android)

if you uploaded a model sample I could have a look at.

(But don't use such annoying fxxxing hoster like 4shared, please,
which requires you to share your email address.)
## Post #6
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-01-22T16:39:22+00:00
- Post Title: Real Racing 3 (Android)

Ok, here are some samples.
[http://www52.zippyshare.com/v/15617071/file.html](http://www52.zippyshare.com/v/15617071/file.html)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-22T20:42:15+00:00
- Post Title: Real Racing 3 (Android)

thx!  
well, I had a look at 2013_mclaren_mp412c_e.m3g,
offset 0x6AC1 where 1358 uvw sets are assumed to be found.
The resulting word values look better but don't show a proper uv map either.
I thought of a problem with the w value but the data block ends at 0x8A94
so it's size is 1358x6 (decimal).

You posted "According to the format, there are three 2-byte vertices per UV"
- could you give a link to the format specifications?

as half floats (undivided)
0.000477 0.000031 0.000049 
0.000477 0.000031 0.000049 
0.000477 0.000031 0.000049 
0.000052 0.000471 0.000038 
0.000052 0.000469 -109312.000000 
0.000045 0.000476 -105856.000000 
0.000045 0.000480 0.000037 
0.000031 0.000483 -102784.000000 
0.000031 0.000487 0.000037 
0.000055 0.000459 -94208.000000 
0.000051 0.000463 -93504.000000 
0.000044 0.000468 -86848.000000 
0.000031 0.000470 -80640.000000 
-101184.000000 0.000468 -86400.000000 
-86144.000000 0.000463 -93504.000000 
-79168.000000 0.000459 -94208.000000 
-84032.000000 0.000469 -109312.000000 
-98752.000000 0.000476 -106176.000000 
-100416.000000 0.000480 0.000037 
-107264.000000 0.000476 0.000046 
0.000031 0.000480 0.000046 
0.000042 0.000476 0.000046 
0.000049 0.000469 0.000046 
0.000052 0.000467 0.000045 

as words (divided by 16384.0)
vt 0.247131 0.000549 0.037720 
vt 0.247131 0.000549 0.037720 
vt 0.247131 0.000549 0.037720 
vt 0.044800 0.245544 0.014526 
vt 0.044861 0.245056 3.979248 
vt 0.030579 0.246948 3.975952 
vt 0.029236 0.247925 0.013794 
vt 0.000305 0.248535 3.973022 
vt 0.000000 0.249634 0.013123 
vt 0.049500 0.242493 3.964844 
vt 0.042847 0.243652 3.964172 
vt 0.028015 0.244812 3.957825 
vt 0.000427 0.245300 3.951904 
vt 3.971497 0.244690 3.957397 
vt 3.957153 0.243652 3.964172 
vt 3.950500 0.242493 3.964844 
vt 3.955139 0.245056 3.979248 
vt 3.969177 0.246948 3.976257 
vt 3.970764 0.247925 0.013794 
vt 3.977295 0.246826 0.032654 
vt 0.000000 0.247864 0.032532 
vt 0.022705 0.246826 0.032654 
vt 0.038452 0.245117 0.030823 
vt 0.043396 0.244446 0.029358 

(divided by 65536.0 would give values <1.0)
## Post #8
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-01-22T21:08:48+00:00
- Post Title: Real Racing 3 (Android)

Thanks for looking into it!   

Here is a link to the format specifications:
[https://jcp.org/aboutJava/communityproc ... index.html](https://jcp.org/aboutJava/communityprocess/mrel/jsr184/index.html)

EDIT: I've decided to check if the second vertex array (two 2-byte vertices) is definitely not the UV array... Turns out I was wrong! I couldn't read them as half floats, but using your method (reading words and dividing by 16384.0) I now have UV maps! Thank you very much for pointing me in the right direction  

[](http://www.imagebam.com/image/680806303288557)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-23T00:00:35+00:00
- Post Title: Real Racing 3 (Android)

that's fine!  
(Looks to me as if dividing by 2048.0 (and applying an offset of -31.0 to tv)
would be the better choice.)

Thank you, too,  for the link to the very informative document! (283 pages to read  )
## Post #10
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2014-02-06T12:42:50+00:00
- Post Title: Real Racing 3 (Android)

Are there any possible dummies and/or other metadata that we can use for putting custom RR3 models back into the game? And dude, you did quite a 'swell job with extracting them models. I'm pretty much convinced that Firemonkeys used a non-standard variant of the M3G/JSR-184 format, and from what it seems it turns out to be correct.
## Post #11
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-02-08T20:27:36+00:00
- Post Title: Real Racing 3 (Android)

Certainly, for example the .points file in each vehicle's directory contains dummies (lights, door hinges etc)
[](http://www.imagebam.com/image/254785306793889) 

Also I've tried to make some improvements to the script recently. I used the code for importing normals from [Chipicao's scripts](http://forum.xentax.com/viewtopic.php?f=16&t=11095) and material assignment is now automatic. Unfortunately textures still have to be applied manually, because the texture names are generic (for exaple Vehicle Exterior_badges instead of 2013_koenigsegg_agera_badges.etc.dds). There are .bin files in the root vehicles which might contain those filenames but they use some kind of encryption.
[](http://www.imagebam.com/image/5d6974306793903) 

Here's my script in its current state, along with a QuickBMS script for decompressing dds.z files, converting .dds files to .tga (and .pkm files if they're ETC1-compressed) and an edited version of etcunpack which converts .pkm directly to .tga.

[Obsolete script. Click here for the newest version.](http://forum.xentax.com/viewtopic.php?f=16&t=10300&p=98840#p98840)
## Post #12
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-09T02:31:49+00:00
- Post Title: Real Racing 3 (Android)

> Reply from barti
>
> I used the code for importing normals from Chipicao's scripts
I see you're using code from some of my older scripts. Might I suggest you use the newer code from Assetto Corsa and Disney's Infinity, which it's a bit faster.

```
      select msh
      addmodifier msh (Edit_Normals ()) ui:off
      msh.Edit_Normals.MakeExplicit selection:#{1..Norm_array.count} --faster than a loop
      EN_convertVS = msh.Edit_Normals.ConvertVertexSelection --assign basic commands to variables to speed-up processing
      EN_setNormal = msh.Edit_Normals.SetNormal
      normID = #{} --define this outside the loop
      --apply normals
      for k = 1 to Vert_array.count do
      (
         free normID --freeing an array is faster than declaring it empty
         EN_convertVS #{k} &normID
         for id in normID do EN_setNormal id Norm_array[v] --get the normal id directly instead of converting bitarray to array
      )
      collapseStack msh
```
## Post #13
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-02-09T02:44:42+00:00
- Post Title: Real Racing 3 (Android)

great script, it loads models correct and UV also I think
But I cant get all textures, I tried to convert dds.z textures of 1993_porsche_911_carrera2_speedster and the only ones that I got are 1993_porsche_911_carrera2_speedster_badges.etc, 1993_porsche_911_carrera2_speedster_lights.etc and 1993_porsche_911_carrera2_speedster_wheel_blur.etc and redblur :S 
etcpack.exe doesnt work at all for me
## Post #14
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-02-09T11:19:22+00:00
- Post Title: Real Racing 3 (Android)

> Reply from Chipicao
>
> I see you're using code from some of my older scripts. Might I suggest you use the newer code from Assetto Corsa and Disney's Infinity, which it's a bit faster.
Thanks for pointing that out, I'll include it in a later release. I've tried it now and it does seem to be a bit faster.

> Reply from TomWin
>
> But I cant get all textures, I tried to convert dds.z textures of 1993_porsche_911_carrera2_speedster and the only ones that I got are 1993_porsche_911_carrera2_speedster_badges.etc, 1993_porsche_911_carrera2_speedster_lights.etc and 1993_porsche_911_carrera2_speedster_wheel_blur.etc and redblur :S
Could you upload / PM me one of the non-working textures?

> Reply from TomWin
>
> etcpack.exe doesnt work at all for me
It's a command-line application. You have to open a command line in its folder and use it like this

```
etcpack <input_path> <output_path>.tga
```

Make sure the input file has the .pkm extension.

But from what I can see you only got the non-compressed textures so that tool wouldn't be very useful for you right now.
## Post #15
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-02-09T13:27:09+00:00
- Post Title: Real Racing 3 (Android)

ok here they are: [http://www.sendspace.com/file/q3dzhl](http://www.sendspace.com/file/q3dzhl)

no idea how to convert them.
## Post #16
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-02-09T14:16:19+00:00
- Post Title: Re: Real Racing 3 (Android)

That's odd, all of them converted fine for me.
[](http://www.imagebam.com/image/51cc96306925975)

Are you using the latest version of QuickBMS?
## Post #17
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-02-09T14:41:36+00:00
- Post Title: Re: Real Racing 3 (Android)

yeah, I get dds textures, but then what, I cannot open them, then I convert them by ddsetc2pkm.bms to pkm textures and they are 16bytes files :S

and that etcpack doesnt work in my Win7 64bit
## Post #18
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-02-09T15:35:12+00:00
- Post Title: Re: Real Racing 3 (Android)

They're only 16bytes because you may have not accepted the append function - when the script asks you to overwrite make sure you hit A and press Enter.

It's strange that etcpack doesn't work for you, I'm using Win7 64bit too. Does it display any error messages?
## Post #19
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-02-09T15:43:48+00:00
- Post Title: Re: Real Racing 3 (Android)

yeah this thing I get, but it's in polish

so i got pkm files i open with mali textures thing, but i cant export this pkm things :S
[](http://www.imagebam.com/image/51a19f306937864)
## Post #20
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-02-09T15:54:26+00:00
- Post Title: Re: Real Racing 3 (Android)

Looks like you don't have the Microsoft Visual C++ 2008 SP1 Redistributable Package (x86).
You can download it here: [http://www.microsoft.com/en-us/download ... en&id=5582](http://www.microsoft.com/en-us/download/details.aspx?displaylang=en&id=5582)
## Post #21
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-02-09T16:39:27+00:00
- Post Title: Re: Real Racing 3 (Android)

I had it installed, installed it again but didnt work :S
how to extract textures from mali textures compression tool? I can open there these pkm files
## Post #22
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-02-09T17:39:00+00:00
- Post Title: Re: Real Racing 3 (Android)

Well in that case I don't know   

But on the bright side, I experimented with that Mali Texture Tool and I managed to export the file:

1. Right-Click on the .pkm file and click Compress selected images
2. Set output format to PKM (KTX throws some error for me)
3. Right-Click the .pkm file again and the Save image as... function should be unlocked 

I didn't notice any additional artifacts so the file shouldn't be recompressed.
But you'll have to flip the texture (or the UVs) vertically.
## Post #23
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-02-09T18:17:31+00:00
- Post Title: Re: Real Racing 3 (Android)

yeah it works, thanks a lot
## Post #24
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-02-16T16:44:03+00:00
- Post Title: Re: Real Racing 3 (Android)

Real Racing models are not in correct metric scale, also some are bigger other are smaller, is that import scrip bug or they are just like that? if so how to find correct scale?
## Post #25
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-02-16T18:58:05+00:00
- Post Title: Re: Real Racing 3 (Android)

Yeah I haven't found the scale values in the model format yet. I just divided the vertices by 100 so that the model isn't huge on import.
## Post #26
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-02-16T19:12:59+00:00
- Post Title: Re: Real Racing 3 (Android)

good that some models can be found in other games and that way rescaled. I find RR3 models more usefull for World Racing 2 than NFS Rivals models, because they have nice textures.
## Post #27
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-02-16T20:15:25+00:00
- Post Title: Re: Real Racing 3 (Android)

As soon as I replied to you I managed to find the scale value, it should be a bit more correct now.

I've also rewritten the script a little to be able to import track models (unfortunately it's ridiculously slow, especially on 32bit).
[](http://www.imagebam.com/image/629c99308422789)

And, as Chipicao suggested, I've included the newer version of his code for loading normals.
[Obsolete script. Click here for the newest version.](http://forum.xentax.com/viewtopic.php?f=16&t=10300&p=98840#p98840)
## Post #28
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-02-16T20:32:22+00:00
- Post Title: Re: Real Racing 3 (Android)

Thanks a lot, I think is better now
## Post #29
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2014-02-20T07:05:01+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from barti
>
> As soon as I replied to you I managed to find the scale value, it should be a bit more correct now.

I've also rewritten the script a little to be able to import track models (unfortunately it's ridiculously slow, especially on 32bit).


And, as Chipicao suggested, I've included the newer version of his code for loading normals.
Download for new script

Cool, didn't know you make mods for WR2. Hopefully my script will be somewhat useful

Lol that's 'swell. I'm sure it won't be long until someone decides to convert stuff like tracks to GTA4 or some other game.

EDIT: Oh, and what about PowerVR/Adreno textures for Snapdragon and/or iOS users?
## Post #30
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-20T11:38:08+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from huckleberrypie
>
> EDIT: Oh, and what about PowerVR/Adreno textures for Snapdragon and/or iOS users?
Use PVRTexTool: [http://www.imgtec.com/powervr/insider/p ... extool.asp](http://www.imgtec.com/powervr/insider/powervr-pvrtextool.asp)

It comes with a tool to view and convert pvr textures, as well as plugins for explorer, 3ds max, and photoshop.
## Post #31
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2014-02-21T01:03:47+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from Chipicao
>
> huckleberrypie wrote:EDIT: Oh, and what about PowerVR/Adreno textures for Snapdragon and/or iOS users?
Use PVRTexTool: http://www.imgtec.com/powervr/insider/p ... extool.asp

It comes with a tool to view and convert pvr textures, as well as plugins for explorer, 3ds max, and photoshop.

Noted. Oh, and has anyone tried converting the first-person viewmodels (i.e. HQ car interiors) too?
## Post #32
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-02-21T14:57:08+00:00
- Post Title: Re: Real Racing 3 (Android)

Yes I've tried importing the HQ meshes as well, they import fine but the steering wheel's position is always 0,0,0. I think that's because the game calculates the steering wheel's position on the fly.
## Post #33
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-03-02T21:01:09+00:00
- Post Title: Re: Real Racing 3 (Android)

any idea where to find texture names used for interiors? Material name doesnt help too much is just Vehicle Interior_mm_mat01, Vehicle Interior_mm_mat02, Vehicle Interior_mm_mat03, ...etc
## Post #34
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-03-03T15:55:48+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from TomWin
>
> any idea where to find texture names used for interiors? Material name doesnt help too much is just Vehicle Interior_mm_mat01, Vehicle Interior_mm_mat02, Vehicle Interior_mm_mat03, ...etc

There's no way to find any texture names at this point, only material names.
## Post #35
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-03-08T10:57:49+00:00
- Post Title: Re: Real Racing 3 (Android)

You may already know about this, but I just found out that [The Compressonator](http://developer.amd.com/tools-and-sdks/archive/legacy-cpu-gpu-tools/the-compressonator/) can open and create both etc.dds and atc.dds textures and export them to common formats. There's also a batch conversion mode but I haven't tested it yet.

[](http://www.imagebam.com/image/de688a312831972)

Unfortunately it doesn't load RGBA4444 .DDS files (the ones with transparent elements) so those still have to be converted.
## Post #36
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-03-09T12:50:01+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from barti
>
> TomWin wrote:any idea where to find texture names used for interiors? Material name doesnt help too much is just Vehicle Interior_mm_mat01, Vehicle Interior_mm_mat02, Vehicle Interior_mm_mat03, ...etc

There's no way to find any texture names at this point, only material names.

so how the game reads materials?
## Post #37
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-03-09T21:54:14+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from TomWin
>
> so how the game reads materials?

From what I can see, the carappearances.appearances file in 'vehicles' folder is an XML file with some material names, but it's encrypted and I can't get the full xor key. I made a thread about the files in the Compressed files and methods section.
## Post #38
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-03-09T22:57:53+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from barti
>
> TomWin wrote:so how the game reads materials?

From what I can see, the carappearances.appearances file in 'vehicles' folder is an XML file with some material names, but it's encrypted and I can't get the full xor key. I made a thread about the files in the Compressed files and methods section.

it would help a lot if we know what materials they really use.
## Post #39
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2014-03-10T06:11:56+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from barti
>
> You may already know about this, but I just found out that The Compressonator can open and create both etc.dds and atc.dds textures and export them to common formats. There's also a batch conversion mode but I haven't tested it yet.



Unfortunately it doesn't load RGBA4444 .DDS files (the ones with transparent elements) so those still have to be converted.

Yep, I tried that too with the textures for Gangstar: West Coast. Even managed to mod the game with a billboard texture lol.
## Post #40
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-09-24T22:55:16+00:00
- Post Title: Re: Real Racing 3 (Android)

Sadly the RealRacing3 script doesn't work good with newest DLC models.
Miura interior cannot be imported, and the quickbms script doesn't work with them :S

[https://www.sendspace.com/file/qmf8im](https://www.sendspace.com/file/qmf8im)

Anybody can help?
## Post #41
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-09-27T17:34:38+00:00
- Post Title: Re: Real Racing 3 (Android)

I'm currently rewriting the importer to make it more accurate with the M3G file format - hopefully that will fix the issue with the new models. I'll post once I get it done.

> Reply from TomWin
>
> the quickbms script doesn't work with them :S
Do you mean the texture files? If so, the textures you provided in the sample are in ATC format. As far as I can tell, the only tool that supports them is ATI's The Compressonator, so you'll have to use that to convert the textures for now. I've found [a document about converting textures between ATC and the PC-friendly DXT format](http://www.guildsoftware.com/papers/2012.Converting.DXTC.to.ATC.pdf), but I haven't looked into it yet.
## Post #42
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-09-27T20:54:35+00:00
- Post Title: Re: Real Racing 3 (Android)

Corrected MAXScript:
[https://www.sendspace.com/file/ucbrlk](https://www.sendspace.com/file/ucbrlk)
[http://s000.tinyupload.com/index.php?fi ... 6312862391](http://s000.tinyupload.com/index.php?file_id=79049198916312862391) (mirror)

The Miura interior sample loads correctly now.
Also materials are automatically loaded into the Material Editor for easier texture replacing.


Aluigi wrote a QuickBMS script for Real Racing 3, which can open the .z files as well as .bin files:
[http://aluigi.altervista.org/papers/bms ... cing_3.bms](http://aluigi.altervista.org/papers/bms/others/real_racing_3.bms)

I also found out a while ago that the PVR format can contain ETC1 and RGBA4444 textures. So I made a etc.dds to pvr QuickBMS script to streamline the texture conversion process for this platform.

```
#
# written by barti
# http://forum.xentax.com
#
# script for QuickBMS http://quickbms.aluigi.org

get NAME basename
string NAME += ".pvr"

idstring "DDS "
get HEADERSZ long
get SIZE     long
get WIDTH    long
get HEIGHT   long
get IMGSIZE  long
goto 84
getdstring ETCHEADER 4
goto 128

set MEMORY_FILE compressed eNp9w7ENAAAIAjAJDxoH/j+FDTabdHWcB7IMMl0A/w==

if ETCHEADER == "ETC "
	putvarchr MEMORY_FILE 8  6 long # stands for ETC1 RGB
elif ETCHEADER == "ATC "
	print "Sadly ATITC textures are not supported in the PVR container. Exiting script."
	cleanexit
elif ETCHEADER == "ATCI"
	print "Sadly ATITC textures are not supported in the PVR container. Exiting script."
	cleanexit
elif ETCHEADER == ""
	xmath IMGSIZE "WIDTH * HEIGHT * 2"

	putvarchr MEMORY_FILE 8  0x61626772 long # "rgba"
	putvarchr MEMORY_FILE 12 0x04040404 long # bits per channel
else
	print "Unsupported header found, exiting script."
	cleanexit
endif

putvarchr MEMORY_FILE 24 WIDTH   long
putvarchr MEMORY_FILE 28 HEIGHT  long
putvarchr MEMORY_FILE 44 1 long # MIPMAPS

append
log MEMORY_FILE 128 IMGSIZE
append

get SIZE asize MEMORY_FILE
log NAME 0 SIZE MEMORY_FILE
```


These are the texture formats in Real Racing 3 I've stumbled upon so far:
.atc.dds - ATI Texture Compression. Can be opened using The Compressonator.
.etc.dds - Ericsson Texture Compression and RGBA4444 for translucent images. I recommend converting them to .pvr using the above script.
.dxt.dds - DXT Texture Compression. These textures can be opened in any DDS viewer without any problems.
.ptc.pvr - PVR Texture Compression. These textures can be opened using PVRTexTool and imported into 3DS Max or Photoshop using PVRTexTool's plugins.
## Post #43
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-09-28T15:53:17+00:00
- Post Title: Re: Real Racing 3 (Android)

Thank you it works fine now.
## Post #44
- Username: MacedoSTI
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 11:57 pm
- Post datetime: 2014-09-29T03:38:12+00:00
- Post Title: Re: Real Racing 3 (Android)


## Post #45
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-09-29T14:55:52+00:00
- Post Title: Re: Real Racing 3 (Android)

MacedoSTI, are your QuickBMS binaries up to date?
## Post #46
- Username: MacedoSTI
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 11:57 pm
- Post datetime: 2014-09-29T19:05:05+00:00
- Post Title: Re: Real Racing 3 (Android)

no   

i only want open .z files
## Post #47
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-09-29T19:32:45+00:00
- Post Title: Re: Real Racing 3 (Android)

... then download the latest version of QuickBMS  
[http://quickbms.aluigi.org](http://quickbms.aluigi.org)
## Post #48
- Username: MacedoSTI
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 11:57 pm
- Post datetime: 2014-09-30T01:15:08+00:00
- Post Title: Re: Real Racing 3 (Android)

lel i use 2.0 version ;-;

i go ttry other, thanks :v

edit:

working
## Post #49
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2014-12-07T05:44:00+00:00
- Post Title: Re: Real Racing 3 (Android)

Sorry to be bumping this, but is there an alternative link for the Real Racing Max Script?

Sendspace won't let me download it.
## Post #50
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-12-07T15:02:51+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from lolwatt
>
> Sorry to be bumping this, but is there an alternative link for the Real Racing Max Script?

Sendspace won't let me download it.

New link:
[http://s000.tinyupload.com/index.php?fi ... 6312862391](http://s000.tinyupload.com/index.php?file_id=79049198916312862391)
## Post #51
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-15T11:48:18+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from barti
>
> lolwatt wrote:Sorry to be bumping this, but is there an alternative link for the Real Racing Max Script?

Sendspace won't let me download it.

New link:
http://s000.tinyupload.com/index.php?fi ... 6312862391Hello, my friends, thank you for sharing, I am testing the script, but an error, here is a sample file  [https://onedrive.live.com/redir?resid=6 ... file%2crar](https://onedrive.live.com/redir?resid=6A28B826BE5F1236!152&authkey=!AGxfVIOyuG_jaPk&ithint=file%2Crar)
[BaiduShurufa_2014-12-15_19-35-44.png](https://xentaxbackup.github.io/file/8275_BaiduShurufa_2014-12-15_19-35-44.png)
## Post #52
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-12-15T17:01:08+00:00
- Post Title: Re: Real Racing 3 (Android)

Works on my end - I guess it's because of different text encoding in your OS. Does this version work?
[http://s000.tinyupload.com/index.php?fi ... 4324165267](http://s000.tinyupload.com/index.php?file_id=12753834754324165267)
## Post #53
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-15T20:40:11+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from barti
>
> Works on my end - I guess it's because of different text encoding in your OS. Does this version work?
http://s000.tinyupload.com/index.php?fi ... 4324165267Hello, my friends, thank you for your help, you're right, is system coding for scripts now run very well.
[BaiduShurufa_2014-12-16_4-36-51.png](https://xentaxbackup.github.io/file/8282_BaiduShurufa_2014-12-16_4-36-51.png)
## Post #54
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2015-04-23T01:36:29+00:00
- Post Title: Re: Real Racing 3 (Android)

I have a problems with importing Renault DeZir model. It imports model but without parts names nor materials names

[https://www.sendspace.com/file/bmh9p1](https://www.sendspace.com/file/bmh9p1)
## Post #55
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-04-23T10:25:20+00:00
- Post Title: Re: Real Racing 3 (Android)

The Loader object inside the M3G file has been changed. Material ID and part name is now at 93 bytes from beginning of object (68 in older models). Replacing this number in the MaxScript is a temporary fix, but it won't work with older models. The Loader object would have to be researched further.

[https://www.sendspace.com/file/rx8ox2](https://www.sendspace.com/file/rx8ox2)
## Post #56
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-04-23T21:41:46+00:00
- Post Title: Re: Real Racing 3 (Android)

Have you tried it with my M3G converter?
## Post #57
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-04-23T22:08:29+00:00
- Post Title: Re: Real Racing 3 (Android)

I did. I downloaded the newest version of M3G2FBX today, and it works with older models, but the Renault model makes it crash with a "index out of range" exception.
## Post #58
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-04-23T22:27:08+00:00
- Post Title: Re: Real Racing 3 (Android)

I managed to look into it. Luckily I already had a check in place because I encountered different offsets for different versions/games.

Here's how I do it for the Mesh object type (in RR and older games which I call "version 1")
- seek 8 bytes
- read int32 - this is the important part; it works like a property count or something
 case 5 => seek 48 (no material ID)
 case 6 => seek 56 & read matID (int32)
 case 7 => seek 81 & read matID
- read mesh name

[](http://www.imagebam.com/image/1b9338405497549) 

The rest seems to be the same although I haven't tested other meshes
## Post #59
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2015-06-03T07:48:36+00:00
- Post Title: Re: Real Racing 3 (Android)

Got a problem right here with LeMans update

For some reason i can't convert the textures for the new nissan

They are downloaded as etc.dds for me , but not a single script works with them...
(Even the new script,it does not even runs)
And yes, i tried both old and new quick BMS versions :\

The mesh has been converted with renault script without any problems...
[](http://www.imagebam.com/image/ba8f66413416762) [](http://www.imagebam.com/image/0c54d3413416764) [](http://www.imagebam.com/image/2525d5413416765) 

[http://www.mediafire.com/download/37zdt ... m_lmp1.rar](http://www.mediafire.com/download/37zdt3qa4l3cj67/2015_nissan_gtr_lm_lmp1.rar)
## Post #60
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-06-03T09:24:31+00:00
- Post Title: Re: Real Racing 3 (Android)

That's odd. I downloaded your sample textures, converted them using scripts from [this post](http://forum.xentax.com/viewtopic.php?p=98840#p98840) and everything converted:
## Post #61
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2015-06-03T17:20:54+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from barti
>
> That's odd. I downloaded your sample textures, converted them using scripts from this post and everything converted:

It's ok now, I didn't realized that I need to use 2 scripts now 
However,had to remaster the livery texture to higher resolution because of "In-game" low quality
## Post #62
- Username: gpfan
- Rank: beginner
- Number of posts: 33
- Joined date: Sat Apr 02, 2011 2:59 am
- Post datetime: 2015-06-03T21:13:41+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from Ferrari formula 1
>
> Got a problem right here with LeMans update

For some reason i can't convert the textures for the new nissan

They are downloaded as etc.dds for me , but not a single script works with them...
(Even the new script,it does not even runs)
And yes, i tried both old and new quick BMS versions :\

The mesh has been converted with renault script without any problems...
   

http://www.mediafire.com/download/37zdt ... m_lmp1.rar

Could you upload the other 2 models please? Audi R18 and Porsche??
## Post #63
- Username: JONATHANTKB
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 24, 2014 12:24 pm
- Post datetime: 2015-06-04T04:10:24+00:00
- Post Title: Re: Real Racing 3 (Android)

help how convert textures?
## Post #64
- Username: joaogamer8
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 09, 2015 8:39 am
- Post datetime: 2015-06-09T00:46:46+00:00
- Post Title: Re: Real Racing 3 (Android)

hey guys, can someone help me to open the m3g files, i already downloaded autoCAD but it doesn't opened the file and i'm very ancious to edit the cars, 
ah,and other question did someone kwnows where the mustang 2015 files has been founded ?
## Post #65
- Username: JONATHANTKB
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 24, 2014 12:24 pm
- Post datetime: 2015-06-11T03:19:02+00:00
- Post Title: Re: Real Racing 3 (Android)

[](http://www.imagebam.com/image/0b3325414957639) 
have files but cant open textures
## Post #66
- Username: JONATHANTKB
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 24, 2014 12:24 pm
- Post datetime: 2015-06-11T03:22:57+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from joaogamer8
>
> hey guys, can someone help me to open the m3g files, i already downloaded autoCAD but it doesn't opened the file and i'm very ancious to edit the cars, 
ah,and other question did someone kwnows where the mustang 2015 files has been founded ?
[http://www.mediafire.com/download/5b5gf ... 3G2FBX.zip](http://www.mediafire.com/download/5b5gfesy459i4cg/M3G2FBX.zip) by chipicao
## Post #67
- Username: gpfan
- Rank: beginner
- Number of posts: 33
- Joined date: Sat Apr 02, 2011 2:59 am
- Post datetime: 2015-06-11T11:49:00+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from JONATHANTKB
>
>  
have files but cant open textures

Do you have the last update files unpacked V3.4.0? I need the 2015_porsche_911_rsr , 2015_audi_r18_e-tron_quattro and 2015_porsche_919_hybrid folders. If you have those could you upload them for me and i help you on the textures......
## Post #68
- Username: JONATHANTKB
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 24, 2014 12:24 pm
- Post datetime: 2015-06-11T18:10:48+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from gpfan
>
> JONATHANTKB wrote: 
have files but cant open textures

Do you have the last update files unpacked V3.4.0? I need the 2015_porsche_911_rsr , 2015_audi_r18_e-tron_quattro and 2015_porsche_919_hybrid folders. If you have those could you upload them for me and i help you on the textures......

ok

[http://www.mediafire.com/download/9db2y ... if/RR3.rar](http://www.mediafire.com/download/9db2yve8dg7ibif/RR3.rar)
## Post #69
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2015-11-13T21:03:44+00:00
- Post Title: Re: Real Racing 3 (Android)

Did anyone manage to get the tracks from this game?
Because I apparently can't find the main textures, just the secondary ones (maybe related to track objects)

I got:
- Catalunya
- Indianapolis
- Lemans
- Melbourne
- Monza
- Suzuka

But with missing textures
## Post #70
- Username: Fraislebem
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 16, 2015 7:36 am
- Post datetime: 2015-12-15T23:42:40+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from barti
>
> As soon as I replied to you I managed to find the scale value, it should be a bit more correct now.

I've also rewritten the script a little to be able to import track models (unfortunately it's ridiculously slow, especially on 32bit).


And, as Chipicao suggested, I've included the newer version of his code for loading normals.
Obsolete script. Click here for the newest version.

hello guys, i'm new here so excuse me for my ignorance.... i just started messing arround with painting cars that cannot be painted in RR3 such as the lemans cars, nascar cars, etc... and this forum was very helpfull... then i saw this picture of a track opened in the 3ds max so i downloaded it... but i can't open any of the track files on it..... how did you managed to open the track in the 3D modelling ??? i hope i can remove the barriers in leman so i can get the full straight.... can you guys help me out ?? thanks for the attention!!
## Post #71
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-12-16T21:52:32+00:00
- Post Title: Re: Real Racing 3 (Android)

This image was made a long time ago, so Firemonkeys probably changed the track model format since then. I know they made changes to the car models etc.

I never made much with track extraction because of no texture names, and while finding ~8 textures for cars is simple enough, it's a much more tedious process with tracks.
## Post #72
- Username: Fraislebem
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 16, 2015 7:36 am
- Post datetime: 2015-12-16T23:23:58+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from barti
>
> This image was made a long time ago, so Firemonkeys probably changed the track model format since then. I know they made changes to the car models etc.

I never made much with track extraction because of no texture names, and while finding ~8 textures for cars is simple enough, it's a much more tedious process with tracks.

Thanks anyway Barti! can you at least tell me some programs that might do the job ??? file extractors, converters.... or if you know someone that is trying to do mdos on tracks...
## Post #73
- Username: olah
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 22, 2016 4:43 am
- Post datetime: 2016-11-21T20:53:42+00:00
- Post Title: Re: Real Racing 3 (Android)

pls i need help, can someone post the RR3.bms and ddsetc2pkm.bms script here, i have searched everywhere and nt found anything
## Post #74
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-24T17:45:17+00:00
- Post Title: Re: Real Racing 3 (Android)

[viewtopic.php?p=98840#p98840](http://forum.xentax.com/viewtopic.php?p=98840#p98840)
## Post #75
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2017-09-06T13:35:57+00:00
- Post Title: Re: Real Racing 3 (Android)

I found bug in McLaren 720S, scirpt didn't name parts
[http://www.mediafire.com/view/0c86bk8bn ... 82u(5).png](http://www.mediafire.com/view/0c86bk8bn5kvnx8/Bez%C2%A0tytu%C5%82u%285%29.png)#
## Post #76
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-09-06T19:50:07+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from zimex25
>
> I found bug in McLaren 720S, scirpt didn't name parts
http://www.mediafire.com/view/0c86bk8bn ... 82u(5).png#can anyone reupload latest scripts?
## Post #77
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2017-09-07T10:34:08+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from Tosyk
>
> can anyone reupload latest scripts?
Not sure about latest or not 
[RealRacing3_m3g_import_by_barti.zip](https://xentaxbackup.github.io/file/13287_RealRacing3_m3g_import_by_barti.zip)
## Post #78
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2017-10-24T14:56:47+00:00
- Post Title: Re: Real Racing 3 (Android)

Anybody Can fix this bug?
## Post #79
- Username: rusTORK
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 26, 2017 7:18 pm
- Post datetime: 2017-11-26T12:02:44+00:00
- Post Title: Re: Real Racing 3 (Android)

Hello everyone.

I have strange problem with *.ETC.DDS files.

Original file was sprites_0.etc.dds.z (907 Kb), i converted it with QuickBMS and QuickBMS script for *.z files. After that i got sprites_0.etc.dds (8 193 Kb) and i can't open it with any tool i got:

1. PVRTexTool (Error: Either file is not a valid image or texture file, or is an unsupported format. If the file is a simple bitmap or texture file, you could try wrapping it as raw data.);
2. Mali Texture Compression Tool (Error: Cannot load images. Cannot load the image. An invalid or unsupported compression method was detected.: *.etc.dds).

I also got barti script for QuickBMS, which convert *.ETC.DDS into *.PVR (8 193 Kb), but... something really wrong with quality of output file (look for attached file, i cut only 1 individual picture of big image):

1. It's upside down;
2. Horizontaly mirrored;
3. Low quality.

At the same time, image on the screen is better quality and bigger resolution. So, maybe it's problem with conversion? I have no such problem with direct conversion in *.pvr.

Also, ddsetc2pkm.bms is the same as barti script or it's something diffirent (but it's named *.pkm)? I didn't founded link on it to test.

Update: Founded that ddsetc2pkm.bms script. Converted sprites_0.etc.dds (8 193 Kb) into sprites_0.etc.tga (16 385 Kb). It's now rotated properly, but image quality is still same low.
[PIC.png](https://xentaxbackup.github.io/file/13597_PIC.png)
## Post #80
- Username: MacedoSTI
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 11:57 pm
- Post datetime: 2018-07-11T06:44:19+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from barti
>
> Corrected MAXScript:
https://www.sendspace.com/file/ucbrlk
http://s000.tinyupload.com/index.php?fi ... 6312862391 (mirror)

The Miura interior sample loads correctly now.
Also materials are automatically loaded into the Material Editor for easier texture replacing.


Aluigi wrote a QuickBMS script for Real Racing 3, which can open the .z files as well as .bin files:
http://aluigi.altervista.org/papers/bms ... cing_3.bms

I also found out a while ago that the PVR format can contain ETC1 and RGBA4444 textures. So I made a etc.dds to pvr QuickBMS script to streamline the texture conversion process for this platform.
Code: Select all# Real Racing 3 .etc.dds to .pvr converter
#
# written by barti
# http://forum.xentax.com
#
# script for QuickBMS http://quickbms.aluigi.org

get NAME basename
string NAME += ".pvr"

idstring "DDS "
get HEADERSZ long
get SIZE     long
get WIDTH    long
get HEIGHT   long
get IMGSIZE  long
goto 84
getdstring ETCHEADER 4
goto 128

set MEMORY_FILE compressed eNp9w7ENAAAIAjAJDxoH/j+FDTabdHWcB7IMMl0A/w==

if ETCHEADER == "ETC "
	putvarchr MEMORY_FILE 8  6 long # stands for ETC1 RGB
elif ETCHEADER == "ATC "
	print "Sadly ATITC textures are not supported in the PVR container. Exiting script."
	cleanexit
elif ETCHEADER == "ATCI"
	print "Sadly ATITC textures are not supported in the PVR container. Exiting script."
	cleanexit
elif ETCHEADER == ""
	xmath IMGSIZE "WIDTH * HEIGHT * 2"

	putvarchr MEMORY_FILE 8  0x61626772 long # "rgba"
	putvarchr MEMORY_FILE 12 0x04040404 long # bits per channel
else
	print "Unsupported header found, exiting script."
	cleanexit
endif

putvarchr MEMORY_FILE 24 WIDTH   long
putvarchr MEMORY_FILE 28 HEIGHT  long
putvarchr MEMORY_FILE 44 1 long # MIPMAPS

append
log MEMORY_FILE 128 IMGSIZE
append

get SIZE asize MEMORY_FILE
log NAME 0 SIZE MEMORY_FILE

These are the texture formats in Real Racing 3 I've stumbled upon so far:
.atc.dds - ATI Texture Compression. Can be opened using The Compressonator.
.etc.dds - Ericsson Texture Compression and RGBA4444 for translucent images. I recommend converting them to .pvr using the above script.
.dxt.dds - DXT Texture Compression. These textures can be opened in any DDS viewer without any problems.
.ptc.pvr - PVR Texture Compression. These textures can be opened using PVRTexTool and imported into 3DS Max or Photoshop using PVRTexTool's plugins.

any can reupload those links? 1 link is off and mirror is deleted file
## Post #81
- Username: jimjack
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 08, 2010 3:56 am
- Post datetime: 2019-03-04T19:37:05+00:00
- Post Title: Re: Real Racing 3 (Android)

does the script work on the newest version of rr3 to xtract cars/tracks ?
## Post #82
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2019-03-05T18:40:49+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from jimjack ↑Tue Mar 05, 2019 3:37 am at Tue Mar 05, 2019 3:37 am
>
> 
does the script work on the newest version of rr3 to xtract cars/tracks ?
[RealRacing3.rar](https://xentaxbackup.github.io/file/15832_RealRacing3.rar)
## Post #83
- Username: jimjack
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 08, 2010 3:56 am
- Post datetime: 2019-03-05T20:49:32+00:00
- Post Title: Re: Real Racing 3 (Android)

thanks....

i've downloaded and playing via bluestacks..
could someone give me some help locating and how to unpack the files 
much appreciated
## Post #84
- Username: djibsone2
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Dec 21, 2016 10:15 am
- Post datetime: 2019-08-03T13:02:04+00:00
- Post Title: Re: Real Racing 3 (Android)

Hello everyone I wonder if it is possible to find the Porsche 919 hibryde evo concept  from le Mans update 

thank you
## Post #85
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2019-08-04T10:02:08+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from djibsone2 ↑Sat Aug 03, 2019 9:02 pm at Sat Aug 03, 2019 9:02 pm
>
> 
Hello everyone I wonder if it is possible to find the Porsche 919 hibryde evo concept  from le Mans update 

thank you

All models extracted by me (GM25) [http://www.mediafire.com/folder/q7kqxyc ... l_Racing_3](http://www.mediafire.com/folder/q7kqxycq8yc5i/Real_Racing_3)
## Post #86
- Username: djibsone2
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Dec 21, 2016 10:15 am
- Post datetime: 2019-08-04T15:16:52+00:00
- Post Title: Re: Real Racing 3 (Android)

big thank zimex
## Post #87
- Username: djibsone2
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Dec 21, 2016 10:15 am
- Post datetime: 2019-08-06T17:02:14+00:00
- Post Title: Re: Real Racing 3 (Android)

thank you very musch for the last porsche update
## Post #88
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-09-10T08:19:37+00:00
- Post Title: Re: Real Racing 3 (Android)

Thanks for your help
## Post #89
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2020-09-07T21:04:26+00:00
- Post Title: Re: Real Racing 3 (Android)

Any chance for script of this files for Quick BMS? Files with .liveries is the car livery list (probably) [https://mega.nz/file/741BUTAJ#jbagP-SS7 ... fUdiAMJYhg](https://mega.nz/file/741BUTAJ#jbagP-SS7Sm9pVSMExCRYaEVTuVJfkUEEfUdiAMJYhg)
I want this file in .txt format and re-import into orginal format.
## Post #90
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-10-13T19:44:09+00:00
- Post Title: Re: Real Racing 3 (Android)

Compressonator not recongizing some of these etc.dds files. The ones are wheel_blur files and the badges files. Can anybody help me convert these?
[http://www.mediafire.com/file/t8cofmood ... c.dds/file](http://www.mediafire.com/file/t8cofmoodtiu6j7/2016_alfa_romeo_giulietta_tcr_wheel_blur.etc.dds/file)
[http://www.mediafire.com/file/4xvpatz4d ... c.dds/file](http://www.mediafire.com/file/4xvpatz4dfym66i/2016_alfa_romeo_giulietta_tcr_badges.etc.dds/file)
## Post #91
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-01-09T20:32:48+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from TomWin ↑Mon Mar 03, 2014 5:01 am at Mon Mar 03, 2014 5:01 am
>
> 
any idea where to find texture names used for interiors? Material name doesnt help too much is just Vehicle Interior_mm_mat01, Vehicle Interior_mm_mat02, Vehicle Interior_mm_mat03, ...etc

I am wondering this too!!!!
## Post #92
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-05T17:22:54+00:00
- Post Title: Re: Real Racing 3 (Android)

Can we get .points files converted? It would help A LOT because it will let us know where to put wheels.
## Post #93
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-05T17:24:19+00:00
- Post Title: Re: Real Racing 3 (Android)


## Post #94
- Username: Ram36
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 08, 2022 7:39 am
- Post datetime: 2022-07-08T01:26:33+00:00
- Post Title: Re: Real Racing 3 (Android)

Hi, i would like to ask if there is a way to modify decals on the game. I already tried modifying like a livery, but doesnt work. Can someone help me
## Post #95
- Username: Kornel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 18, 2022 4:54 am
- Post datetime: 2022-07-17T20:57:58+00:00
- Post Title: Re: Real Racing 3 (Android)

All models extracted by me (GM25) [http://www.mediafire.com/folder/q7kqxyc ... l_Racing_3](http://www.mediafire.com/folder/q7kqxycq8yc5i/Real_Racing_3)
[/quote]

Envision FE livery from 2022 missing
## Post #96
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2022-10-17T05:42:37+00:00
- Post Title: Re: Real Racing 3 (Android)

> Reply from zimex25 ↑Sun Aug 04, 2019 6:02 pm at Sun Aug 04, 2019 6:02 pm
>
> All models extracted by me (GM25) http://www.mediafire.com/folder/q7kqxyc ... l_Racing_3

> Reply from Kornel ↑Mon Jul 18, 2022 4:57 am at Mon Jul 18, 2022 4:57 am
>
> Envision FE livery from 2022 missing
Also missing these models:
1985_lamborghini_countach
1999_nissan_skyline_r34
2005_ford_gt
2005_pagani_zondaf
2008_bmw_z4_m
2009_bentley_supersports
2009_chevrolet_cobaltss
2009_pagani_zondar
2010_bmw_m3
2010_bmw_m3_gt2
2010_dodge_vipersrt10
2010_dodge_vipersrt_acrx
2010_ford_focus_rs
2010_renault_dezirconcept
2011_nissan_jrm_gtr_gt1
2011_nissan_sumo_gtr_gt1
2012_audi_r8_lms
2012_audi_tt
2012_bmw_z4sdrive35is
2012_bugatti_veyron_ss
2012_dodge_challenger_rt
2012_dodge_challenger_srt8
2012_ford_gt1
2012_lamborghini_gallardo_gt3
2012_lexus_lfa
2012_mercedes_sl65amg
2012_nissan_370z
2013_ariel_atom_35
2013_astonmartin_db9
2013_astonmartin_vantage
2013_audi_r8
2013_bentley_cgtspeed
2013_caterham_seven_620r
2013_chevrolet_camarozl1
2013_chevrolet_corvette_zr1
2013_dodge_charger_rt
2013_dodge_charger_srt8
2013_dodge_viper_srtgts
2013_ford_mustang_shelbygt500
2013_lexus_isf
2013_mercedes_sls
2013_mercedes_sls_gt3
2013_porsche_911_rsr
2014_lexus_is_f350_sport
2014_toyota_ts040_hybrid
2015_chevrolet_ss_nascar
2015_chevrolet_ss_nascar_stewart_haas
2015_ford_fusion_nascar
2015_ford_fusion_nascar_penske
2015_hennessey_venom_gt
2016_chevrolet_ss_nascar
2016_chevrolet_ss_nascar_elliot
2016_chevrolet_ss_nascar_harvick
2016_ford_fusion_nascar
2016_ford_fusion_nascar_petty
2016_toyota_camry_nascar
2016_toyota_camry_nascar_kenseth
2017_ford_falcon_v8_supercar
2017_holden_commodre_v8_supercar
2017_nissan_altima_v8_supercar
2022_formula_e_s08_envision
(Comparing with download lists in com.ea.games.r3_row\files\apk\res\)
