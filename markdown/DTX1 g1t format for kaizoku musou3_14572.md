## Post #1
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-06-26T18:33:37+00:00
- Post Title: DTX1 g1t format for kaizoku musou3

Hi, I edit a bms script for PC version of this game. It can convert *.g1t to dds(DTX5) but has problem for DTX1. Can someone fix it?

```
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\x80\x00\x00\x00\x80\x00\x00\x00\x00\x20\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"

get dataSize long
get dataOffset long
get texCount long
goto dataOffset
savepos OFFTABLE

set NUM 0
for i = 0 < texCount
math NUM + 1
get NAME BASENAME
string NAME + "_"
string NAME += NUM
string NAME + ".dds"
goto OFFTABLE

set JUMP 0
get JUMP long

savepos OFFTABLE
math JUMP + dataOffset
goto JUMP
get ukn4 byte
get texC byte
get texD byte
get NULL byte

set set1 texD
set set2 texD

math set1 & 0xF0
print "%set1% 1st set1"
math set1 / 16
print "%set1% 2nd set1"
math set2 & 0x0F

if set1 == 0
get unk5 long
else
get unk5 long
get unk6 long
get unk7 long
get unk8 long
endif
savepos OFFSET

set texH 2
set texW 2
Math texW p set1
Math texH p set2

putVarChr MEMORY_FILE 0x0C texH short
putVarChr MEMORY_FILE 0x10 texW short

if texC == 0x01
print "{0x01} ARGB32 Found!"
set bbp 32
math MAGIC = texW
math MAGIC * texH
math MAGIC / 0x4
math MAGIC * 0x10
putVarChr MEMORY_FILE 0x14 MAGIC long
putVarChr MEMORY_FILE 0x50 0x41 long
putVarChr MEMORY_FILE 0x54 0x00 byte
putVarChr MEMORY_FILE 0x55 0x00 byte
putVarChr MEMORY_FILE 0x56 0x00 byte
putVarChr MEMORY_FILE 0x57 0x00 byte
putVarChr MEMORY_FILE 0x58 0x20 long
putVarChr MEMORY_FILE 0x5E 0xFF Short
putVarChr MEMORY_FILE 0x61 0xFF Short
putVarChr MEMORY_FILE 0x64 0xFF Short
putVarChr MEMORY_FILE 0x6B 0xFF Short
endif
if texC == 0x06
print "{0x06} DXT1 Found!"
set bbp 4
math MAGIC = texW
math MAGIC * texH
math MAGIC / 0x2
putVarChr MEMORY_FILE 0x14 MAGIC long
putVarChr MEMORY_FILE 0x50 0x41 long
putVarChr MEMORY_FILE 0x54 0x44 byte
putVarChr MEMORY_FILE 0x55 0x58 byte
putVarChr MEMORY_FILE 0x56 0x54 byte
putVarChr MEMORY_FILE 0x57 0x31 byte
putVarChr MEMORY_FILE 0x58 0x00 long
putVarChr MEMORY_FILE 0x5E 0x00 Short
putVarChr MEMORY_FILE 0x61 0x00 Short
putVarChr MEMORY_FILE 0x64 0x00 Short
putVarChr MEMORY_FILE 0x6B 0x00 Short
endif
if texC == 0x08
print "{0x08} DXT5 Found!"
set bbp 8
math MAGIC = texW
math MAGIC * texH
putVarChr MEMORY_FILE 0x14 MAGIC long
putVarChr MEMORY_FILE 0x50 0x04 long
putVarChr MEMORY_FILE 0x54 0x44 byte
putVarChr MEMORY_FILE 0x55 0x58 byte
putVarChr MEMORY_FILE 0x56 0x54 byte
putVarChr MEMORY_FILE 0x57 0x35 byte
putVarChr MEMORY_FILE 0x58 0x00 long
putVarChr MEMORY_FILE 0x5E 0x00 Short
putVarChr MEMORY_FILE 0x61 0x00 Short
putVarChr MEMORY_FILE 0x64 0x00 Short
putVarChr MEMORY_FILE 0x6B 0x00 Short
endif
set SIZE texH
math SIZE * texW
math bbp / 8
math SIZE * bbp
log NAME 0 0x80 MEMORY_FILE
append
log NAME OFFSET SIZE
append
next i
```

