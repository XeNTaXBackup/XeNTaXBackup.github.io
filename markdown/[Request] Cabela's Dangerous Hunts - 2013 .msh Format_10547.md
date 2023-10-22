## Post #1
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2013-06-28T15:29:15+00:00
- Post Title: [Request] Cabela's Dangerous Hunts - 2013 .msh Format

the animals in this game look gorgeous and would be great to have
in a common 3D format such as .fbx (if there's even bone support possible).

there's a script for quickbms which can be found here.
source: [http://www.extractor.ru/ipb/index.php?showtopic=8588](http://www.extractor.ru/ipb/index.php?showtopic=8588)
to extract the conent of the game from the .CRF container file.

however, now that these files can be extracted, i'd like to know if there's
someone around here who might have a look into the mesh files.
for a possible import into 3DSMax, Blender, Noesis or C4D via script or plugin.
i know the most talented people are around here, so i try my luck.

here's a sample containing 4 animals from the game. (extracted files)
[https://www.dropbox.com/s/9bwjr81v7nu86fo/Sample.7z](https://www.dropbox.com/s/9bwjr81v7nu86fo/Sample.7z)

thanks for your time.
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-06-29T09:55:40+00:00
- Post Title: [Request] Cabela's Dangerous Hunts - 2013 .msh Format

Since there's PC version of the game, I guess you could get models with Ninja Ripper or GA. Did you try them? As for .msh format, it's structure almost understandable. Though I didn't find bones info there.
[Lion.jpg](https://xentaxbackup.github.io/file/6490_Lion.jpg)
## Post #3
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2013-06-29T14:56:38+00:00
- Post Title: [Request] Cabela's Dangerous Hunts - 2013 .msh Format

thanks for the quick reply.
well i tried Ninja-Ripper but it's spitting out the model with very wrong texture coordinates.
i tried a lot of varieties in 3DSMax with the UV Coordinates. none of the settings seems to work. 
the Ninja Ripper Noesis plugin also only gives wrong texture coordinates.
as for GA, i've only found a japanese version once. and my "eastern language skill" is ... non existent.
isn't the bone information for the Anubis model (for example) stored in the "papio_anubis_skeleton.msh"
or the "papio_anubis_skeleton.scn" instead of the "papio_anubis.msh"? just wondering.
so i was hoping someone could get the models with bones intact, since hours and hours of re-rig
every single model could be avoided that way.
looks promising so far, though. so you were able to get it into max? good work!

here's another Sample with skins included and their searchpath to the specific meshes
[https://www.dropbox.com/s/nfcqjp7pbrgsjgm/Sample_2.7z](https://www.dropbox.com/s/nfcqjp7pbrgsjgm/Sample_2.7z)
## Post #4
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-07-24T11:06:24+00:00
- Post Title: [Request] Cabela's Dangerous Hunts - 2013 .msh Format

First off the .msh files that have the name skeleton in them are for the xray vision models. The real bones are in the regular .msh files.
You can get a free Steam demo of this game here:
[http://store.steampowered.com/app/218860](http://store.steampowered.com/app/218860)
(Click download demo)
Here is a quickbms script I made to convert the animal .MSH files (not tested on humans):
[http://ps23dformat.wikispaces.com/file/ ... o3dsUV.bms](http://ps23dformat.wikispaces.com/file/view/DH2013MSHto3dsUV.bms)

```
log MEMORY_FILE2 0 0 ;
log MEMORY_FILE3 0 0 ;
log MEMORY_FILE4 0 0 ;
log MEMORY_FILE5 0 0 ;
log MEMORY_FILE6 0 0 ;
GoTo 0x1B 0 ;
Get numberofmeshes Short 0 ;


Get sizeoffile ASIZE 0 ;
Math sizeoffile -= 0x4 ;
GoTo sizeoffile 0 ;
Get tomeshindex Long 0 ;
GoTo tomeshindex 0 ;
GoTo 0x4 0 SEEK_CUR ;
Get jump Long 0 ;
GoTo tomeshindex 0 ;
GoTo 0x10 0 SEEK_CUR ;
GoTo jump 0 SEEK_CUR ;
GoTo 0x24 0 SEEK_CUR ;
SavePos meshindex 0 ;
For animesh = 1 To numberofmeshes ;
GoTo meshindex 0 ;
Get null Long 0 ;
Get null Long 0 ;
Get null Long 0 ;
Get meshbaseoffset Long 0 ;
Get typeofmesh Long 0 ;
Get null Long 0 ;
Get jump1 Long 0 ;
Get jump2 Long 0 ;
Get jump3 Long 0 ;
Get jump4 Long 0 ;
Get vertexdata Long 0 ;
Math otherdata = 0 ;
If typeofmesh = 0x9 ;
Get otherdata Long 0 ;
EndIF ;
Get facedata1 Long 0 ;
Get facedata2 Long 0 ;
If typeofmesh != 0x7 ;
Get null Long 0 ;
EndIF ;
SavePos meshindex 0 ;
Math vertexnumber = vertexdata ;
Math vertexnumber /= 32 ;
Math vertexstartbase = meshbaseoffset ;
Math vertexstartbase += jump1 ;
Math vertexstartbase += jump2 ;
Math vertexstartbase += jump3 ;
Math vertexstartbase += jump4 ;
Math uvstartbase = vertexstartbase ;
Math uvstartbase += 28 ;
Math facebase1 = vertexstartbase ;
Math facebase1 += vertexdata ;
Math facebase1 += otherdata ;
Math facebase2 = facebase1 ;
Math facebase2 += facedata1 ;
Math facenumber1 = facedata1 ;
Math facenumber1 /= 6 ;
Math facenumber2 = facedata2 ;
Math facenumber2 /= 6 ;











log MEMORY_FILE1 0 0 ;
log MEMORY_FILE2 0 0 ;
log MEMORY_FILE3 0 0 ;
log MEMORY_FILE5 0 0 ;
log MEMORY_FILE6 0 0 ;
Math Qprime = 0 ;
Math Qprimeprime = 0 ;
Math Qer = 0 ;
Math GG = 0 ;
Math YFYF = 0 ;


For vcx = 1 To vertexnumber ;
GoTo uvstartbase 0 ;
Get first Byte 0 ;
Get second Byte 0 ;
SavePos uvstartbase 0 ;
If second > 127 ;
Math second -= 256 ;
Endif ;
Math nb = second ;
Math nb *= 256 ;
Math nb += first ;
GoTo Qer MEMORY_FILE6 ;
Put nb Float MEMORY_FILE6 ;
SavePos Qer MEMORY_FILE6 ;


GoTo uvstartbase 0 ;
Get first Byte 0 ;
Get second Byte 0 ;
SavePos uvstartbase 0 ;
If second > 127 ;
Math second -= 256 ;
Endif ;
Math nb = second ;
Math nb *= 256 ;
Math nb += first ;
GoTo Qer MEMORY_FILE6 ;
Put nb Float MEMORY_FILE6 ;
SavePos Qer MEMORY_FILE6 ;
GoTo uvstartbase 0 ;
GoTo 28 0 SEEK_CUR ;
SavePos uvstartbase 0 ;
Next vcx ;

For V = 1 To vertexnumber ;
GoTo vertexstartbase 0 ;
Get Type1 Long 0 ;
Get Type2 Long 0 ;
Get Type3 Long 0 ;
GoTo 20 0 SEEK_CUR ;
SavePos vertexstartbase 0 ;
GoTo Qprime MEMORY_FILE2 ;
Put Type1 Long MEMORY_FILE2 ;
Put Type2 Long MEMORY_FILE2 ;
Put Type3 Long MEMORY_FILE2 ;
SavePos Qprime MEMORY_FILE2 ;
Next V ;




For FFF = 1 To facenumber1 ;
GoTo facebase1 0 ;
Get Type1 Short 0 ;
Get Type2 Short 0 ;
Get Type3 Short 0 ;
SavePos facebase1 0 ;
GoTo YFYF MEMORY_FILE3 ;
Put Type1 Short MEMORY_FILE3 ;
Put Type2 Short MEMORY_FILE3 ;
Put Type3 Short MEMORY_FILE3 ;
Put 0 Short MEMORY_FILE3 ;
SavePos YFYF MEMORY_FILE3 ;
Next FFF ;















Get Zw3 ASIZE MEMORY_FILE3 ;
Math Zf3 = Zw3 ;
Math Zf3 /= 8 ;
Get Zw2 ASIZE MEMORY_FILE2 ;
Math Zf2 = Zw2 ;
Math Zf2 /= 12 ;
Math facenumber = Zf3 ;
Math vertexnumber = Zf2 ;


Math lion = vertexnumber ;
Math lion *= 0x14 ;
Math liger = facenumber ;
Math liger *= 0xa ;
Math total3ds = lion ;
Math total3ds += liger ;
Math total3ds += 0x89 ;
Math total1 = total3ds ;
Math total1 -= 0x10 ;
Math total2 = total3ds ;
Math total2 -= 0x54 ;
Math total3 = total3ds ;
Math total3 -= 0x5E ;
Math vertexbase = 0x6c ;
Math WHEREvertex = vertexbase ;
Math tigervertex = vertexnumber ;
Math tigervertex *= 0xc ;
Math facebase1 = vertexbase ;
Math facebase1 += tigervertex ;
Math tigerface = facenumber ;
Math tigerface *= 0x8 ;
Math tigertigerface = facenumber ;
Math tigertigerface *= 0xa ;
Math facebase2 = facebase1 ;
Math facebase2 += 0x8 ;
Math WHEREface = facebase2 ;
Math facebase3 = facebase2 ;
Math facebase3 += tigerface ;
Math tigertigertigerface = facenumber ;
Math tigertigertigerface *= 0x2 ;
Math weretiger = tigertigerface ;
Math weretiger += 0x15 ;
Math tiger1 = tigervertex ;
Math tiger1 += 0x8 ;
Math tiger4 = tigertigertigerface ;
Math tiger4 += 0xd ;
Math WHEREfacecount = facebase3 ;
Math WHEREfacecount += 0xd ;
Math uvbase = WHEREfacecount ;
Math uvbase += tigertigertigerface ;
Math tigon = tigerface ;
Math tigon += 0x8 ;
Math WHEREuv = uvbase ;
Math WHEREuv += 0x8 ;
Math WHEREvertexq = WHEREvertex ;
Math WHEREuvq = WHEREuv ;
Math WHEREfaceq = WHEREface ;
Math WHEREfacecountq = WHEREfacecount ;
log MEMORY_FILE1 0 total3ds ;
Math vertexstart = 0 ;
Math facestart = 0 ;
Math uvstart = 0 ;


set M Byte 0x4d ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x4d ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xed ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x22 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x01 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x02 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x0a ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x03 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x3d ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x3d ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xdd ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x22 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x01 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xff ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xaf ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x3e ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xa0 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x0b ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x4e ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x6f ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x6e ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x65 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x10 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xa0 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x0f ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x11 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x09 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x20 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xa0 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x0f ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x11 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x09 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xcc ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xcc ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xcc ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x30 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xa0 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x0f ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x11 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x09 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xff ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xff ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xff ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x40 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x99 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x22 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x01 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x64 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x69 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x6x ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x8f ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x22 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x01 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x10 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x64 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x67 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x9d ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x08 ;
Put M Byte MEMORY_FILE1 ;
GoTo 0x2 MEMORY_FILE1 ;
Put total3ds Long MEMORY_FILE1 ;
GoTo 0x12 MEMORY_FILE1 ;
Put total1 Long MEMORY_FILE1 ;
GoTo 0x56 MEMORY_FILE1 ;
Put total2 Long MEMORY_FILE1 ;
GoTo 0x60 MEMORY_FILE1 ;
Put total3 Long MEMORY_FILE1 ;
GoTo 0x66 MEMORY_FILE1 ;
Put tiger1 Long MEMORY_FILE1 ;
GoTo 0x6A MEMORY_FILE1 ;
Put vertexnumber Short MEMORY_FILE1 ;
GoTo facebase1 MEMORY_FILE1 ;
set M Byte 0x20 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE1 ;
Put weretiger Long MEMORY_FILE1 ;
Put facenumber Short MEMORY_FILE1 ;
GoTo facebase3 MEMORY_FILE1 ;
set M Byte 0x30 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE1 ;
Put tiger4 Long MEMORY_FILE1 ;
set M Byte 0x4e ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x6f ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x6e ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x65 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x0 ;
Put M Byte MEMORY_FILE1 ;
Put facenumber Short MEMORY_FILE1 ;
GoTo uvbase MEMORY_FILE1 ;
set M Byte 0x40 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE1 ;
Put tigon Long MEMORY_FILE1 ;
Put vertexnumber Short MEMORY_FILE1 ;
For vwolf = 1 To vertexnumber ;
GoTo vertexstart MEMORY_FILE2 ;
Get Type1 Long MEMORY_FILE2 ;
Get Type2 Long MEMORY_FILE2 ;
Get Type3 Long MEMORY_FILE2 ;
SavePos vertexstart MEMORY_FILE2 ;
GoTo WHEREvertexq MEMORY_FILE1 ;
Put Type1 Long MEMORY_FILE1 ;
Put Type2 Long MEMORY_FILE1 ;
Put Type3 Long MEMORY_FILE1 ;
SavePos WHEREvertexq MEMORY_FILE1 ;
Next vwolf ;
For fwolf = 1 To facenumber ;
GoTo facestart MEMORY_FILE3 ;
Get Type1 short MEMORY_FILE3 ;
Get Type2 short MEMORY_FILE3 ;
Get Type3 short MEMORY_FILE3 ;
Get Type4 short MEMORY_FILE3 ;
SavePos facestart MEMORY_FILE3 ;
GoTo WHEREfaceq MEMORY_FILE1 ;
Put Type1 short MEMORY_FILE1 ;
Put Type2 short MEMORY_FILE1 ;
Put Type3 short MEMORY_FILE1 ;
Put Type4 short MEMORY_FILE1 ;
SavePos WHEREfaceq MEMORY_FILE1 ;
Next fwolf ;
For uvwolf = 1 To vertexnumber ;
GoTo uvstart MEMORY_FILE6 ;
Get Type1 Long MEMORY_FILE6 ;
Get Type2 Long MEMORY_FILE6 ;
SavePos uvstart MEMORY_FILE6 ;
GoTo WHEREuvq MEMORY_FILE1 ;
Put Type1 Long MEMORY_FILE1 ;
Put Type2 Long MEMORY_FILE1 ;
SavePos WHEREuvq MEMORY_FILE1 ;
Next uvwolf ;
For fcwolf = 0 < facenumber ;
GoTo WHEREfacecountq MEMORY_FILE1 ;
Put fcwolf short MEMORY_FILE1 ;
SavePos WHEREfacecountq MEMORY_FILE1 ;
Next fcwolf ;
Get purpledragon ASIZE MEMORY_FILE1 ;
Get name FILENAME 0 ;
string name += . ;
string name += animesh ;
string name += .3ds ;
Log name 0 purpledragon MEMORY_FILE1 ;
Next animesh ;
```

[http://ps23dformat.wikispaces.com/file/ ... uffalo.jpg](http://ps23dformat.wikispaces.com/file/view/DH2013Buffalo.jpg)
YOU MUST RESCALE THE UVS DOWN ALOT (there are so big you will not see them)
Use the script as follows, making sure you ONLY use the version of quickbms found here (versions on other sites are too old):
[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)

When you use the script you MUST use it with the microsoft windows command prompt IT WILL NOT work by double clicking quickbms.exe. Also the w in -w must be lowercase! No Asian characters or spaces in the path names. Place stuff in the appropriate folders.
Use the script as follows on one command.
C:\dh2013\quickbms.exe -w C:\dh2013\DH2013MSHto3dsUV.bms C:\dh2013\wolfboss.msh C:\dh2013\output
## Post #5
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2013-07-24T16:22:29+00:00
- Post Title: [Request] Cabela's Dangerous Hunts - 2013 .msh Format

> [Request] Cabela's Dangerous Hunts - 2013 .msh Format
>
> the animals in this game look gorgeous
>
> 
>
> FurryFan
[](http://www.hostingpics.net/viewer.php?id=748030original.jpg)
## Post #6
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2013-07-25T19:41:22+00:00
- Post Title: [Request] Cabela's Dangerous Hunts - 2013 .msh Format

> Reply from FurryFan
>
> *answer*

thank you so much! i will have a look at this. should be very useful!
## Post #7
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-08-08T13:15:22+00:00
- Post Title: [Request] Cabela's Dangerous Hunts - 2013 .msh Format

> Reply from TheMask85
>
> FurryFan wrote:*answer*

thank you so much! i will have a look at this. should be very useful!
Here are some scripts for the WII version of this game:
Use this to extract the CRS files (The WII version uses the .CRS extension)
[http://ps23dformat.wikispaces.com/file/ ... 3andHE.bms](http://ps23dformat.wikispaces.com/file/view/CabelasDH2013andHE.bms)
Then use this script to convert the WMH files into .3ds files with UV coords:
[http://ps23dformat.wikispaces.com/file/ ... o3dsUV.bms](http://ps23dformat.wikispaces.com/file/view/DH2013WIIwmhTo3dsUV.bms)
## Post #8
- Username: joqqy
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Feb 21, 2012 7:40 pm
- Post datetime: 2013-10-20T15:27:17+00:00
- Post Title: [Request] Cabela's Dangerous Hunts - 2013 .msh Format

I have added a quick fix for the big UV problem in the PC version.

After you import the model into 3DS Max, select the object, chose the preset and press the button and the UVs will be properly resized and moved.
[http://www.scriptspot.com/3ds-max/scrip ... dels-tools](http://www.scriptspot.com/3ds-max/scripts/game-models-tools)


Requires 3D Studio Max 2012 or higher
## Post #9
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-11-20T23:27:33+00:00
- Post Title: [Request] Cabela's Dangerous Hunts - 2013 .msh Format

Nice work. By the way the textures are all .DDS. Also for anyone that wants to make mods:
Extract ALL of the .CRF files into the same directory as dh_2013_demo.exe (or the .exe file from the full game).
Then delete archive_list.rmf
The game will then load the extracted files, which you can then mod. I have been changing the .AI, and switching animals. I want to eventually switch the player model with an animal model, and switch the animal models with hunter models. I got the AI switched so that the player uses animal AI.
I want to also enable the debug menu, but it seems to have been removed.
