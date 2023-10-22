## Post #1
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2021-03-26T22:02:35+00:00
- Post Title: Is there a way to find out the format of this 3d model?

This is the location of a small ghetto area from the game 25 to life
I would like to know what the format of this geometry is and how to open it?
Most likely, this 3d model does not have the necessary header. Knowing this game, I suspect that the header is substituted by the .exe  himself.

[https://drive.google.com/file/d/1UmAV6- ... sp=sharing](https://drive.google.com/file/d/1UmAV6-zpXOn429iwLW6Z2E7v9CqX7fP3/view?usp=sharing)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-03-26T22:59:23+00:00
- Post Title: Is there a way to find out the format of this 3d model?

I'm not sure what you mean by "necessary header" - headers can be absolutely anything.

Just from a quick look, you've got a file table at the start with offsets to each section - the first Short value in the file is the number of entries in this table (0x251).  So this file has 0x251 separate meshes.  Basically, each section seems to have a header, face index values, and then vertex data.

For example, the first small section - face data at 0xbdc (count value of 0x22 stored at 0xbd4), vertices at 0xc30 (count value of 0x18 at 0xc2, and then 0x18 for the vertex stride value).  It appears to be standard Float values for the vertices

If there's not already a script somewhere, then one would need to be made.  It doesn't look to be that complicated a format, just needs some analysis to figure out the exact structure.
## Post #3
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2021-03-27T09:05:34+00:00
- Post Title: Is there a way to find out the format of this 3d model?

Can you help with this?

> Reply from DKDave ↑Sat Mar 27, 2021 6:59 am at Sat Mar 27, 2021 6:59 am
>
> 
I'm not sure what you mean by "necessary header" - headers can be absolutely anything.

It just seems to me that all the files in the game don't have headers. The developers cut them out. And when you start game, the game itself substitutes headers for each file to read them. It sounds crazy, but it's possible.

I mean cut out, those titles that characterize this very 3d model, so that it is not possible to recognize them. Such protection from developers is possible.
## Post #4
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2021-03-27T09:11:55+00:00
- Post Title: Is there a way to find out the format of this 3d model?

I took a smaller 3D model. Maybe this will help identify them. This is a 3D model of the 44 Magnum weapon.

file NAME - textures 
file NAME_00000002 - unknown 3d model
[44mag.7z](https://xentaxbackup.github.io/file/19779_44mag.7z)
## Post #5
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-03-27T11:42:55+00:00
- Post Title: Is there a way to find out the format of this 3d model?

I've had a bit more of a look at it.  The header is the first part of the file.  The magnum file seems to have an extra 8 bytes at the start compared to the previous level file.  Not sure if that's how it's supposed to be - i.e. it should start with the 0x09 value if it's meant to be the same format as the other one.  But that is the header, so there's no need for any substituion - the data required *should* all be in the file.

Which platform is this from?  Windows, XBox or PS2?

I've seen a similar format in other games.  It looks like each file has 2 headers.  You've got the main header, which is everything up to the start of where you can see the value 0xEFBEADDE (or 0xDEADBEEF).  The main header has some basic info about where to find this DEADBEEF section.  The DEADBEEF section contains offsets on where to find each bit of data required for the model - i.e. face indices, vertices, info on the vertex structure.  The magnum one is easier because it's just 1 section, but in the level data, some parts have 2 or 3 sections, but I couldn't find a reference on how it indexes the face data for each section when there's more than 1 part.  And each section also contains vertices with different stride sizes for the vertex structure.

So it's not completely straightforward, unfortunately.
## Post #6
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2021-03-27T16:48:35+00:00
- Post Title: Is there a way to find out the format of this 3d model?

These files are from the PC version. But the game exists on both PS2 and xbox. But the files there are slightly different. Files from consoles will not work on the PC, the game will crash.

> Reply from DKDave ↑Sat Mar 27, 2021 7:42 pm at Sat Mar 27, 2021 7:42 pm
>
> 
I've had a bit more of a look at it. The header is the first part of the file. The magnum file seems to have an extra 8 bytes at the start compared to the previous level file. Not sure if that's how it's supposed to be - i.e. it should start with the 0x09 value if it's meant to be the same format as the other one

What you wrote is quite possible. Because in this game there are some other files that have extra bytes in the header. If I delete these extra bytes, then I can read these files using standard windows tools. So I think it's the same story with 3D models. Many of them may have extra information in the title that only the game itself understands. And probably these extra bytes need to be deleted in order to read the 3d model, by some program.

> Reply from DKDave ↑Sat Mar 27, 2021 7:42 pm at Sat Mar 27, 2021 7:42 pm
>
> 
but I couldn't find a reference on how it indexes the face data for each section when there's more than 1 part. And each section also contains vertices with different stride sizes for the vertex structure.

Maybe I didn't unpack the archive very well. Try unpacking it yourself. I used the bms script from the game Dragon Ballz 
It does not quite suit this game, but nevertheless it decompresses files. 

[https://drive.google.com/file/d/19rsA4E ... sp=sharing](https://drive.google.com/file/d/19rsA4EoyDIyPKRkJtmbuKY_VCucx4Tjj/view?usp=sharing)

But keep in mind that the models may well contain unnecessary information in the header, which only the game itself understands. Such bytes most likely need to be deleted to read the file.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-27T18:02:19+00:00
- Post Title: Is there a way to find out the format of this 3d model?

> Reply from Elephantkilla ↑Sun Mar 28, 2021 12:48 am at Sun Mar 28, 2021 12:48 am
>
> Maybe I didn't unpack the archive very well.whatever you did exactly, using a dbl directly gives me this:
.



44MAG-dbl.png (45.72 KiB) Viewed 122 times
## Post #8
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2021-03-27T18:10:53+00:00
- Post Title: Is there a way to find out the format of this 3d model?

Yes, that's exactly what this weapon looks like. But is it possible to somehow determine the format of this 3d model in order to find a program that can open it in order to change 3d models in the future?



TTL 2021-03-27 21-06-43.jpg (231.04 KiB) Viewed 119 times
## Post #9
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-03-27T18:51:46+00:00
- Post Title: Is there a way to find out the format of this 3d model?

No, it looks like the file is fine.  It's just a custom format.  Unless there's a script for another game that uses the exact format, then something needs to be created for it.  Not an easy task considering these formats can be quite complex at times.  I can hack something together for the level data, but it's far from complete.  There's some sort of positioning info in there as things are out of place, etc.

But this gives you an idea of the contents of the file.  This is just the most basic data:
## Post #10
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2021-03-27T19:28:42+00:00
- Post Title: Is there a way to find out the format of this 3d model?

Wow, that's cool. This location actually looks like this:



TTL 2021-03-27 22-18-43.jpg (185.79 KiB) Viewed 113 times


[](https://ibb.co/swwmbNV)
[](https://ibb.co/XzdzG3f)
[](https://ibb.co/kG7F8xR)
## Post #11
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2021-03-27T19:40:26+00:00
- Post Title: Is there a way to find out the format of this 3d model?

One of the goals of modifying this location is to at least remove these marked fences and windows, which greatly interfere with movement in multiplayer. In principle, I can visually remove them using winhex, but there is no way to remove the collision. The location has a common collision, which is responsible for the contact, and here it would be desirable to modify it.

[](https://ibb.co/kQL2F0Q)
[](https://ibb.co/2SNz0GY)
[](https://ibb.co/59bT0jS)

"APT_FencePerimeter11" and "APT_FencePerimeter10" 
These are the names of the identifiers, just the same fences, the collision in place of which greatly interferes. This is the place of the code that is responsible for displaying objects on the location in the screenshot. I don't remember which byte, but here you can make the object invisible. But the collision will remain. You can copy the code for example windows, and paste it behind the fence location and the window will be displayed. The main thing is that the number of bytes is the same. Later I will send a screenshot where you can change the size of objects. By changing some bytes, you can stretch or narrow the models. But the collision is immutable.
[Безымянныйrrr.jpg](https://xentaxbackup.github.io/file/19785_Безымянныйrrr.jpg)
## Post #12
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2021-03-27T19:56:14+00:00
- Post Title: Is there a way to find out the format of this 3d model?

If I write zero bytes after the number 1 for "APT_FencePerimeter11", then the fence will not be displayed in the game. But the collision still exists and I can't get through here.



dgd.jpg (198.49 KiB) Viewed 109 times
## Post #13
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2021-03-27T20:15:34+00:00
- Post Title: Is there a way to find out the format of this 3d model?

This area probably contains the names of the main non-dynamic (non-mobile) 3d objects.



Безымянныwwwй.jpg (203.33 KiB) Viewed 107 times


I mean those 3d models that can't be added via the script. Dynamic objects are added using a script file (for example, doors that can be opened, windows that can be broken, cars that can be blown up. You can set parameters for these objects in the script file, example file:
SP_APARTMENTS.AP

```
cp=-1
class=StartPos

[Checkpoint1]
cp=-1
class=SpawnBox
team=1
spawn_mode=All modes

[Checkpoint2]
cp=-1
class=SpawnBox
team=2
spawn_mode=All modes

[tipper_enemy_hides]
cp=1
class=SpawnBox
team=2
spawn_mode=All modes

[NPCBeacon7]
cp=1
class=SpawnBox
team=1
spawn_mode=All modes

[NPC_Cop2]
cp=1
class=SpawnBox
team=1
spawn_mode=All modes

[NPCBeacon22]
cp=1
class=SpawnBox
team=1
spawn_mode=All modes

[NPCBeacon4w4]
cp=1
class=SpawnBox
team=2
spawn_mode=All modes

[NPC_Gang3]
cp=-1
class=SpawnBox
team=1
spawn_mode=All modes

[NPC_Gang1]
cp=-1
class=SpawnBox
team=2
spawn_mode=All modes

[NPC_Gang10]
cp=-1
class=SpawnBox
team=2
spawn_mode=All modes

[APT_BathTub03]
cp=-1
class=SpawnBox
team=2
spawn_mode=All modes

[APT_BalconyRails05]
cp=-1
class=SpawnBox
team=2
spawn_mode=All modes

[APT_DOOR_Locked11]
cp=-1
class=SpawnBox
team=2
spawn_mode=All modes

[APT_ApartmentInterior06]
cp=-1
class=SpawnBox
team=2
spawn_mode=All modes

[APT_BathroomSink02]
cp=-1
class=SpawnBox
team=2
spawn_mode=All modes

[occluder01]
cp=-1
class=occluder

[occluder02]
cp=-1
class=occluder

[occluder03]
cp=-1
class=occluder

[occluder04]
cp=-1
class=occluder

[occluder05]
cp=-1
class=occluder

[occluder06]
cp=-1
class=occluder

[occluder07]
cp=-1
class=occluder

[occluder08]
cp=-1
class=occluder

[occluder09]
cp=-1
class=occluder

[occluder10]
cp=-1
class=occluder

[occluder11]
cp=-1
class=occluder

[occluder12]
cp=-1
class=occluder

[occluder13]
cp=-1
class=occluder

[occluder14]
cp=-1
class=occluder

[occluder15]
cp=-1
class=occluder

[occluder16]
cp=-1
class=occluder

[occluder17]
cp=-1
class=occluder

[occluder18]
cp=-1
class=occluder

[occluder19]
cp=-1
class=occluder

[occluder20]
cp=-1
class=occluder

[occluder21]
cp=-1
class=occluder

[occluder22]
cp=-1
class=occluder

[occluder24]
cp=-1
class=occluder

[occluder25]
cp=-1
class=occluder

[occluder26]
cp=-1
class=occluder

[occluder27]
cp=-1
class=occluder

[occluder28]
cp=-1
class=occluder

[JukeBox]
cp=-1
class=compactor
name=jukebox
ai=jukebox.sx

[JukeBox1]
cp=-1
class=compactor
name=jukebox
ai=jukebox.sx

[APT_BoomBoxA02]
cp=-1
class=compactor
name=jukebox
ai=jukebox.sx

[APT_FencePerimeter10]
SurfaceType=ladder
cp=-1
class=compActor
name=ladder
ai=ladder.sx
double_sided=False
model_name=active/SODAMACHINE.dbl

[APT_Dumpster]
SurfaceType=ladder
cp=-1
class=compActor
name=ladder
ai=ladder.sx
double_sided=True
model_name=active/MAIDENGRASS_A.dbl

[APT_FencePerimeter11]
SurfaceType=ladder
cp=-1
class=compActor
name=ladder
ai=ladder.sx
double_sided=False
model_name=active/SODAMACHINE.dbl

[Health10]
cp=-1
class=triggerbox
name=teleport
net=local
ai=teleport.sx
ai/target=APT_DOOR_Openable25
ai/delay=0
player_included=True
npcs_included=False

[APT_DOOR_Openable25]
cp=-1
class=triggerbox
name=walkintrigger
ai=walkintrigger.sx
net=local
ai/actorToTrigger=APT_DOOR_Openable25
ai/entryMessage=nothing
ai/entryMessageDelay=0
ai/exitMessage=nothing
ai/exitMessageDelay=0
ai/once=False
player_included=True
npcs_included=False

[NPCTrigger33]
cp=-1
class=triggerbox
name=teleport
net=local
ai=teleport.sx
ai/target=APT_BathTub03
ai/delay=0
player_included=True
npcs_included=False

[APT_BathTub03]
cp=-1
class=triggerbox
name=walkintrigger
ai=walkintrigger.sx
net=local
ai/actorToTrigger=APT_BathTub03
ai/entryMessage=nothing
ai/entryMessageDelay=0
ai/exitMessage=nothing
ai/exitMessageDelay=0
ai/once=False
player_included=True
npcs_included=False

[APT_CeilingFanBlades01]
cp=-1
class=compactor
name=spinner
ai=spinner.sx
ai/rotateX=0.000f
ai/rotateY=3.000f
ai/rotateZ=0.000f
ai/acceleration=3.000f
ai/deceleration=0.000f
ai/rotateMaxX=0.000f
ai/rotateMaxY=0.000f
ai/rotateMaxZ=0.000f
SurfaceType=default
Spinner is Destructible=False

[APT_CeilingFanBlades02]
cp=-1
class=compactor
name=spinner
ai=spinner.sx
ai/rotateX=0.000f
ai/rotateY=6.000f
ai/rotateZ=0.000f
ai/acceleration=6.000f
ai/deceleration=-1
ai/rotateMaxX=0.000f
ai/rotateMaxY=6.000f
ai/rotateMaxZ=0.000f
SurfaceType=default
Spinner is Destructible=False

[APT_CeilingFanBlades03]
cp=-1
class=compactor
name=spinner
ai=spinner.sx
ai/rotateX=0.000f
ai/rotateY=6.000f
ai/rotateZ=0.000f
ai/acceleration=6.000f
ai/deceleration=-1
ai/rotateMaxX=0.000f
ai/rotateMaxY=6.000f
ai/rotateMaxZ=0.000f
SurfaceType=default
Spinner is Destructible=False

[Door_at_cross]
cp=2
class=compActor
name=door
ai=door.sx
ai/friction=0.75
ai/maxangle=180
ai/delay=0
ai/soundOpen=door_open_squeak
ai/soundClose=door_close
ai/soundKick=door_kick
ai/messageOn=enter_the_light
ai/swingdir=both
ai/once=False
ai/initialState=Closed
Players can open=True
playerlocked=0
Npcs can open=True
npclocked=0
ai/inventory=none
SurfaceType=wooddoor
ai/shatterable=False

[APT_DOOR_Openable03]
cp=1
class=compActor
name=door
ai=door.sx
ai/friction=0.500f
ai/maxangle=180.000f
ai/delay=0
ai/soundOpen=door_open_squeak
ai/soundClose=door_close
ai/soundKick=door_kick
ai/messageOn=AI_opens
ai/messageOff=AI_closes
ai/swingdir=both
ai/once=False
ai/initialState=Closed
Players can open=True
playerlocked=0
Npcs can open=True
npclocked=0
ai/inventory=none
SurfaceType=wooddoor
ai/shatterable=False

[APT_DOOR_Openable04]
cp=2
class=compActor
name=door
ai=door.sx
ai/friction=0.500f
ai/maxangle=180.000f
ai/delay=0
ai/soundOpen=door_open_squeak
ai/soundClose=door_close
ai/soundKick=door_kick
ai/swingdir=both
ai/once=False
ai/initialState=Closed
Players can open=True
playerlocked=0
Npcs can open=False
npclocked=1
ai/inventory=none
SurfaceType=wooddoor
ai/shatterable=False

[APT_DOOR_Openable13]
cp=-1
class=compActor
name=door
ai=door.sx
ai/friction=0.500f
ai/maxangle=180.000f
ai/delay=0
ai/soundOpen=door_open_squeak
ai/soundClose=door_close
ai/soundKick=door_kick
ai/swingdir=both
ai/once=False
ai/initialState=Closed
Players can open=True
playerlocked=0
Npcs can open=False
npclocked=1
ai/inventory=none
SurfaceType=wooddoor
ai/shatterable=False

[APT_DOOR_Openable49]
cp=2
class=compActor
name=door
ai=door.sx
ai/friction=0.500f
ai/maxangle=180.000f
ai/delay=0
ai/soundOpen=door_open_squeak
ai/soundClose=door_close
ai/soundKick=door_kick
ai/swingdir=out
ai/once=False
ai/initialState=Closed
Players can open=True
playerlocked=0
Npcs can open=True
npclocked=0
ai/inventory=none
SurfaceType=wooddoor
ai/shatterable=False

[APT_DOOR_Openable50]
cp=1
class=compActor
name=door
ai=door.sx
ai/friction=0.500f
ai/maxangle=180.000f
ai/delay=0
ai/soundOpen=door_open_squeak
ai/soundClose=door_close
ai/soundKick=door_kick
ai/swingdir=out
ai/once=False
ai/initialState=Closed
Players can open=True
playerlocked=0
Npcs can open=True
npclocked=0
ai/inventory=none
SurfaceType=wooddoor
ai/shatterable=False

[APT_DOOR_Openable51]
cp=1
class=compActor
name=door
ai=door.sx
ai/friction=0.500f
ai/maxangle=180.000f
ai/delay=0
ai/soundOpen=door_open_squeak
ai/soundClose=door_close
ai/soundKick=door_kick
ai/swingdir=out
ai/once=False
ai/initialState=Closed
Players can open=True
playerlocked=0
Npcs can open=True
npclocked=0
ai/inventory=none
SurfaceType=wooddoor
ai/shatterable=False

[APT_DOOR_Openable52]
cp=2
class=compActor
name=door
ai=door.sx
ai/friction=0.500f
ai/maxangle=180.000f
ai/delay=0
ai/soundOpen=door_open_squeak
ai/soundClose=door_close
ai/soundKick=door_kick
ai/swingdir=in
ai/once=False
ai/initialState=Closed
Players can open=True
playerlocked=0
Npcs can open=True
npclocked=0
ai/inventory=none
SurfaceType=wooddoor
ai/shatterable=False

[APT_DOOR_Openable14]
cp=2
class=compActor
name=door
ai=door.sx
ai/friction=0.500f
ai/maxangle=180.000f
ai/delay=0
ai/soundOpen=door_open_squeak
ai/soundClose=door_close
ai/soundKick=door_kick
ai/messageOn=open_it
ai/swingdir=both
ai/once=False
ai/initialState=Closed
Players can open=True
playerlocked=0
Npcs can open=False
npclocked=1
ai/inventory=none
SurfaceType=wooddoor
ai/shatterable=False

[APT_DOOR_Openable25]
cp=2
class=compActor
name=invisible_wall
ai=invisible_wall.sx
ai/player=False
ai/npc=True
ai/bullets=False
ai/seethru=True
ai/on=True

[APT_DOOR_Openable43]
cp=2
class=compActor
name=slidedoor
ai=slidedoor.sx
ai/friction=0.250f
ai/distance=3.400f
ai/delay=0.000f
ai/soundStart=slidedoorstart
ai/soundMove=slidedoormove
ai/soundStop=slidedoorstop
ai/messageOn=open2
ai/doorMovement=Side to Side
ai/initialState=Closed
Players can open=True
playerlocked=0
Npcs can open=True
npclocked=0
ai/inventory=none
SurfaceType=wooddoor
ai/shatterable=False

[APT_ShowerWindow01]
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_ShowerWindow02]
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_ShowerWindow03]
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_ShowerWindow04]
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass01]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass02]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass03]
OBBValue=0
SurfaceType=glass
cp=2
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass04]
OBBValue=0
SurfaceType=glass
cp=2
class=glass
name=glass
ai/health=35
OBBDepth=0.25
messageDie=breakglass1

[APT_WindowGlass05]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass07]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass08]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass09]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass10]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass11]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass13]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass14]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass15]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass18]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass16]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass17]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass19]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass20]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass21]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass22]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass23]
OBBValue=0
SurfaceType=glass
cp=2
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass24]
OBBValue=0
SurfaceType=glass
cp=2
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass25]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass26]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass27]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass28]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass29]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass30]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass31]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass32]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass33]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass34]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass35]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass36]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_WindowGlass37]
OBBValue=0
SurfaceType=glass
cp=-1
class=glass
name=glass
ai/health=35
OBBDepth=0.25

[APT_Train01]
cp=-1
class=compactor
name=pathfollower
ai=pathfollower.sx
interacts=false
net=local
ai/sound=train_loop
ai/idle=False
ai/stopSendMessage=False
ai/soundEnd=False
ai/soundOff=False
path_name=path_train01
path_init_speed=40
path_target_speed=0
path_accel=0
path_max_g=0
path_reset_delay=0
path_drop_on_ground=False
path_keep_orient=False
path_reverse_at_end=False
path_face_movement_direction=True
path_follower_is_cushioned=False

[APT_Train02]
cp=-1
class=compactor
name=pathfollower
ai=pathfollower.sx
interacts=false
net=local
ai/idle=False
ai/stopSendMessage=False
ai/soundEnd=False
ai/soundOff=False
path_name=path_train02
path_init_speed=40
path_target_speed=0
path_accel=0
path_max_g=0
path_reset_delay=0
path_drop_on_ground=False
path_keep_orient=False
path_reverse_at_end=False
path_face_movement_direction=True
path_follower_is_cushioned=False

[APT_Train03]
cp=-1
class=compactor
name=pathfollower
ai=pathfollower.sx
interacts=false
net=local
ai/idle=False
ai/stopSendMessage=False
ai/soundEnd=False
ai/soundOff=False
path_name=path_train03
path_init_speed=40
path_target_speed=0
path_accel=0
path_max_g=0
path_reset_delay=0
path_drop_on_ground=False
path_keep_orient=False
path_reverse_at_end=False
path_face_movement_direction=True
path_follower_is_cushioned=False

[APT_Train04]
cp=-1
class=compactor
name=pathfollower
ai=pathfollower.sx
interacts=false
net=local
ai/idle=False
ai/stopSendMessage=False
ai/soundEnd=False
ai/soundOff=False
path_name=path_train04
path_init_speed=40
path_target_speed=0
path_accel=0
path_max_g=0
path_reset_delay=0
path_drop_on_ground=False
path_keep_orient=False
path_reverse_at_end=False
path_face_movement_direction=True
path_follower_is_cushioned=False

[APT_Train05]
cp=-1
class=compactor
name=pathfollower
ai=pathfollower.sx
interacts=false
net=local
ai/idle=False
ai/stopSendMessage=False
ai/soundEnd=False
ai/soundOff=False
path_name=path_train07
path_init_speed=25
path_target_speed=0
path_accel=0
path_max_g=0
path_reset_delay=0
path_drop_on_ground=False
path_keep_orient=False
path_reverse_at_end=False
path_face_movement_direction=True
path_follower_is_cushioned=False

[APT_Train06]
cp=-1
class=compactor
name=pathfollower
ai=pathfollower.sx
interacts=false
net=local
ai/idle=False
ai/stopSendMessage=False
ai/soundEnd=False
ai/soundOff=False
path_name=path_train06
path_init_speed=25
path_target_speed=0
path_accel=0
path_max_g=0
path_reset_delay=0
path_drop_on_ground=False
path_keep_orient=False
path_reverse_at_end=False
path_face_movement_direction=True
path_follower_is_cushioned=False

[APT_Train07]
cp=-1
class=compactor
name=pathfollower
ai=pathfollower.sx
interacts=false
net=local
ai/idle=False
ai/stopSendMessage=False
ai/soundEnd=False
ai/soundOff=False
path_name=path_train05
path_init_speed=25
path_target_speed=0
path_accel=0
path_max_g=0
path_reset_delay=0
path_drop_on_ground=False
path_keep_orient=False
path_reverse_at_end=False
path_face_movement_direction=True
path_follower_is_cushioned=False

[APT_Train08]
cp=-1
class=compactor
name=pathfollower
ai=pathfollower.sx
interacts=false
net=local
ai/sound=train_loop
ai/idle=False
ai/stopSendMessage=False
ai/soundEnd=False
ai/soundOff=False
path_name=path_train08
path_init_speed=25
path_target_speed=0
path_accel=0
path_max_g=0
path_reset_delay=0
path_drop_on_ground=False
path_keep_orient=False
path_reverse_at_end=False
path_face_movement_direction=True
path_follower_is_cushioned=False

[APT_TVScreenGlow01]
cp=-1
class=compactor
name=destructable
ai=destructable.sx
ai/exploder=none
particle_effect=none
SurfaceType=carpet
ai/health=200
ai/respawn=-1
ai/messageDie=tvone
ai/delayDeath=0
ai/collide=False

[APT_TVScreenGlow02]
cp=-1
class=compactor
name=destructable
ai=destructable.sx
ai/exploder=none
particle_effect=none
SurfaceType=carpet
ai/health=200
ai/respawn=-1
ai/messageDie=tvtwo
ai/delayDeath=0
ai/collide=False

[APT_TVScreenGlow04]
cp=-1
class=compactor
name=destructable
ai=destructable.sx
ai/exploder=none
particle_effect=none
SurfaceType=carpet
ai/health=200
ai/respawn=-1
ai/messageDie=tvfour
ai/delayDeath=0
ai/collide=False

[APT_TVScreenGlow05]
cp=-1
class=compactor
name=destructable
ai=destructable.sx
ai/exploder=none
particle_effect=none
SurfaceType=carpet
ai/health=200
ai/respawn=-1
ai/messageDie=tvtwo
ai/delayDeath=0
ai/collide=False

[APT_TVScreenStatic01]
OBBValue=0
SurfaceType=glass
cp=-1
class=compactor
name=destructable
ai=destructable.sx
ai/exploder=none
particle_effect=BrokenLightSparks
ai/health=10
ai/respawn=-1
ai/messageDeath=tvone
ai/delayDeath=0
ai/collide=False

[APT_TVScreenStatic04]
cp=-1
class=compactor
name=destructable
ai=destructable.sx
ai/exploder=none
particle_effect=BrokenLightSparks
SurfaceType=default
ai/health=10
ai/respawn=-1
ai/messageDeath=tvfour
ai/delayDeath=0
ai/collide=False

[APT_TVScreenStatic02]
OBBValue=0
SurfaceType=default
cp=-1
class=compactor
name=destructable
ai=destructable.sx
ai/exploder=none
particle_effect=BrokenLightSparks
ai/health=10
ai/respawn=-1
ai/messageDeath=tvtwo
ai/delayDeath=0
ai/collide=False

[col_InnvisibleWall01]
cp=-1
class=compActor
name=invisible_wall
ai=invisible_wall.sx
ai/player=True
ai/npc=True
ai/bullets=False
ai/seethru=True
ai/on=True

[col_InnvisibleWall03]
cp=-1
class=compActor
name=invisible_wall
ai=invisible_wall.sx
ai/player=True
ai/npc=True
ai/bullets=False
ai/seethru=True
ai/on=True

[col_InnvisibleWall05]
cp=-1
class=compActor
name=invisible_wall
ai=invisible_wall.sx
ai/player=True
ai/npc=True
ai/bullets=False
ai/seethru=True
ai/on=True

[col_InnvisibleWall016]
cp=-1
class=compActor
name=invisible_wall
ai=invisible_wall.sx
ai/player=True
ai/npc=True
ai/bullets=False
ai/seethru=True
ai/on=True

[col_InnvisibleWall04]
cp=-1
class=compActor
name=invisible_wall
ai=invisible_wall.sx
ai/player=True
ai/npc=True
ai/bullets=False
ai/seethru=True
ai/on=True

[col_InnvisibleWall06]
cp=-1
class=compActor
name=invisible_wall
ai=invisible_wall.sx
ai/player=True
ai/npc=True
ai/bullets=False
ai/seethru=True
ai/on=True

[Inviswall2]
cp=1
class=compActor
name=invisible_wall
ai=invisible_wall.sx
ai/player=False
ai/npc=True
ai/bullets=True
ai/seethru=True
ai/on=True
ai/offMessage=turnon2

[Inviswall1]
cp=-1
class=compActor
name=invisible_wall
ai=invisible_wall.sx
ai/player=True
ai/npc=True
ai/bullets=False
ai/seethru=True
ai/on=True

[COPCAR]
cp=-1
class=compActor
name=car
ai=carexplode.sx
ai/delay=3
ai/size=0
ai/layer=30

[COPCAR1]
cp=-1
class=compActor
name=car
ai=carexplode.sx
ai/delay=3
ai/size=0
ai/layer=31

[CarCollision_10A1]
cp=-1
class=compActor
name=car
ai=carexplode.sx
ai/sfx=car_alarm1
ai/delay=10.000f
ai/size=0
ai/layer=27

[CarCollision_2A]
cp=-1
class=compActor
name=car
ai=carexplode.sx
ai/delay=3
ai/size=0
ai/layer=26

[veh_kad_demille15]
cp=-1
class=compActor
name=car
ai=carexplode.sx
ai/delay=3
ai/size=1
ai/layer=15

[veh_linkin_citycar13]
cp=1
class=compActor
name=car
ai=carexplode.sx
ai/sfx=car_alarm1
ai/delay=10.000f
ai/size=1
ai/layer=13

[roach01]
cp=-1
class=compactor
name=pathfollower
ai=pathfollower.sx
interacts=false
net=local
ai/idle=False
ai/stopSendMessage=False
ai/soundEnd=False
ai/soundOff=False
path_name=path_roach01
path_init_speed=1
path_target_speed=1
path_accel=1
path_max_g=0
path_reset_delay=0
path_drop_on_ground=True
path_keep_orient=False
path_reverse_at_end=True
path_face_movement_direction=True
path_follower_is_cushioned=False

[roach03]
cp=-1
class=compactor
name=pathfollower
ai=pathfollower.sx
interacts=false
net=local
ai/idle=False
ai/stopSendMessage=False
ai/soundEnd=False
ai/soundOff=False
path_name=path_roach02
path_init_speed=1
path_target_speed=1
path_accel=1
path_max_g=0
path_reset_delay=0
path_drop_on_ground=True
path_keep_orient=False
path_reverse_at_end=True
path_face_movement_direction=True
path_follower_is_cushioned=False

[roach05]
cp=-1
class=compactor
name=pathfollower
ai=pathfollower.sx
interacts=false
net=local
ai/idle=False
ai/stopSendMessage=False
ai/soundEnd=False
ai/soundOff=False
path_name=path_roach03
path_init_speed=1
path_target_speed=1
path_accel=1
path_max_g=0
path_reset_delay=0
path_drop_on_ground=True
path_keep_orient=False
path_reverse_at_end=True
path_face_movement_direction=True
path_follower_is_cushioned=False

[roach08]
cp=-1
class=compactor
name=pathfollower
ai=pathfollower.sx
interacts=false
net=local
ai/idle=False
ai/stopSendMessage=False
ai/soundEnd=False
ai/soundOff=False
path_name=path_roach05
path_init_speed=1
path_target_speed=1
path_accel=1
path_max_g=0
path_reset_delay=0
path_drop_on_ground=True
path_keep_orient=False
path_reverse_at_end=True
path_face_movement_direction=True
path_follower_is_cushioned=False

[roach15]
cp=-1
class=compactor
name=pathfollower
ai=pathfollower.sx
interacts=false
net=local
ai/idle=False
ai/stopSendMessage=False
ai/soundEnd=False
ai/soundOff=False
path_name=path_roach09
path_init_speed=1
path_target_speed=1
path_accel=1
path_max_g=0
path_reset_delay=0
path_drop_on_ground=True
path_keep_orient=False
path_reverse_at_end=True
path_face_movement_direction=True
path_follower_is_cushioned=False

[roach17]
cp=-1
class=compactor
name=pathfollower
ai=pathfollower.sx
interacts=false
net=local
ai/idle=False
ai/stopSendMessage=False
ai/soundEnd=False
ai/soundOff=False
path_name=path_roach10
path_init_speed=1
path_target_speed=1
path_accel=1
path_max_g=0
path_reset_delay=0
path_drop_on_ground=True
path_keep_orient=False
path_reverse_at_end=True
path_face_movement_direction=True
path_follower_is_cushioned=False

[roach19]
cp=-1
class=compactor
name=pathfollower
ai=pathfollower.sx
interacts=false
net=local
ai/idle=False
ai/stopSendMessage=False
ai/soundEnd=False
ai/soundOff=False
path_name=path_roach11
path_init_speed=1
path_target_speed=1
path_accel=1
path_max_g=0
path_reset_delay=0
path_drop_on_ground=True
path_keep_orient=False
path_reverse_at_end=True
path_face_movement_direction=True
path_follower_is_cushioned=False

[roach10]
cp=-1
class=compactor
name=pathfollower
ai=pathfollower.sx
interacts=false
net=local
ai/idle=False
ai/stopSendMessage=False
ai/soundEnd=False
ai/soundOff=False
path_name=path_roach06
path_init_speed=1
path_target_speed=1
path_accel=1
path_max_g=0
path_reset_delay=0
path_drop_on_ground=True
path_keep_orient=False
path_reverse_at_end=True
path_face_movement_direction=True
path_follower_is_cushioned=False

[roach23]
cp=-1
class=compactor
name=pathfollower
ai=pathfollower.sx
interacts=false
net=local
ai/idle=False
ai/stopSendMessage=False
ai/soundEnd=False
ai/soundOff=False
path_name=path_roach13
path_init_speed=1
path_target_speed=1
path_accel=1
path_max_g=0
path_reset_delay=0
path_drop_on_ground=True
path_keep_orient=False
path_reverse_at_end=True
path_face_movement_direction=True
path_follower_is_cushioned=False

[apt_TableCoffee03]
OBBValue=0
SurfaceType=ndwood
cp=1
class=compActor
name=tipper
ai=tipper.sx
ai/tipAngle=90
ai/speed=0.500f
ai/mass=0
ai/bounce=8

[EXIT1]
cp=-1
class=actor
name=emittercontroller
ai=emittercontroller.sx
emitter_name=ComeHereVertical
LOD1RadiusOverride=1000
LOD2RadiusOverride=1000
emitter_type=Standard
ai/delayOn=0
ai/delayOff=0
ai/initialState=On

[EXIT1]
cp=-1
class=triggerbox
name=teleport
net=local
ai=teleport.sx
ai/target=Health7
ai/delay=0
player_included=True
npcs_included=False

[Health7]
cp=-1
class=triggerbox
name=walkintrigger
ai=walkintrigger.sx
net=local
ai/actorToTrigger=Health7
ai/entryMessage=nothing
ai/entryMessageDelay=0
ai/exitMessage=nothing
ai/exitMessageDelay=0
ai/once=False
player_included=True
npcs_included=False

[apt_blanket02]
cp=-1
class=compActor
name=cloth
net=local
ai=cloth.sx
model_name=active/blanket_apt
path_init_speed=0
path_target_speed=0
path_accel=0
path_max_g=0
path_reset_delay=0
path_drop_on_ground=True
path_keep_orient=False
path_reverse_at_end=True
path_face_movement_direction=True
path_follower_is_cushioned=False

[apt_blanket04]
cp=-1
class=compActor
name=cloth
net=local
ai=cloth.sx
model_name=active/blanket_apt
path_init_speed=0
path_target_speed=0
path_accel=0
path_max_g=0
path_reset_delay=0
path_drop_on_ground=True
path_keep_orient=False
path_reverse_at_end=True
path_face_movement_direction=True
path_follower_is_cushioned=False

[SensorLightTRIGGER]
cp=-1
class=triggerbox
name=walkintrigger
ai=walkintrigger.sx
net=local
ai/actorToTrigger=all
ai/entryMessage=Busted
ai/entryMessageDelay=0
ai/exitMessageDelay=0
ai/once=False
ai/minspeed=5
player_included=True
npcs_included=False

[spot2]
cp=-1
class=actor
name=triggered light
ai=triggeredlight.sx
ai/delay=0
ai/lightR=1
ai/lightG=1
ai/lightB=1
ai/lightAttenuation=0.300f
ai/instance=Hotspot
ai/initialState=Off
ai/messageOn=Busted

[Health1]
cp=2
class=compactor
name=healthpickup
ai=pickups.sx
ai/triggered=False
ai/timeout=-1
pickupType=health
model_name=objects/Health_Pkup.dbl
emitter_name=Pickup
ai/health=50
ai/sound=health_pu
ai/yoffset=0.2

[Health2]
cp=1
class=compactor
name=healthpickup
ai=pickups.sx
ai/triggered=False
ai/timeout=-1
pickupType=health
model_name=objects/Health_Pkup.dbl
emitter_name=Pickup
ai/health=50
ai/sound=health_pu
ai/yoffset=0.2

[Health3]
cp=1
class=compactor
name=healthpickup
ai=pickups.sx
ai/triggered=False
ai/timeout=-1
pickupType=health
model_name=objects/Health_Pkup.dbl
emitter_name=Pickup
ai/health=50
ai/sound=health_pu
ai/yoffset=0.2

[Health4]
cp=2
class=compactor
name=healthpickup
ai=pickups.sx
ai/triggered=False
ai/timeout=-1
pickupType=health
model_name=objects/Health_Pkup.dbl
emitter_name=Pickup
ai/health=50
ai/sound=health_pu
ai/yoffset=0.2

[Health5]
cp=2
class=compactor
name=healthpickup
ai=pickups.sx
ai/triggered=False
ai/timeout=-1
pickupType=health
model_name=objects/Health_Pkup.dbl
emitter_name=Pickup
ai/health=50
ai/sound=health_pu
ai/yoffset=0.2

[Health6]
cp=2
class=compactor
name=healthpickup
ai=pickups.sx
ai/triggered=False
ai/timeout=-1
pickupType=health
model_name=objects/Health_Pkup.dbl
emitter_name=Pickup
ai/health=50
ai/sound=health_pu
ai/yoffset=0.2

[Health8]
cp=2
class=compactor
name=healthpickup
ai=pickups.sx
ai/triggered=False
ai/timeout=-1
pickupType=health
model_name=objects/Health_Pkup.dbl
emitter_name=Pickup
ai/health=50
ai/sound=health_pu
ai/yoffset=0.2

[Health9]
cp=2
class=compactor
name=healthpickup
ai=pickups.sx
ai/triggered=False
ai/timeout=-1
pickupType=health
model_name=objects/Health_Pkup.dbl
emitter_name=Pickup
ai/health=50
ai/sound=health_pu
ai/yoffset=0.2

[Health10]
cp=2
class=compactor
name=healthpickup
ai=pickups.sx
ai/triggered=False
ai/timeout=-1
pickupType=health
model_name=objects/Health_Pkup.dbl
emitter_name=Pickup
ai/health=50
ai/sound=health_pu
ai/yoffset=0.2

[Primary_ammo1]
cp=2
class=compactor
name=ammopickup
ai=pickups.sx
ai/triggered=False
ai/timeout=-1
pickupType=ammo
emitter_name=Pickup
ai/ammo=primaryAmmo
model_name=objects/AmmoP_Pkup.dbl
ai/ammoAmount=50
ai/sound=ammo_pu
ai/yoffset=0.2

[Secondary_ammo1]
cp=2
class=compactor
name=ammopickup
ai=pickups.sx
ai/triggered=False
ai/timeout=-1
pickupType=ammo
emitter_name=Pickup
ai/ammo=secondaryAmmo
model_name=objects/AmmoS_Pkup.dbl
ai/ammoAmount=50
ai/sound=ammo_pu
ai/yoffset=0.2

[Primary_ammo3]
cp=-1
class=compactor
name=ammopickup
ai=pickups.sx
ai/triggered=False
ai/timeout=-1
pickupType=ammo
emitter_name=Pickup
ai/ammo=primaryAmmo
model_name=objects/AmmoP_Pkup.dbl
ai/ammoAmount=50
ai/sound=ammo_pu
ai/yoffset=0.2

[Sniper1]
cp=-1
class=triggerbox
name=robberytrigger
ai=robberytrigger.sx
net=local
player_included=True
npcs_included=False

[apt_PicnicTable02]
cp=-1
class=compActor
name=robbery_objective
ai=robberyobjective.sx
model_name=avatars\pieces\p56.dbl

[NPC_NonCombat]
cp=-1
NonCombatants=NPC Cowerer
class=combatant
name=bistander
ai=bistander.sx
ai_var_file=ai_nc_cowerer
aiType=6
bodytype=lowpoly
npc_geom=Hot Club Girl 2
voiceset=fn2
npc_model=partygirl1
npc_texture=prtygrl1/partygirl2
npc_accmodel=f_acc_hair_pony_thick
npc_acctexture=f_acc_hair_pony/brown
sex=f
hitpoints=50
visual_radius=20
hearing_radius=20
npc_team=4
PickupSpawnType=False
disable_hostage=True

[NPC_NonCombat2]
cp=-1
NonCombatants=NPC Cowerer
class=combatant
name=bistander
ai=bistander.sx
ai_var_file=ai_nc_cowerer
aiType=6
bodytype=lowpoly
npc_geom=AverageGirl3
voiceset=fn2
npc_model=partygirl1
npc_texture=prtygrl1/averagegirl3
npc_accmodel=f_acc_hair_fernanda
npc_acctexture=f_acc_hair_fernanda/black
sex=f
hitpoints=50
visual_radius=20
hearing_radius=20
npc_team=4
PickupSpawnType=False
disable_hostage=True

[NPC_NonCombat3]
cp=-1
NonCombatants=NPC Cowerer
class=combatant
name=bistander
ai=bistander.sx
ai_var_file=ai_nc_cowerer
aiType=6
bodytype=lowpoly
npc_geom=ShortsTeeshirtGuy
voiceset=mn1
npc_model=shortsteeguy
npc_texture=shortsteeguy/shorts1
sex=m
hitpoints=50
visual_radius=20
hearing_radius=20
npc_team=4
PickupSpawnType=False
disable_hostage=False

[NPC_NonCombat4]
cp=-1
NonCombatants=NPC Cowerer
class=combatant
name=bistander
ai=bistander.sx
ai_var_file=ai_nc_watcher
aiType=1
bodytype=lowpoly
npc_geom=Generic Male4
voiceset=mn1
npc_model=skinnyguy
npc_texture=sknyguy/averageguy1
npc_accmodel=m_acc_ballcap
npc_acctexture=m_acc_ballcap/ltblue
sex=m
hitpoints=50
visual_radius=20
hearing_radius=20
npc_team=4
PickupSpawnType=False
disable_hostage=True

[NPC_NonCombat1]
cp=-1
NonCombatants=NPC Watcher
class=combatant
name=bistander
ai=bistander.sx
ai_var_file=ai_nc_watcher
aiType=1
bodytype=lowpoly
npc_geom=Rapper
voiceset=mn1
npc_model=stockyguy
npc_texture=stkyguy/rapper
sex=m
hitpoints=50
visual_radius=20
hearing_radius=20
npc_team=4
PickupSpawnType=False
disable_hostage=True

[Primary_ammo2]
cp=-1
NonCombatants=NPC Watcher
class=combatant
name=bistander
ai=bistander.sx
ai_var_file=ai_nc_watcher
aiType=1
bodytype=lowpoly
npc_geom=Rapper
voiceset=mn1
npc_model=stockyguy
npc_texture=stkyguy/rapper
sex=m
hitpoints=50
visual_radius=20
hearing_radius=20
npc_team=4
PickupSpawnType=False
disable_hostage=True

[Secondary_ammo2]
cp=-1
NonCombatants=NPC Cowerer
class=combatant
name=bistander
ai=bistander.sx
ai_var_file=ai_nc_watcher
aiType=1
bodytype=lowpoly
npc_geom=Generic Gangster 2
voiceset=mn1
npc_model=stockyguy
npc_texture=stkyguy/genericgangster2
sex=m
hitpoints=50
visual_radius=20
hearing_radius=20
npc_team=4
PickupSpawnType=False
disable_hostage=True

[Secondary_ammo3]
cp=-1
NonCombatants=NPC Cowerer
class=combatant
name=bistander
ai=bistander.sx
ai_var_file=ai_nc_handsup
aiType=4
bodytype=lowpoly
npc_geom=ShortsTeeshirtGuy
voiceset=mn1
npc_model=shortsteeguy
npc_texture=shortsteeguy/shorts1
sex=m
hitpoints=50
visual_radius=20
hearing_radius=20
npc_team=4
PickupSpawnType=False
disable_hostage=True

[AK48]
cp=2
NonCombatants=NPC Cowerer
class=combatant
name=bistander
ai=bistander.sx
ai_var_file=ai_nc_watcher
aiType=1
bodytype=lowpoly
npc_geom=Generic Gangster 3
voiceset=mn2
npc_model=stockyguy
npc_texture=stkyguy/genericgangster3
sex=m
hitpoints=50
visual_radius=20
hearing_radius=20
npc_team=4
PickupSpawnType=False
disable_hostage=True

[APT_WindowBars10]
cp=-1
class=compActor
name=vaultable
ai=vaultable.sx
trigger_only=False
specify_anim=True
animIndex=1

```
## Post #14
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2021-03-30T13:52:47+00:00
- Post Title: Is there a way to find out the format of this 3d model?

So this is just a custom single format and there is no chance to convert it to any 3ds?