[sample.zip](https://xentaxbackup.github.io/file/11120_sample.zip)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-06-26T22:25:58+00:00
- Post Title: DTX1 g1t format for kaizoku musou3

I don't know much about QuickBMS but i made a Noesis script to open both of your samples  
*script removed*
see this post for proper Noesis python script
[viewtopic.php?p=123534#p123534](http://forum.xentax.com/viewtopic.php?p=123534#p123534)

i couldn't figure out where or how the width and height is stored in your samples but luckily they were both 512x512 
if you can share more samples of various size i might be able to update the script
## Post #3
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-06-26T23:55:08+00:00
- Post Title: DTX1 g1t format for kaizoku musou3

> Reply from AceWell
>
> I don't know much about QuickBMS but i made a Noesis script to open both of your samples  
tex_KaizokuMusou3_g1tg.zip
i couldn't figure out where or how the width and height is stored in your samples but luckily they were both 512x512 
if you can share more samples of various size i might be able to update the script

Unfortunately, quickbms script is the thing for me.
## Post #4
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-06-27T02:37:48+00:00
- Post Title: DTX1 g1t format for kaizoku musou3

Well.. I solve it.

```
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\x80\x00\x00\x00\x80\x00\x00\x00\x00\x20\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"

get dataSize long
get dataOffset long
get texCount long
goto dataOffset
savepos OFFTABLE

set NUM 0
for i = 0 < texCount
math NUM + 1
get NAME BASENAME
string NAME + "_"
string NAME += NUM
string NAME + ".dds"
goto OFFTABLE

set JUMP 0
get JUMP long

savepos OFFTABLE
math JUMP + dataOffset
goto JUMP
get ukn4 byte	#0x10
get texC byte	#0x06
get texD byte	#0x99
get NULL byte

set set1 texD	#0x99
set set2 texD	#0x99

math set1 & 0xF0	#0x99 to 0x90 = 144
print "%set1% 1st set1"
math set1 / 16		#144 / 16 = 9
print "%set1% 2nd set1"
math set2 & 0x0F	#0x99 to 0x09 = 9

get unk5 longlong
get unk6 longlong
savepos OFFSET

set texH 2
set texW 2
Math texW p set1	#2^9 = 512
Math texH p set2	#2^9 = 512

putVarChr MEMORY_FILE 0x0C texH short
putVarChr MEMORY_FILE 0x10 texW short

if texC == 0x06
print "{0x06} DXT1 Found!"
set bbp 4
math MAGIC = texW
math MAGIC * texH
putVarChr MEMORY_FILE 0x14 MAGIC long
putVarChr MEMORY_FILE 0x50 0x04 long
putVarChr MEMORY_FILE 0x54 0x44 byte
putVarChr MEMORY_FILE 0x55 0x58 byte
putVarChr MEMORY_FILE 0x56 0x54 byte
putVarChr MEMORY_FILE 0x57 0x31 byte
putVarChr MEMORY_FILE 0x58 0x00 long
putVarChr MEMORY_FILE 0x5E 0x00 Short
putVarChr MEMORY_FILE 0x61 0x00 Short
putVarChr MEMORY_FILE 0x64 0x00 Short
putVarChr MEMORY_FILE 0x6B 0x00 Short
endif

if texC == 0x08
print "{0x08} DXT5 Found!"
set bbp 8
math MAGIC = texW
math MAGIC * texH
putVarChr MEMORY_FILE 0x14 MAGIC long
putVarChr MEMORY_FILE 0x50 0x04 long
putVarChr MEMORY_FILE 0x54 0x44 byte
putVarChr MEMORY_FILE 0x55 0x58 byte
putVarChr MEMORY_FILE 0x56 0x54 byte
putVarChr MEMORY_FILE 0x57 0x35 byte
putVarChr MEMORY_FILE 0x58 0x00 long
putVarChr MEMORY_FILE 0x5E 0x00 Short
putVarChr MEMORY_FILE 0x61 0x00 Short
putVarChr MEMORY_FILE 0x64 0x00 Short
putVarChr MEMORY_FILE 0x6B 0x00 Short
endif

set SIZE texH		#0x200 = 512
math SIZE * texW	#SIZE = 0x200 * 0x200 = 0x40000
math SIZE / 8
math SIZE * bbp

log NAME 0 0x80 MEMORY_FILE
append
log NAME OFFSET SIZE
append
next i
```
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-06-27T10:13:01+00:00
- Post Title: DTX1 g1t format for kaizoku musou3

> Reply from adol365
>
> Unfortunately, quickbms script is the thing for me.
> Reply from adol365
>
> Well.. I solve it.
great! i would still like to try completing the script though, can you please upload more samples?  

edit
i am lost in your bms script at these parts

```
set set2 texD   #0x99

math set1 & 0xF0   #0x99 to 0x90 = 144
math set1 / 16      #144 / 16 = 9
math set2 & 0x0F   #0x99 to 0x09 = 9

.....

set texH 2
set texW 2
Math texW p set1   #2^9 = 512
Math texH p set2   #2^9 = 512
```
 
how did you know to set set1 and set2 to 0x99?
how did you know to change set1 to 0x90 and where did you get that value from?
and where did you get 0xF0 from?
where did you get the 16 from?
how did you know to change set2 to 0x09 and where did you get that value from?
and where did you get 0x0F from?

are you using a known formula and if so where can i learn more about it?
## Post #6
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-06-27T16:58:22+00:00
- Post Title: DTX1 g1t format for kaizoku musou3

That's my old bms script i made for the dynasty warriors format games.
They store their width and height in the same format as the xbox 360 sdk.
you can look at it here
[viewtopic.php?f=18&t=8102](http://forum.xentax.com/viewtopic.php?f=18&t=8102)
Microsoft did this for fun and to limit the max width and height to 4096 x 4096 on the 360.
Its just raising them to their correct powers 1 , 2 ,4 ,8 , 16 ext till it gets to the correct width and height.
## Post #7
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-06-27T23:25:05+00:00
- Post Title: DTX1 g1t format for kaizoku musou3

Here is the sample files which include ARGB32, DTX1, and DTX5.
[https://drive.google.com/file/d/0B8JGJb ... sp=sharing](https://drive.google.com/file/d/0B8JGJb-FRy_baTR3bzlBOUl4aVk/view?usp=sharing)

And the modified quickbms script for PC version. One can understand this code using hex editor.

```
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\x80\x00\x00\x00\x80\x00\x00\x00\x00\x20\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"

get dataSize long
get dataOffset long
get texCount long
goto dataOffset
savepos OFFTABLE

set NUM 0
for i = 0 < texCount
math NUM + 1
get NAME BASENAME
string NAME + "_"
string NAME += NUM
string NAME + ".dds"
goto OFFTABLE

set JUMP 0
get JUMP long

savepos OFFTABLE
math JUMP + dataOffset
goto JUMP
get ukn4 byte	#0x10
get texC byte	#0x06
get texD byte	#0x99
get NULL byte

set set1 texD	#0x99
set set2 texD	#0x99

math set1 & 0xF0	#0x99 to 0x90 = 144
print "%set1% 1st set1"
math set1 / 16		#144 / 16 = 9
print "%set1% 2nd set1"
math set2 & 0x0F	#0x99 to 0x09 = 9

get unk5 longlong
get unk6 longlong
savepos OFFSET

set texH 2
set texW 2
Math texW p set2	#2^9 = 512
Math texH p set1	#2^9 = 512

putVarChr MEMORY_FILE 0x10 texW short
putVarChr MEMORY_FILE 0x0C texH short

if texC == 0x01
print "{0x01} ARGB32 Found!"
set bbp 32
math MAGIC = texW
math MAGIC * texH
math MAGIC / 4
math MAGIC * 16
putVarChr MEMORY_FILE 0x14 MAGIC long
putVarChr MEMORY_FILE 0x50 0x41 long
putVarChr MEMORY_FILE 0x54 0x00 byte
putVarChr MEMORY_FILE 0x55 0x00 byte
putVarChr MEMORY_FILE 0x56 0x00 byte
putVarChr MEMORY_FILE 0x57 0x00 byte
putVarChr MEMORY_FILE 0x58 0x20 long
putVarChr MEMORY_FILE 0x5E 0xFF Short
putVarChr MEMORY_FILE 0x61 0xFF Short
putVarChr MEMORY_FILE 0x64 0xFF Short
putVarChr MEMORY_FILE 0x6B 0xFF Short
endif
if texC == 0x06
print "{0x06} DXT1 Found!"
set bbp 4
math MAGIC = texW
math MAGIC * texH
math MAGIC / 2
putVarChr MEMORY_FILE 0x14 MAGIC long
putVarChr MEMORY_FILE 0x50 0x04 long
putVarChr MEMORY_FILE 0x54 0x44 byte
putVarChr MEMORY_FILE 0x55 0x58 byte
putVarChr MEMORY_FILE 0x56 0x54 byte
putVarChr MEMORY_FILE 0x57 0x31 byte
putVarChr MEMORY_FILE 0x58 0x00 long
putVarChr MEMORY_FILE 0x5E 0x00 Short
putVarChr MEMORY_FILE 0x61 0x00 Short
putVarChr MEMORY_FILE 0x64 0x00 Short
putVarChr MEMORY_FILE 0x6B 0x00 Short
endif

if texC == 0x08
print "{0x08} DXT5 Found!"
set bbp 8
math MAGIC = texW
math MAGIC * texH
putVarChr MEMORY_FILE 0x14 MAGIC long
putVarChr MEMORY_FILE 0x50 0x04 long
putVarChr MEMORY_FILE 0x54 0x44 byte
putVarChr MEMORY_FILE 0x55 0x58 byte
putVarChr MEMORY_FILE 0x56 0x54 byte
putVarChr MEMORY_FILE 0x57 0x35 byte
putVarChr MEMORY_FILE 0x58 0x00 long
putVarChr MEMORY_FILE 0x5E 0x00 Short
putVarChr MEMORY_FILE 0x61 0x00 Short
putVarChr MEMORY_FILE 0x64 0x00 Short
putVarChr MEMORY_FILE 0x6B 0x00 Short
endif

set SIZE texH		#0x200 = 512
math SIZE * texW	#SIZE = 0x200 * 0x200 = 0x40000
math SIZE / 8
math SIZE * bbp

log NAME 0 0x80 MEMORY_FILE
append
log NAME OFFSET SIZE
append
next i
```
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-06-28T08:18:40+00:00
- Post Title: DTX1 g1t format for kaizoku musou3

> Reply from adol365
>
> Here is the sample files which include ARGB32, DTX1, and DTX5.
.....
And the modified quickbms script for PC version. One can understand this code using hex editor.
Right and thanks for the samples, i guess my questions are mainly about the "and" bitwise operation
because this is the first time i ever encountered a need for it and now i want to understand it a little.   

0x99 = 0xFF
0xF0 = 0x90 = 144 dec
0x0F = 0x09 = 9 dec

> math set1 / 16
i still don't get where the 16 comes from, does that represent 16 bits?
## Post #9
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-06-29T01:48:49+00:00
- Post Title: DTX1 g1t format for kaizoku musou3

he divided by 16 to shift the position.
f5 = 0xF0 + 0x5
he wanted 0xF so he divided by 16
another more common way would be bit.shift
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-15T06:44:57+00:00
- Post Title: DTX1 g1t format for kaizoku musou3

> Reply from adol365
>
> Here is the sample files which include ARGB32, DTX1, and DTX5.
https://drive.google.com/file/d/0B8JGJb ... sp=sharing

finally got around to finishing this Noesis python script that will open all of your samples  


 tex_KaizokuMusou3_g1tg.zip
(1 KiB) Downloaded 260 times
