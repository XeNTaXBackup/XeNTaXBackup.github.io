## Post #1
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-09T10:54:49+00:00
- Post Title: Orcs must die 2 - 3D Models

I just installed the game and I see that the data is packed in a simple zip file.

Textures are easy to get, they are just in a dds file format   

but

the models, easy to spot, since they have the .model extension need to be converted of course. 

Anyone an idea how to get started on this ?   

Download a sample here: [http://users.telenet.be/u122561/Downloa ... st_die.rar](http://users.telenet.be/u122561/Downloads/Orcs_must_die.rar)

T.
## Post #2
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-10T10:44:25+00:00
- Post Title: Orcs must die 2 - 3D Models

You can easely capture the models with 3DRipperDX, but it is not the same... is it :/

Anyone got any progress on this ??


I opened it with 010 Editor, but it is a mystery for me as is Japanese


T.
## Post #3
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-10T17:01:09+00:00
- Post Title: Orcs must die 2 - 3D Models

I've been studying the model I submitted in the 010 Editor... 
and I've come up with the following chunks of data

The comment I added is just what I think it is... anyone any ideas on this stuff ?


```
    // char[4] VBIN
    // short minVersion 
    // short maxVersion
    // bytes[4] empty_1

//HSMV
    // char[4] HSMV
    // UInt32 SizeOffHSMV

//HSMV
    // char[4] HSMV
    // data that is as big as SizeOffHSMV
    // char[4] HSMV
    // bytes[4] empty_2
//HSMV END


//SRTM
    //LRTM
        //--> contains shader reference
        //--> contains dds texture reference
        //--> contains some settings for the material
    //LRTM
//SRTM

//HSMS
//HSMS

//RMSV
//RMSV

// RMST
// RMST

// MBUS
// MBUS

// RPXE
// RPXE

// LEKS
    // -> 3 * 4 bytes
    //AlphaBone
        // -> 15 * 4bytes + 2 bytes
    //BoneWaist
    //BonePelvis 
    //BoneSpine1
    //Bone_L_Thigh
    //Bone_R_Thigh
    //Bone_L_Calf
    //Bone_L_Foot
    //Bone_R_Calf
    //Bone_R_Foot
    //BoneSpine2
    //Bip01 Head
    //BoneHead
    //Bone_L_Upperarm
    //Bone_R_Upperarm
    //BoneJaw
    //boneGoogleEyesFX
    //Bone_L_Forearm
    //Bone_L_Hand
    //Bone_R_Forearm
    //Bone_R_Hand
    //BoneFX01
    //BoneWeapon

// LEKS

// THGW

// XBBB
// XBBB

// RPBC
    // 4 bytes
    // nbrOfBoneProperties 4 bytes --> in this case 23
    // 1 byte
    // --> contains a list of strings for properties, 1 for each bone!
    // 3 properties per bone: Visible,vision.ExportAs, vMax.bone.NoCull
    // seperated by 0D 0A 3F 00 00 00 --> CHAR(13) + length of the next character set

// RPBC

// SDNB
    // 4bytes => length of the upcoming chunk in bytes
    // always finishes with 4 emty bytes
// SDNB

```


Help is required here ppl

Thnx

T.
## Post #4
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2011-10-10T17:43:39+00:00
- Post Title: Orcs must die 2 - 3D Models

This is Trinigy vision engine files, look here [http://thepiratebay.org/torrent/6069637 ... _Tutorials](http://thepiratebay.org/torrent/6069637/Trinigy_Vision_SDK___Samples___Tutorials)
## Post #5
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-10-10T18:20:05+00:00
- Post Title: Orcs must die 2 - 3D Models

The contents of this post was deleted because of possible forum rules violation.
[orc.jpg](https://xentaxbackup.github.io/file/4761_orc.jpg)
## Post #6
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-10T22:41:03+00:00
- Post Title: Orcs must die 2 - 3D Models

[http://users.telenet.be/u122561/Downloa ... stDie2.rar](http://users.telenet.be/u122561/Downloads/OrcsMustDie2.rar)
Right here baby 

I don't have blender, any idea how to get it into max ?

T.
## Post #7
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-10-10T23:16:39+00:00
- Post Title: Orcs must die 2 - 3D Models

umm nice work Szkaradek123 good job.
## Post #8
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-10-12T19:24:30+00:00
- Post Title: Orcs must die 2 - 3D Models

Szkaradek123 Rocks
## Post #9
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-12T22:56:02+00:00
- Post Title: Orcs must die 2 - 3D Models

YES !! I finally did it in c#.NET 

I made a command line tool to convert the .model file(s) to obj file and their mtl file with it!

No Bones are supported nor any animation

You can download it here [http://users.telenet.be/u122561/index.html](http://users.telenet.be/u122561/index.html)

Enjoy



screenshot01.jpg (32.56 KiB) Viewed 585 times



T.
## Post #10
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-10-13T01:22:37+00:00
- Post Title: Orcs must die 2 - 3D Models

nice work TaylorMouse, keep working mate, really interesting.
## Post #11
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2011-10-14T07:30:07+00:00
- Post Title: Orcs must die 2 - 3D Models

Nice! Anyone willing to link me to some models, the above link isnt working
## Post #12
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-15T17:48:09+00:00
- Post Title: Orcs must die 2 - 3D Models

Connect to steam and download the demo, it has nearly all the models 

T.
## Post #13
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2011-10-15T18:02:18+00:00
- Post Title: Orcs must die 2 - 3D Models

> Reply from TaylorMouse
>
> Connect to steam and download the demo, it has nearly all the models 

T.
I dont have steam no more, and I dont think I wanna redownload it. Would you mind extracting them and sending them to me via mediafire? I need the ones that you can import with Blender. Please and thank you
## Post #14
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2011-10-15T19:57:17+00:00
- Post Title: Orcs must die 2 - 3D Models

Wow, lazybones to the max I would say.
## Post #15
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2011-10-16T09:13:50+00:00
- Post Title: Orcs must die 2 - 3D Models

> Reply from AceAngel
>
> Wow, lazybones to the max I would say.
Well I would extract them from the demo but i dont know how to extract from Steam games...
## Post #16
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-20T09:48:13+00:00
- Post Title: Re: Orcs must die - 3D Models

Well you do need to download Steam for this or download it from ... somewhere else, if you just want to study the models, I guess it is ok ???

If you use steam, go to 

C:\Program Files\Steam\steamapps\common\Orcs Must Die!\

or something like that

T.
## Post #17
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2011-10-20T16:25:30+00:00
- Post Title: Re: Orcs must die - 3D Models

Thanks  Ill redownload steam
## Post #18
- Username: AbyssRaider
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 21, 2011 7:50 am
- Post datetime: 2011-12-22T02:40:29+00:00
- Post Title: Re: Orcs must die - 3D Models

I know this is an old topic, but I've been trying to view the models for OMD (Specifically Kobold) for a while now. I have no experience in this type of stuff, so I was wondering if anyone could help me on how to view the models. Thanks in advance
## Post #19
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2011-12-22T16:17:30+00:00
- Post Title: Re: Orcs must die - 3D Models

Just use the latest (unpublished yet) 3D Object Converter version:

[http://web.t-online.hu/karpo/3doc_4801_20111215.zip](http://web.t-online.hu/karpo/3doc_4801_20111215.zip)
## Post #20
- Username: AbyssRaider
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 21, 2011 7:50 am
- Post datetime: 2011-12-23T23:58:03+00:00
- Post Title: Re: Orcs must die - 3D Models

Awesome that's perfect, thanks a million, Karpati!
## Post #21
- Username: superchickensoup
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 13, 2011 8:32 pm
- Post datetime: 2012-02-29T17:58:37+00:00
- Post Title: Re: Orcs must die - 3D Models

Can someone explain how to extract the models please. I have tried to use the -f and -d switches and nothing works.
## Post #22
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-03T15:12:31+00:00
- Post Title: Re: Orcs must die - 3D Models

It seems that for Orcs Must Die 2, the same objects are used, but the texture coordinates are off....

Trying to solve it and making an easier way to use my tool with a user interface.

T.
## Post #23
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-03T16:02:55+00:00
- Post Title: Re: Orcs must die - 3D Models

Here we are:

Download tool
Unzip the data.zip from the Orcs Must Die 2 folder
Unzip tool
Run tool and check the CheckBox for Loop through all sub folders ( or not)

This will convert all the model files to a obj file with mtl file
Keep the structure of the data.zip file, the references to the textures of the model are set up like that.

enjoy
T.
[OrcsMustDieConverter.rar](https://xentaxbackup.github.io/file/5631_OrcsMustDieConverter.rar)
## Post #24
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-08-03T17:22:19+00:00
- Post Title: Re: Orcs must die - 3D Models

> Reply from TaylorMouse
>
> Here we are:

Download tool
Unzip the data.zip from the Orcs Must Die 2 folder
Unzip tool
Run tool and check the CheckBox for Loop through all sub folders ( or not)

This will convert all the model files to a obj file with mtl file
Keep the structure of the data.zip file, the references to the textures of the model are set up like that.

enjoy
T.wow thanks a lot for awesome work man, keep working mate, greetings.
## Post #25
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-04T10:51:32+00:00
- Post Title: Re: Orcs must die - 3D Models

Thnx 

could it be interesting to use the code and make a py file for Neosis ?

I don't know how to do that, but someone could 

T.
## Post #26
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-08-04T16:08:30+00:00
- Post Title: Re: Orcs must die - 3D Models

> Reply from TaylorMouse
>
> Thnx 

could it be interesting to use the code and make a py file for Neosis ?

I don't know how to do that, but someone could 

T.well if you can send me code via private maybe we can do something
## Post #27
- Username: Maxunit
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 28, 2010 7:49 am
- Post datetime: 2012-08-12T21:36:14+00:00
- Post Title: Re: Orcs must die - 3D Models

Awesome progress!

The old converter worked a bit on the OMD2 models, but they were borked.

Is there a chance to get the OMD2 models with bones and rigged? That would be cool.
## Post #28
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-13T10:24:19+00:00
- Post Title: Re: Orcs must die - 3D Models

In Neosis, maybe, but not in OBJ, since it does not support any bones or rigging.

But, I haven't heard anything from CriticalError, so...


T.
## Post #29
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2013-07-21T08:28:20+00:00
- Post Title: Re: Orcs must die - 3D Models

[out]
