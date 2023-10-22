## Post #1
- Username: peter2005
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Mar 25, 2016 3:26 pm
- Post datetime: 2016-11-14T20:02:06+00:00
- Post Title: identify algorithm

This is going to be just a shot in the dark.

I'm looking for a help on decompression algo from an old DOS game.
I've spend several hours of debugging with DOSBOX just to find it and to unsuccessfully rewrite it to my tool. 


This is only small part(beginning) of whole code.


```
		xor	cl, cl             - iteration loop
		mov	ax, [si]           - 1st and 2nd byte from compressed data
		mov	dx, [si+1]         - 2nd and 3rd byte from compressed data
		shr	dx, cl
		shr	ax, cl
		or	ah, dl
		shr	dx, 1
		shr	ax, 1
		pushf
		or	ah, dl
		inc	cl
		and	cl, 7              - only 7 times
		jnz	short loc_29F16
		inc	si
		call	sub_29FCF
		popf
		jnb	short loc_29F21
		stosb			  - store decompressed byte


```


Actually algo is is much longer and numerous jump branches are present.

There are also only two constants used 0x1fff 0x3ff.


Any idea what type of algorithm is it?
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-11-15T00:48:31+00:00
- Post Title: identify algorithm

this isn't enough to go on can you dump the disaassembly with addresses?    

also, no idea why this tries shifting right with cl, when cl is 0!
## Post #3
- Username: peter2005
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Mar 25, 2016 3:26 pm
- Post datetime: 2016-11-15T15:15:51+00:00
- Post Title: identify algorithm

Hi , check the attachment , subroutine calls deal mostly with comparing processed file size to total file size and with reading another pair of data.
[dis1.txt.zip](https://xentaxbackup.github.io/file/11920_dis1.txt.zip)
