## Post #1
- Username: saurav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 12:19 am
- Post datetime: 2015-03-22T13:39:53+00:00
- Post Title: Need help with DIZZEL unpacker

Hi,

Can anyone please help me with unpacking DIZZEL .PAC & .pak files ? Files can be downloaded from here
[http://www.uploadmb.com/dw.php?id=1427031258](http://www.uploadmb.com/dw.php?id=1427031258)

I changed the .PAC to .7z & extracted using 7zip, but only one file is extracted which is much smaller in size than the archive.
The .MODEL files within .PAC files can be opened with 3D Object Converter.

Thanks,
Saurav
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-22T15:46:42+00:00
- Post Title: Need help with DIZZEL unpacker

search for 44 44 53 20 7C  in the .pac file. There's 11 findings.

Save your selection in a hexeditor as *.DDS file (H_HEAD_010_N.DDS, normal map):



pac_1_dds.JPG (139 KiB) Viewed 472 times


(Filepath\filename in the pic should belong to the 2nd DDS.)
## Post #3
- Username: saurav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 12:19 am
- Post datetime: 2015-03-24T11:03:41+00:00
- Post Title: Need help with DIZZEL unpacker

It's shakotay2 to my rescue again !!  

Thanks shakotay2. Following your guide I extracted 11 textures.
How to extract the .MODEL files ? I don't need the other files.

Thanks,
Saurav
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-24T13:29:33+00:00
- Post Title: Need help with DIZZEL unpacker

using offzip and hex2obj does the trick:



30250_vbi.JPG (150.06 KiB) Viewed 453 times
## Post #5
- Username: saurav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 12:19 am
- Post datetime: 2015-03-25T11:24:50+00:00
- Post Title: Need help with DIZZEL unpacker

Thanks shakotay2. What arguments you used for offzip ?

In .pac files, the word 'TFSZIP' is found several times. So I've uploaded some files here [http://www.uploadmb.com/dw.php?id=1427273952](http://www.uploadmb.com/dw.php?id=1427273952) that may be useful for unpacking the .pac archives. 

Thanks,
Saurav
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-25T16:30:28+00:00
- Post Title: Need help with DIZZEL unpacker

offzip -a -z -15 PAC_Char_011.bin D:\xxx 0

(PAC_Char_011.bin is a datablock I cut from the pac file.)
## Post #7
- Username: saurav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 12:19 am
- Post datetime: 2015-04-03T17:51:23+00:00
- Post Title: Need help with DIZZEL unpacker

Hi shakotay2,
Sorry for the late reply & thanks a lot for your help. I've extracted a few models using your guide.
However, extracting in this way is very time consuming. An extractor would be very helpful.
Could you please check the files uploaded at [http://www.uploadmb.com/dw.php?id=1427273952](http://www.uploadmb.com/dw.php?id=1427273952) ?
The client can be downloaded from [http://dizzel.ogplanet.com/en/download/game.og](http://dizzel.ogplanet.com/en/download/game.og).

Thanks,
Saurav
## Post #8
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-04-03T19:32:20+00:00
- Post Title: Need help with DIZZEL unpacker

Experimental QuickBMS script, autounpacks TFSZIP files for convenience:

```
# script for QuickBMS http://quickbms.aluigi.org

get DUMMY long
get FSIZE long
get DUMMY long
get FSIZE2 long
get FSIZE2 long
goto 532

for OFFSET = 0 < FSIZE2
	get ID long
	getdstring NAME 260
	
	get SIZE long
	get HASH long # only for TFSZIP
	goto 32 0 SEEK_CUR
	
	savepos OFFSET
	getdstring TEST 6
	
	if TEST == "TFSZIP"
		math OFFSET += 32
		math SIZE -= 32
		log MEMORY_FILE OFFSET SIZE
		callfunction ParseZIP
	else
		log NAME OFFSET SIZE
	endif
	
	math OFFSET += SIZE
	goto OFFSET
next

startfunction ParseZIP
	ComType deflate
	idstring "PK\x03\x04" MEMORY_FILE
	get ver             short MEMORY_FILE
	get flag            short MEMORY_FILE
	get method          short MEMORY_FILE
	get modtime         short MEMORY_FILE
	get moddate         short MEMORY_FILE
	get crc             long  MEMORY_FILE
	get comp_size       long  MEMORY_FILE
	get uncomp_size     long  MEMORY_FILE
	get name_len        short MEMORY_FILE
	get extra_len       short MEMORY_FILE
	getdstring dummy    name_len  MEMORY_FILE
	getdstring extra    extra_len MEMORY_FILE
	savepos zip_offset MEMORY_FILE

	if method == 0
		Log name zip_offset uncomp_size MEMORY_FILE
	else
		CLog name zip_offset comp_size uncomp_size MEMORY_FILE
	endif
endfunction
```
## Post #9
- Username: saurav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 12:19 am
- Post datetime: 2015-04-06T09:02:42+00:00
- Post Title: Need help with DIZZEL unpacker

Thanks a lot barti for the script.This is exactly what I needed. Everthing's working fine.

Thanks,
Saurav
