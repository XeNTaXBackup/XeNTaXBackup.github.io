## Post #1
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-12-18T23:48:01+00:00
- Post Title: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

Hey everyone.

I'm having trouble extracting the BF files from Beyond Good & Evil HD. The old BF extractors for all of the Jade Engine games don't seem to work on it anymore, so I guess a new one needs to be written for this. Don't worry though, it looks like it's similar to the previous ones so it won't be so hard to do. As the BF files were too large (1,62GB for the Xbox version's BF), I used aluigi's File Cutter script to cut out the first and last megabyte of the files.

Xbox 360 version: [http://www.box.com/s/2rq10hn1lthyx3lqvhxn](http://www.box.com/s/2rq10hn1lthyx3lqvhxn)
PS3 version: [http://www.box.com/s/0smkhalacim93g59ee2o](http://www.box.com/s/0smkhalacim93g59ee2o)

Thanks!
Droolie.

PS: This same format is probably also used for Prince of Persia Trilogy HD on PS3.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-19T08:17:47+00:00
- Post Title: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

*EDIT* updated script

the format is very similar to the one I have seen yesterday in NCIS with some little differences:

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "BIG\0"
get DUMMY long
get FILES long
math INFO_OFF = 0x44
math NAMES_OFF = 0x15ab8

        goto INFO_OFF
        get OFFSET long
        get DUMMY long
        savepos INFO_OFF
for i = 1 <= FILES
    if i == FILES
        get NEXT_OFFSET asize
    else
        goto INFO_OFF
        get NEXT_OFFSET long
        get DUMMY long
        savepos INFO_OFF
    endif

    goto NAMES_OFF
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get TSTAMP long
    getdstring NAME 0x40
    savepos NAMES_OFF

    math SIZE = NEXT_OFFSET
    math SIZE -= OFFSET
    string NAME R= "_" "/"
    log NAME OFFSET SIZE
    math OFFSET = NEXT_OFFSET
next i
```

I guess I will need to write a better and more universal script in future for working with any game
## Post #3
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-12-19T11:28:47+00:00
- Post Title: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

Thanks! That works great for extracting the files with the correct sizes, although there seems to be a problem with the filenames. They all take their names from the next file in the file list. For example, the file that's supposed to be named "Stealth_StreamC.wam" is named "Stealth_StreamZ.wam". The file that's supposed to be named "Stealth_StreamZ.wam" is extracted as "intro_snake_US.wad", etc.
It's only a small issue but otherwise it's perfect.
## Post #4
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-12-19T20:35:23+00:00
- Post Title: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

Somethings wrong with the PS3 version. The extracted files not contain the right data. Somehow the whole data is shifted.
The X360 files are good. (The fd40xxxx.bin should contain readable english texts somewhere at the start of the file.)
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-20T22:12:48+00:00
- Post Title: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

ah sorry, my fault.
I mistyped the NAMES_OFFSET... I have corrected the script of the previous post.
tell me if it's ok now
## Post #6
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-12-20T23:39:35+00:00
- Post Title: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

Works perfectly for the Xbox version now, thanks a lot! That's what I needed. 
It doesn't work for PS3 though, as evin said.
## Post #7
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-12-21T07:41:59+00:00
- Post Title: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

> Reply from aluigi
>
> ah sorry, my fault.
I mistyped the NAMES_OFFSET... I have corrected the script of the previous post.
tell me if it's ok now

Unfortunately, nothings changed.  

I uploaded a bigger cut from the beginning of PS3 bf file, I hope this should help: [http://dl.dropbox.com/u/4953836/Xentax/ ... _header.bf](http://dl.dropbox.com/u/4953836/Xentax/bgeHDPS3_header.bf)
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-21T19:25:19+00:00
- Post Title: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

I have checked it but that's it.
I handle the files sequentially because the format sux and I don't see a number which indicates what filename matches the entry (where is contained the offset).
so if the names and the entries are not sequential I can do nothing.
## Post #9
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-12-21T19:32:38+00:00
- Post Title: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

> Reply from aluigi
>
> I have checked it but that's it.
I handle the files sequentially because the format sux and I don't see a number which indicates what filename matches the entry (where is contained the offset).
so if the names and the entries are not sequential I can do nothing.
The names and the entries are sequential for the Xbox version. It works perfectly for that.
They're probably sequential in the PS3 version as well, but the size/offset seems to be wrong there - that's all.
## Post #10
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-12-22T09:50:22+00:00
- Post Title: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

I found where goes wrong everything: after ff800bdd.bin
In the PS3 bf file, the ff800bdd.bin has wrong size, and after this file, some file are missing, or somehow changed the order. Or the ff800bdd.bin already not the ff800bdd.bin file.
I think, I have to unpack by hand all the 90 English language file, based on the unpacked files of correct X360 bf.  
Unfortunately my PS3 is not works now, so I can't test if the bf file is wrong, or working the game well.
## Post #11
- Username: DuderDuder
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Dec 10, 2010 10:12 pm
- Post datetime: 2012-02-28T02:27:32+00:00
- Post Title: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

Hey hi. Just extracted this with quickbms, great tool. Just a few questions.

Do these extracted waa, wam etc files work with any current tool?

Comparing to the old PC extractions, these files from x360 are significantly smaller. Compressed somehow?

[03 - Theme Home.wam (x360) 3.7megs](http://beerlake.net/stuff/03%20-%20Theme%20Home%20x360.wam)
[03 - Theme Home.wam (PC)  6.3megs](http://beerlake.net/stuff/03%20-%20Theme%20Home%20pc.wam)

I have no idea how to make either of these into a regular wav.
Any ideas?
## Post #12
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2012-02-28T12:16:23+00:00
- Post Title: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

The Xbox 360 file is XMA, you can convert it using VGMToolbox. The PC one used Ubisoft native compression, it can be converted with towav.
## Post #13
- Username: DuderDuder
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Dec 10, 2010 10:12 pm
- Post datetime: 2012-02-28T15:03:34+00:00
- Post Title: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

Thanks Droolie.

Used the New Vegas preset in vgmtoolbox, only had to modify the block size to get full songs.
## Post #14
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-07-07T19:12:30+00:00
- Post Title: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

BTW, my xma_process.bms also supports these files and many more XMA types: [viewtopic.php?f=17&t=9023](http://forum.xentax.com/viewtopic.php?f=17&t=9023)
## Post #15
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2016-01-16T01:32:37+00:00
- Post Title: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

What about the 3D Models, textures, and animations?
## Post #16
- Username: ka87
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 23, 2011 8:14 am
- Post datetime: 2018-06-15T13:56:43+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

I wrote a tool, it can open BGAE's bf file, and it can display whole maps, display models, and play animations.
You can check this on youtube:
[https://youtu.be/l3Knr59wdpA](https://youtu.be/l3Knr59wdpA)
## Post #17
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2018-06-16T07:15:10+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

> Reply from ka87
>
> I wrote a tool, it can open BGAE's bf file, and it can display whole maps, display models, and play animations.
You can check this on youtube:
https://youtu.be/l3Knr59wdpA
Does it work on King Kong?
## Post #18
- Username: ka87
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 23, 2011 8:14 am
- Post datetime: 2018-06-16T08:47:04+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

> Reply from Puterboy1
>
> ka87 wrote:I wrote a tool, it can open BGAE's bf file, and it can display whole maps, display models, and play animations.
You can check this on youtube:
https://youtu.be/l3Knr59wdpA
Does it work on King Kong?

Not yet. Only BGE (all versions)
## Post #19
- Username: ka87
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 23, 2011 8:14 am
- Post datetime: 2018-06-16T14:03:03+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

[https://mega.nz/#!6S4EFD6L!f2POyp_v9gnt ... OVzQt9N18g](https://mega.nz/#!6S4EFD6L!f2POyp_v9gntjQrkeWzB6iS6SWJ28taChOVzQt9N18g)
IrisTool 0.24 download, it requires Java JRE to be installed.
## Post #20
- Username: jackblack
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri May 20, 2011 7:56 am
- Post datetime: 2018-06-22T11:09:53+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

Wow, that is amazing! Can you export geometry?
## Post #21
- Username: ka87
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 23, 2011 8:14 am
- Post datetime: 2018-06-26T10:59:51+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

> Reply from jackblack
>
> Wow, that is amazing! Can you export geometry?
Yes I can, but I can not know any format where I can store texturing as game uses. (eg. transformation matrices, blending)
## Post #22
- Username: Resiliaxia
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Jun 25, 2016 4:59 am
- Post datetime: 2018-07-20T20:54:15+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

This tool is fantastic is it possible to make it work with Rise of a Ninja and Broken Bond ? Here some RoaN samples : [https://mega.nz/#!WdsEFSoC!KJuC363AwJDQ ... uLNZjjuZqQ](https://mega.nz/#!WdsEFSoC!KJuC363AwJDQxZUGqwS_QUIp7aK_hhrr4uLNZjjuZqQ)
## Post #23
- Username: Fewnity
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 24, 2018 6:09 am
- Post datetime: 2018-07-23T22:32:23+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

> Reply from ka87
>
> https://mega.nz/#!6S4EFD6L!f2POyp_v9gnt ... OVzQt9N18g
IrisTool 0.24 download, it requires Java JRE to be installed.
Your tool is very good, but we can't export texture and 3d models...
## Post #24
- Username: Nathbusia
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 01, 2018 7:15 pm
- Post datetime: 2018-08-01T11:20:16+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

I'm trying to use The IrisTool but I don't have jade.spe
I was hoping if I can view some Rayman Raving Rabbids 2 files (RRR2.bf) but i need jade.spe.

Can I have the download for jade.spe please?
## Post #25
- Username: fouzberzerk
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 07, 2018 7:55 pm
- Post datetime: 2018-08-03T00:53:18+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

Can you make this work with Naruto: The Broken Bond? the header of the Xbox 360 .BF variant is 'BF64'
and the bfextractor made for BGAE doesn't work with it.
Trying to use results in this error: [https://media.discordapp.net/attachment ... nknown.png](https://media.discordapp.net/attachments/292590509057376256/474737996126748674/unknown.png)
Example file: [https://mega.nz/#!XCgU2QqC!C0fczJJzfCKA ... rJg6PnHLgs](https://mega.nz/#!XCgU2QqC!C0fczJJzfCKA9CaRLf_eymMujZrgFL5GFrJg6PnHLgs)
Thanks!
## Post #26
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-09-14T23:38:24+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

> Reply from ka87
>
> I wrote a tool, it can open BGAE's bf file, and it can display whole maps, display models, and play animations.
You can check this on youtube:
https://youtu.be/l3Knr59wdpA
The tool is great. Will there be a feature to extract the models and textures?
## Post #27
- Username: ka87
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 23, 2011 8:14 am
- Post datetime: 2018-09-19T19:22:45+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

I'm not planning those features, because I can not store texture transformations into some common format.
BTW: I'm planning to release a new version, you can see it on youtube: [https://youtu.be/SSgINERmWKg](https://youtu.be/SSgINERmWKg)
I've fixed lighting, and added sprites & particles support.

> Reply from Escope12
>
> ka87 wrote:I wrote a tool, it can open BGAE's bf file, and it can display whole maps, display models, and play animations.
You can check this on youtube:
https://youtu.be/l3Knr59wdpA
The tool is great. Will there be a feature to extract the models and textures?
## Post #28
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-09-19T21:59:56+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

> Reply from ka87
>
> I'm not planning those features, because I can not store texture transformations into some common format.
BTW: I'm planning to release a new version, you can see it on youtube: https://youtu.be/SSgINERmWKg
I've fixed lighting, and added sprites & particles support.
Escope12 wrote:ka87 wrote:I wrote a tool, it can open BGAE's bf file, and it can display whole maps, display models, and play animations.
You can check this on youtube:
https://youtu.be/l3Knr59wdpA
The tool is great. Will there be a feature to extract the models and textures?
RIP. I really want to extract the models. Wish I can help.

EDIT: What’s this common format you speak of for textures? Do you mean DDS, PNG, TGA, BMP, JPEG, & GIF?
## Post #29
- Username: ka87
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 23, 2011 8:14 am
- Post datetime: 2018-10-29T17:59:37+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

I have no problem with textures, but their transformations. They're using matrices to stretch textures. I can not implement these in common way.

> Reply from Escope12
>
> ka87 wrote:I wrote a tool, it can open BGAE's bf file, and it can display whole maps, display models, and play animations.
You can check this on youtube:
https://youtu.be/l3Knr59wdpA
The tool is great. Will there be a feature to extract the models and textures?[/quote]
RIP. I really want to extract the models. Wish I can help.

EDIT: What’s this common format you speak of for textures? Do you mean DDS, PNG, TGA, BMP, JPEG, & GIF?[/quote]
## Post #30
- Username: ka87
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 23, 2011 8:14 am
- Post datetime: 2018-10-29T18:10:54+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

IrisTool: New version (0.25.2)
You can download it from here: [https://mega.nz/#!qDBTxQjK!G0fqHGsx29Go ... Xf46taUHIM](https://mega.nz/#!qDBTxQjK!G0fqHGsx29GoXLWCw8vF9Sgws3oXQ0_iZXf46taUHIM)

Changelog
- Fixed aspect ratio 
- Usable FPS-like camera
- Realtime lights support
- Fog support
- Sprite generator support
- Particle engine
- Mesh wave modifier support
- File list searchable, Game object key & name search

Screenshots
## Post #31
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-10-30T21:52:42+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

> Reply from ka87
>
> IrisTool: New version (0.25.2)
You can download it from here: https://mega.nz/#!qDBTxQjK!G0fqHGsx29Go ... Xf46taUHIM

Changelog
- Fixed aspect ratio 
- Usable FPS-like camera
- Realtime lights support
- Fog support
- Sprite generator support
- Particle engine
- Mesh wave modifier support
- File list searchable, Game object key & name search

Screenshots
The shield's in Hillys are a little messed up.
## Post #32
- Username: ka87
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 23, 2011 8:14 am
- Post datetime: 2018-10-30T22:02:44+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

It is not a problem, they stored a broken geometry morphing during a progress of development and using scripting to disable it. IrisTool can not handle scripting due it is not present in bf file, but compiled into binary file (eg. BGE.exe). Just hit "m" key when you are viewing that level to disable morphing. That should fix this issue.

> Reply from Escope12
>
> ka87 wrote:IrisTool: New version (0.25.2)
You can download it from here: https://mega.nz/#!qDBTxQjK!G0fqHGsx29Go ... Xf46taUHIM

Changelog
- Fixed aspect ratio 
- Usable FPS-like camera
- Realtime lights support
- Fog support
- Sprite generator support
- Particle engine
- Mesh wave modifier support
- File list searchable, Game object key & name search

Screenshots


The shield's in Hillys are a little messed up.
## Post #33
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-10-30T22:46:15+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

> Reply from ka87
>
> It is not a problem, they stored a broken geometry morphing during a progress of development and using scripting to disable it. IrisTool can not handle scripting due it is not present in bf file, but compiled into binary file (eg. BGE.exe). Just hit "m" key when you are viewing that level to disable morphing. That should fix this issue.
Escope12 wrote:ka87 wrote:IrisTool: New version (0.25.2)
You can download it from here: https://mega.nz/#!qDBTxQjK!G0fqHGsx29Go ... Xf46taUHIM

Changelog
- Fixed aspect ratio 
- Usable FPS-like camera
- Realtime lights support
- Fog support
- Sprite generator support
- Particle engine
- Mesh wave modifier support
- File list searchable, Game object key & name search

Screenshots


The shield's in Hillys are a little messed up.I didn't know that. Thank you.
## Post #34
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-11-08T00:58:36+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

How do you hide certain objects when you "Render World"?
## Post #35
- Username: ka87
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 23, 2011 8:14 am
- Post datetime: 2019-01-11T13:54:06+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

> Reply from Escope12
>
> How do you hide certain objects when you "Render World"?
I'm not sure, what are you asking. Do you want to hide something in world view?
## Post #36
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-01-11T14:04:26+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

> Reply from ka87
>
> Escope12 wrote:How do you hide certain objects when you "Render World"?
I'm not sure, what are you asking. Do you want to hide something in world view?
Yes.
## Post #37
- Username: ka87
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 23, 2011 8:14 am
- Post datetime: 2019-01-11T14:14:03+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

IrisTool: New version (0.26)
You can download it from here: [https://mega.nz/#!vbAyhK5K!z01lMT9Hb5Ny ... ry8ccWm3tU](https://mega.nz/#!vbAyhK5K!z01lMT9Hb5NynpuzdzMsV74YNEEW2FEcSry8ccWm3tU)

Animation in action:
[https://www.youtube.com/watch?v=VVmieQfnxfI](https://www.youtube.com/watch?v=VVmieQfnxfI)

Changelog
- Collision map & instance debug display ("n", "b" key in Render World or in Render Geometry)
- Fixed lights distance calculation
- More modifier support: Snake, Lazy (makes animation more loook like as in original game: eg PeyJ's ears), 
  and Inverse Kinematics (cranes movement and calculation)
- Implemented "object look at camera"-type rendering (eg. fixes pearl's halo display)
- Fixed particle generator generated particles misplacement
- Implemented diffuse UV mapping
- Implemented planar UV mapping for remaining matrix types (viewMatrix, globalMatrix) (fixes BGE logo display)
- Added Goto Game Object possibility in Goto Position dialog ("p" key in Render World)
## Post #38
- Username: ka87
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 23, 2011 8:14 am
- Post datetime: 2019-01-11T14:15:05+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

> Reply from Escope12
>
> ka87 wrote:Escope12 wrote:How do you hide certain objects when you "Render World"?
I'm not sure, what are you asking. Do you want to hide something in world view?
Yes.

Currently it is not possible. I'll make an option for this in the next version.
## Post #39
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-01-18T17:20:32+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

> Currently it is not possible. I'll make an option for this in the next version.
[/quote]
Hi, please add a simple obj export opton
## Post #40
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2019-07-09T21:06:20+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

Has anyone tested this on King Kong yet?
## Post #41
- Username: Fewnity
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 24, 2018 6:09 am
- Post datetime: 2019-07-09T23:21:20+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

Surely we can never have his models 3d ...
## Post #42
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-07-09T23:52:39+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

I wish we can extract the models from Beyond Good & Evil.
## Post #43
- Username: lisa066
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 20, 2020 9:06 pm
- Post datetime: 2020-04-20T13:10:42+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

nice work kandras
## Post #44
- Username: rockspam15
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 13, 2020 3:00 pm
- Post datetime: 2020-05-13T07:21:47+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

Will this extractor work with TMNT 2007 game?
## Post #45
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2021-01-09T15:55:41+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

I tried to view the map files in the PC Version of Beyond Good & Evil on Steam but it doesn't work.
## Post #46
- Username: ConTrast
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 04, 2021 6:16 am
- Post datetime: 2021-07-03T22:31:01+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

Hello

How can I extract and repackage audio?
  (for a successful language change). 

--
I am familiar with the repack of the text (from internet-page):
[viewtopic.php?f=32&t=7101&p=176068#p176068](https://forum.xentax.com/viewtopic.php?f=32&t=7101&p=176068#p176068)

, although the practice will not be easy    ... 
... usability
## Post #47
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2022-01-04T13:18:19+00:00
- Post Title: Re: Beyond Good & Evil HD *.BF files (Xbox 360 / PS3)

Is there a way that I can request someone to make a tool from Beyond Good & Evil to view and extract models from the .bin files?
