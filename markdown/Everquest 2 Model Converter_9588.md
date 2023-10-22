## Post #1
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-09-02T23:37:35+00:00
- Post Title: Everquest 2 Model Converter

I have made a Quickbms script that will covert .draw model files into .3ds files including the UVs.
The first step is to extract the .draw files you want using the free tool found here:
[http://ps23dformat.wikispaces.com/file/ ... -1.2.3.zip](http://ps23dformat.wikispaces.com/file/view/Eq2VpkTool-1.2.3.zip)

The second step is to download the program called "quickbms" from here:
[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)

Then download my script from here:
[http://ps23dformat.wikispaces.com/file/ ... ctober.bms](http://ps23dformat.wikispaces.com/file/view/eq2drawto3dsOctober.bms)

Put the .draw file you want to convert in the same folder as quickbms.exe
Also put the script in the same folder as quickbms.exe as well
Then run the script by using the Microsoft Windows command-prompt
by specifying the path to quickbms.exe (with the -w parameter and the w must be lowercase) followed by the path to the script followed to the path to the draw file, followed by the path to the folder that contains quickbms.exe for example:

```
C:\quickbms\quickbms.exe -w C:\quickbms\eq2DRAWto3DSoctober.bms C:\quickbms\wolf.draw C:\quickbms\
```

The script will then ask you to open another file, simply just type in the name that you want to save the converted mesh, for example you could type in wolf.3ds. Do not type in the whole path, just the name you want to save as.
The script will then convert the file and save it as wolf.3ds. It should work on EVERY .draw file from the game, even the ones that have the vertex deformers (deformers are not converted though). If it does not work on any .draw file, I would like to hear about it.
Updated October 21 to now work on more .draw files
Known Issues:
Must flip UV's by Y axis to display properly.
Some models have more then one UV set, they are converted fine, but you will need to manually place the textures in the right spot, for example 0,0 to 1,1 is the default UV, but an armored horse mount, might also have a saddle UV, in 1,1 to 2,2 and a armor UV from -1,-1 to 0,0.
Here is an image:


Here is the script:

```
GoTo 0x14 0 ;
Get vertexnumber Long 0 ;
SavePos vertexstart 0 ;
Math jump = vertexnumber ;
Math jump *= 0xc ;
Math hop = vertexnumber ;
Math hop *= 0x8 ;
GoTo vertexstart 0 ;
GoTo jump 0 SEEK_CUR ;
Get normalnumber Long 0 ;
If vertexnumber != normalnumber ;
CleanExit ;
EndIf ;
GoTo jump 0 SEEK_CUR ;
Get uvnumber Long 0 ;
If vertexnumber != uvnumber ;
CleanExit ;
EndIf ;
SavePos uvstart 0 ;
GoTo hop 0 SEEK_CUR ;
SavePos gold 0 ;
Get goldtest Long 0 ;
If goldtest = vertexnumber ;
GoTo hop 0 SEEK_CUR ;
SavePos qprime 0 ;
Get silvertest Long 0 ;
GoTo qprime 0 ;


SavePos gold 0 ;
Elif goldtest = 0 ;
SavePos qprime 0 ;
Get silvertest Long 0 ;
GoTo qprime 0 ;


SavePos gold 0 ;
Else ;
CleanExit ;
EndIf ;
If silvertest = vertexnumber ;
GoTo qprime 0 ;
GoTo hop 0 SEEK_CUR ;
GoTo 4 0 SEEK_CUR ;
SavePos goldgold 0 ;


SavePos gold 0 ;
EndIf ;
If silvertest = vertexnumber ;
GoTo goldgold 0 ;
Get vtest Long 0 ;
GoTo gold 0 ;
EndIF ;
If vtest = vertexnumber ;
GoTo goldgold 0 ;
GoTo hop 0 SEEK_CUR ;
GoTo 4 0 SEEK_CUR ;


SavePos gold 0 ;
EndIf ;


GoTo gold 0 ;
Get goldtest2 Long 0 ;
If goldtest2 = 0 ;
Get goldtest2 Long 0 ;
EndIF ;
If goldtest2 = 0 ;
Get goldtest2 Long 0 ;
EndIF ;
If goldtest2 = 0 ;
Get goldtest2 Long 0 ;
EndIF ;
If goldtest2 = 0 ;
Get goldtest2 Long 0 ;
EndIF ;
SavePos facestart 0 ;
Math goldtest2 *= 2 ;
Math goldtest2 /= 6 ;
Math facenumber = goldtest2 ;
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
set M Byte 0x4d ;
Put M Byte 1 ;
set M Byte 0x4d ;
Put M Byte 1 ;
set M Byte 0xed ;
Put M Byte 1 ;
set M Byte 0x22 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x02 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x0a ;
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
set M Byte 0x3d ;
Put M Byte 1 ;
set M Byte 0x3d ;
Put M Byte 1 ;
set M Byte 0xdd ;
Put M Byte 1 ;
set M Byte 0x22 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xff ;
Put M Byte 1 ;
set M Byte 0xaf ;
Put M Byte 1 ;
set M Byte 0x3e ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xa0 ;
Put M Byte 1 ;
set M Byte 0x0b ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x4e ;
Put M Byte 1 ;
set M Byte 0x6f ;
Put M Byte 1 ;
set M Byte 0x6e ;
Put M Byte 1 ;
set M Byte 0x65 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x10 ;
Put M Byte 1 ;
set M Byte 0xa0 ;
Put M Byte 1 ;
set M Byte 0x0f ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x11 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x09 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x20 ;
Put M Byte 1 ;
set M Byte 0xa0 ;
Put M Byte 1 ;
set M Byte 0x0f ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x11 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x09 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xcc ;
Put M Byte 1 ;
set M Byte 0xcc ;
Put M Byte 1 ;
set M Byte 0xcc ;
Put M Byte 1 ;
set M Byte 0x30 ;
Put M Byte 1 ;
set M Byte 0xa0 ;
Put M Byte 1 ;
set M Byte 0x0f ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x11 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x09 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xff ;
Put M Byte 1 ;
set M Byte 0xff ;
Put M Byte 1 ;
set M Byte 0xff ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x40 ;
Put M Byte 1 ;
set M Byte 0x99 ;
Put M Byte 1 ;
set M Byte 0x22 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x64 ;
Put M Byte 1 ;
set M Byte 0x69 ;
Put M Byte 1 ;
set M Byte 0x6x ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x41 ;
Put M Byte 1 ;
set M Byte 0x8f ;
Put M Byte 1 ;
set M Byte 0x22 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x10 ;
Put M Byte 1 ;
set M Byte 0x41 ;
Put M Byte 1 ;
set M Byte 0x64 ;
Put M Byte 1 ;
set M Byte 0x67 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x9d ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
GoTo 0x2 1 ;
Put total3ds Long 1 ;
GoTo 0x12 1 ;
Put total1 Long 1 ;
GoTo 0x56 1 ;
Put total2 Long 1 ;
GoTo 0x60 1 ;
Put total3 Long 1 ;
GoTo 0x66 1 ;
Put tiger1 Long 1 ;
GoTo 0x6A 1 ;
Put vertexnumber Short 1 ;
GoTo facebase1 1 ;
set M Byte 0x20 ;
Put M Byte 1 ;
set M Byte 0x41 ;
Put M Byte 1 ;
Put weretiger Long 1 ;
Put facenumber Short 1 ;
GoTo facebase3 1 ;
set M Byte 0x30 ;
Put M Byte 1 ;
set M Byte 0x41 ;
Put M Byte 1 ;
Put tiger4 Long 1 ;
set M Byte 0x4e ;
Put M Byte 1 ;
set M Byte 0x6f ;
Put M Byte 1 ;
set M Byte 0x6e ;
Put M Byte 1 ;
set M Byte 0x65 ;
Put M Byte 1 ;
set M Byte 0x0 ;
Put M Byte 1 ;
Put facenumber Short 1 ;
GoTo uvbase 1 ;
set M Byte 0x40 ;
Put M Byte 1 ;
set M Byte 0x41 ;
Put M Byte 1 ;
Put tigon Long 1 ;
Put vertexnumber Short 1 ;
For vwolf = 0 < vertexnumber ;
GoTo vertexstart 0 ;
Get Type1 Long 0 ;
Get Type2 Long 0 ;
Get Type3 Long 0 ;
SavePos vertexstart 0 ;
GoTo WHEREvertexq 1 ;
Put Type1 Long 1 ;
Put Type2 Long 1 ;
Put Type3 Long 1 ;
SavePos WHEREvertexq 1 ;
Next vwolf ;
For fwolf = 0 < facenumber ;
GoTo facestart 0 ;
Get Type1 short 0 ;
Get Type2 short 0 ;
Get Type3 short 0 ;
SavePos facestart 0 ;
GoTo WHEREfaceq 1 ;
Put Type1 short 1 ;
Put Type2 short 1 ;
Put Type3 short 1 ;
Put 0 short 1 ;
SavePos WHEREfaceq 1 ;
Next fwolf ;
For uvwolf = 0 < vertexnumber ;
GoTo uvstart 0 ;
Get Type1 Long 0 ;
Get Type2 Long 0 ;
SavePos uvstart 0 ;
GoTo WHEREuvq 1 ;
Put Type1 Long 1 ;
Put Type2 Long 1 ;
SavePos WHEREuvq 1 ;
Next uvwolf ;
For fcwolf = 0 < facenumber ;
GoTo WHEREfacecountq 1 ;
Put fcwolf short 1 ;
SavePos WHEREfacecountq 1 ;
Next fcwolf ;
```


Any questions or comments or anything not working please contact me.
## Post #2
- Username: Pilgrim
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 03, 2010 1:41 am
- Post datetime: 2012-09-03T15:56:15+00:00
- Post Title: Everquest 2 Model Converter

Thank you very much for this!
