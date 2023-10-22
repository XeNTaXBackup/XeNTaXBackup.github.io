## Post #1
- Username: Chthonic
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-25T04:16:48+00:00
- Post Title: (X360) Marvel Vs Capcom 3

Marvel Vs Capcom 3 arc extractor

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

quickbmsver 0.3.13
set HFS long 0
set BASE_OFF long 0

get SIGN long
if SIGN == 0x00534648   # " SFH"
    endian big
    set HFS long 1
elif SIGN == 0x48465300 # "HFS "
    endian little
    set HFS long 1
endif

if HFS != 0
    get DUMMY short
    get TYPE short
    if TYPE == 0
        set BASE_OFF long 0x20000
    else
        set BASE_OFF long 0x10
    endif
    goto BASE_OFF
    get SIGN long
endif

if SIGN == 0x00435241   # " CRA"
    endian little
elif SIGN == 0x41524300 # "ARC "
    endian big
else
    cleanexit
endif
get VERSION short
if VERSION == 4
    comtype zlib
elif VERSION == 8
    set TYPE2 ".ps3"
    comtype deflate
elif VERSION == 0x11
    set TYPE2 ".360"
    comtype XMemDecompress 0x8000   # yeah 0x8000 is the "magic" for RE5
else
    comtype zlib
    print "unknown version %VERSION%, I try zlib compression"
endif
get FILES short

for i = 0 < FILES
    getdstring NAME 0x40
    string name + TYPE2
    get TYPE long
    get ZSIZE long
    get SIZE long
    get OFFSET long
    print %TYPE%
    if TYPE == 606035435
     string name + .TEX
    elif TYPE == 1486968918
    string name + .DOM
    elif TYPE == 659146920
    string name + .MRL
    elif TYPE == 1988234625
    string name + .LMT
    elif TYPE == 329180445
    string name + .LMT
    else
    string name + .
    string name + TYPE
    print "unknown TYPE %TYPE%, let me know what it is"
    endif
    if SIZE & 0x40000000
        math SIZE -= 0x40000000
    endif

    if HFS != 0 # used in RE5 PS3
        math ZSIZE += 32
        #math SIZE /= 8
        math TMP = OFFSET
        math TMP /= 0x20000
        math TMP *= 0x10
        math ZSIZE  += TMP
        math SIZE   += TMP
        math OFFSET += TMP
        math OFFSET += 2
    endif

    math OFFSET += BASE_OFF # needed for HFS header
    clog NAME OFFSET ZSIZE SIZE
next i

