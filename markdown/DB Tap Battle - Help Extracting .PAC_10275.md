## Post #1
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2013-03-27T13:45:21+00:00
- Post Title: DB Tap Battle - Help Extracting .PAC

I can already extract a few .PNG files, but it seems there are more than that; .BMP .SPR .DAT .HDR .CNV .DAC can anyone have a look?

[http://www.sendspace.com/file/ppt3js](http://www.sendspace.com/file/ppt3js)

minidump hex:
0000: 08 00 00 00 00 00 75 1F 01 00 70 6E 67 00 00 00  ......u...png...
0010: 00 00 75 1F 01 00 5A 27 00 00 70 6E 67 00 00 00  ..u...Z'..png...
0020: 00 00 CF 46 01 00 00 03 00 00 61 63 74 00 00 00  ...F......act...
0030: 00 00 CF 49 01 00 E6 0F 00 00 63 6E 76 00 00 00  ...I......cnv...
0040: 00 00 B5 59 01 00 32 00 00 00 64 61 63 00 00 00  ...Y..2...dac...
0050: 00 00 E7 59 01 00 B1 A0 11 00 73 70 72 00 00 00  ...Y......spr...
0060: 00 00 98 FA 12 00 23 00 00 00 62 69 6E 00 00 00  ......#...bin...
0070: 00 00 BB FA 12 00 DC 00 00 00 67 64 74 00 00 00  ..........gdt...
0080: 00 00 89 50 4E 47 0D 0A 1A 0A 00 00 00 0D 49 48  ...PNG........IH
0090: 44 52 00 00 02 00 00 00 02 00 08 03 00 00 00 C3  DR..............
00A0: A6 24 C8 00 00 03 00 50 4C 54 45 FF 00 FF 42 31  .$.....PLTE...B1
00B0: 06 24 49 10 46 38 12 49 41 22 54 46 21 1F 62 20  .$I.F8.IA"TF!.b 
00C0: 2E 5E 17 18 64 47 57 4D 2E 5F 51 1F 33 6B 1E 5C  .^..dGWM._Q.3k.\
00D0: 53 33 2A 6F 2A 5E 57 3A 60 59 31 35 72 32 2A 71  S3*o*^W:`Y15r2*q
00E0: 56 35 75 25 67 58 3A 6B 59 2C 5E 5B 44 64 62 23  V5u%gX:kY,^[Ddb#
00F0: 4E 6E 22 66 5F 42 37 7D 28 27 7C 67 2E 7D 58 29  Nn"f_B7}('|g.}X)
## Post #2
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-03-28T12:15:14+00:00
- Post Title: DB Tap Battle - Help Extracting .PAC

Here a quickbms script for unpack

```
set table files
math table *= 16
math table += 2
for i = 1 to files
get offset long
math offset += table
get size long
getdstring ext 8
set name i
string name += "."
string name += ext
log name offset size
next i
```

I think there are no names in the archive, only extensions.
## Post #3
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2013-03-28T13:45:28+00:00
- Post Title: DB Tap Battle - Help Extracting .PAC

Thank you that worked! However, none of the character sprites are found in either of the .pac files, I came across a few .spr that were larger than what they gave for example this one gave 1 .PNG file(using nova extractor/game extractor also) that is only 183 kb yet the .spr archive has 1 mb of more data left. Here I have uploaded the .spr file, the whole game itself is 15 mb, but none of the 19 .pac files contain the character animation sprites (they are 2D, so it's not a 3D model I'm sure of it) This is a mystery to me where they might be, do you think it might be possible that the game itself requires you to install it on your android phone and attempts to connect to the internet and download some more data which is provided only then just once in order to even play the game? Even though it is an offline game played with max one more player using bluetooth...   

[http://www.sendspace.com/file/05d409](http://www.sendspace.com/file/05d409)

EDIT: 
Just now I tried using bitmaprip on the .spr archive, it extracted 2 .JPG images 1 is 333 kb the other is 485 kb but both show nothing upon opening them.
## Post #4
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-03-28T14:25:52+00:00
- Post Title: DB Tap Battle - Help Extracting .PAC

You can use the same script on the spr files too.
## Post #5
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2013-03-28T15:20:33+00:00
- Post Title: DB Tap Battle - Help Extracting .PAC

Never mind, thank you for everything, it all worked out, major thanks, 
there are secret characters nobody even knew existed in this game too..hehe!  
If I ever meet you in real life I'd treat you a beer or two or whatever drink you want, really happy for everything you've done!!
## Post #6
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2013-04-01T03:06:07+00:00
- Post Title: DB Tap Battle - Help Extracting .PAC

Bump! I'm sorry to trouble you again, but can a repack script also be made? 
I already have a lot of people who've done edits of their own and  would be happy 
to play with new skins/looks such as this one if you find it fancy    : 

original:  edited by fans:
