## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-07T14:47:35+00:00
- Post Title: Beast Sacrifice

I think this is a weird encryption.

It is XOR'd by some key (which I am not too sure about), but after looking for some repeating values, I tried 0x3547FAAD, the file sort of looked like a normal binary .x

Since I know that it is a .x file, I would expect there to be a material list that has a large number of 0's for indexing material, so the key up there is probably the right one.

But it's all scrambled?? 



Like in the beginning you can see "f xo".
Normally, it should be "xof ".
Similarly, that "n bi" should be "bin ".

So ok, every group of 4 bytes appears to be shuffled over by 2 spots, so all we have to do is re-order everything.

But how?
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-07T20:30:53+00:00
- Post Title: Beast Sacrifice

sxm = .x
sxb = .bmp
uep = .png

you have to xor it with the key
3547FAAD

then the file needs to be byte swapped

so if the file went
1 2 3 4
it needs to be swapped to
3 4 1 2


sxb files use the key

74781954
and also need the swap

uep files use the key
D92C5B00

sxm files use the key
8A217D2E

swap bms

```
math count / 4
for i = 0 < count
savepos off1
get tmp1 short
savepos off2
get tmp2 short
putVarChr MEMORY_FILE off1 tmp2 short
putVarChr MEMORY_FILE off2 tmp1 short
next i
get size asize MEMORY_FILE
log NAME 0 SIZE MEMORY_FILE

```

[NAME.png](https://xentaxbackup.github.io/file/4596_NAME.png)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-07T23:15:44+00:00
- Post Title: Beast Sacrifice

So that's how byte swapping works
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-08T13:17:02+00:00
- Post Title: Beast Sacrifice

Oh, what did you use to open the binary .x? directx SDK tools?
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-30T05:54:22+00:00
- Post Title: Beast Sacrifice

Anyone experiencing performance issues with the swap code just get the latest version of quickbms.

Btw the swap code does not work completely correctly because it pretty much assumes a filesize of multiple of 4. Hack in the cases for the leftover bytes?
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-30T11:45:50+00:00
- Post Title: Beast Sacrifice

the easiest hack would be just get the file size then just check how much padding you need to make it a multiple of 4 store it in a memory file and insert that many 0's a the end then swap it in memory and save.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-31T01:01:23+00:00
- Post Title: Beast Sacrifice

Can we create multiple memory files?
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-31T01:03:26+00:00
- Post Title: Beast Sacrifice

yeah in quickbms you can have as many as you want.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-06T07:20:20+00:00
- Post Title: Beast Sacrifice

LOL, they decided to encrypt the file with their 4-byte key, but the leftover bytes they just ignored and didn't bother doing the swap either >.>

Which makes sense I guess. It's not like you can do much with leftover bytes...
Well now the situation is pretty clear.

Here's some horribly ugly code I put together to deal with it lol
It decrypts the file and swaps it as well.

They seem to have a whole bunch of different decryption keys though.
I will be updating the script as I find more keys.

```

startfunction swap
	math count = SIZE
	math count / 4
	for i = 0 < count
		savepos off1 MEMORY_FILE
		get tmp1 short MEMORY_FILE
		savepos off2 MEMORY_FILE
		get tmp2 short MEMORY_FILE
		putVarChr MEMORY_FILE1 off1 tmp2 short
		putVarChr MEMORY_FILE1 off2 tmp1 short
	next i
endfunction

get NAME filename
get SIZE asize

#get the extra bytes
math rem = SIZE
math rem %= 4

#round it to the nearest 4, floored
math NEWSIZE = SIZE
math NEWSIZE /= 4
math NEWSIZE *= 4

#decrypt it
get IDSTRING long
goto 0
if IDSTRING == 0xC2826753 #sxm
	set KEY "0x35 0x47 0xFA 0xAD"
elif IDSTRING == 0x67ECD11B #sxm
	set KEY "0x8A 0x21 0x7D 0x2E"
elif IDSTRING == 0x195B0282 #sxb
	set KEY "0x74 0x78 0x19 0x54"
elif IDSTRING == 0xE84EFC7F #sxm
	set KEY "0x14 x0EC 0x06 0xB7"
elif IDSTRING == 0xB4E0BE8A #Virtual H sxm
	set KEY "0xEC 0x9E 0x98 0xDB"
elif IDSTRING == 0x35528CA5
	set KEY "0x53 0xF6 0x10 0x78"
else
	print "Unknown encryption"
	cleanexit
endif
FileXOR KEY
log MEMORY_FILE 0 NEWSIZE
FILEXOR ""

#add the leftover bytes
math OFFSET = NEWSIZE
goto OFFSET
print %OFFSET%
for i = 0 < rem 
	get tmp byte
	putVarChr MEMORY_FILE OFFSET tmp
	math OFFSET += 1
	goto OFFSET
next i

#swap it
callfunction swap

get size asize MEMORY_FILE1
log NAME 0 SIZE MEMORY_FILE1

```
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-06T08:44:17+00:00
- Post Title: Beast Sacrifice

Here's some more files.
Maybe there's a better way to figure out the XOR key.

The sxm file is not a binary .x file.
It might be ascii .x, don't know.

sxt file is just a bmp file, but I don't have the width or height...
[samples.7z](https://xentaxbackup.github.io/file/5261_samples.7z)
## Post #11
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2012-04-30T16:03:29+00:00
- Post Title: Beast Sacrifice

Hex Workshop has byte-flipping built into it.  Just go to Tools - Operations - Byte Flip, then choose whether to flip it as 16, 32, or 64 bit.  It's a very valuable tool inside of the hex editor.  Hex Workshop also has many more operations other than Byte Flip, such as shifting, rotating, OR, AND, XOR, etc.