```


Models coming soon 
[m vs c 3.png](https://xentaxbackup.github.io/file/4260_m vs c 3.png)
## Post #2
- Username: timkango
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 12, 2011 4:16 pm
- Post datetime: 2011-05-25T08:44:55+00:00
- Post Title: (X360) Marvel Vs Capcom 3

Would it be possible to see the actual code for the decompression routine? ("xmemdecompress 0x8000")
## Post #3
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-05-25T09:03:37+00:00
- Post Title: (X360) Marvel Vs Capcom 3

yay :D
## Post #4
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-05-25T10:37:37+00:00
- Post Title: (X360) Marvel Vs Capcom 3

Cool sir chrrox, do the models come out of the arc file immediately or there is another compression method for the models?
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-25T11:23:22+00:00
- Post Title: (X360) Marvel Vs Capcom 3

I have to make a max script for the models to import into 3ds max i am working on bones and weights.
The source code for quickbms is freely available to see what that command does.
## Post #6
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-05-25T12:31:09+00:00
- Post Title: (X360) Marvel Vs Capcom 3

Ok then I'll be watching this thread for new updates 
btw sir chrrox are you gonna do models Naruto Shippuden Ultimate ninja storm 2 too?
## Post #7
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-05-25T22:15:43+00:00
- Post Title: (X360) Marvel Vs Capcom 3

in this case, is the arc format format the same in some way that the format used in RE5 DLC??

Just curious.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-25T22:49:03+00:00
- Post Title: (X360) Marvel Vs Capcom 3

its the same as the re5 arc format.
## Post #9
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-05-25T23:46:32+00:00
- Post Title: (X360) Marvel Vs Capcom 3

wow wow
This is great chrrox
## Post #10
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-05-26T00:35:10+00:00
- Post Title: (X360) Marvel Vs Capcom 3

> Reply from chrrox
>
> its the same as the re5 arc format.

Thanks
## Post #11
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2011-05-26T07:51:40+00:00
- Post Title: (X360) Marvel Vs Capcom 3

Will the extractor be region-specific?
## Post #12
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-05-26T09:43:21+00:00
- Post Title: (X360) Marvel Vs Capcom 3

Well "comtype xmemdecompress 0x8000"

Is where everyone went wrong; it seems that the compressed data starts at 0x8000.
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-26T20:20:01+00:00
- Post Title: (X360) Marvel Vs Capcom 3

Actually its the window size they just changed that.
## Post #14
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-05-27T00:05:30+00:00
- Post Title: (X360) Marvel Vs Capcom 3

Chrrox any chance you're gonna continue with mgs 4 model extraction ??
## Post #15
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-05-27T18:27:14+00:00
- Post Title: (X360) Marvel Vs Capcom 3

Noesis opens those models now with v3.2. Although there are various issues. Can't find the texture index for the materials (although the materials are correctly mapped), and I think pointweighting still has issues with > 2 weights. Haven't had a lot of time to look at it (and I'm about to take off again for the day), so hopefully chrrox or revelation can make some progress from my code.
## Post #16
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-05-27T18:35:54+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

Amazing!!!!!!!!!!!!!!!
## Post #17
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-05-27T18:46:16+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

Successfully exported the models with noesis but the problem is the textures now, is there a script to convert them? Noesis can't convert the textures.
## Post #18
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-05-27T19:44:04+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from rexil
>
> Successfully exported the models with noesis but the problem is the textures now, is there a script to convert them? Noesis can't convert the textures.

You can use ps3 textures xD and noesis do convert them
## Post #19
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-05-27T20:16:40+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from maniacoloco
>
> rexil wrote:Successfully exported the models with noesis but the problem is the textures now, is there a script to convert them? Noesis can't convert the textures.

You can use ps3 textures xD and noesis do convert them

Oh thank you for the info. Thanks chroxx and Mr Adults too. Great job as always.
## Post #20
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-05-27T20:52:16+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from rexil
>
> Successfully exported the models with noesis but the problem is the textures now, is there a script to convert them? Noesis can't convert the textures.
It can but it has no way of knowing whether they are PS3 or 360. As you will notice it yelling at you that it can't figure out the platform when you export them. Rename to .360.tex and it will work.
## Post #21
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-05-27T21:17:01+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

Is someone working on converting 360 textures?
## Post #22
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-05-27T21:17:55+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from MrAdults
>
> rexil wrote:Successfully exported the models with noesis but the problem is the textures now, is there a script to convert them? Noesis can't convert the textures.
It can but it has no way of knowing whether they are PS3 or 360. As you will notice it yelling at you that it can't figure out the platform when you export them. Rename to .360.tex and it will work.

Thank you for the info. The file is named Felicia_tex01_BM.360.TEX but it still can't recognize if it's 360 or ps3 file and it defaults to ps3 file.
## Post #23
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-05-27T22:12:56+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

Maybe I made a typo or something. I'll test and put a fix up if necessary when I'm back home.

Edit: It was checking for 360.mod for the textures because I lazily copy-pasted and never actually tested. Fixed and made a build from my phone.
## Post #24
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-05-27T22:22:36+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from MrAdults
>
> Maybe I made a typo or something. I'll test and put a fix up if necessary when I'm back home.

Ok, thank you for your awesome work. Ps3 files are exporting correctly just the 360 ones have the problem.
## Post #25
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2011-05-28T03:27:16+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

Darn, it doesn't work with the PS3 version's files. Welp, guess I'll have to get the 360 version if I want the models from this game.
## Post #26
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2011-05-28T09:55:21+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

So what's the right way to export the chars? From X360 files but I tried one (SpiderMan) and had weight problems.
## Post #27
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2011-05-29T04:24:38+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

Another problem. Other than the weighting problem (Taskmaster's cape and pretty much anyone's face are examples of this), there's also a problem with certain models being exported. For example, Tron Bonne's Servbots are able to be exported, but they aren't rigged AND they don't have their UV mapping, either. Same thing with Taskmaster's shield, and for some reason Taskmaster's sword won't even be previewed, let alone exported.
## Post #28
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2011-05-29T11:22:17+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

Why I have this error?
File is 360 version, and I have this error only with this script:
## Post #29
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-29T12:37:32+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

what version of quickbms?
I have extracted the entire game with no errors.
## Post #30
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2011-05-29T12:51:41+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from chrrox
>
> what version of quickbms?
I have extracted the entire game with no errors.

Solved!
I update quickbms and work
## Post #31
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-05-31T15:42:27+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

How extract with noesis???
.dom or .mod?

for me not extract.
## Post #32
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-06-01T14:20:47+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

I'm assuming these are different to the PS3 models.

Whether they are the same or not, may I still see your notes/max script?

I want to create a model exporter/importer for the PS3 (and possibly 360, but that would come second) for MvC3.
## Post #33
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-06-02T00:14:30+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from logansan25
>
> How extract with noesis???
.dom or .mod?

for me not extract.

Just rename it to .mod.
## Post #34
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-06-02T20:22:51+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

I make all i see on this guides and use the scripts, all works fine, also i convert Textures with neses, ut uv maping are lost and something textures are damaged, any solution?. regards.
## Post #35
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-06-03T13:16:58+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from Rimbros
>
> I make all i see on this guides and use the scripts, all works fine, also i convert Textures with neses, ut uv maping are lost and something textures are damaged, any solution?. regards.

Use texture of ps3 files y not xbox360.
## Post #36
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-06-04T13:56:36+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

Thanks for the info,so its possible to convert the texture from ps3 file
By the way is it possible to convert the model from ps3 ??
## Post #37
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-06-04T19:36:01+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from jaden
>
> Thanks for the info,so its possible to convert the texture from ps3 file
By the way is it possible to convert the model from ps3 ??

Models no, only textures!
## Post #38
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2011-06-04T21:09:30+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from logansan25
>
> jaden wrote:Thanks for the info,so its possible to convert the texture from ps3 file
By the way is it possible to convert the model from ps3 ??

Models no, only textures!It's kinda odd how the model formats between games are so different from each other that only one of the two will work. I think that you'd expect them to be the same, but I guess not.
## Post #39
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-06-05T00:40:29+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from RandomTBush
>
> logansan25 wrote:jaden wrote:Thanks for the info,so its possible to convert the texture from ps3 file
By the way is it possible to convert the model from ps3 ??

Models no, only textures!It's kinda odd how the model formats between games are so different from each other that only one of the two will work. I think that you'd expect them to be the same, but I guess not.

They are actually pretty similar.
## Post #40
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-06-06T03:40:35+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

any discovery respecting the weights??
## Post #41
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-06-08T08:20:08+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from maniacoloco
>
> any discovery respecting the weights??

The weights work already.
## Post #42
- Username: svayericsson
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 16, 2011 12:34 am
- Post datetime: 2011-06-16T07:03:55+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

Hi

Can someone extract the models of Captain America and Wolverine from the game? We are currently working on a project at the university of design in Schwaebisch Gmuend, Germany, wherefore we need these models as soon as possible, because we are running out of time. Would be really awesome if someone could do that, I'm not very familiar with game model extraction  

Regards
Sven
## Post #43
- Username: sidneymadmax
- Rank: beginner
- Number of posts: 35
- Joined date: Fri Sep 17, 2010 11:10 pm
- Post datetime: 2011-06-17T17:56:07+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

I think I got !

[http://fc04.deviantart.net/fs71/i/2011/ ... 3j5nqw.jpg](http://fc04.deviantart.net/fs71/i/2011/168/5/a/dante_mvsc_3_fuuu_by_sidneymadmax-d3j5nqw.jpg)
## Post #44
- Username: andthen619
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 7:43 pm
- Post datetime: 2011-06-23T13:50:20+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

so u can extract the textures... 
mod them...
then put them back into the game and play on the 360?
i am an artist so i am good at modding textures but extracting coding i am a noob.
## Post #45
- Username: coopmaster
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 07, 2010 1:55 pm
- Post datetime: 2011-06-23T16:17:23+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

im lost, how do i extract the arcs?
## Post #46
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-06-23T19:11:42+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from coopmaster
>
> im lost, how do i extract the arcs?

for tha 360 you use tha bms chrrox wrote
for ps3 you can use noesis
## Post #47
- Username: coopmaster
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 07, 2010 1:55 pm
- Post datetime: 2011-06-23T20:03:03+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from protosk8
>
> coopmaster wrote:im lost, how do i extract the arcs?

for tha 360 you use tha bms chrrox wrote
for ps3 you can use noesis

how would i do that for the 360? is it like a program or a batch file or what?
## Post #48
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-06-23T22:32:29+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from coopmaster
>
> protosk8 wrote:coopmaster wrote:im lost, how do i extract the arcs?

for tha 360 you use tha bms chrrox wrote
for ps3 you can use noesis

how would i do that for the 360? is it like a program or a batch file or what?

For extracting 360's arcs just use the bms posted here, for ps3's version use noesis, that's all.
## Post #49
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-06-24T11:02:43+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

If you mean Extract the arc's from tha game then, First you need to have tha game, then use something like Xbox Backup Creator. You pick the iso or dvd and you'll see tha list of arc files.

If you meant extract tha models and textures from tha arcs. You use tha .bms posted by chrrox.
Way it works is, You gotta have quickbms.exe, copy tha code .bms code, paste it in a .txt file, Save it as extract.bms or whatever you wanna call it.
then you run cmd and type

```

