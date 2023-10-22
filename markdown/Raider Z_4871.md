## Post #1
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-08-11T22:29:38+00:00
- Post Title: Raider Z

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-16T20:37:35+00:00
- Post Title: Raider Z

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-08-16T23:46:15+00:00
- Post Title: Raider Z

Can you post the specs of the archive if you know them is it some kind of xor?
## Post #4
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-08-17T07:09:13+00:00
- Post Title: Raider Z

nice, will try this later. hoping we can get models moving soon
## Post #5
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2010-08-17T09:49:24+00:00
- Post Title: Raider Z

thx,I download the 1.45 version, Extract all files.
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-17T13:43:04+00:00
- Post Title: Raider Z

> Reply from pixellegolas
>
> nice, will try this later. hoping we can get models moving soon

the elu files are models, ani files are animations.
the elus differ from gunz in that their texture information is in a seperate xml file but the format looks quite similar. i couldnt spend much time on this, but when comparing the versions, i was able to extract the vertex information, which hasn't changed from the other versions. hope to work on this soon, as the realspace engine will be used in gunz 2.


the mrs archive is a zip format with the headers with some byte shifting (see bottom function curtosy of aluigi).

```
log MEMORY_FILE 0 SIZE

comtype deflate

for

	savepos POS MEMORY_FILE
	
	math EOH = POS
	math EOH += 30

	for i = POS < EOH

		callfunction decbytei

	next i

	idstring "PK\x03\x04" MEMORY_FILE
	
	get VERSION 	short MEMORY_FILE
	get BITFLAG 	short MEMORY_FILE
	get COMPVER 	short MEMORY_FILE
	
	get FILEMOD	long MEMORY_FILE
	get CRC32 	long MEMORY_FILE
	get CSIZE 	long MEMORY_FILE
	get USIZE 	long MEMORY_FILE
	
	get FNAMELEN 	short MEMORY_FILE
	get EXTRALEN 	short MEMORY_FILE
	
	math EOFN = EOH
	math EOFN += FNAMELEN
	
	for i = EOH < EOFN

		callfunction decbytei

	next i
	
	getdstring FNAME FNAMELEN MEMORY_FILE
	getdstring EXTRA EXTRALEN MEMORY_FILE
	
	savepos POS MEMORY_FILE
	
	math POS2 = POS
	math POS2 += CSIZE
	
	if COMPVER == 0
	
		log FNAME POS USIZE MEMORY_FILE
		
	elif COMPVER == 8
	
		clog FNAME POS CSIZE USIZE MEMORY_FILE
		
	endif

	goto POS2 MEMORY_FILE

next

startfunction decbytei

	getvarchr BYTE MEMORY_FILE i
	math TMP = BYTE
	math TMP >>= 3
	math BYTE <<= 5
	math BYTE |= TMP
	math BYTE ^= 0xff
	putvarchr MEMORY_FILE i BYTE

endfunction

```


the data is either deflate or raw, and offzip can extract the files. 

```
offzip -a -z -15 file.mrs . 0
```



edit:

can you upload and texture mrs files? or the client.exe? i cant download the beta.
also are there and .pdb files with the client   ?
[obj vertices.zip](https://xentaxbackup.github.io/file/3342_obj vertices.zip)
## Post #7
- Username: WRS
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-08-17T20:34:23+00:00
- Post Title: Raider Z

ah cool thanks for posting the code i found this formula o another site for gunz but i dint know how to make it into bms.
i got bones loading the rest should not be hard.
[bone1.png](https://xentaxbackup.github.io/file/3343_bone1.png)
## Post #8
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-17T21:09:55+00:00
- Post Title: Raider Z

> Reply from chrrox
>
> i got bones loading the rest should not be hard.

from what file?

also, still looking for cbt client download links. the official one no longer works ([http://file.nowcdn.co.kr/down/NeowizGam ... 081113.exe](http://file.nowcdn.co.kr/down/NeowizGames/RAIDERZ/Full/raiderz_full_2010081113.exe))
## Post #9
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-30T11:03:56+00:00
- Post Title: Raider Z

gotten any further with those bones?

i cant make much sense of the face information - there are vertex and uv indexes (both tables are easy to read), and some seem to repeat themselves. its also fustrating to see maiet updating their elu format without changing the version with 0x5007 elu files.
