## Post #1
- Username: terry336
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Mar 30, 2022 5:56 am
- Post datetime: 2022-06-29T22:43:33+00:00
- Post Title: Dinosaur King FIL / DIR / BIN extraction (SSZL archive)

Hello, 
I have a bin file of an arcade game from which I would like to extract all the files present (models in nj and njm format, textures in pvr format, etc...) however when I open the bin file with a hex editor, I don't know where exactly these files are located. Is there a bms script that can extract file contents? Or is it possible for someone to develop one for me since I don't have any programming skills. 
You will find below the bin file with the two files summarizing the contents of the bin file:
[https://drive.google.com/file/d/1diQMDK ... sp=sharing](https://drive.google.com/file/d/1diQMDKgFYV_KYF7aK6DlK8bQ99uRy2Z8/view?usp=sharing)

Thanks for your help! I would very much like to extract the contents of this file.
See ya
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2022-07-05T14:37:36+00:00
- Post Title: Dinosaur King FIL / DIR / BIN extraction (SSZL archive)

I posted this script on Discord, so I'll add it here too in case anyone else wants to experiment with the files.

Use the script on the .dir file and it will automatically pick up the relevant .fil and .bin files.  The files are split into compressed and uncompressed folders, if anybody wants to look at the compressed ones to determine the exact format.  The header info "SSZL" suggests LZSS, but it may be some custom variation as I can't determine the exact compression type.

@ikskoks - probably another one to add on the wiki!  Let me know if you need the full structure.



 dir.zip
(525 Bytes) Downloaded 29 times
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-07-05T21:02:51+00:00
- Post Title: Dinosaur King FIL / DIR / BIN extraction (SSZL archive)

> @ikskoks - probably another one to add on the wiki! Let me know if you need the full structure.

Ok, added. 
[http://wiki.xentax.com/index.php/Dinosa ... IL_DIR_BIN](http://wiki.xentax.com/index.php/Dinosaur_King_FIL_DIR_BIN)
[http://wiki.xentax.com/index.php/PVR_Image](http://wiki.xentax.com/index.php/PVR_Image)

You can post full structure here and I'll update the wiki later. 


Btw, here are more samples from discord in case someone else would like to check this:
[https://drive.google.com/file/d/1FKz0vb ... pHFs5/view](https://drive.google.com/file/d/1FKz0vbBKoo1ZN3Jq5AqzRBMt0BzpHFs5/view)
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2022-07-05T22:35:49+00:00
- Post Title: Dinosaur King FIL / DIR / BIN extraction (SSZL archive)

Here's the structure of the files:

DIR file - this is a list of the main folders

No header, so divide file size by 40 to get number of entries.  Each entry is as follows:

uint32		Start file index in FIL file for this folder
uint32		Number of files in this folder
char (32)		Full folder path (null-padded to 32 bytes)


FIL file - this is a list of the actual files

No header, files are referenced from the DIR file.  Each entry is 44 bytes as follows:

uint32		File offset in BIN file
uint32		File size
uint32		Compression flag (0 = uncompressed, 1 = compressed)
char (32)		Filename (null-padded to 32 bytes)


If files are compressed, they begin with a 16-byte header as follows:

char (4)		"SSZL"
uint32		Total size of the decompresssed file
uint32		Total size of the compressed file, including this header
uint32		Unknown - maybe some custom value for LZSS decompression
## Post #5
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-07-13T10:21:20+00:00
- Post Title: Dinosaur King FIL / DIR / BIN extraction (SSZL archive)

As DKDave said, compression is probably a variant of LZSS. The final field of the SSZL header is the control value which (usually) denotes a back-reference. If two sequential bytes are control values then the back reference is escaped and a literal is stored instead. There is also a quirk where the back-reference index is decremented if it is larger than the control value but I'm not sure why or if correct.

[Example implementation](https://gist.github.com/barncastle/f931764404b4f5d1d2d93cbd04ac94d8#file-dinokingsszl-cs-L37). FYI, this was hand-rolled from file comparisons rather than debugging the game so could have issues but works for all the PVR files from the original sample.
## Post #6
- Username: terry336
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Mar 30, 2022 5:56 am
- Post datetime: 2022-09-10T09:34:53+00:00
- Post Title: Dinosaur King FIL / DIR / BIN extraction (SSZL archive)

> Reply from barncastle ↑Wed Jul 13, 2022 6:21 pm at Wed Jul 13, 2022 6:21 pm
>
> 
As DKDave said, compression is probably a variant of LZSS. The final field of the SSZL header is the control value which (usually) denotes a back-reference. If two sequential bytes are control values then the back reference is escaped and a literal is stored instead. There is also a quirk where the back-reference index is decremented if it is larger than the control value but I'm not sure why or if correct.

Example implementation. FYI, this was hand-rolled from file comparisons rather than debugging the game so could have issues but works for all the PVR files from the original sample.

Hello, I tried your software, it works for the most of the files, however some nj files and most animations in njm format are unreadable by the Noesis software, are they badly decompressed by your software? Also, I would like to extract the source code of this game rom except that there are only unknown files dating from 1996. So, I wonder if there is no hidden files?

[https://1drv.ms/u/s!AvAalMnZzI2LgcMUaZh ... Q?e=9NpphL](https://1drv.ms/u/s!AvAalMnZzI2LgcMUaZhehqPwhVqSRQ?e=9NpphL)
## Post #7
- Username: terry336
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Mar 30, 2022 5:56 am
- Post datetime: 2022-09-18T12:27:06+00:00
- Post Title: Dinosaur King FIL / DIR / BIN extraction (SSZL archive)

Finally I was able to extract the source code of the first Dinosaur King game in bin format, however I couldn't find any dir and fil files listing the game data files. Can you extract the data from the bin file?

[https://mega.nz/file/am4XRDjb#sRJOR3wcY ... fgmbmDMMJA](https://mega.nz/file/am4XRDjb#sRJOR3wcYnmcQRPX0ZRp7sVTOyOFNA_F4fgmbmDMMJA)
