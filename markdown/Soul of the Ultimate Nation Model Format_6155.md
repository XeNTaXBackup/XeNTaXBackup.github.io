## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-02-28T21:53:20+00:00
- Post Title: Soul of the Ultimate Nation Model Format

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-28T22:43:15+00:00
- Post Title: Soul of the Ultimate Nation Model Format

The whole archive is just xored with 0x69 if someone wants to make a new extractor.
## Post #3
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-03-02T21:18:48+00:00
- Post Title: Soul of the Ultimate Nation Model Format

Fine but this time the true hard its see how to read the files format.
## Post #4
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2011-03-26T10:33:18+00:00
- Post Title: Soul of the Ultimate Nation Model Format

i found a new wpk unpacker
[http://www.geocities.jp/junk2ool/netgame.html](http://www.geocities.jp/junk2ool/netgame.html)
and i tried mesh importing to 3dsmax with maxscript ( not perfect )

May i ask you one thing, chrrox ?
Please, give me a rough file format about wpk
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-03-26T12:37:08+00:00
- Post Title: Soul of the Ultimate Nation Model Format

Just post or send me what you know and i can telly you whats missing.
## Post #6
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2011-03-27T03:26:47+00:00
- Post Title: Soul of the Ultimate Nation Model Format

i have no idea about the wpk file format  
here is the wzm file format which have been researched until now   

[https://code.google.com/p/gamefileforma ... ileFormat/](https://code.google.com/p/gamefileformat/source/browse/trunk/FileFormat/)
## Post #7
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-03-29T16:07:42+00:00
- Post Title: Soul of the Ultimate Nation Model Format

ooh, I like to see where this is going because SUN is still one of the games I have been drooling about for a long time
## Post #8
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2011-04-15T12:36:56+00:00
- Post Title: Soul of the Ultimate Nation Model Format

This is what i have solved so far
I could not figure out how to decode the name field
Please, help me to decode the name field

[
https://code.google.com/p/gamefileform ... ateWPK.bt
](https://code.google.com/p/gamefileformat/source/browse/trunk/FileFormat/SunTemplateWPK.bt)

```

//#include "CommonTemplate.bt"
#include "SunTemplateCommon.bt"


//------------------------------------------------------------------------

typedef struct
{
    uint32              mNameSize ;
    char                mName[mNameSize] ;
    uint32              mUnknown1 ;
    uint32              mUnknown2 ;
    uint32              mUnknown3 ;
    uint32              mSize ;
    uint32              mUnknown5 ;
    uint32              mOffset ;
    uint32              mUnknown7 ;
    uint32              mUnknown8 ;
 
    local int32 padding = -1 ;
    while( padding == -1 )
    {
        padding = ReadInt( FTell() ) ;
        int32           mPaddings ;
    } 


} WPKChunk < bgcolor = cLtPurple , read = ReadWPKChunk > ;

string ReadWPKChunk( WPKChunk& chunk )
{
    string s = "(none)" ;
    SPrintf( s , "[%u] [%d] [%s]" ,
        chunk.mOffset ,
        chunk.mSize ,
        chunk.mName
        ) ;
    return s ;
}

typedef struct
{
    char                mFourCC[4] ;
    uint32              mUnknown1 ;
    uint32              mSize ;
    uint32              mUnknown3 ;
    uint32              mUnknown4 ;

} WPKChunkHeader ;


//////////////////////////////////////////////////////////////////////////

LittleEndian() ;

FSeek( 80034 ) ; //< 0x138A2

WPKChunkHeader          gChunkHeader ;

local uint32 chunkTableSize = gChunkHeader.mSize ;
local uint32 chunkTableEnd = FTell() + chunkTableSize - 32 ;
while( FTell() < chunkTableEnd )
{
    WPKChunk            gChunks ;
}

```
## Post #9
- Username: ybh1231
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 06, 2011 7:35 am
- Post datetime: 2011-05-05T23:38:13+00:00
- Post Title: Soul of the Ultimate Nation Model Format

hey
i used MrMoonKr's extractor 
it worked well
im now seeing all the things i can edit
anyways
after editing how do i combine all these files?
like how do i combine everything into tat .wpk file
## Post #10
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-05-15T17:10:36+00:00
- Post Title: Soul of the Ultimate Nation Model Format

MrMoonKr , great job.

This is Blender249 importer for .wzm model (yet not for all):
 - geometry
 - uvmapping
 - bones
Update:
[import-soul-nation-2011-06-13.zip](https://xentaxbackup.github.io/file/4373_import-soul-nation-2011-06-13.zip)
## Post #11
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-05-17T17:41:24+00:00
- Post Title: Soul of the Ultimate Nation Model Format

Szkaradek123 Rocks, another amazing job from the blender master Szkaradek123, i shure in the future you can domine the animations too, anyway you are one of the bests, congratulations bro.Thanks too to mr.moonk
## Post #12
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-05-18T23:17:46+00:00
- Post Title: Soul of the Ultimate Nation Model Format

yup, this is really really nice!
## Post #13
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-06-12T00:32:37+00:00
- Post Title: Soul of the Ultimate Nation Model Format

The contents of this post was deleted because of possible forum rules violation.
## Post #14
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-06-12T21:48:03+00:00
- Post Title: Soul of the Ultimate Nation Model Format

you have to put the blender file where the model files are, when you open the blender file you must run the script inside blender, everything is shown to you inside blender once you open it
## Post #15
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-06-13T00:06:47+00:00
- Post Title: Soul of the Ultimate Nation Model Format

> Reply from pixellegolas
>
> you have to put the blender file where the model files are, when you open the blender file you must run the script inside blender, everything is shown to you inside blender once you open it
well thanks a lot for reply but in console get it, I try with a lot models and fail T_T.
## Post #16
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-06-13T10:45:52+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

could be wrong python you have too.

Try to put the blender file inside a folder in SUN where you have all the files and try. If not I guess it could be python
## Post #17
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-06-13T13:56:49+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

> Reply from pixellegolas
>
> could be wrong python you have too.

Try to put the blender file inside a folder in SUN where you have all the files and try. If not I guess it could be pythonFixed thanks a lot for support Szkaradek123 and pixellegolas
## Post #18
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-06-13T18:20:03+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

What did you do to make it work if other have problem?
## Post #19
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2011-06-14T11:33:10+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

Same issue here.  it works fine with some files but in the major case it gives me an index error like the one posted before by CriticalError. can you explain how did you fix that?
## Post #20
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-06-14T14:22:51+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

my problem get before is because I download new version of SUN, Limited Edition, so author of script fix it ^^ amd try with so many weapons and it work without errors.
## Post #21
- Username: nightsqual05
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 26, 2010 11:38 am
- Post datetime: 2011-06-30T16:41:55+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

> Reply from MrMoonKr
>
> i found a new wpk unpacker
http://www.geocities.jp/junk2ool/netgame.html
and i tried mesh importing to 3dsmax with maxscript ( not perfect )

May i ask you one thing, chrrox ?
Please, give me a rough file format about wpk

can you share your max script for 2010?
## Post #22
- Username: cardoval
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 24, 2011 5:23 am
- Post datetime: 2011-08-23T21:41:22+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

Hi !!
I'm very fan of SUN and i wanted to see models of this game, but I don't know how to proceed.
I've download the wpk unpacker but what i have to do after to unpack the resources file ? and how i can import mesh in 3dsmax ? I'm a real newbie in this stuff but I know a little how to use 3DS max.

Can you explain me what I have to do with my wpktool and the resource.wpk to unpack some models of SUN ?

Thanx and forgive my poor english ^^
## Post #23
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-23T22:02:06+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

Drag the maxscript into 3dmax and then it should ask you to load a file.
## Post #24
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-08-23T22:05:24+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

> Reply from finale00
>
> Drag the maxscript into 3dmax and then it should ask you to load a file.well this is interesting but where is the importer to .max? I only get Blender Importer but I don't like and don't know how adapt Blender Script to 3D Max
## Post #25
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-23T22:27:23+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

lol I thought he had a maxscript already cause someone mentioned they wrote a maxscript for it.
Guess they didn't share it.

Well I guess someone could write a maxscript since the format is already out there (ie: blender import)
## Post #26
- Username: cardoval
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 24, 2011 5:23 am
- Post datetime: 2011-08-23T22:29:52+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

Please, someone on this thread, if you have the maxscript importer, can you give it to us ? thank you !!!
## Post #27
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-08-24T21:38:25+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

Max Script for SUN doesnt exist, this its a image of model loaded in blender with skara plugin and exported to Max, stop ask to nightsqual05 cause he not have this, its only a joke post.
## Post #28
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2011-09-24T17:02:05+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

Was wondering if anyone knew an importer for the .wza animation format for this game?
## Post #29
- Username: Yooo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 12, 2011 1:39 pm
- Post datetime: 2011-11-12T05:43:22+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

Someone kindly tell me step by step how to use the importer .blend, I can not understand how to use it. Now I have the .wzm. thanks
## Post #30
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-11-12T05:48:19+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

> Reply from Demonsangel
>
> Was wondering if anyone knew an importer for the .wza animation format for this game?
I don't think somebody make a script for this format.

> Reply from Yooo
>
> Someone kindly tell me step by step how to use the importer .blend, I can not understand how to use it. Now I have the .wzm. thanks

1º File-->>Open-->> import-cabal-2011-09-03.blend
2º Select text opened script and press execute script.
3º Search path where have wzm files and load.
4º Have fun.
## Post #31
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-13T18:28:12+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

[https://www.dropbox.com/sh/qbct1tjyv7al ... e%20Nation](https://www.dropbox.com/sh/qbct1tjyv7alpoi/JbJheVDlTi/Soul%20of%20the%20Ultimate%20Nation)
noesis script

It isn't finished yet, some models use 3 floats instead of quaternions and I couldn't get the armature correct for them.
I'm stil working on the rest of animation formats.
## Post #32
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-07-13T19:27:31+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

thanks for looking into this format. Really nice models so waiting patientlly
## Post #33
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-18T19:50:12+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

This its bether script thanks man, the last one i get keep out the meshes with doublefaces and errors, this rip out clean models, thanks man.
## Post #34
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-20T12:37:15+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

Updated the script so more models should work now.

I haven't checked all models so if a models doesn't work, post it's name + the subfolder where it's in here and what seems to be the problem
Make sure the debugger doesn't say "Version: 112 Skeleton won't show up correctly" if the animations don't seem right for a model. I'm still trying to correct it.

The script loads up all animations in the models subfolder, so make sure when you preview an animation in Noesis and it doesn't seem right it does actually belong to that model.
Alternatively you can create a subfolder "/anims" and it will load only the animations in there.

If the debugger shows something like attack1.wza it means it couldn't load the animation file so feel free to report that as well.
## Post #35
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-20T16:48:07+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

> Reply from Demonsangel
>
> Updated the script so more models should work now.

I haven't checked all models so if a models doesn't work, post it's name + the subfolder where it's in here and what seems to be the problem
Make sure the debugger doesn't say "Version: 112 Skeleton won't show up correctly" if the animations don't seem right for a model. I'm still trying to correct it.

The script loads up all animations in the models subfolder, so make sure when you preview an animation in Noesis and it doesn't seem right it does actually belong to that model.
Alternatively you can create a subfolder "/anims" and it will load only the animations in there.

If the debugger shows something like attack1.wza it means it couldn't load the animation file so feel free to report that as well.

The new plugin send this window in open Noesis and cant load any model. any idea how to fix that? thanks
## Post #36
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-20T16:53:14+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

Oops forgot to close the quotes, try now.
## Post #37
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-20T20:33:24+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

Man, this its amazing and incredible plugin, u made a piece of art, 99% of the animations are loaded perfect and models too, Thank by your greath contribution and greath efort in made this plugin, one question its, if i want export animations from noesis separated i need delete the other animations from folder? since i see animations are already separated but in noesis run all the animations like one single.

I cant tell 100% because files like this
\Data\NPC\M0113 or M0131
## Post #38
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-20T21:26:39+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

In noesis you can run a single animation by clicking it's name, it will then loop that animation.
To just load 1 animation create a "<your model folder here> /anims" subfolder and put the animation in there. Noesis will only load that one into the model.
## Post #39
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-20T21:32:57+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

If he decided to load multiple animations would they be separated into their own tracks which you could go through by clicking the next/prev buttons?
## Post #40
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-20T21:41:30+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

To select a single animation you have to click on it in the list, there are no next/previous buttons only button to speed up/slow down animation preview speed.

I don't know of a way to select animations and only save those to the selected output.
I've tried to install tkinter for Noesis, but it simply crashes when I place the dll's, to show a tiny GUI with all the animations listed in there with some checkboxes.
I have to wait till Noesis supports multi select in the in-script file loader to change the way we load animations atm.
## Post #41
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-20T21:49:44+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

lol if the user really needs it we can provide them with:

```

filename = rapi.loadPairedFileOptional(...)
while filename:
   files.append(filename)
   filename = rapi.loadPairedFileOptional(...)
load_all_files(files)

```


So they just keep picking files until they hit cancel.
## Post #42
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-20T22:03:01+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

I know, but I thought it was an ugly workaround. :p
## Post #43
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-21T03:12:58+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

I already pick the animation walk, run, etc, best way its export  .psk and animation to .psa, import in max with ActorX guildor plugin and choose the animation u want to run and export, in Noesis show export only first atack01 animations but already export all, ActorX divide the animations.
## Post #44
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-23T04:23:45+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

Data\Data\Armor\Valkyrie\A000

All face and hair files have error, cant be loaded.

Any idea to fix?
## Post #45
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-07-23T05:32:37+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

> Reply from Demonsangel
>
> I see you support Soul of the Ultimate nation, could you explain the boneRotation info for mesh versio 112?
I can get the other versions to work, but not the Euler angle ones.

As far as I remember, the float value you read from wza are radian. so you have to convert [radian_X,radian_Y,radian_Z] into [degree_X,degree_Y,degree_Z].
Then use this value as Euler angles. But as I remember, the rotation are reversed. So you have to apply conjugate() to it to mke it work!

Good Luck!
## Post #46
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-23T06:06:50+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

OMG, Fath importar have suppor for SUN .... 
But have error
## Post #47
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-07-24T06:18:08+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

Which file causing the error!?
## Post #48
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-25T02:28:53+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

> Reply from fatduck
>
> Which file causing the error!?

All Wzm files.
## Post #49
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-25T05:32:04+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

LOL that means it doesn't work.
## Post #50
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-07-25T08:53:00+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

Sorry to hijeck this topic, I can't found a single error in my script. So could anyone report the detail errors in my own [topic](http://forum.xentax.com/viewtopic.php?p=75831#p75831)!
## Post #51
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2012-07-25T10:13:11+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

> Reply from fatduck
>
> Sorry to hijeck this topic, I can't found a single error in my script. So could anyone report the detail errors in my own topic!

hello, i posted a reply in your [topic](http://forum.xentax.com/viewtopic.php?p=75831#p75831) regarding that same error and sent you samples in a private message.

And many thanks for that awesome script.
## Post #52
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-25T10:56:59+00:00
- Post Title: Re: Soul of the Ultimate Nation Model Format

Updated the script to support mesh version 117, version 112 will look like the skeleton is now aligned with the mesh, but it isn't, even when I know what to do I can't get it to work.
