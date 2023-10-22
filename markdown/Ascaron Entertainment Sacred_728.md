## Post #1
- Username: brdarkmoon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 17, 2004 11:51 am
- Post datetime: 2004-05-17T04:17:39+00:00
- Post Title: Ascaron Entertainment Sacred

.Pak files support for Sacred...Do you plan to put it up?
## Post #2
- Username: flaz
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Aug 06, 2004 3:38 pm
- Post datetime: 2005-02-11T07:45:04+00:00
- Post Title: Ascaron Entertainment Sacred

Hoping to hear if you will work with Sacred's PAK files. Thanks.
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-11T11:02:40+00:00
- Post Title: Ascaron Entertainment Sacred

Sure - any chance we could get an archive from the game? We will always help out if possible, but it is much easier if we can get access to an archive.

Thanks guys,

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-14T08:26:47+00:00
- Post Title: Ascaron Entertainment Sacred

Yes, we can always have a quick glance at a file to assess whether support is likely.  But we do need to be able to get a whole archive or parts of that archive.
## Post #5
- Username: flaz
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Aug 06, 2004 3:38 pm
- Post datetime: 2005-02-25T00:50:21+00:00
- Post Title: Ascaron Entertainment Sacred

Sorry for the delay in responding...I have been away.

  Sacred uses PAK files. I can send you a sample; just tell me how best to do that. ICQ?

  (The sound and texture PAK's are 273megs and 540megs respectively.)

  Thanks.
## Post #6
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-25T03:21:20+00:00
- Post Title: Ascaron Entertainment Sacred

There aren't any small archives?   

If you can't find a small one, say max 4MB, then the next best thing to do is grab a hex editor and cut the first and last MB of data from one of the archives and send it to us. The sound archive would probably be the better one to do, but if you could do both archives it would be great.

Just post the snippets to the forums here, or you can email us. I am at [watto@watto.org](mailto:watto@watto.org), and Mr Mouse's email can be found at the bottom of this page... [http://multiex.xentax.com](http://multiex.xentax.com)

Thanks mate,

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-25T08:21:52+00:00
- Post Title: Ascaron Entertainment Sacred

Yes, please do send them. You could also send them to [mr.mouse@xentax.com](mailto:mr.mouse@xentax.com) but make sure the subject = multiex. Thanks!
## Post #8
- Username: flaz
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Aug 06, 2004 3:38 pm
- Post datetime: 2005-02-25T23:32:27+00:00
- Post Title: Ascaron Entertainment Sacred

There is one PAK file only 1.7 megs. I sent it to Mr Mouse.

  Thanks for your help! : )
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-26T19:05:56+00:00
- Post Title: Ascaron Entertainment Sacred

```
IDString 0 TEX ;
Get Version Byte 0 ;
Get Items Long 0 ;
Get Unknown Long 0 ;
Set ListStart Long 256 ;
GoTo ListStart 0 ;
For T = 1 To Items ;
Get ItemType Long 0 ;
SavePos OOFF 0 ;
Get ItemOffset Long 0 ;
Savepos SOFF 0 ;
Get ItemComSize Long 0 ;
SavePos FilePos 0 ;
If ItemType > 0 ;
GoTo ItemOffset 0 ;
GetDString ItemName 32 0 ;
Get XSize Int 0 ;
Get YSize Int 0 ;
Set ItemUncomSize Long XSize ;
Math ItemUncomSize *= YSize ;
Math ItemUncomSize *= 2 ;
Math ItemOffset += 80 ;
CLog ItemName ItemOffset ItemComSize 0 0 ItemUncomSize 0 ;
EndIf ;
GoTo FilePos 0 ;
Next T ;

```


That's the script I came up with. Will post BMS soon, have to take a look at more PAK files first to compare.
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-26T23:22:43+00:00
- Post Title: Ascaron Entertainment Sacred

Here's some info onall the pak formats (I downloaded the demo):

Scroll below for the new script for the textures.pak and the BMS. 

