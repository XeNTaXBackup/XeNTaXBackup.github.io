## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-23T19:38:53+00:00
- Post Title: How to extracting files play archive?

Hi all..Would be desirable to learn who as it does make in order to dismantle recreation area and to write for an example of plugins for Game Extractr or script for MultiEx Commander? For example I took play archive from game Mercedes Benz Truck Racing the play archive SYN.... it found in Watto the description of the play archive :

```
// 4 - Number Of Files
// 8 - null
// 24 - Filename
// 4 - Data Offset
// 4 - Raw File Length
```


With the title and with numbers files is file everything understandably, but is not understandable why Filename = 24?
And still it would be desirable to know that it does indicate this description?

```
// 4 - Raw File Length
```


Watto and Mr.Mouse you will explain if you please and that in me nothing it is obtained
## Post #2
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-23T20:11:41+00:00
- Post Title: How to extracting files play archive?

This example Mercedes Benz Truck Racing archive.....
## Post #3
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-23T20:16:55+00:00
- Post Title: How to extracting files play archive?

And this example Mercedes Benz World Racing archive.....



Filename = ?
Raw offset = ?
Data offset = ?

What say guys ?
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-24T07:31:18+00:00
- Post Title: How to extracting files play archive?

OK, lets see what I can do...

Firstly - the specs from the wiki for this game... ( [http://wiki.xentax.com/index.php/SYN_FNYS](http://wiki.xentax.com/index.php/SYN_FNYS) )

```
uint32 {4}   - Number Of Files
uint64 {8}   - null

// for each file

    char {24}    - Filename (null)
    uint32 {4}   - Data Offset
    uint32 {4}   - File Length


byte {X}     - File Data 
```


Now, why Filename=24? This means that the filename can be <= 24, NOT =24. In some archives, the filename is set to a maximum length, so that it is more efficient when reading the archive from the hard disk. Many of the filenames will be <24 , if this happens then the filename ends with a null (0) byte.

So, in the example image, the first filename is amatur1.tga, then there is a  byte=0, then other bytes to make it have length 24. Following that is 4 bytes for the data offset, and 4 bytes for the raw file length.

What does Data Offset mean? The Data Offset tells where the file is in the archive. So, in the first example, the offset is 816. So, if you go to byte=816 in the archive, you will find the start of the file.

What does Raw File Length mean? This means the length of the file, and that the file is not compressed. I don't usually write "Raw File Length" any more, I write "File Length" or "Decompressed File Length". In this example, it is length=6064 bytes.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-24T07:45:53+00:00
- Post Title: How to extracting files play archive?

OK, now for the next archive. I am not really good with Hex Editors - I can't read them well - but I think that it would go something like this...

```
4 - Number Of Files?
52 - null

// for each file
  48 - Filename (null terminated)
  4 - Compressed File Length
  4 - Decompressed File Length
  4 - File Offset?
  4 - null

```


Some of these fields will be around the other way - like I said, I can't read Hex 

Something to note when dealing with files - most fields are either 2, 4, or 8 bytes long - you don't usually see fields of 9 bytes or other numbers (note the header is 8 bytes, it would only be rare to be 9 bytes long.)

If you have any further questions, just ask and I will try to help. If you want me to write the correct specs, you can send me an archive. Also, if you do deside to write GE plugins, excellent  - I welcome your help and can give you a template file if you want.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-24T07:53:40+00:00
- Post Title: How to extracting files play archive?

Well, in the archive you show Kornet, the header is 8 bytes "SYN!V2.0"
Then indeed comes the number of files probably. 

The file information starts at 0x40.

It starts with the filename, that can be 48 in length (so, when we write [24] FileName we are talking about how many bytes are reserved for each filename, NOT if they are used or not. )
In your example the files are null-terminated (0 at the end of the name) strings of maximum 48 length. 

Then, just guessing, there's an (un)signed integer of 32 bit (4 bytes) which is the OFFSET of the current resource in the archive. (Again, the OFFSET is the position of the resource in the archive where it begins.) 

Next, another 32-bit value that is the SIZE of the resource. 

Then, again a value of 32-bit that is perhaps pointing to somewhere else in the archive, I can't tell just looking at a screenshot. 

And finally, there a 32-bit value of 0. 

So each entry (folder entry, filelist entry, whatever you wish to call it) is 64 bytes. 48 for the filename, and 12 for the offset, size and something unknown, and one reserved 32-bit value. 

You should know that OFFSET can be relative from a certain position in the archive. So, when the offset is at 40 for instance, and it's value is 32, it might be that the offset of the resource is not 32, but 40+32. Be aware of this.
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-24T11:14:03+00:00
- Post Title: How to extracting files play archive?

I think Mr Mouse answered this much better than I did 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #8
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-24T16:19:06+00:00
- Post Title: How to extracting files play archive?

Ok thanks guys .... this example archive Mercedes Benz World Racing

SYN!v2.0 

Wattooooo you can write plugin ?   

Download here  
[http://rapidshare.de/files/9756550/MBWR.ZIP.html](http://rapidshare.de/files/9756550/MBWR.ZIP.html)
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-24T17:36:38+00:00
- Post Title: How to extracting files play archive?

```
IDString 0 SYN!v2.0 ;
Get FN Long 0 ;
Set D Long 64 ;
GoTo D 0 ;
For T = 1 To FN ;
GetDString FNAME 48 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
SavePos UKO 0 ;
Get UK Long 0 ;
Get UK2 Long 0 ;
Log FNAME FO FS FOO FSO ;
Next T ;

```


MultiEx Commander BMS script. 

The resources are compressed/encrypted. Let's put them on the Compressed Files list. Or, does Watto know the method? I noticed on the WIKI page for the other SYN format that Alexander sais Dragon Unpacker does not support decryption, while GE says nothing like that, so I assume Michael might know the answer?
[syn.zip](https://xentaxbackup.github.io/file/512_syn.zip)
## Post #10
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-24T18:39:38+00:00
- Post Title: How to extracting files play archive?

Excellent  

Mr.Mouse this example Mercedes Benz Truck Racing 
[http://rapidshare.de/files/9763972/MBTR.ZIP.html](http://rapidshare.de/files/9763972/MBTR.ZIP.html)

Set D Long 64 ; - Mr.Mouse what this does indicate?
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-24T20:48:10+00:00
- Post Title: How to extracting files play archive?

The 
```
Set D Long 64 ; 
```
 means I asign the value 64 to the 32-bit (long) variable I gave the name 'D' , so: D=64. 

I do this so I can use the variable in the GoTo command. Because I wish to jump to position 64 in the archive, as the resource information starts there.
## Post #12
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-24T22:47:52+00:00
- Post Title: How to extracting files play archive?

Yes which that to me is with difficulty given to write the scripts for MultiEx Commander
## Post #13
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-24T22:49:54+00:00
- Post Title: How to extracting files play archive?

Thanks for the files, I will write a plugin soon - I can send you the source code for it too since you are interested.

Re: the compression - no I don't know what the compression is - actually I looked at this format a long time ago (when I was only new to this) and I don't think I noted any compression - might have to go back and take a look at it. As for the "decompression not supported" on the wiki - no Game Extractor doesn't support decompression either - its just that I havn't written it on there (partly due to the point I just raised about me not knowing about compression) - I havn't written many decompression methods so most of the formats with compression are not fully supported.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #14
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-24T22:59:16+00:00
- Post Title: How to extracting files play archive?

You guys fine people that still it is possible to say... Professionals in its matter

Mr.Mouse , Watto - Respect
## Post #15
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-24T23:03:18+00:00
- Post Title: How to extracting files play archive?

many thanks! We are always here to help.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #16
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-26T06:45:25+00:00
- Post Title: 

Oke guys..... you will look this

[[img=http://img373.imageshack.us/img373/9012 ... urc.th.png]](http://img373.imageshack.us/my.php?image=backspinbilliardsdeluxeresourc.png)

I still missed what with the selection game arhive ? Help to complete to the end plz  .... According to the form you will say that light archive and plugin of script it will be fast written  

Archive download here
[http://rapidshare.de/files/9834773/reso ... t.zip.html](http://rapidshare.de/files/9834773/resources.dat.zip.html)
5271217 Bytes
 

Thx
## Post #17
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-26T07:05:47+00:00
- Post Title: 

Hi mate,

I have been out all night for christmas, and havn't really had much sleep, but the main thing to remember is that fields are usually 2, 4, or 8 bytes. So, the header would be 4 bytes (PXMD), the number of files and the version field would both be 2 bytes, etc.

I will have a better analysis in probably 12-ish hours - I need some sleep 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #18
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-26T08:50:39+00:00
- Post Title: 

Well, KorNet was right about the format. The IDString = PXMDY.  followed by the number of resources. 

Here's the whole BMS:

```
IDString 0 PXMDY ;
Get RN Long 0 ;
For T = 1 To RN ;
SavePos FSO 0 ;
Get FS Long 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
Get NameSize Byte 0 ;
GetDString FileName NameSize 0 ;
Log FileName FO FS FOO FSO ;
Next T ;

```


Scroll down for the actual BMS. 

Small explanation for those interested:

ImpType Standard; (This tells MultiEx Commander (MexCom) that we can support replacement of resources in archives of this type as well. Standard means we can provide the offset of the resource offsets and resource sizes). 

IDString 0 PXMDY ; (this archive (file 0) is identified by the string "PXMDY") 

Get RN Long 0 ; (read the next 4 bytes (32-bit value or 'long' ) in file 0 and store it in the (new) variable 'RN' - these are the number of resources)

For T = 1 To RN ; (Create a loop that will repeat 'RN' times)

SavePos FSO 0 ; (Store the position the 'filepointer'  (or 'filecursor') is at in file 0 in the variable 'FSO' - This is the position where MexCom can find the  filesize of the current resource)

Get FS Long 0 ; (Get the 32-bit (long) value from file 0 and store it in 'FS' - this is the size of the current resource)

SavePos FOO 0 ; (Store the current position in file 0 in the variable FOO - this is the offset of the current resource offset )

Get FO Long 0 ; (Get the 32-bit (long) value from file 0 and store it in 'FO' - this is the offset of the current resource in the archive)

Get NameSize Byte 0 ; (Get the 8-bit value (a byte) from file 0 and store it in 'NameSize' - this is the size of the filename string, so the number of characters in the filename)

GetDString FileName NameSize 0 ; (Get a string from file 0 that is NameSize in length, the D in the command stands for (pre)-Determined size - this is the filename of the current resource ) 

Log FileName FO FS FOO FSO ; (Log all of this information for the current resource in the list that MexCom will need, so Log filename, the offset of the resource in the archive, the size of the resource in the archive, the offset of the resource offset variable and the offset of the resource size variable - Note that the latter are only needed in case we can support Importation with this archive , if we don't we can just fill in 0 and 0 there. )

Next T; (Repeat this loop, 'next T'  and T will be upped with 1)
[dat.zip](https://xentaxbackup.github.io/file/518_dat.zip)
## Post #19
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-26T10:09:58+00:00
- Post Title: 

Thanks Mike
## Post #20
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-27T03:59:17+00:00
- Post Title: 

Yeah, you are right  - wow, this must be one of the rare exceptions 

My specs are basically the same as Mr Mouses...

```
| Backspin Billiards Deluxe *.dat |
+---------------------------------+

5 - Header (PXMDY)
4 - Number Of Files

// for each file
  4 - File Length
  4 - File Offset
  1 - Filename Length
  X - Filename
  
X - File Data
```


WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #21
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-28T20:04:09+00:00
- Post Title: 

hi guys ....  Took here game one in it archives in size BIG - BIGF but it by what that not usual... Modified   

Watto , Mike ?
[sfx.zip](https://xentaxbackup.github.io/file/523_sfx.zip)
## Post #22
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-28T20:13:45+00:00
- Post Title: 

And this archive in game Scratches RES file... I know guys you can help me  
[scream.zip](https://xentaxbackup.github.io/file/524_scream.zip)
## Post #23
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-12-29T00:32:31+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Small explanation for those interested:

ImpType Standard; (This tells MultiEx Commander (MexCom) that we can support replacement of resources in archives of this type as well. Standard means we can provide the offset of the resource offsets and resource sizes). 

IDString 0 PXMDY ; (this archive (file 0) is identified by the string "PXMDY") 
...
Heh... I've been wanting to start on writing a guide for dummies for BMScripting (Whoa, did I just coin a new word for you?), but haven't gotten around to starting... this little bit will just help me all the more when I decide to start.
## Post #24
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-29T07:37:31+00:00
- Post Title: 

This is the specs for the BIG(BIGF) file. Could you please tell what game this archive is from.

```
| Unknown *.big |
+---------------+

// ARCHIVE HEADER
  4 - Header (BIGF)
  4 - Number Of Files
  4 - First File Offset
  4 - Padding Multiple (2048)
  20 - Description? Directory Name? (null)

// FILES DIRECTORY
  // for each file
    16 - Filename (null)
    4 - File Length
    4 - File Offset (relative to the start of the file data)

0-2047 - null Padding to a multiple of 2048 bytes

// FILE DATA  
  // for each file
    X - File Data
    0-2047 - null Padding to a multiple of 2048 bytes
```


The following 2 fields might be swapped - this would need to be checked against a larger archive.

```
  4 - Padding Multiple (2048)
```


WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #25
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-29T07:57:54+00:00
- Post Title: 

Here is the specs for the RES file

```
| Scratches *.res |
+-----------------+

// ARCHIVE HEADER (256 bytes)
  20 - Header (SCream resource file)
  4 - Unknown
  4 - Unknown (14)
  4 - Version (1)
  224 - Junk Padding to offset 256

// DIRECTORY
  4 - Number Of Files
  
  // for each file (92 bytes per entry)
    16 - Filename (null)
    68 - Junk Padding
    4 - File Offset
    4 - File Length
    
// FILE DATA
  // for each file
    X - File Data
```


I have decided that many of the fields are just junk - they don't seem to have any real value relating to the archive. Some archives do use junk to pad out the files, so it could be that the filename has a maximum length of 84 bytes, although the null padding only goes to byte 16.

Hope this helps. I will make plugins for these games for the next update.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #26
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-29T11:08:23+00:00
- Post Title: 

> Reply from Dinoguy1000
>
> Mr.Mouse wrote:Small explanation for those interested:

ImpType Standard; (This tells MultiEx Commander (MexCom) that we can support replacement of resources in archives of this type as well. Standard means we can provide the offset of the resource offsets and resource sizes). 

IDString 0 PXMDY ; (this archive (file 0) is identified by the string "PXMDY") 
...
Heh... I've been wanting to start on writing a guide for dummies for BMScripting (Whoa, did I just coin a new word for you?), but haven't gotten around to starting... this little bit will just help me all the more when I decide to start.
 Yeah...
## Post #27
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-29T21:01:04+00:00
- Post Title: 

Sorry Watto immediately he did not say   ...

Toca Race Driver 3 Honda Civic 2006

the same archives in the games

Colin McRae Rally 04
Colin McRae Rally 05
Toca Race Driver
Toca Race Driver 2
