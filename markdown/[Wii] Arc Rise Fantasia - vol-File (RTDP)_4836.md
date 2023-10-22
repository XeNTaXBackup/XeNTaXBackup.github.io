## Post #1
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2010-08-03T14:51:05+00:00
- Post Title: [Wii] Arc Rise Fantasia - vol-File (RTDP)

Hi,
I was curious about this GRAF maybe someone can tell me how to extract it.
This is what I found out so far:

```
0000000B 1byte - number of files in the archive
0000000C 4bytes - filesize of the archive itself
00000020 40bytes for each compressed file - fileinfo for one compressed file including filename at the beginning
relative offset (for each compressed file): 00000022 2bytes - compressed filesize
```


Im not sure about the size of the compressed files (maybe its some other data and the files arent compressed) but at least the other infos should be right 
Here is a picture in case I didnt make me clear: [](http://www.apload.de)

cya
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-03T22:47:22+00:00
- Post Title: [Wii] Arc Rise Fantasia - vol-File (RTDP)

I approached it differently, but I'm clueless about any compression methods.

See what you make of it.

```
#    xentax.com
#    .vol BMS script

idstring "RTDP"

endian big

get EOH long
get FILES long
get THISSIZE long

goto 0x20

for i = 1 to FILES

  getdstring FILENAME 32
  get FILESIZE long
  get FILEOFFSET long # relative to EOH

  math FILEOFFSET += EOH
  log FILENAME FILEOFFSET FILESIZE

next i

```
## Post #3
- Username: swosho
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-08-04T00:26:04+00:00
- Post Title: [Wii] Arc Rise Fantasia - vol-File (RTDP)

i could make an bms script for this but its simple just xor everything after the first offset that is given with 0x55 then the rest should become clear.
if you still need help let me know but this is simple format once you know that.
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-04T11:31:37+00:00
- Post Title: [Wii] Arc Rise Fantasia - vol-File (RTDP)

> Reply from chrrox
>
> i could make an bms script for this but its simple just xor everything after the first offset that is given with 0x55 then the rest should become clear.
if you still need help let me know but this is simple format once you know that.

Useful info - but silly comment. Just modify the script I posted.

```
#    xentax.com
#    .vol BMS script

idstring "RTDP"

endian big

get EOH long
get FILES long
get THISSIZE long

goto 0x20

for i = 1 to FILES

  getdstring FILENAME 32
  get FILESIZE long
  get FILEOFFSET long # relative to EOH

  filexor 0x55
  math FILEOFFSET += EOH
  log FILENAME FILEOFFSET FILESIZE
  filexor 0

next i

```
## Post #5
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2010-08-04T16:32:05+00:00
- Post Title: [Wii] Arc Rise Fantasia - vol-File (RTDP)

Thanks for the fast reply everyone  Looks like I dont put enough thought in to this...

Could you explain the BMS-script a bit WRS, please?
I got that much: You get the FILENAME with "getdstring FILENAME 32" but what does the 32 stands for (a 32 bytes string)? After that you get FILESIZE and FILEOFFSET. Looking at the btl_auto_demo.vol for example I guess the FILESIZE should be 389152byte for the first and 19488byte for the second file and right after that there is the FILEOFFSET. What I don't understand is how we get to the offsets of the FILESIZE? Jumping to 0x20 and adding 32 bytes is a way to far.
Right after that Im totally lost. Where does the 0x55 comes from and (question to chrrox) how do you found out that the data is xored? Does filexor xors everything behind a given offset? Why is the FILEOFFSET = FILEOFFSET + EOH?

Sorry, for the many questions. Looks more like a school lesson now...

Thanks again

EDIT: Ah, I found out about the 32  I thought its hex but its not. Ok, at least this is clear now.
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-04T21:07:05+00:00
- Post Title: [Wii] Arc Rise Fantasia - vol-File (RTDP)

The data is aligned to 16-byte blocks, which means data is padded to a multiple of 16. The VOL header is only 20 bytes long, but padded to 32 bytes.

In the BMS script, I read the header like this:

```

get EOH long		# Then I read 3 of the 4 integers which follow. I don't read the last because I don't know what it is.
get FILES long
get THISSIZE long

goto 0x20			# This skips to the end padding
# padding 16  		<< this is what i should have used

```


Then come the file headers. This is a single block, and padded at the end;
Then comes the file data. Each file is padded.

FILEOFFSET
When the VOL was created, the generator couldn't use raw offsets to the file data. This is because it didn't calculate the size of the header and file headers, and as a fix, just saved the size as EOH.

So FILEOFFSET is a pointer from the end of the header and file headers, which can be truly found by adding EOH.

xor value
I just didn't look for the xor value, but I had a suspicion the data was still not extracted.

0x00 xor 0x55 = 0x55, and 0x00 is a common byte - so you could have found the xor value easily if you bothered to look.

endian
You didn't mention the endian so I'll just point out that it is big, which is common of Wii titles.
## Post #7
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2010-08-05T14:00:11+00:00
- Post Title: [Wii] Arc Rise Fantasia - vol-File (RTDP)

Nice one, now I got it.  
So the xorvalue was the "U". I didnt know how this xor command worked (if only I had read the quickbms.txt before this...)

Thank you for explaining.
