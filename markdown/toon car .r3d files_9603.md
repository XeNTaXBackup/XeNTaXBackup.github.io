## Post #1
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-09-05T14:46:28+00:00
- Post Title: toon car .r3d files

hello all
how can i find vertices and faces in .r3d files from toon car game?
i was looking for but did not find
new link to demo:
[http://toon-car-demo.en.softonic.com/](http://toon-car-demo.en.softonic.com/)
## Post #2
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-09-13T23:25:23+00:00
- Post Title: toon car .r3d files

> Reply from Bogus
>
> hello all
how can i find vertices and faces in .r3d files from toon car game?
i was looking for but did not find
new link to demo:
http://toon-car-demo.en.softonic.com/
Use the following Quickbms script (get quickbms for free here: [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm))
Here is the script:
[http://ps23dformat.wikispaces.com/file/ ... hto3ds.bms](http://ps23dformat.wikispaces.com/file/view/tooncarR3Dmeshto3ds.bms)
To use you must put the script and the .r3d files you want to convert in the quickbms folder
To run the script use the windows command prompt (under the start menu), and type in the path to quickbms.exe followed by -w
followed by the path to the script, followed by the path to the .r3d file followed by the path to the quickbms folder.
the w in -w must be lowercase
For example if your computer was set up like mine you would type in:

```
c:\quickbms\quickbms.exe -w c:\quickbms\tooncarr3dmeshto3ds.bms c:\quickbms\Jaguar.r3d c:\quickbms\
```

The script will convert most of the models inside a .r3d file into a separate .3ds file. I got to update the script so that in submeshes that contain 2 sections, both sections get converted, but right now only the first section in each submesh gets converted. Also I need to add in UV's and maybe figure out the file header in .r3d files so I can get past the textures, because right now I just use a hardcoded address that appears to be constant for all of the car r3d files but would not work on r3d files if textures were different sizes (say level terrain .r3d files).

```
GoTo 0x2006e0 0 ;
Get bones Long 0 ;
Math bones *= 0x60 ;
Math Qprime = 0 ;
Math Qprimeprime = 0 ;
GoTo bones 0 SEEK_CUR ;
SavePos gold 0 ;
Math silversilversilver = gold ;
Math ccount = 0 ;
For htp = 0 < SIZE ;
Math Qprime = 0 ;
Math Qprimeprime = 0 ;
Math ccount += 1 ;
log MEMORY_FILE 0 0 ;
log MEMORY_FILE2 0 0 ;
log MEMORY_FILE3 0 0 ;
GoTo silversilversilver 0 ;
Math gold = silversilversilver ;
GoTo 0x14 0 SEEK_CUR ;
Get meshnumber Long 0 ;
If meshnumber > 2 ;
Cleanexit ;
EndIF ;
If meshnumber = 0 ;
Cleanexit ;
EndIF ;
If meshnumber = 2 ;
GoTo gold 0 ;
GoTo 0x70 0 SEEK_CUR ;
Get mesh2vertex Long 0 ;
Get mesh1vertex Long 0 ;
Get mesh2face Long 0 ;
Get mesh1face Long 0 ;
Math vertextotal = mesh2vertex ;
Math vertextotal += mesh1vertex ;
Math facetotal = mesh2face ;
Math facetotal += mesh1face ;
GoTo gold 0 ;
GoTo 0x88 0 SEEK_CUR ;
SavePos goldgold 0 ;
SavePos silversilver 0 ;
EndIF ;
If meshnumber = 1 ;
GoTo gold 0 ;
GoTo 0x54 0 SEEK_CUR ;
Get mesh1vertex Long 0 ;
GoTo gold 0 ;
GoTo 0x5C 0 SEEK_CUR ;
Get mesh1face Long 0 ;
Math vertextotal = mesh1vertex ;
Math facetotal = mesh1face ;
GoTo gold 0 ;
GoTo 0x6C 0 SEEK_CUR ;
SavePos goldgold 0 ;
SavePos silversilver 0 ;
EndIF ;
For jjj = 1 To mesh1vertex ;
GoTo silversilver 0 ;
Get Type1 Long 0 ;
Get Type2 Long 0 ;
Get Type3 Long 0 ;
GoTo 0x24 0 SEEK_CUR ;
SavePos silversilver 0 ;
GoTo Qprime MEMORY_FILE2 ;
Put Type1 Long MEMORY_FILE2 ;
Put Type2 Long MEMORY_FILE2 ;
Put Type3 Long MEMORY_FILE2 ;
SavePos Qprime MEMORY_FILE2 ;
Next jjj ;
GoTo goldgold 0 ;
Math jump = vertextotal ;
Math jump *= 0x30 ;
GoTo jump 0 SEEK_CUR ;
SavePos goldgoldgold 0 ;
SavePos silversilversilver 0 ;
For tyty = 1 To mesh1face ;
GoTo silversilversilver 0 ;
Get Type1 Short 0 ;
Get Type2 Short 0 ;
Get Type3 Short 0 ;
SavePos silversilversilver 0 ;
GoTo Qprimeprime MEMORY_FILE3 ;
Put Type1 short MEMORY_FILE3 ;
Put Type2 short MEMORY_FILE3 ;
Put Type3 short MEMORY_FILE3 ;
Put 0 Short MEMORY_FILE3 ;
SavePos Qprimeprime MEMORY_FILE3 ;
Next tyty ;
If meshnumber = 2 ;
Math silversilversilver += mesh2face ;
Math silversilversilver += mesh2face ;
Math silversilversilver += mesh2face ;
Math silversilversilver += mesh2face ;
Math silversilversilver += mesh2face ;
Math silversilversilver += mesh2face ;
EndIF ;
Get Zw3 ASIZE MEMORY_FILE3 ;
Math Zf3 = Zw3 ;
Math Zf3 /= 8 ;
Get Zw2 ASIZE MEMORY_FILE2 ;
Math Zf2 = Zw2 ;
Math Zf2 /= 12 ;
Math FaceNumber = Zf3 ;
Math VertexNumber = Zf2 ;
Math Snake = VertexNumber ;
Math Snake *= 12 ;
Math Dragon = FaceNumber ;
Math Dragon *= 8 ;
Math Sum = Dragon ;
Math Sum += Snake ;
Math SumSum = Sum ;
Math SumSum += 60 ;
Math QQQ = 60 ;
Math QQQ += Snake ;
Math QQ = 52 ;
Math qaz = 0 ;
Math wsx = 0 ;
log MEMORY_FILE4 0 SumSum ;
For Vertex = 0 < Zw2 ;
GoTo qaz MEMORY_FILE2 ;
Get D byte MEMORY_FILE2 ;
SavePos qaz MEMORY_FILE2 ;
GoTo QQ MEMORY_FILE4 ;
Put D Byte MEMORY_FILE4 ;
SavePos QQ MEMORY_FILE4 ;
Next Vertex ;
For Face = 0 < Zw3 ;
GoTo wsx MEMORY_FILE3 ;
Get D byte MEMORY_FILE3 ;
SavePos wsx MEMORY_FILE3 ;
GoTo QQQ MEMORY_FILE4 ;
Put D Byte MEMORY_FILE4 ;
SavePos QQQ MEMORY_FILE4 ;
Next Face ;
GoTo 0 MEMORY_FILE4 ;
set M Byte 0x4D ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x4D ;
Put M Byte MEMORY_FILE4 ;
Math M = Sum ;
Math M += 60 ;
Put M Long MEMORY_FILE4 ;
set M Byte 0x02 ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x0A ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x03 ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x3D ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x3D ;
Put M Byte MEMORY_FILE4 ;
Math M = Sum 
Math M += 44 ;
Put M Long MEMORY_FILE4 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x40 ;
Put M Byte MEMORY_FILE4 ;
Math M = Sum 
Math M += 38 ;
Put M Long MEMORY_FILE4 ;
set M Byte 0x64 ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x72 ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x61 ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x67 ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x6F ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x6E ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x6A ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x61 ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x6E ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE4 ;
Math M = Sum 
Math M += 22 ;
Put M Long MEMORY_FILE4 ;
Set M Byte 0x10 ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE4 ;
Math M = Snake ;
Math M += 8 ;
Put M Long MEMORY_FILE4 ;
Math M = VertexNumber ;
Put M Short MEMORY_FILE4 ;
Math JumpJump = Snake ;
Math JumpJump += 52 ;
GoTo JumpJump MEMORY_FILE4 ;
set M Byte 0x20 ;
Put M Byte MEMORY_FILE4 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE4 ;
Math M = FaceNumber ;
Math M *= 8 ;
Math M += 8 ;
Put M Long MEMORY_FILE4 ;
Math M = FaceNumber ;
Put M Short MEMORY_FILE4 ;
Get SIZE4m ASIZE MEMORY_FILE4 ;
Math cccount = ccount ;
string cccount += .3ds ;
Log cccount 0 SIZE4m MEMORY_FILE4 ;
Next htp ;
```
## Post #3
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-09-14T05:39:21+00:00
- Post Title: toon car .r3d files

thanks the script works
but what to do, in order to to import all files at once?
because i can import only one file at the same time
