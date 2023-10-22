## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-01-22T07:00:35+00:00
- Post Title: Unreal 1998 beta (PC) .u [oldunreal.com beat me to it]

This is from an earlier Unreal I .u datafile that seems to use a much older form of encryption. My major interest is more so the script data since some things got left out. This is just the Engine.u but it should give a decent idea. No modern extractors are compatible. A look through gives me an idea that there are not major differences in the formats.

Edit: Is there a possibility to convert to the standard U1 format? Or dump texture, sound, and script data as Unreal 3D models, unreal scripts, and the like?
[Engine.zip](https://xentaxbackup.github.io/file/1427_Engine.zip)
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-02-12T06:08:58+00:00
- Post Title: Unreal 1998 beta (PC) .u [oldunreal.com beat me to it]

I've found out how to rip the scripts with a hex editor (no text compression) but texture extraction doesn't work... and the UnrealEd that comes with the beta just crashes when it opens. Added to this no newer UnrealED works with the older files.

It is as I thought, there are no tools available it seems to read this far back. O_o
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-02-12T23:52:46+00:00
- Post Title: Unreal 1998 beta (PC) .u [oldunreal.com beat me to it]

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2008-02-13T13:30:49+00:00
- Post Title: Unreal 1998 beta (PC) .u [oldunreal.com beat me to it]

Have you tried the UTPAS delphi package library?
[http://www.acordero.org/prog_proj_UTPDL_Download.html](http://www.acordero.org/prog_proj_UTPDL_Download.html)
This is an open source .pas library to open/parse/identify various (older) UT engine files

--Darkstar
## Post #5
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-02-13T19:38:36+00:00
- Post Title: Unreal 1998 beta (PC) .u [oldunreal.com beat me to it]

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2008-02-14T11:56:53+00:00
- Post Title: Unreal 1998 beta (PC) .u [oldunreal.com beat me to it]

The .pas file should work with Unreal (not UT) as well. It seems that only the native functions for U1 have not been generated.
My Pascal skills are also not very fresh anymore, but I guess you could use the source as a reference for the file format and whip up your own exporter or something.

I might take a look at this as soon as I'm back at home at my own computer where I have FreePascal installed.

-Darkstar
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-02-14T17:01:47+00:00
- Post Title: Unreal 1998 beta (PC) .u [oldunreal.com beat me to it]

The problem is that there is a development gap between Unreal and the Unreal beta formats. They are too different by a certain amount of bytes that makes them unreadable to each other.

Either:

A) A means to convert between the versions of the u/utx/umx files

or 

B) A means to read and export data from the older u/utx/umx files. They are all the same format, just hold different data.

I've been working on "A" with little to no success. Like filling in areas with the data from a U1 .u with it's equal in U1B only resulting in a crash.
## Post #8
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-02-18T20:53:30+00:00
- Post Title: Unreal 1998 beta (PC) .u [oldunreal.com beat me to it]

The format has various differences from it's final counterpart that makes them incompatible with one another. I know I've established that... but what seems to be the same is the overall structure. If I'm not mistaken. Perhaps the final U1 format had more put into it or some needless things were removed? Not sure but I certainly still can't open it after several conversion attempts.
## Post #9
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-04-18T19:59:09+00:00
- Post Title: Unreal 1998 beta (PC) .u [oldunreal.com beat me to it]

Sorry to bump again but has there been any progress on the U1 beta format?
## Post #10
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2008-06-07T09:33:57+00:00
- Post Title: Unreal 1998 beta (PC) .u [oldunreal.com beat me to it]

> Reply from Darkfox
>
> Sorry to bump again but has there been any progress on the U1 beta format?Best bet would be to look at how the beta executable loads this data.
## Post #11
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-06-17T08:10:49+00:00
- Post Title: Unreal 1998 beta (PC) .u [oldunreal.com beat me to it]

I can't read assembly code. I'm no good at reverse engineering.
## Post #12
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-10-26T03:27:52+00:00
- Post Title: Unreal 1998 beta (PC) .u [oldunreal.com beat me to it]

Ok, I'm able to extract textures and scripts and sounds. Perhaps even music.

The last step is... extracting LODMeshes...

Apparently 1998 .u files do not compress data so perhaps one could make a file ripper?
## Post #13
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-10-31T20:39:04+00:00
- Post Title: Unreal 1998 beta (PC) .u [oldunreal.com beat me to it]

Here's the main UnrealI.u