```
Creatures.pak
[============================================]

ID	CIF
Type	BYTE (0)
ItemNum	LONG
UNKNOWN	LONG

Items start at 256, all items are 64 in length

[============================================]
weapons.pak
[============================================]

ID	WPN
Version	BYTE (8)
ItemNum	LONG
UNKNOWN	LONG

Items start at 256, all items are 322 in length

[============================================]
sound.pak
[============================================]

ID	SND
Type	BYTE (1)
ItemNum	LONG (Reserved! Not all used (demo)!)
UNKNOWN LONG

Items information start at 256, 

Item Information:

Type/Unknown	LONG
Offset		LONG
Size		LONG

[============================================]
texture.pak
[============================================]

ID	TEX
Type	BYTE (3)
ItemNum	LONG (Reserved! Not all used (demo)!)
UNKNOWN LONG

Items information starts at 256,

Item information:

Type/Unknown	LONG
Offset		LONG
Size		LONG

The textures are in principle 16-bit RGB encoded, uncompressed TGA files with their headers 

stripped from them, replaced by a new custom header of 80 bytes in size, while the image 

data is compressed using ZLib. The new header is as follows:

ItemName	STRING of 32 bytes
X Size 		WORD (16-bit) of the number of pixels in X direction
Y Size 		WORD (16-bit) of the number of pixels in Y direction
UNKNOWN		LONG
TRAIL		40 BYTES of 0's (reserved space?)

The size in the Item information header refers to the Compressed Size 
of the ZLib-compressed data segment (that follows right after the above mentioned custom 

header).To obtain the size of the uncompressed data segment you should calculate:
xsize * ysize * 2 (as each pixel is 16-bit, i.e. 2 bytes). 
The images are upside down as well, so you should flip them vertically. 
Note also that the palette is not saved, so actual colours in the game may be
different. 

You should insert a standard Targa header before the uncompressed image data, in order to 

view them and edit them. 

Targa header:

   BYTE  idlength; 		(0)
   BYTE  colourmaptype;		(0)
   BYTE  datatypecode;		(2)
   WORD  colourmaporigin;	(0)
   WORD  colourmaplength;	(0)
   BYTE  colourmapdepth;	(0)
   WORD  int x_origin;		(0)
   WORD  int y_origin;		(0)
   WORD  width;			(X Size)
   WORD  height;		(Y Size)
   BYTE  bitsperpixel;		(16)
   BYTE  imagedescriptor;	(0)

[============================================]
Items.pak
[============================================]

ID	ITM
Type	BYTE (5)
ItemNum	LONG (Reserved! Not all used (demo)!)

Items information starts at 256,

Type	LONG (0 has no name, 2 has a 32-byte string at position 56 of the item data)
OFFSET 	LONG
SIZE	LONG

Note that the string in Type 2 items refers to a model in models.pak. 


[============================================]
Models.pak
[============================================]

ID	ITM
Type	BYTE (3)
ItemNum	LONG (Reserved! Not all used (demo)!)
UNKNOWN	LONG (multiple, don't know)

Items information starts at 256, 

Type	LONG 
OFFSET 	LONG
SIZE	LONG

Each item (go to the offset of the item to see it!) has its own header, that starts with 

the filename (32-byte string). 
I don't what it's all about, but the models were made using
RAD's Game Tools' 3D Studio Max. 

```
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-26T23:27:32+00:00
- Post Title: Ascaron Entertainment Sacred

Here's the new script for textures.pak:

```
IDString 0 TEX ;
Get Version Byte 0 ;
Get Items Long 0 ;
Get Unknown Long 0 ;
Set ListStart Long 256 ;
GoTo ListStart 0 ;
For T = 1 To Items ;
Get ItemType Long 0 ;
SavePos OOFF 0 ;
Get ItemOffset Long 0 ;
Savepos SOFF 0 ;
Get ItemComSize Long 0 ;
SavePos FilePos 0 ;
If ItemComSize > 0 ;
GoTo ItemOffset 0 ;
GetDString ItemName 32 0 ;
Get XSize Int 0 ;
Get YSize Int 0 ;
Set ItemUncomSize Long XSize ;
Math ItemUncomSize *= YSize ;
Math ItemUncomSize *= 2 ;
Math ItemOffset += 80 ;
CLog ItemName ItemOffset ItemComSize 0 0 ItemUncomSize 0 ;
EndIf ;
GoTo FilePos 0 ;
Next T ;

```

