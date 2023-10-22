## Post #1
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2012-11-30T08:10:11+00:00
- Post Title: Resident Evil: Outbreak room meshes (.nbd)

I'm trying to extract the room meshes from RE Outbreak using NBDX-win for a Source-related project I'm working on. The meshes export fine, but each piece or element of the room is collapsed into the origin of the mesh, so my imported meshes look like this:


I'm wondering if anyone with knowledge of this format can take a look and see how these room nbd files differ from regular character nbd files and figure out how to get them to export with the pieces all in the right place.

Also, for a related question, extracting the .sld files that contain the textures for each room results in a miscolored texture that I can't figure out how to fix. I was hoping someone might know how to fix the texture so it has proper colors.

Examples here because the max attachment size is so small now that it's completely useless: [http://www.mediafire.com/?a8l0qeir5d5yzzh](http://www.mediafire.com/?a8l0qeir5d5yzzh)
## Post #2
- Username: DrMask
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 10, 2012 1:14 pm
- Post datetime: 2012-12-02T02:34:14+00:00
- Post Title: Resident Evil: Outbreak room meshes (.nbd)

What tool are you using to extract the .sld files ?
also you need this script to extract the model from .nbd Archive the model's are .amo .

#PS2 Resident Evil Outbreak 1&2
#quickbms script
#By chrrox
get name2 basename
goto 0x4
get files long
math files / 16
goto 0x0
for i = 0 < files
getdstring type 4
get offset long
get size long
get unk01 long
set name name2
string name + .
string name + type
if size != 0
log name offset size
else
endif
next i
## Post #3
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2012-12-02T09:42:36+00:00
- Post Title: Resident Evil: Outbreak room meshes (.nbd)

A tool called sld_unpack that came with nbdx-win. It dumps .tm2 textures, but the colors are messed up (maybe because the room textures differ from char textures somehow)

nbdx already converts the amo it unpacks from the nbd into obj, it seems to not know some file types though, it says 'unrecognized file type' during the export, so I'm assuming it doesn't support some of the files contained within, which might be key to getting the models out unharmed.

Here's the tools for unpacking the sld files anyways. [http://www.mediafire.com/?bl88c5su5w33m1q](http://www.mediafire.com/?bl88c5su5w33m1q)

Also, if I get the .amo out of the nbd, what do I use to import it into Max?
## Post #4
- Username: DrMask
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 10, 2012 1:14 pm
- Post datetime: 2012-12-02T16:32:53+00:00
- Post Title: Resident Evil: Outbreak room meshes (.nbd)

Geting the .amo's in 3ds max your going to have to create a max script or convert .amo to .obj .  
How did you get sld_unpack to unpack the .sld's, didn't work at all for
me what did you do to get it working ?
## Post #5
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2012-12-03T07:46:57+00:00
- Post Title: Resident Evil: Outbreak room meshes (.nbd)

I lack the expertise to reverse engineer the format, much less code a program to import it, which is why I'm posting here. I think I pm'd you about the script you wrote for getting .amo into Noesis, did you get it? nbdx imports the room nbd's into obj, but messes it up in the process by smashing every piece together into the model's origin.

sld_unpack is a command line program, but unlike nbdx you can't just drag the file onto it, so run it through the command prompt (Start Menu > Search Files or Folders > type 'cmd' > hit enter > use cd command to change directory to where you have sld_unpack unzipped)

Then you type 'sld_unpack filename.sld nameyouwanttosavetextureas.tm2', and then it dumps the tm2, which you can convert into png or something with Sagethumbs or Xnview. But as I said, the colors are messed up.
## Post #6
- Username: DrMask
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 10, 2012 1:14 pm
- Post datetime: 2012-12-03T17:10:13+00:00
- Post Title: Resident Evil: Outbreak room meshes (.nbd)

Sorry dude its fake I didn't create a script for Noesis or max.
## Post #7
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2012-12-04T07:26:38+00:00
- Post Title: Resident Evil: Outbreak room meshes (.nbd)

Who did then?

And why would you do something like that?
## Post #8
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-01-03T19:45:46+00:00
- Post Title: Resident Evil: Outbreak room meshes (.nbd)

