## Post #1
- Username: saajd
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-01T12:35:47+00:00
- Post Title: Catwoman

Hello
you can help me?
I need tool for catwoman game for unpack *.avl and *.vol 
Thank you!
## Post #2
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-01T17:55:22+00:00
- Post Title: Catwoman

> Reply from saajd
>
> Hello
you can help me?
I need tool for catwoman game for unpack *.avl and *.vol 
Thank you!
Download PakScape Program!!!
## Post #3
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-08-02T11:16:52+00:00
- Post Title: Catwoman

No

I have full game Catwoman(2cds)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-02T18:09:56+00:00
- Post Title: Catwoman

I looked at them and they are way to small to be real archives. I can't find a demo of the game anywhere. Do you have bigger .VOL files? But not TOO big?
## Post #5
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-08-03T20:09:34+00:00
- Post Title: Catwoman

yes
this is file vol 500k
  to ideate package vol and avl be one package with different name
## Post #6
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-04T12:56:32+00:00
- Post Title: Catwoman

Mr Mouse - I think this should be enough for you to work with...

```
| Catwoman *.vol *.avl |
+----------------------+

4 - Header (VOLT)
4 - Version? (2)
4 - numFiles
4 - Directory Size

// for each file
4 - Unknown
4 - File Type ID? (1)
4 - File ID Number? (goes up by 25 for each file)

// for each file
4 - File Offset
4 - null
4 - File Size
4 - null
X - Filename (null) (this may be a constant size of 8 + 1 null?)

X - File Data
```
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-04T15:00:07+00:00
- Post Title: Catwoman

Yep,  , and here's the MexScript:

> IDString 0 VOLT ;
>
> Get VN Long 0 ;
>
> Get FN Long 0 ;
>
> Get HS Long 0 ;
>
> SavePos ST 0 ;
>
> Set J Long 12 ;
>
> Math J *= FN ;
>
> Math ST += J ;
>
> GoTo ST 0 ;
>
> For T = 1 To FN ;
>
> SavePos FOO 0 ;
>
> Get FO Long 0 ;
>
> Get D Long 0 ;
>
> SavePos FSO 0 ;
>
> Get FS Long 0 ;
>
> Get D Long 0 ;
>
> Get FNA String 0 ;
>
> Log FNA FO FS FOO FSO ;
>
> Next T ;

Use the update function in MultiEx Commander (Web) to retrieve the new MC.MRF file.  Will write a script to extract from PCS files.
## Post #8
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-08-05T10:03:09+00:00
- Post Title: Catwoman

Thank you
## Post #9
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-08-05T11:34:16+00:00
- Post Title: Catwoman

Hello
after type script and clck on button "test on"and open pcs files send message error:

Process error:
Id string of format invalid

after ok

error in line:
numeric value instead of text variable

but with click on button "check script " send message:  no errors!

Please help me

thank you
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-05T11:48:52+00:00
- Post Title: Catwoman

The script is for VOL files, not for PCS files. You can extract PCS files from the VOL files using the above script. But use the Web update function in MultiEx Commander and you can select Catwoman vol files.
## Post #11
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-05T11:49:05+00:00
- Post Title: Catwoman

Try updating MexCom using the web update tool - I tested it and it worked for me.

The web update tool is found at the menus at the top
Web --> Check web for new version

You may notice that it downloads the script for you.

Give that a go

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #12
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-08-05T12:21:32+00:00
- Post Title: Catwoman

after extract from vol file
two pack extract : pcs and pcm
need unpack pcm
## Post #13
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-05T12:27:17+00:00
- Post Title: Catwoman

I took a look at the file you supplied, and the PCS files in the *.vol archive - they are both the same. These files don't appear to be an archive at all - at least not that I can see - so I presume that it is some other format used by the game. I think it is either a map, or is something used in a map.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #14
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-05T13:12:32+00:00
- Post Title: Catwoman

Actualy, The PCS file looks like a "semi" archive.  I took a quick look and i saw a bunch of RIFF headers, include WAVE, so there IS a wave file contained in this file.  RIFF AMPC?.. I'm not sure what that is, could be a propriety codec.  I see DTX? which is used in Direct X as Texture file format.  I see the same in the PCM file only I don't see riff headers, so it COULD have RAW PCM audio data in it, in fact, i looked like it (Just scrolling through it in a hex editor you can see patterns that look almost like raw audio).