[pak.zip](https://xentaxbackup.github.io/file/138_pak.zip)
## Post #12
- Username: flaz
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Aug 06, 2004 3:38 pm
- Post datetime: 2005-02-28T20:03:26+00:00
- Post Title: Ascaron Entertainment Sacred

Mr Mouse... Thanks for taking a look at the game. I am not sure what the next step is.
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-28T22:14:24+00:00
- Post Title: Ascaron Entertainment Sacred

Well, 

[viewtopic.php?t=1098](http://forum.xentax.com/viewtopic.php?t=1098)

That would be the next step, using the BMS file above.   

Then you can open the textures.pak file and extract the (stripped) TGA files.
## Post #14
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-04-12T11:52:41+00:00
- Post Title: Ascaron Entertainment Sacred

> Reply from Mr.Mouse
>
> Here's the new script for textures.pak:
Code: Select allComType ZLib1 ;
IDString 0 TEX ;
Get Version Byte 0 ;
Get Items Long 0 ;
Get Unknown Long 0 ;
Set ListStart Long 256 ;
GoTo ListStart 0 ;
For T = 1 To Items ;
Get ItemType Long 0 ;
SavePos OOFF 0 ;
Get ItemOffset Long 0 ;
Savepos SOFF 0 ;
Get ItemComSize Long 0 ;
SavePos FilePos 0 ;
If ItemComSize > 0 ;
GoTo ItemOffset 0 ;
GetDString ItemName 32 0 ;
Get XSize Int 0 ;
Get YSize Int 0 ;
Set ItemUncomSize Long XSize ;
Math ItemUncomSize *= YSize ;
Math ItemUncomSize *= 2 ;
Math ItemOffset += 80 ;
CLog ItemName ItemOffset ItemComSize 0 0 ItemUncomSize 0 ;
EndIf ;
GoTo FilePos 0 ;
Next T ;

Run-time error 5
Invalid procedure call of argument
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-12T13:22:45+00:00
- Post Title: Ascaron Entertainment Sacred

Could you please describe what it is you do that gives you this error?
## Post #16
- Username: tecknomage
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 12, 2005 8:02 am
- Post datetime: 2005-07-12T00:18:35+00:00
- Post Title: Sacred PAK Files

What I specifically need is a viewer/reader for all PAK for Sacred by Ascaron.

Looking for code for the console.     

I've attached an example PAK from the Sacred Underworld Expansion.  Again, all I need is a reader/viewer that will work with all the PAK files.
[SacredPAK.zip](https://xentaxbackup.github.io/file/353_SacredPAK.zip)
## Post #17
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-12T07:54:20+00:00
- Post Title: Sacred PAK Files

Are you saying there's some PAK files not supported by MultiEx Commander ?
## Post #18
- Username: tecknomage
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 12, 2005 8:02 am
- Post datetime: 2005-07-14T11:33:02+00:00
- Post Title: Sacred PAK Files

> Reply from Mr.Mouse
>
> Are you saying there's some PAK files not supported by MultiEx Commander ?
   Uhh...  Yes, that's why there is a game requests forum.

MultiEx extracts according to specific game, that's why there is a drop-down list of supported games when you want to open a file.
## Post #19
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-07-14T12:41:20+00:00
- Post Title: Sacred PAK Files

The problem with the game is that there are different formats for the different archives, thus the reason why there are several different scripts for that game. In Game Extractor, there are 6 different scripts for opening that game - its a real pain! So when you say you want a reader for all archives in that game, it isn't really possible. For any other game it would be OK because most games only use 1 format, but for sacred it is only possible if we writes scripts for every archive separately.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #20
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-14T13:33:47+00:00
- Post Title: Sacred PAK Files

Exactly. It may be possible to do it via a plugin, but it takes a little more work and depends on feasibility of detection of the correct PAK formats.
## Post #21
- Username: schme
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 16, 2005 9:51 pm
- Post datetime: 2005-08-16T13:53:00+00:00
- Post Title: Sacred PAK Files

so, is there a place to download the .pak files, cos my disk2 won't work, and i need its files to make the game work.
## Post #22
- Username: vsouza
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 31, 2005 12:58 am
- Post datetime: 2005-08-30T18:17:52+00:00
- Post Title: Sacred PAK Files

When I try to add the script to a bms file, it shows me 
'Run Time error 9'
Subscript out of range.


What should I do?
## Post #23
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2006-01-26T14:47:25+00:00
- Post Title: Sacred PAK Files

I got the bms script working but I'm not sure what to do about the tga files.  If I understand correctly they need to be edited somehow before they can be previewed?
## Post #24
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-28T10:51:36+00:00
- Post Title: Sacred PAK Files

Could you upload an example of one of the TGA files ripped from the game so i can have a look whats wrong with them? =o
## Post #25
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-18T22:46:50+00:00
- Post Title: Sacred PAK Files

Well, I've come up with a ONE SCRIPT RULES ALL thing, as I took another look at those PAK files. We were idiots, those archives are not all that different from eachother. 

This is the full script that will open a lot of those Sacred pak files and let you edit them as well (back em up first).

```
ImpType Standard ;
Get MW Byte 0 ;
Get M2 Byte 0 ;
Get M3 Byte 0 ;
Math M2 *= 256 ;
Math M3 *= 65536 ;
Math MW += M2 ;
Math MW += M3 ;
Get Version Byte 0 ;
Get FileNum Long 0 ;
GoTo 256 0 ;
If MW = 5261389 ;
CleanExit ;
EndIf ;
If MW = 5132375 ;
SavePos Here 0 ;
GoTo EOF 0 ;
SavePos END 0 ;
GoTo Here 0 ;
Set C Long 0 ;
Set FNF String "wpn" ;
Set EXT String ".bin" ;
SavePos FO 0 ;
Do ;
Set FS Long 258 ;
Set FN String FNF ;
String FN += C ;
String FN += EXT;
Log FN FO FS 0 0 ;
Math FO += FS ;
Math Here += FS ;
Math C += 1 ;
While Here < END ;
CleanExit ;
EndIf ;
If MW = 4606275 ;
SavePos Here 0 ;
GoTo EOF 0 ;
SavePos END 0 ;
GoTo Here 0 ;
Set C Long 0 ;
Set FNF String "crt" ;
Set EXT String ".crt" ;
SavePos FO 0 ;
Do ;
Set FS Long 64 ;
Set FN String FNF ;
String FN += C ;
String FN += EXT;
Log FN FO FS 0 0 ;
Math FO += FS ;
Math Here += FS ;
Math C += 1 ;
While Here < END ;
CleanExit ;
EndIf ;
For T = 1 To FileNum ;
Get FID Long 0 ;
Set FN String "unk" ;
String FN += FID ;
String FN += "_" ;
Set EXT String ".bin";
If FID = 32 ;
Set FN String "snd" ;
Set EXT String ".wav";
EndIf;
If FID = 35 ;
Set FN String "spf" ;
Set EXT String ".spf";
EndIf;
If FID = 33 ;
Set FN String "snd" ;
Set EXT String ".mp3";
EndIf;
If FID = 66 ;
Set FN String "iso" ;
Set EXT String ".til";
EndIf;
If FID = 64 ;
Set FN String "mdl" ;
Set EXT String ".mdl";
EndIf;
If FID = 65 ;
Set FN String "mdl2" ;
Set EXT String ".mdl2";
EndIf;
If FID = 99 ;
Set FN String "mix" ;
Set EXT String ".mix";
EndIf;
SavePos FOO 0 ;
Get FO Long 0 ;
If MW = 5785933 ;
Math FO += 12 ;
EndIf ;
If MW = 5067849 ;
Set FN String "item" ;
Set EXT String ".itm";
EndIf ;
SavePos FSO 0 ;
Get FS Long 0 ;
String FN += T ;
String FN += EXT ;
If FS > 0 ;
Log FN FO FS FOO FSO ;
EndIf ;
Next T ;

```

[pak.zip](https://xentaxbackup.github.io/file/1275_pak.zip)
