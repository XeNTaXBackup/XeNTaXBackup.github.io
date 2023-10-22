## Post #1
- Username: Crykin
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 21, 2017 3:11 pm
- Post datetime: 2017-07-21T13:10:55+00:00
- Post Title: Converting .gtf files

Hey there, I have extracted some .gtf files and I need help converting into a readable format.

Here is some of the files in question: .GTFs

Here is the equivalent files from the PC version: .PNGs

I believe that they would be the same image as the file sizes of the .gtfs compare to the PC .pngs match up somewhat.
## Post #2
- Username: Crykin
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 21, 2017 3:11 pm
- Post datetime: 2017-07-21T22:29:55+00:00
- Post Title: Converting .gtf files

Update: I managed to convert one of the background pngs to a dds before using the tool on it. As you can see below the 2 files are very different. I'm not sure if this is because there is some other compression/encryption or something going on OR I'm on a wild goose chase  

Extracted .gtf: Original
.gtf converted from .png: Converted
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-07-22T01:39:55+00:00
- Post Title: Converting .gtf files

here is a bms script to extract the image from compressed gtf  

```

comtype zlib_noerror
get GTF_SIZE asize
get NAME basename
string NAME + "_ext.gtf"
get TOTAL_UNCOMP_SIZE long
savepos TMP
get FIRST_OFFSET long
xmath NUM_BLOCKS "(FIRST_OFFSET - 4) / 4"
goto TMP
for i = 0 < NUM_BLOCKS
	get OFFSET long
	savepos TMP2
	get NEXT_OFFSET long
	if NEXT_OFFSET < 0 
		xmath ZSIZE "GTF_SIZE - OFFSET"
	elif NEXT_OFFSET > GTF_SIZE 
		xmath ZSIZE "GTF_SIZE - OFFSET"
	else
		xmath ZSIZE "NEXT_OFFSET - OFFSET"
	endif
	append
	clog NAME OFFSET ZSIZE ZSIZE
	append
	goto TMP2
next i

```


the extracted texture has a 128 byte big-endian header with width and height stored as shorts at  0x20 and 0x22

edit
here is a Noesis python script to open the extracted texture  


 tex_Terraria_PS3_gtf.zip
(613 Bytes) Downloaded 109 times


supports dxt1

edit again   
found some specs for gtf here
[http://www.psdevwiki.com/ps3/Multimedia ... _Tools#GTF](http://www.psdevwiki.com/ps3/Multimedia_Formats_and_Tools#GTF)

and some gtf tools here
[https://www.tapatalk.com/groups/sfxt_mo ... -t883.html](https://www.tapatalk.com/groups/sfxt_mods/endian-tools-vfx-eff-packer-and-unpacker-and-gtf-t-t883.html)
## Post #4
- Username: Crykin
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 21, 2017 3:11 pm
- Post datetime: 2017-07-22T08:56:35+00:00
- Post Title: Converting .gtf files

Great work man! I actually don't need the Noesis script since the tool now works on the extracted gtf files   

Just one more thing, when the gtf file has more than one texture in the script doesn't work. Here is a file: .gtf (multiple textures)
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-07-22T17:05:01+00:00
- Post Title: Converting .gtf files

ok i updated the bms script   
you can also use offzip to extract the textures if need be

```
offzip -a -1 somename.gtf c:\offzip\extracted
```
## Post #6
- Username: Crykin
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 21, 2017 3:11 pm
- Post datetime: 2017-07-22T18:33:27+00:00
- Post Title: Converting .gtf files

Success! You really know what you're doing, thanks very much for your time
## Post #7
- Username: Nolanbet
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 17, 2022 5:23 am
- Post datetime: 2022-12-16T22:48:02+00:00
- Post Title: Converting .gtf files

I know I am 5 years late, but how you view the textures themselfs?