Now there aren't any "names" in this, so it prolly not a "real" archive file.  Possibly a specially formated archive.
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-05T13:16:53+00:00
- Post Title: Catwoman

Ah, well, I had been busy a bit with that. 

Looks like PCM and PCS are alike. 

There's at least a header of 0x1f4 size and a tail, but also a middle part. 

[0-3] - BIGB (id string)
[128-131] - relative offset of tail (add 0x1f4), 4-byte value 
[420-423] - number of record (each record has at least three files, including a TGA, a AMF-header and an AMF-file), in PCM files these last two don't have actual names. 

Data starts at 0x1f4 (500)

At the TAIL entries each have three 4-byte values first  :

[0-3] xx xx xx 80 (file ID, 01 00 00 80 is TGA file) 
[4-7] relative offset of data entry (add 0x1f4 again!)  (Note: each data entry normally has its own header. In case of tga files, this starts NOT with the string of the archivename, but with a 4-byte variable. Unlike AMF files in PCS archives, they start without this variable first.)
[8-11] relative offset of the tail of the header part of the file (just prior to the actual file) 
etc. 
There's more to the tail after this, I don't know yet. 

At the TAIL PART OF THE HEADER OF THE FILE :
[0-3] - relative offset of actual file data 
[4-7] - size in bytes of the file

This should be enough information to extract the TGAs at least. 

Perhaps we can find out more. 



