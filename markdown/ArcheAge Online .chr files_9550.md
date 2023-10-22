## Post #1
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-08-26T12:49:15+00:00
- Post Title: ArcheAge Online .chr files

Hi, can someone help me identify this  format.

Samples [here](https://dl.dropbox.com/u/62180803/captain001.rar)
## Post #2
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-08-27T17:09:26+00:00
- Post Title: ArcheAge Online .chr files

This game uses the crytek engine.
I made a QuickBMS script, that will convert the .chr files into .3ds files.
You need to run the script using the commandprompt window in Windows (such as under start under programs under accessories then commandprompt)
First download QuickBMS for free:
[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
Then unzip it to a place where there is no spaces in the path such as to D:/black/QuickBMS
(not D:/program files/QuickBMS).
Then put the script:
[http://ps23dformat.wikispaces.com/file/ ... Rto3ds.bms](http://ps23dformat.wikispaces.com/file/view/ArcheAgeCHRto3ds.bms)
in the QuickBMS folder
along with a chr file from archeage online, also in the quick bms file

Then if I wanted to convert nu_f_pt_captain001.chr into a 3ds file named nu_f_bo_captain001.3ds
I would put the following in commandprompt on the same command (the -w w must be lowercase):

```
D:\black\quickbms\quickbms.exe -w D:\black\quickbms\ArcheAgeCHRto3ds.BMS D:\black\quickbms\nu_f_pt_captain001.chr D:\black\quickbms
```

Then it will ask you what other file you want to open. Simply type in what you want the .3ds file to be named, so type in say nu_f_pt_captain001.3ds
do not type in the path name for that one, just what you want the name to be. Then the script will run for less then a second, and in you quickbms folder there would be a new file called nu_f_pt_captain001.3ds that has the same model, from the game but in .3ds format. You can open up .3ds files in almost any type of 3d program, for example blender (by using the import menu), or 3d studio max, or wavefront or maya, or cinema4D, and many others. Blender 3d is free, and I think 3D studio max is free for current college students with a .edu email address. Also for ArcheAge online, each mesh will be in a box, just delete outside box to see the model. Here is an example of a model, in wireframe:

Here is the script, making note that entering a file name for a file that does not exist is a bug the way I entered it, it would not work if you used the regular quickbms by double clicking it would say file not valid it only works in the commandline. Making another note, that the "put" function only works by design by doing the commandline (will not work by double clicking quickbms.exe):

```
open FDSE ? 1 ;
findloc OFFSET string "\x16\x00\xCC\xCC\x00\x08\x00\x00" ;
GoTo OFFSET 0 ;
GoTo 8 0 SEEK_CUR ;
Get ToVertexes Long 0 ;
GoTo ToVertexes 0 ;
GoTo 24 0 SEEK_CUR ;
Get VertexNumber Long 0 ;
GoTo 12 0 SEEK_CUR ;
SavePos VertexStart 0 ;
GoTo 0 0 ;
findloc OFFSET string "\x16\x00\xCC\xCC\x00\x08\x00\x00" ;
GoTo OFFSET 0 ;
GoTo 1 0 SEEK_CUR ;
findloc OFFSET string "\x16\x00\xCC\xCC\x00\x08\x00\x00" ;
GoTo OFFSET 0 ;
GoTo 1 0 SEEK_CUR ;
findloc OFFSET string "\x16\x00\xCC\xCC\x00\x08\x00\x00" ;
GoTo OFFSET 0 ;
GoTo 1 0 SEEK_CUR ;
findloc OFFSET string "\x16\x00\xCC\xCC\x00\x08\x00\x00" ;
GoTo OFFSET 0 ;
GoTo 8 0 SEEK_CUR ;
Get ToFaces Long 0 ;
GoTo ToFaces 0 ;
GoTo 24 0 SEEK_CUR ;
Get FaceNumber Long 0 ;
Math FaceNumber *= 2 ;
Math FaceNumber /= 6 ;
GoTo 12 0 SEEK_CUR ;
SavePos FaceStart 0 ;
set QQQ long 45 ;
set GoldGold short 00 ;
GoTo VertexStart 0 ;
SavePos Base 0 ;
GoTo FaceStart 0 ;
SavePos FaceBase 0 ;
Math Snake = VertexNumber ;
Math Snake *= 12 ;
Math Dragon = FaceNumber ;
Math Dragon *= 8 ;
Math Sum = Dragon ;
Math Sum += Snake ;
Math QQQ = 60 ;
Math QQQ += Snake ;
Math QQ = 52 ;
For Vertex = 0 < VertexNumber ;
GoTo Base 0 ;
Get Type1 Long 0 ;
Get Type2 Long 0 ;
Get Type3 Long 0 ;
SavePos Base 0 ;
GoTo QQ 1 ;
Put Type1 Long 1 ;
Put Type2 Long 1 ;
Put Type3 Long 1 ;
SavePos QQ 1 ;
Next Vertex ;
For Face = 0 < FaceNumber ;
GoTo FaceBase 0 ;
Get Type1 Short 0 ;
Get Type2 Short 0 ;
Get Type3 Short 0 ;
SavePos FaceBase 0 ;
GoTo QQQ 1 ;
Put Type1 Short 1 ;
Put Type2 Short 1 ;
Put Type3 Short 1 ;
Put GoldGold Short 1 ;
SavePos QQQ 1 ;
Next Face ;
GoTo 0 1 ;
set M Byte 0x4D ;
Put M Byte 1 ;
set M Byte 0x4D ;
Put M Byte 1 ;
Math M = Sum ;
Math M += 60 ;
Put M Long 1 ;
set M Byte 0x02 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x0A ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x03 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x3D ;
Put M Byte 1 ;
set M Byte 0x3D ;
Put M Byte 1 ;
Math M = Sum 
Math M += 44 ;
Put M Long 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x40 ;
Put M Byte 1 ;
Math M = Sum 
Math M += 38 ;
Put M Long 1 ;
set M Byte 0x64 ;
Put M Byte 1 ;
set M Byte 0x72 ;
Put M Byte 1 ;
set M Byte 0x61 ;
Put M Byte 1 ;
set M Byte 0x67 ;
Put M Byte 1 ;
set M Byte 0x6F ;
Put M Byte 1 ;
set M Byte 0x6E ;
Put M Byte 1 ;
set M Byte 0x6A ;
Put M Byte 1 ;
set M Byte 0x61 ;
Put M Byte 1 ;
set M Byte 0x6E ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x41 ;
Put M Byte 1 ;
Math M = Sum 
Math M += 22 ;
Put M Long 1 ;
Set M Byte 0x10 ;
Put M Byte 1 ;
set M Byte 0x41 ;
Put M Byte 1 ;
Math M = Snake ;
Math M += 8 ;
Put M Long 1 ;
Math M = VertexNumber ;
Put M Short 1 ;
Math JumpJump = Snake ;
Math JumpJump += 52 ;
GoTo JumpJump 1 ;
set M Byte 0x20 ;
Put M Byte 1 ;
set M Byte 0x41 ;
Put M Byte 1 ;
Math M = Dragon ;
Math M += 8 ;
Put M Long 1 ;
Math M = FaceNumber ;
Put M Short 1 ;
```
## Post #3
- Username: anotherrandomperson
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 29, 2014 4:55 am
- Post datetime: 2014-10-28T21:00:08+00:00
- Post Title: ArcheAge Online .chr files

This is great, though I'd love to have some way to just convert all .chr files in a folder automatically. This would allow me to search for the meshes I need a lot faster than having to manually convert every single file I'd like to check. Is this possible at all? And if so, will you do it? 

Cheers,


Nick

EDIT: Sorry for the necro post, I didn't notice when this was posted...o_o
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-10-29T07:33:02+00:00
- Post Title: ArcheAge Online .chr files

Did you try the 3D Object Converter's batch converter module?
## Post #5
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2018-10-15T16:37:16+00:00
- Post Title: ArcheAge Online .chr files

Model viewer for ArcheAge ? 

[http://shader.tistory.com/129](http://shader.tistory.com/129)