```

you can make a batch file too if you want and put it in tha folder with all those files. copy/edit tha "code" above.
## Post #50
- Username: coopmaster
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 07, 2010 1:55 pm
- Post datetime: 2011-06-24T19:19:56+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from protosk8
>
> If you mean Extract the arc's from tha game then, First you need to have tha game, then use something like Xbox Backup Creator. You pick the iso or dvd and you'll see tha list of arc files.

If you meant extract tha models and textures from tha arcs. You use tha .bms posted by chrrox.
Way it works is, You gotta have quickbms.exe, copy tha code .bms code, paste it in a .txt file, Save it as extract.bms or whatever you wanna call it.
then you run cmd and type
Code: Select allquickbms.exe extract.bms ARC_File_Here.arc C:/path_here

you can make a batch file too if you want and put it in tha folder with all those files. copy/edit tha "code" above.

okay i got it all but i get an error in cmd i get error:  wrong argument (extract.bms) please help
## Post #51
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-06-30T02:13:07+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

Would someone be kinda enough to upload all of the character archives, please?

I wanna work on this and the PS3's model format, I hope to create a program to rebuild these models.
## Post #52
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-07-28T06:07:59+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

Hey can anyone help





As you can see the model is not textured,and i already put the xbox360 .mod file and ps 3 texture file in the folder also i already put Dante.360.MRL in the same folder but it still textureless can anyone help me ??
## Post #53
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-07-28T06:44:48+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

Noesis won't show textured models you will have to apply the texture with Max/Blender...
## Post #54
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-07-28T06:51:59+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from rexil
>
> Noesis won't show textured models you will have to apply the texture with Max/Blender...

I already and export the model at obj and applying the texture but its to much mesh to assign its about 150 part to be assigned,can you help me rexil if you have time ??
## Post #55
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-07-28T09:05:46+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from jaden
>
> 
I already and export the model at obj and applying the texture but its to much mesh to assign its about 150 part to be assigned,can you help me rexil if you have time ??
I trying attaching texture for Dante handling.
Can you hold on?
## Post #56
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-07-28T09:36:52+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from porimac
>
> jaden wrote:
I already and export the model at obj and applying the texture but its to much mesh to assign its about 150 part to be assigned,can you help me rexil if you have time ??
I trying attaching texture for Dante handling.
Can you hold on?

Yeah i can wait
Thanks a lot for your help
Arigato gozaimashita
## Post #57
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-07-28T10:38:51+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

It ended. 
Please try this. 
<sorry, It deleted.>
I attached texture on metaseq,
Hope it went well on your model viewer...
## Post #58
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-07-29T13:48:29+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

The contents of this post was deleted because of possible forum rules violation.
## Post #59
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-07-29T14:14:57+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

You bet!  
Ive been wanting texture applied Dante model, too!
## Post #60
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-07-29T17:44:04+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

It is uncalled for..  

Oh its like DEVILMAN.
Dante DLC applied texture, wavefont OBJ model is here.
<sorry, It deleted.>
## Post #61
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-07-30T00:29:31+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

Wow Wow Wow Wow
You're so aweeeeeeeeeeeeesome man       
Thanks a lot for this
I really appreciate it porimac
Arigato gozaimasu
Japanese people are aweeeeeeeeeeeeeeesome      
Thanks thanks thanks,DOMO
## Post #62
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-07-30T00:30:57+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

Oops sorry for the double post
## Post #63
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-07-30T07:57:35+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

DMI, jaden.
But really awesome, chrrox(wrote arc extractor script), MrAdults (product Noesis) and MVC3 staff.
I only applied ready-made textures for ready-made model.
## Post #64
- Username: iK1L73r
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 08, 2011 6:21 am
- Post datetime: 2011-08-08T18:50:01+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

can somebody sendme some or all of these arcs
storm
wolverine
wesker
chris
hope you can help me
## Post #65
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-08-09T11:04:52+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

iK1L73r, I can help you.
But I am not should do it.
First, You must obtain gamedisk(or ISO).
You will be able to find method of extracting arc in this topic.
## Post #66
- Username: iK1L73r
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 08, 2011 6:21 am
- Post datetime: 2011-08-09T18:55:44+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from porimac
>
> iK1L73r, I can help you.
But I am not should do it.
First, You must obtain gamedisk(or ISO).
You will be able to find method of extracting arc in this topic.
i dont have the iso but i have some arcs extracted and some of them i cant extract
also when i try 2 convert .mod to obj whit noesis it crashes
## Post #67
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-08-09T21:05:02+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

hmm, I think that you should post [>here<](http://forum.xentax.com/viewtopic.php?t=4582) for your problem.
## Post #68
- Username: iK1L73r
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 08, 2011 6:21 am
- Post datetime: 2011-08-09T21:25:54+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from porimac
>
> hmm, I think that you should post >here< for your problem.
Thanx but the problem was that i were trying to extract the ps3 model
## Post #69
- Username: iK1L73r
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 08, 2011 6:21 am
- Post datetime: 2011-08-10T17:59:53+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

somebody have x360 wolverine arc or .mod ?
i got the textures
## Post #70
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-11-03T16:17:57+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

Download now the PS3 game to extract textures its a true head pain, can read this guide i made and the problem of textures its fixex witht the same files of the X360 game 100%. 

I made guide abouth how to fix this in Milkshape.
Convert Meshes with Noesis To OBJ
Convert Textures with Noesis To jpg

Open Texture In Phothosop and Invert Textures Position


Import the OBJ in Milkshape and select Group Area.


Atach the inverted Texture


Go to texture coordinate editor


Search the mesh with the texture atached in the list of meshes when you see the wireframe in texture you found.


With the texuture coordinate editor tools move the wireframe mapping to the right position, you need look and pay atention to see
wath its the area of the texture. Thanks to good the Ctrl + z comand works here.


repeat all the steeps with the other meshes and you get the file you want with the same textures of the same xbox game.
## Post #71
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2011-11-14T22:39:03+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

Ultimate Marvel vs Crapcom 3





THX Mr Addults.
## Post #72
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-11-15T16:52:46+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from Darko
>
> Ultimate Marvel vs Crapcom 3





THX Mr Addults.

very cool! ultimate for xbox 360?
## Post #73
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2011-11-15T19:46:54+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from logansan25
>
> Darko wrote:Ultimate Marvel vs Crapcom 3





THX Mr Addults.

very cool! ultimate for xbox 360?

Yep
## Post #74
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2011-11-17T02:39:57+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from Darko
>
> Ultimate Marvel vs Crapcom 3





THX Mr Addults.

great job!! my noesisv358 can't open UMVC3's MOD files
## Post #75
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-11-17T04:47:46+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

So you signed up, and made your first ever post about your outdated version of Noesis not doing something that was added in the most recent version of Noesis. Impressive. Very impressive.
## Post #76
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-11-17T23:36:52+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from Darko
>
> Great job!! my noesisv358 can't open UMVC3's MOD files

> Reply from MrAdults
>
> So you signed up, and made your first ever post about your outdated version of Noesis not doing something that was added in the most recent version of Noesis. Impressive. Very impressive.

I can just imagine how quickly the excitement must have faded...
## Post #77
- Username: iK1L73r
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 08, 2011 6:21 am
- Post datetime: 2011-11-22T16:48:20+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from Darko
>
> Ultimate Marvel vs Crapcom 3





THX Mr Addults.
woooowwww thats awesome
btw do you have a link to download the iso ?
## Post #78
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2011-11-22T23:40:16+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from iK1L73r
>
> Darko wrote:Ultimate Marvel vs Crapcom 3





THX Mr Addults.
woooowwww thats awesome
btw do you have a link to download the iso ?

I'm gonna upload a pack with the correct textures and characters, beacause for getting all the textures you need both versions (360 and ps3).
## Post #79
- Username: iK1L73r
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 08, 2011 6:21 am
- Post datetime: 2011-11-23T02:54:43+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from Darko
>
> I'm gonna upload a pack with the correct textures and characters, beacause for getting all the textures you need both versions (360 and ps3).
that mean youll post all the dlc costumes ? that would be the best thing ever!!!
also most of the models i ripped from the vanilla mvc3 360 version had the textures well
## Post #80
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2011-11-23T04:33:55+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

I've already got 'em all packed and uploaded. Not sure what the rules are about posting models, though.
## Post #81
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2011-11-23T06:19:50+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from RandomTBush
>
> I've already got 'em all packed and uploaded. Not sure what the rules are about posting models, though.

I posted ffxiii models before and I didn't have problems for that, also doax2 ss files. If the mod's consider that as something wrong then I don't mind if the post is deleted or edited.
## Post #82
- Username: iK1L73r
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 08, 2011 6:21 am
- Post datetime: 2011-11-23T17:55:02+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from RandomTBush
>
> I've already got 'em all packed and uploaded. Not sure what the rules are about posting models, though.
will yu postem at the models resource ?
## Post #83
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2011-11-23T20:35:06+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from iK1L73r
>
> RandomTBush wrote:I've already got 'em all packed and uploaded. Not sure what the rules are about posting models, though.
will yu postem at the models resource ?I would, but I don't plan on doing so until that rigging problem gets fixed... whenever that may be.
## Post #84
- Username: iK1L73r
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 08, 2011 6:21 am
- Post datetime: 2011-11-23T21:09:42+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from RandomTBush
>
> iK1L73r wrote:RandomTBush wrote:I've already got 'em all packed and uploaded. Not sure what the rules are about posting models, though.
will yu postem at the models resource ?I would, but I don't plan on doing so until that rigging problem gets fixed... whenever that may be.
well if you already uploaded them somewhere cn you send the link to me ?
## Post #85
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2011-11-23T22:38:53+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

Hi everyone I'm hoping someone can help I sent a message to Chrrox, and MrAdults so I'm hoping that I might recieve a repose from one of them but in the meantime, would anyone happen to have a OBJ or 3DS file for Doctor Doom I don't need the textures just the 3D model for a project I'm working on. I do papercrafting as one of my hobbies using a program called Pepakura Designer which allows me to take a 3D Model and turn it into a papercraft model, and I would be looking to get the model so I can break it up into sections for papercrafting to make it life size. I'm not joking here, but I'm just looking for that one little bit of help. Thanks.
## Post #86
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-11-24T00:09:47+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

I don't think MrAdults is going to give you the file, but look a couple posts up, and it would appear that someone is considering posting the files...
## Post #87
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2011-11-25T06:31:08+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

I hope they decide to post the files, that's the only 3D Model I'm looking for, or I hope someone can help me with the only 3D Model I need which is Dr. Doom.
## Post #88
- Username: swordzero
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 17, 2009 2:07 am
- Post datetime: 2011-12-07T06:19:51+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

Can anyone help me, I can't open the models, I'm using the Ultimate version for X360
I used the QuickBMS Script on all files in the chr folder then I tried using noesis on the files in nativeXenon\chr\archive\Out\chr\Dante\model\1p textures look fine but I have .DOM files instead of .MOD, I tried changing the extension, didn't work
I even tried changing the HEX value of DOM to MOD and also didn't work
Can anyone tell me what I did wrong? Thanks in advance
## Post #89
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-12-07T06:58:37+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from swordzero
>
> .DOM files instead of .MOD, I tried changing the extensionFor me it's working fine!
just change the extension! of course if you used chrrox's bms script on the first page to unpack the arc files.
## Post #90
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2011-12-14T17:26:36+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

Still hping someone can help me with Dr.Doom I don't need the textures just the model in a OBJ format if possible.
## Post #91
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-12-20T23:03:51+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

any chance to keep out animations
## Post #92
- Username: headgehof
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jun 27, 2010 10:11 pm
- Post datetime: 2011-12-31T00:08:07+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

new ultimate Marvel Vs Capcom 3 exploracion in noesis not reviewed
pls update plg
## Post #93
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-05-06T16:56:59+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from headgehof
>
> new ultimate Marvel Vs Capcom 3 exploracion in noesis not reviewed
pls update plg

Anybody can update this for Ultimate please!
## Post #94
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2012-07-05T11:29:38+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

Hello!
Could someone tell me please, Noesis supports bones and weights for this game? Thanks in advance!
## Post #95
- Username: spartan00j
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Oct 31, 2010 10:57 am
- Post datetime: 2013-09-21T23:24:45+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from logansan25
>
> headgehof wrote:new ultimate Marvel Vs Capcom 3 exploracion in noesis not reviewed
pls update plg  

Anybody can update this for Ultimate please!
use the ultimate Marvel Vs Capcom 3 files from xbox 360. you can rip those to get the model and ps3 files to get texture with noesis
## Post #96
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-09-22T02:23:49+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

> Reply from spartan00j
>
> logansan25 wrote:headgehof wrote:new ultimate Marvel Vs Capcom 3 exploracion in noesis not reviewed
pls update plg  

Anybody can update this for Ultimate please!
use the ultimate Marvel Vs Capcom 3 files from xbox 360. you can rip those to get the model and ps3 files to get texture with noesis

Why are you answering a thread from 2 years ago? Even Noesis supports 360 textures from that game right now.
## Post #97
- Username: neociano
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 12, 2017 8:08 pm
- Post datetime: 2017-04-29T01:12:37+00:00
- Post Title: Re: (X360) Marvel Vs Capcom 3

seems like a long shot but is anyone gonna be tackling the pc port of umvc3?