[UnrealI.u](http://www.sendspace.com/file/4ubc8z)

And here are some mesh samples to get an idea of the format. I'm trying hard to export the data and animation .3D files from Unreal Beta

[Example Meshes](http://www.sendspace.com/file/s1yi5o)

One of the mesh files I'm trying to get to is ChameleonM from the beta UnrealI.u.
## Post #14
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2008-11-06T20:21:19+00:00
- Post Title: Unreal 1998 beta (PC) .u [oldunreal.com beat me to it]

Wow, this is hard. The file formats seem to lack any common identifier, so it's nearly impossible to find them inside the *.u file. The newer Unreal games work with an internal Virtual Machine (similar to Java), and the file formats are just the dumped internal state of the VM clases. But even they have identifiers (32 bit words) at the beginning of the file/objects. This here has nothing.

Well, here's what I see so far.

The _d files hold some sort of frame information. They start with a 32 byte header and then they have 16 bytes for each animation frame. For example, the krallm .uc file says "NUMFRAMES=498", and 498*16+32 is 8000, which is exactly the size of the krallm_d file.

The _a file also seems to have a fixed size, depending on the number of frames. The krallm_a file is exactly 810748 bytes, which is 4 + 498*1628. So there's 1628 bytes for each frame in there (which also seems consistent with the other models in the .rar file).
This leaves a 4 byte header which doeode the file size, so the size is probably stored somewhere else in the .u file (not in the model file itself). As for the frame format itself, it doesn't seem to have any structure by itself. Probably just raw floats or something.
[edit: no, don't look like floats, at least they don't contain any "sensible" float values]

Maybe each frame is encrypted with some data from the _d files...

...I will try to find out more later but I'm not very good with 3D data...

-Darkstar
## Post #15
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-11-07T09:54:40+00:00
- Post Title: Unreal 1998 beta (PC) .u [oldunreal.com beat me to it]

Those are example 3D models from Unreal 1 (final, not Beta) to compare to the Beta .u for exporting them. The beta "UnrealI.u" is seen above. Currently there is no means to export mesh data from the Unreal Beta UnrealI.u main data file because the data file format is radically different and not so compressed.

To clarify a bit on the Unreal 1 model format:

NUMFRAMES refers to total number of animation frames. KrallM contains a total of 498 frames of animation in it's _a.3D file.

_d is the mesh/model data
_a is the animation data

You may be able to find other data regarding Unreal Engine 1 Mesh. This is what I know from dealing with it.

UPDATE

While searching the net I found public source code for Unreal 1. In it there is a full description of the Unreal mesh format among other things.

You can get it here: [Unreal v224 Public Source](http://www.sendspace.com/file/7sodnu)

Things of interest in the code:

In "Engine\Inc\" there is a C++ script called "UnMesh.h" which describes the Unreal Mesh format.
In "Core\Inc\" there is a C++ script called "UnArc.h" that gives a description of the ".u" archive I believe.

Unfortunately this is AFTER the Unreal beta so the archive format has changed a bit but this should still be useful. There is code for exporting data so perhaps tweaked enough an exporter for the beta .u files.
## Post #16
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-11-08T02:17:59+00:00
- Post Title: Re: Unreal 1998 beta (PC) .u

As for some beta UnrealI *.uc files (import parts)

```
// PeaceBarrel.
//=============================================================================
class PeaceBarrel expands Projectile;

#exec MESH IMPORT MESH=peace ANIVFILE=MODELS\peace_a.3D DATAFILE=MODELS\peace_d.3D X=0 Y=0 Z=0
#exec MESH ORIGIN MESH=peace X=0 Y=0 Z=0 YAW=-64 ROLL=0 PITCH=0
#exec MESH SEQUENCE MESH=peace SEQ=All       STARTFRAME=0   NUMFRAMES=33
#exec MESH SEQUENCE MESH=peace SEQ=UnFold    STARTFRAME=0   NUMFRAMES=29
#exec MESH SEQUENCE MESH=peace SEQ=Launch1   STARTFRAME=29  NUMFRAMES=1
#exec MESH SEQUENCE MESH=peace SEQ=Launch2   STARTFRAME=30  NUMFRAMES=1
#exec MESH SEQUENCE MESH=peace SEQ=Launch3   STARTFRAME=31  NUMFRAMES=1
#exec MESH SEQUENCE MESH=peace SEQ=Launch4   STARTFRAME=32  NUMFRAMES=1
#exec TEXTURE IMPORT NAME=Jpeace1 FILE=MODELS\peaceg.PCX
#exec MESHMAP SCALE MESHMAP=peace  X=0.08 Y=0.08 Z=0.16
#exec MESHMAP SETTEXTURE MESHMAP=peace NUM=1 TEXTURE=Jpeace1
```


```
// Chameleon.
//=============================================================================
class Chameleon expands Pawn;

#exec MESH IMPORT MESH=ChameleonM ANIVFILE=MODELS\chamel_a.3D DATAFILE=MODELS\chamel_d.3D ZEROTEX=1
#exec MESH ORIGIN MESH=ChameleonM X=20 Y=-230 Z=40 YAW=64 ROLL=-64

#exec MESH SEQUENCE MESH=ChameleonM SEQ=All       STARTFRAME=0   NUMFRAMES=173
#exec MESH SEQUENCE MESH=ChameleonM SEQ=Crawl     STARTFRAME=0   NUMFRAMES=20
#exec MESH SEQUENCE MESH=ChameleonM SEQ=Dead1     STARTFRAME=20  NUMFRAMES=41
#exec MESH SEQUENCE MESH=ChameleonM SEQ=TakeHit   STARTFRAME=20  NUMFRAMES=1
#exec MESH SEQUENCE MESH=ChameleonM SEQ=Glide     STARTFRAME=61  NUMFRAMES=1
#exec MESH SEQUENCE MESH=ChameleonM SEQ=Hide      STARTFRAME=62  NUMFRAMES=30
#exec MESH SEQUENCE MESH=ChameleonM SEQ=Wait      STARTFRAME=92  NUMFRAMES=30
#exec MESH SEQUENCE MESH=ChameleonM SEQ=Land      STARTFRAME=122 NUMFRAMES=1
#exec MESH SEQUENCE MESH=ChameleonM SEQ=Run       STARTFRAME=123 NUMFRAMES=20
#exec MESH SEQUENCE MESH=ChameleonM SEQ=Walk      STARTFRAME=143 NUMFRAMES=30

#exec MESHMAP SCALE MESHMAP=ChameleonM X=0.032 Y=0.032 Z=0.064
#exec TEXTURE IMPORT NAME=Cham2 FILE=Models\CameLion2.PCX GROUP="Skins"
#exec MESHMAP SETTEXTURE MESHMAP=ChameleonM NUM=0 TEXTURE=Cham2 
```


```
// Peacemaker.
//=============================================================================
class Peacemaker expands Weapon;

#exec MESH IMPORT MESH=peacehand ANIVFILE=MODELS\phand_a.3D DATAFILE=MODELS\phand_d.3D X=0 Y=0 Z=0
#exec MESH ORIGIN MESH=peacehand X=0 Y=0 Z=0 YAW=-64 ROLL=0 PITCH=0
#exec MESH SEQUENCE MESH=peacehand SEQ=All       STARTFRAME=0   NUMFRAMES=54
#exec MESH SEQUENCE MESH=peacehand SEQ=Select    STARTFRAME=0   NUMFRAMES=20
#exec MESH SEQUENCE MESH=peacehand SEQ=Still     STARTFRAME=20  NUMFRAMES=1
#exec MESH SEQUENCE MESH=peacehand SEQ=Down      STARTFRAME=21  NUMFRAMES=12
#exec MESH SEQUENCE MESH=peacehand SEQ=Throw     STARTFRAME=33  NUMFRAMES=10
#exec MESH SEQUENCE MESH=peacehand SEQ=Count     STARTFRAME=43  NUMFRAMES=11
#exec TEXTURE IMPORT NAME=Jpeacehand1 FILE=MODELS\peaceh.PCX GROUP=Skins
#exec MESHMAP SCALE MESHMAP=peacehand  X=0.005 Y=0.005 Z=0.01
#exec MESHMAP SETTEXTURE MESHMAP=peacehand NUM=1 TEXTURE=Jpeacehand1

#exec MESH IMPORT MESH=peacepick ANIVFILE=MODELS\peacpi_a.3D DATAFILE=MODELS\phand_d.3D X=0 Y=0 Z=0
#exec MESH ORIGIN MESH=peacepick X=0 Y=0 Z=10 YAW=-64 ROLL=0 PITCH=0
#exec MESH SEQUENCE MESH=peacepick SEQ=All       STARTFRAME=0   NUMFRAMES=1
#exec MESH SEQUENCE MESH=peacepick SEQ=Still     STARTFRAME=0   NUMFRAMES=1
#exec TEXTURE IMPORT NAME=Jpeacehand1 FILE=MODELS\peaceh.PCX GROUP=Skins
#exec MESHMAP SCALE MESHMAP=peacepick  X=0.08 Y=0.08 Z=0.16
#exec MESHMAP SETTEXTURE MESHMAP=peacepick NUM=1 TEXTURE=Jpeacehand1
```


```
// hawk.
//=============================================================================
class Hawk expands ScriptedPawn;

#exec MESH IMPORT MESH=Hawk ANIVFILE=MODELS\hawk_a.3D DATAFILE=MODELS\hawk_d.3D X=0 Y=0 Z=0
#exec MESH ORIGIN MESH=Hawk X=0 Y=0 Z=0 YAW=64

#exec MESH SEQUENCE MESH=Hawk SEQ=All    STARTFRAME=0   NUMFRAMES=1
#exec MESH SEQUENCE MESH=Hawk SEQ=Still  STARTFRAME=0   NUMFRAMES=1

#exec TEXTURE IMPORT NAME=JHawk1 FILE=MODELS\hawk.PCX GROUP=Skins FLAGS=2
#exec MESHMAP SCALE MESHMAP=hawk X=0.1 Y=0.1 Z=0.2
#exec MESHMAP SETTEXTURE MESHMAP=hawk NUM=1 TEXTURE=Jhawk1
```


```
// MiniGunSentry.
//=============================================================================
class MiniGunSentry expands Pickup;

#exec MESH IMPORT MESH=Sentry ANIVFILE=MODELS\sentry_a.3D DATAFILE=MODELS\sentry_d.3D X=0 Y=0 Z=0
#exec MESH ORIGIN MESH=Sentry X=-90 Y=90 Z=-80 YAW=64
#exec MESH SEQUENCE MESH=Sentry SEQ=All    STARTFRAME=0  NUMFRAMES=46
#exec MESH SEQUENCE MESH=Sentry SEQ=Up     STARTFRAME=0  NUMFRAMES=5
#exec MESH SEQUENCE MESH=Sentry SEQ=Still  STARTFRAME=5  NUMFRAMES=1
#exec MESH SEQUENCE MESH=Sentry SEQ=WarmUp STARTFRAME=6  NUMFRAMES=14
#exec MESH SEQUENCE MESH=Sentry SEQ=Fire   STARTFRAME=20 NUMFRAMES=4
#exec MESH SEQUENCE MESH=Sentry SEQ=Down   STARTFRAME=24  NUMFRAMES=21
#exec TEXTURE IMPORT NAME=Ainv1 FILE=MODELS\sentry.PCX GROUP="Skins"
#exec MESHMAP SCALE MESHMAP=Sentry X=0.06 Y=0.06 Z=0.12
#exec MESHMAP SETTEXTURE MESHMAP=Sentry NUM=1 TEXTURE=Ainv1

#exec MESH NOTIFY MESH=Sentry SEQ=Fire TIME=0.3 FUNCTION=GenerateBullet
#exec MESH NOTIFY MESH=Sentry SEQ=Fire TIME=0.8 FUNCTION=GenerateBullet
```


The beta U1 *.u files and the final *.u files should still contain a file index table. That is, tell where each file is and identify them. As to what they are and where they are at. Even for the beta *.u files this rule must be followed for the beta Unreal to locate each file and make the proper display of the data. This means that it may not be neccesary to run a hex rip of the files but identify the way it locates files. Making exporting the data easier.
## Post #17
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-02-07T04:24:59+00:00
- Post Title: Re: Unreal 1998 beta (PC) .u

There's definitely a structure to it but each .U file uses different headers for formats. It must be defined somewhere. But I'll give a bit of help here.

This link is to an archive containing decompiled LODMeshes and the raw extractions from the .u file (compiled). Note that for each package the header data is different even though it's the same version of Unreal but also note what is the same. Each raw mesh ends with 9A 99 99 3E then nine pairs of 0. This is specific to LODMeshes of Unreal (not in the beta so much, though some finds were made).

[http://www.sendspace.com/file/8q1llg](http://www.sendspace.com/file/8q1llg)
## Post #18
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-30T17:50:47+00:00
- Post Title: Re: Unreal 1998 beta (PC) .u

Nevermind this, [http://oldunreal.com/](http://oldunreal.com/) has already cracked it and included the beta stuff in their latest patch except the stuff that I got which makes it complete.