So, this archive is specially designed for the game (I'm guessing this is part of a complete level resource), but it's still an archive.
## Post #16
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-05T13:31:20+00:00
- Post Title: 

```
0000200: 6775 6964 1000 0000 479c 6206 822a 9248  guid....G.b..*.H
0000210: 996e b26a 869b 6262 6e61 6d65 1800 0000  .n.j..bbname....
0000220: 436f 7272 6964 6f72 5f41 746d 6f73 3032  Corridor_Atmos02
0000230: 2e77 6176 0000 0000 666d 7420 1400 0000  .wav....fmt ....
0000240: 6900 0100 44ac 0000 e660 0000 2400 0400  i...D....`..$...
0000250: 0200 4000 6661 6374 0400 0000 0350 3200  ..@.fact.....P2.
0000260: 7773 6d70 2400 0000 1400 0000 0000 0000  wsmp$...........
0000270: 0000 0000 0000 0000 0100 0000 1000 0000  ................
0000280: 0000 0000 0000 0000 004d 1c00 7374 726d  .........M..strm
0000290: 0800 0000 0000 0000 244d 1c00            ........$M..

```


RIFF File

Main Block: WAVS ??? (WAVE = Wave file  maybe wave script?)
First Block: guid (GUID for?)  Size: 16 Bytes
Second Block: name   Size: 24 Bytes
Third Block: "fmt " Size: 20 Bytes
Fourth Block: fact  Size: 4 Bytes
Fifth Block: wsmp  Size: 36 Bytes
Sixth Block: strm  Size: 8 Bytes

Googling for Riff and WSMP i found a site

[http://stud.fh-heilbronn.de/~cschoene/p ... ource.html](http://stud.fh-heilbronn.de/~cschoene/projects/libgig/APIDocumentation/DLS_8cpp-source.html)

Looks like information on sampling.
## Post #17
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-05T13:38:41+00:00
- Post Title: 

Well, I see that I was alittle mistaken then 

I was focusing mainly on the PCM file, which does appear to have some audio content when I tried to play it with an audio program that supports RAW PCM.

I understand what you are saying about the semi-archive nature of the file - I agree with you there. Similarly to Mr Mouse, I had noticed some of the header and linking information contained in these files, but I didn't go as far as to see the RIFF headers - I will take a look into this alittle further, and see what I come up with.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #18
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-05T14:27:24+00:00
- Post Title: 

Here is what I have working so far - hopefully you can understand it. I have been working with the first file extracted from the *.vol archive

```
| Catwoman *.pcm *.pcs |
+----------------------+

4 - Header (BIGB)
4 - Header Size? (484)
120 - Unknown
4 - Directory Offset [+500]
288 - Unknown
4 - Number Of Files
76 - Unknown
X - File Data

// go to dirOffset

// for each file
2 - File ID (1 = tga)
2 - Unknown
4 - File Offset [+500]
4 - Offset to File Size Header [+500]

// go to file offset
4 - Unknown
64 - Filename of Archive this file is located in (null)
16 - Name 1
16 - Name 2
64 - Last Edited Date
64 - Created Date
64 - Filename (null)
4 - Offset to DDS Header [+fileSizeHeaderOffset]
4 - Offset to DDS Header [+fileSizeHeaderOffset]
4 - null
//NOTE - If using the file size header offset, it jumps to this position
4 - File Header Size [+500]
4 - File Size
4 - Unknown
4 - Unknown
16 - null
X - File Header (to FileHeaderSize)
X - File Data

//NOTE:      FileSize - FileOffset = 336
//And:       FileOffset + 336 = DDS Offset
//Therefore: Header size = 336?
```


Note the last comments - I think we may be incorrectly assuming the functions of the FileHeaderSize field and the FileSize field?

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #19
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-05T14:33:15+00:00
- Post Title: 

No, I did not assume that at all   
As I said, it's not the header size, it's the relative offset of the actual file (the offset of the dds file header), the "DDS". That's how DDS files start. So it points to the start of the file and then comes the size of the file.
## Post #20
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-05T14:39:17+00:00
- Post Title: 

Yeah sorry, I realise that you didn't call it the header size - that was just my representation of the information you gave (when someone says that you need to skip a few bytes, i normally look at it from the other direction that says that there is something there which is unknown at the moment)

But anyway, I was making the assumption about incorrent labling of the fields, because for the file I was analysing, the 'relative offset of the actual file' was not pointing to the DDS header - rather it was pointing further through the file (maybe another 100 or so bytes past the DDS header).

I will take a look at this again tomorrow - I didn't mean to accuse or abuse people 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #21
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-05T14:41:44+00:00
- Post Title: 

Hehe, now abuse? That's way too harsh a word to use  There's more to this format than meets the eye, we'll work it out.
## Post #22
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-05T14:46:01+00:00
- Post Title: 

Ah, you may be right Mr Mouse, I think I see what I was doing wrong - in which case you would be correct 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)

PS - now we are all back to normal - yippee
## Post #23
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-05T14:47:57+00:00
- Post Title: 


## Post #24
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-05T15:06:04+00:00
- Post Title: 

You should see diablo files.  They are password encrypted and the password changes per archive.  (Good thing diablo only has one ).  Formating the password a certain way creates a nice MD5 hash that rotates continuously through the file.  AND THEN you can start extracting, only, like this file, it doesn't have any filenames in the header.  The files are stored in the diablo executables, but the index is in the archive file.... The way they search, is run the filename, through 3 different hash code generators.  Then with the first one, that tells them where in the index might the file be .  Then you have to verify that the 2 OTHER hashes in the index match the 2 others you just generated.  If they match, then you found the index location which contains the offset into the file and the size.  Then you can go and extract it
## Post #25
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-05T15:11:32+00:00
- Post Title: 


## Post #26
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-06T09:51:48+00:00
- Post Title: 

Here's some more detail:

Damn, that stupid forum indent. 
Here's the text file
[http://www.xentax.com/taoc/pcspcmformat_mike.txt](http://www.xentax.com/taoc/pcspcmformat_mike.txt)

> Note that all pointers should be incremented with 0x1f4 (the size of the archive header)
>
> 
>
> At 128 : offset of tail
>
> At 132 : Size of tail
>
> At 404 : number of SOUND entries (RIFF and additionals)
>
> At 408 : size of the sound data
>
> At 420 : number of TGA entries
>
> At 424 : size of TGA data
>
> 
>
> Filetypes in PCS PCM
>
> Found at the TAIL:
>
> 
>
> 
>
> 
>
> Hex values 	Type	Additional variables
>
> 
>
> 0204 0080 :	Info	This is the last type in the TAIL, and actually 
>
> 			a pointer list to the stuff right before the TAIL:
>
> 			- Pointer to :
>
> 				- Number of TGA files
>
> 				- Pointer to a pointer to a list of offsets of 
>
> 				the TGA files
>
> 					- This list is supplemented with two additional
>
> 					  values: 
>
> 						- Number of large chunks (unknown)
>
> 						- pointer to a list of offsets of these
>
> 						  chunks (size = offset 2nd - offset 1st)
>
> 						  The last file ends where the first of the
>
> 						  AMF files begin (type 2100 0080)
>
> 
>
> 				- Pointers to each entry in the same list of offsets 
>
> 				  of the TGA files! (so: Number-of-TGA-files times!)
>
> 				- Pointer to a pointer to the list of offsets of the large
>
> 				  chunks! 
>
> 				- Pointers to each entry in the list of offsets of the 
>
> 				  large chunks
>
> 
>
> 			It seems to me that this part is about TGA files 
>
> 			and possibly binaries? Other graphic type?. 
>
> 
>
> 0E01 0080 :	Unknown	This is followed by one 4-byte variable:
>
> 			It points to some script part
>
> 
>
> 2400 0080 : 	Unknown	This covers the large chunks as mentioned above, 
>
> 			Three 4-byte values:
>
> 			- pointer to the start of the large chunk 
>
> 			- Pointer to a pointer in the large chunk
>
> 			  The pointer in points to points to the first list in the chunk 
>
> 			  The list has entries of 32 bytes in length, and you can
>
> 			  get the number of entries from the variable right before
>
> 			  that pointer. 
>
> 
>
> 			- pointer to a pointer in the large chunk
>
> 			  Likewise, the pointer in points to points to the 
>
> 			  second list in the large chunk, most likely a list of 
>
> 			  2-byte values (integers). Again, the number of entries 
>
> 			  you can get from the variable right before this pointer. 
>
> 
>
> 
>
> 
>
> 1301 0080 : 	WAV	one 4-byte value (pointer to the file)
>
> 			note that this points to the RIFF id-tag, 
>
> 			the 4-byte value right after the RIFF tag is the size of 
>
> 			the file (minus the header of the file, 8 bytes) 
>
> 			so you can simply calculate the whole size. 
>
> 			Note that there are two types of RIFF:
>
> 			WAVE and AMPC. 
>
> 			THe names of the files are written in the headers:
>
> 			after "bbname" in WAVEs comes the size of the string that follows
>
> 			after "name" in AMPC comes the size of the string that follows
>
> 1801 0080 : 	Unknown one 4-byte value that points to a string (or a header?)
>
> 1501 0080 :	Unknown sometimes three 4-byte values, sometimes two 4 byte values
>
> 0100 0080 : 	TGA 	two 4-byte values : 
>
> 			Pointer to file header,
>
> 			Pointer to tail of file header.
>
> 			- this tail has two 4-byte values of interest:
>
> 				Pointer to actual file, 
>
> 				Size of actual file
>
> 1701 0080 :	Table	This is a list of pointers to 
>
> 			A. table entries of variable bytes in size, with the first value 
>
> 			a pointer to a string in a string table
>
> 			B. table entries of variable size with the first pointer
>
> 			a pointer to an entry in yet another table (of 88-byte entry-size)
>
> 			C. Table entries to yet another table
>
> 
>
> 2100 0080 : 	AMF 	Three 4-byte values:
>
> 			Pointer to header of AMF file, 
>
> 			Pointer to data part of AMF file
>
> 			Pointer to header part of AMF file (has pointers to other areas!)
>
> 			Note: Many are followed by the next entry type after these 
>
> 			values, but there are a lot of 2100 0080 files that have more
>
> 			variables, and are not "broken" by a 0400 0080 entry. However,
>
> 			ALL 2100 0080 types are followed by 19 4-byte values before the
>
> 			next one. All these 19 values are pointers to the insides of
>
> 			the AMF file, which in turn may be pointers to other areas in the
>
> 			AMF file. I'm guessing these are sequences of animation. 
>
> 			Strikingly, whenever a 2100 0080 tail entry is interrupted by a
>
> 			0400 0080, the next value (ultimately the first of the 0400 0080)
>
> 			points to the same area in the AMF file as that the 4th value of
>
> 			an uninterrupted 2100 0080 would point to!
>
> 0400 0080 : 	AMF-support type, read above
>
> 
>
> 
>
> A note : After all the 0100 0080 types (TGAs) have been listen comes a list of pointers to 
>
> 
>
> .anim files. I haven't quite understood yet how this list is made up, in numbers. The 
>
> 
>
> number of pointers to sections in the .anim files differs per anim file.
## Post #27
- Username: SMaz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 26, 2006 9:58 pm
- Post datetime: 2006-02-26T14:04:28+00:00
- Post Title: 

So, did have anybody now an Idea, how I can edit the Textures in the pcs Files ?

Is there a script now for MultiEx Commander ?

Thx a lot