[quote="TehDave"]Who did then?
Here is a quickbms script that will convert each of the individual meshes in a .amo file keeping the UVs.
[http://ps23dformat.wikispaces.com/file/ ... o3dsUV.bms](http://ps23dformat.wikispaces.com/file/view/ResidentEvilOutbreak2AMOto3dsUV.bms)
Use the script with the free program called quickbms [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
The script must be run using the Microsoft Windows Command Prompt (it will not work just by double clicking quickbms.exe)
Use the script like the following (the w must be lowercase):

```
I:\1\quickbms.exe -w I:\1\outbreak.bms I:\1\test.amo I:\1
```

The first is the path to quickbms.exe
The second is the path to the script
The third is the path to the amo
The fourth is the path to the output
Change according to where things are on your computer, also make sure there are no spaces to the paths (Program Files will not work, but programfiles will), and no Asian characters in the paths.
Here is the script:

```
log MEMORY_FILE2 0 0 ;
GoTo 0x20 0 ;
Get setnumber Long 0 ;
GoTo 0x28 0 ;
SavePos startgold 0 ;
For s = 1 To setnumber ;
log MEMORY_FILE1 0 0 ;
log MEMORY_FILE2 0 0 ;
GoTo startgold 0 ;
SavePos blue 0 ;
GoTo startgold 0 ;
GoTo 0x8 0 SEEK_CUR ;
Get tjump Long 0 ;
GoTo startgold 0 ;
GoTo tjump 0 SEEK_CUR ;
SavePos startgold 0 ;
GoTo blue 0 ;
GoTo 0x1C 0 SEEK_CUR ;
Get trinumber Long 0 ;
Get qjump Long 0 ;
GoTo blue 0 ;
GoTo 0x18 0 SEEK_CUR ;
GoTo qjump 0 SEEK_CUR ;
Get testq Long 0 ;
If testq = 262144 ;
Math red = 2 ;
Else ;
Math red = 1 ;
EndIF ;
GoTo blue 0 ;
GoTo 0x18 0 SEEK_CUR ;
SavePos blue 0 ;
For blueblue = 1 To red ;
GoTo blue 0 ;
SavePos green 0 ;
GoTo 0x8 0 SEEK_CUR ;
Get jump Long 0 ;
GoTo blue 0 ;
GoTo jump 0 SEEK_CUR ;
SavePos blue 0 ;
GoTo green 0 ;
GoTo 0x4 0 SEEK_CUR ;
Get trinumber Long 0 ;
GoTo 0x4 0 SEEK_CUR ;
SavePos green 0 ;
For mul = 1 To trinumber ;
GoTo green 0 ;
Get pink Long 0 ;
SavePos grass 0 ;
Math pink -= 2 ;
For deer = 1 To pink ;
GoTo grass 0 ;
Get type1 Long 0 ;
SavePos grass 0 ;
Get type2 Long 0 ;
Get type3 Long 0 ;
Put type1 Short MEMORY_FILE2 ;
Put type2 Short MEMORY_FILE2 ;
Put type3 Short MEMORY_FILE2 ;
Put 0 Short MEMORY_FILE2 ;
Put type1 Short MEMORY_FILE2 ;
Put type3 Short MEMORY_FILE2 ;
Put type2 Short MEMORY_FILE2 ;
Put 0 Short MEMORY_FILE2 ;
Next deer ;
Math pink += 2 ;
Math pink *= 4 ;
Math pink += 4 ;
GoTo green 0 ;
GoTo pink 0 SEEK_CUR ;
SavePos green 0 ;
Next mul ;
Next blueblue ;
GoTo blue 0 ;
GoTo 0x8 0 SEEK_CUR ;
Get jump Long 0 ;
GoTo blue 0 ;
GoTo jump 0 SEEK_CUR ;
SavePos blue 0 ;
GoTo blue 0 ;
GoTo 0x8 0 SEEK_CUR ;
Get jump Long 0 ;
GoTo blue 0 ;
GoTo jump 0 SEEK_CUR ;
SavePos blue 0 ;
GoTo 0x4 0 SEEK_CUR ;
Get vertexnumber Long 0 ;
Get jump Long 0 ;
SavePos vertexstart 0 ;
GoTo blue 0 ;
GoTo jump 0 SEEK_CUR ;
SavePos blue 0 ;
GoTo blue 0 ;
GoTo 0x8 0 SEEK_CUR ;
Get jump Long 0 ;
GoTo blue 0 ;
GoTo jump 0 SEEK_CUR ;
SavePos blue 0 ;
GoTo 0xC 0 SEEK_CUR ;
SavePos uvstart 0 ;
log MEMORY_FILE1 0 0 ;
Get slsl ASIZE MEMORY_FILE2 ;
Math slsl /= 8 ;
Math facenumber = slsl ;
Math facestart = 0 ;
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
Log MEMORY_FILE1 0 total3ds ;
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
GoTo vertexstart 0 ;
Get Type1 Long 0 ;
Get Type2 Long 0 ;
Get Type3 Long 0 ;
SavePos vertexstart 0 ;
GoTo WHEREvertexq MEMORY_FILE1 ;
Put Type1 Long MEMORY_FILE1 ;
Put Type2 Long MEMORY_FILE1 ;
Put Type3 Long MEMORY_FILE1 ;
SavePos WHEREvertexq MEMORY_FILE1 ;
Next vwolf ;
For fwolf = 1 To facenumber ;
GoTo facestart MEMORY_FILE2 ;
Get Type1 short MEMORY_FILE2 ;
Get Type2 short MEMORY_FILE2 ;
Get Type3 short MEMORY_FILE2 ;
Get Type4 short MEMORY_FILE2 ;
SavePos facestart MEMORY_FILE2 ;
GoTo WHEREfaceq MEMORY_FILE1 ;
Put Type1 short MEMORY_FILE1 ;
Put Type2 short MEMORY_FILE1 ;
Put Type3 short MEMORY_FILE1 ;
Put Type4 short MEMORY_FILE1 ;
SavePos WHEREfaceq MEMORY_FILE1 ;
Next fwolf ;
For uvwolf = 1 To vertexnumber ;
GoTo uvstart 0 ;
Get Type1 Long 0 ;
Get Type2 Long 0 ;
SavePos uvstart 0 ;
GoTo WHEREuvq MEMORY_FILE1 ;
Put Type1 Long MEMORY_FILE1 ;
Put Type2 Long MEMORY_FILE1 ;
SavePos WHEREuvq MEMORY_FILE1 ;
Next uvwolf ;
Math bluegreen = facenumber ;
Math bluegreen -= 1 ;
For fcwolf = 0 To bluegreen ;
GoTo WHEREfacecountq MEMORY_FILE1 ;
Put fcwolf short MEMORY_FILE1 ;
SavePos WHEREfacecountq MEMORY_FILE1 ;
Next fcwolf ;
Get purpledragon ASIZE MEMORY_FILE1 ;
Math name = s ;
string name += .3ds ;
Log name 0 purpledragon MEMORY_FILE1 ;
Next s ;
```

Let me know if things do or do not work.
## Post #9
- Username: DrMask
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 10, 2012 1:14 pm
- Post datetime: 2013-01-05T00:12:20+00:00
- Post Title: Resident Evil: Outbreak room meshes (.nbd)

Works fine thanks.
## Post #10
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2013-01-07T11:33:31+00:00
- Post Title: Resident Evil: Outbreak room meshes (.nbd)

> Reply from TehDave
>
> A tool called sld_unpack that came with nbdx-win. It dumps .tm2 textures, but the colors are messed up (maybe because the room textures differ from char textures somehow)

nbdx already converts the amo it unpacks from the nbd into obj, it seems to not know some file types though, it says 'unrecognized file type' during the export, so I'm assuming it doesn't support some of the files contained within, which might be key to getting the models out unharmed.

Here's the tools for unpacking the sld files anyways. http://www.mediafire.com/?bl88c5su5w33m1q

Also, if I get the .amo out of the nbd, what do I use to import it into Max?

unsupported files are the AHI files that contain the scene bones /skeleton, in order to make the room look correct you need to load the ahi file and the bone id in each mesh block then transform/rotate the mesh according to the bone , same trick is used in re4 ps2 and pc version and maybe some other re games (not used in re5 or re6)
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-13T16:09:54+00:00
- Post Title: Resident Evil: Outbreak room meshes (.nbd)

Years later (as a designated member of the riders-of-dead-horses-club)  I feel obliged to contribute some room correction feature; it may be a little bit confusing, but works (for room r0150100.AMO at least), better than copying 115 positions by hand, imho:


PS2 Resident Evil Outbreak
--------------------------

- extract .AMO and .AHI from NBD archive:
[viewtopic.php?f=16&t=9923&p=81422&hilit ... eak#p81422](http://forum.xentax.com/viewtopic.php?f=16&t=9923&p=81422&hilit=PS2+Resident+Evil+Outbreak#p81422)

- extract 3ds from .AMO
[viewtopic.php?f=16&t=9923&p=82047&hilit ... bms#p82047](http://forum.xentax.com/viewtopic.php?f=16&t=9923&p=82047&hilit=ResidentEvilOutbreak2AMOto3dsUV.bms#p82047)

- create smd from .AHI with The Dude's Noesis script from the starting post here:
[viewtopic.php?f=16&t=18333](http://forum.xentax.com/viewtopic.php?f=16&t=18333)

- drag 'n drop smd to chg_bin.exe, you'll get three txt files.

- The positions have to be copied (overwrite mode) to the position arrays
  in the script move_0150100.py

  I'll show the steps for vertOffs_x_out.txt:
  cut 0.000000, 0.000000, 0.000000, from the beginning, (delete the last comma) 
  and paste it to the end behind last value, -126.010063,

  Select the whole line and overwrite the contents of the brackets of
  xpos = [...]
  in the script move_0150100.py

  Repeat this for vertOffs_y_out.txt, ypos = [...]
  and for vertOffs_z_out.txt, zpos = [...]

  ### VERY important: before you can use the following mentioned script
  you have to adapt the path to your 3ds files in it:  
  models_path = os.path.join('C:\\', 'REO\\r0150100')

- Open load_several_3ds_blender2.69.py in a blender text window
  and press Alt-p -> meshes are being imported (clumped)

- delete the script (ctrl-A, delete-key) then
  copy contents of modified move_0150100.py into that window

  Alt-p -> room should be displayed correctly


 chg_bin.zip
(12.73 KiB) Downloaded 36 times



You may view the result here:
[viewtopic.php?f=16&t=18333&p=142219&hil ... on#p142219](http://forum.xentax.com/viewtopic.php?f=16&t=18333&p=142219&hilit=+description#p142219)
