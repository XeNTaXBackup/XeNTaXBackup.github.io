## Post #1
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2018-11-05T10:33:50+00:00
- Post Title: Help with vertices blocks and faces data!!!

here are two files: One is from fifa11, second from fifa14. Can someone help me converting fifa 11 to fifa14. I've decompressed files.
[HEADS.rar](https://xentaxbackup.github.io/file/15126_HEADS.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-05T11:07:34+00:00
- Post Title: Help with vertices blocks and faces data!!!

> Reply from mita996
>
> here are two files: One is from fifa11, second from fifa14. Can someone help me converting fifa 11 to fifa14.From my experience you'll need a full format analysis (of fifa14, at least) for such; a tedious task generally.



head_192190_0_0_0-rx3.png (178.43 KiB) Viewed 92 times

(They changed from big endian to little endian, btw, a minor problem.)

Face indices blocks and vertex blocks seem to have identical lengths. So in this case the conversion might be possible and simple, can't guarantee, though. With little coding skills you can just do a "big to little endian" conversion and then copy the binary blocks  (FIs and vertex) to the fifa14 head.
## Post #3
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2018-11-05T11:14:36+00:00
- Post Title: Help with vertices blocks and faces data!!!

> Reply from shakotay2
>
> mita996 wrote:here are two files: One is from fifa11, second from fifa14. Can someone help me converting fifa 11 to fifa14.From my experience you'll need a full format analysis (of fifa14, at least) for such; a tedious task generally.
head_192190_0_0_0-rx3.png(They changed from big endian to little endian, btw, a minor problem.)
Actually the fifa 14 head is fifa12, but I converted to fifa14. What can I do precise, sorry I"m noob
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-05T11:17:13+00:00
- Post Title: Help with vertices blocks and faces data!!!

> Reply from mita996
>
> Actually the fifa 14 head is fifa12, but I converted to fifa14. What can I do precise, sorry I"m noobyeah, I was just "expanding" my post. Do you have any coding skills?
## Post #5
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2018-11-05T11:21:25+00:00
- Post Title: Help with vertices blocks and faces data!!!

> Reply from shakotay2
>
> mita996 wrote:Actually the fifa 14 head is fifa12, but I converted to fifa14. What can I do precise, sorry I"m noobyeah, I was just "expanding" my post. Do you have any coding skills?
No master  But I have a will
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-05T11:36:51+00:00
- Post Title: Help with vertices blocks and faces data!!!

> Reply from mita996
>
> shakotay2 wrote:[...]Do you have any coding skills?
No master  But I have a willyeah, that's good   , but not sufficient - 2969 vertex blocks have to be treated via code.



head_vertex_fifa12.png (31.01 KiB) Viewed 88 times

(I'm too busy to care for it atm, maybe later, when I have more spare time.)

(If you have a professional hex editor which can swap data endianess, you could treat the complete blocks, but sadly I don't know the name of such an editor. A, well, forget about this, we've 16 and 32 bit values here to be swapped. Could work, though, swapping 32 bit, BUT tx and ty would be exchanged then.)
## Post #7
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2018-11-05T11:51:20+00:00
- Post Title: Help with vertices blocks and faces data!!!

> Reply from shakotay2
>
> mita996 wrote:shakotay2 wrote:[...]Do you have any coding skills?
No master  But I have a will yeah, that's good   , but not sufficient - 2969 vertex blocks have to be treated via code.
head_vertex_fifa12.png(I'm too busy to care for it atm, maybe later, when I have more spare time.)

(If you have a professional hex editor which can swap data endianess, you could treat the complete blocks, but sadly I don't know the name of such an editor. A, well, forget about this, we've 16 and 32 bit values here to be swapped.)
Ooo it beats me. Can you just one favor for me. I have 5 files need to convert. When you have time, one week, two weeks, not worries. It will take years to understand this... Can I send you files?
## Post #8
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2018-11-05T12:05:36+00:00
- Post Title: Help with vertices blocks and faces data!!!

> Reply from shakotay2
>
> mita996 wrote:shakotay2 wrote:[...]Do you have any coding skills?
No master  But I have a will yeah, that's good   , but not sufficient - 2969 vertex blocks have to be treated via code.
head_vertex_fifa12.png(I'm too busy to care for it atm, maybe later, when I have more spare time.)

(If you have a professional hex editor which can swap data endianess, you could treat the complete blocks, but sadly I don't know the name of such an editor. A, well, forget about this, we've 16 and 32 bit values here to be swapped. Could work, though, swapping 32 bit, BUT tx and ty would be exchanged then.)

You are geniuos, when you have time could you convert these files. There are one scoreboard from fifa 11 and head from fifa11. I've posted also this head, and that makes 2 head files and one scoreboard. I will really appreciate that ))
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-05T12:46:28+00:00
- Post Title: Help with vertices blocks and faces data!!!

> Reply from mita996
>
> You are geniuos,yeah, if I were...  sadly I'm not. I'm trying to reach the "next level" since years now...  and there's too many of them.

Anyways I made a quick 32 bit endianess swap of FIs' and vertex block data of the fifa11 head and pasted them into the fifa12 head. uvs are swapped, too, tx and ty, that's not intended but this file should serve as a testing case only. So all 32 bit data in the 32 BYTES vertex block is swapped. There's a good chance this head may crash the fifa12 game. You have been warned!

fifa12-head  ("converted" from fifa11):


 head_115533_0-192190.zip
(102.68 KiB) Downloaded 14 times
## Post #10
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2018-11-05T14:14:36+00:00
- Post Title: Help with vertices blocks and faces data!!!

> Reply from shakotay2
>
> mita996 wrote:You are geniuos, yeah, if I were...  sadly I'm not. I'm trying to reach the "next level" since years now...  and there's too many of them.

Anyways I made a quick 32 bit endianess swap of FIs' and vertex block data of the fifa11 head and pasted them into the fifa12 head. uvs are swapped, too, tx and ty, that's not intended but this file should serve as a testing case only. So all 32 bit data in the 32 BYTES vertex block is swapped. There's a good chance this head may crash the fifa12 game. You have been warned!

fifa12-head  ("converted" from fifa11):
head_115533_0-192190.zip

Not very recent one good guy said this to me and he successed, but it will help: I copied vertices block and faces data from Fifa 11 file to Fifa 12 file. Then I added new data offsets for each data, vertices and faces number values, data block sizes in Fifa 12 header.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-05T14:36:25+00:00
- Post Title: Help with vertices blocks and faces data!!!

> Reply from mita996
>
> Then I added new data offsets for each data, vertices and faces number values, data block sizes in Fifa 12 header.I wouldn't know why you should do that with the head I uploaded because counts and block sizes didn't change.
## Post #12
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2018-11-05T14:43:48+00:00
- Post Title: Help with vertices blocks and faces data!!!

> Reply from shakotay2
>
> mita996 wrote:Then I added new data offsets for each data, vertices and faces number values, data block sizes in Fifa 12 header.I wouldn't know why you should do that with the head I uploaded because counts and block sizes didn't change.
I thought it will be helpful. Looking forward in the files that I uploaded, of course, when you have time. I will now check the head, that you converted
## Post #13
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2018-11-05T16:10:19+00:00
- Post Title: Help with vertices blocks and faces data!!!

> Reply from shakotay2
>
> mita996 wrote:You are geniuos, yeah, if I were...  sadly I'm not. I'm trying to reach the "next level" since years now...  and there's too many of them.

Anyways I made a quick 32 bit endianess swap of FIs' and vertex block data of the fifa11 head and pasted them into the fifa12 head. uvs are swapped, too, tx and ty, that's not intended but this file should serve as a testing case only. So all 32 bit data in the 32 BYTES vertex block is swapped. There's a good chance this head may crash the fifa12 game. You have been warned!

fifa12-head  ("converted" from fifa11):
The attachment head_115533_0-192190.zip is no longer available

There are some good and some bad news. The good news is that it can be open in cm15 and has no crush in game. But have some head bugs. Take a look
[bug.png](https://xentaxbackup.github.io/file/15131_bug.png)
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-05T16:21:32+00:00
- Post Title: Help with vertices blocks and faces data!!!

> Reply from mita996
>
> The good news is that it can be open in cm15 and has no crush in game."No crush" is great!   (you usually speak of "crash" or freezing)

> But have some head bugs. Take a lookwell, I'm not surprised; as I wrote, tx and ty are swapped. You need to combine 16 bit and 32 bit data endianess swapping in the vertex block to leave the uvs in tx, ty order.
But that would require some coding; it's easy but I'm too busy atm to care for it.

It's  simple swapping of bytes in a binary file, you seriously should think about learning basic coding.

A function would go like this (parameters): starting offset, FVFsize, vertexCount, sizeofdata, dataPos, dataCount
sizeofdata, dataPos, dataCount for the vertices: 4, 0, 3
for the uvs: 2, 20, 2
## Post #15
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2018-11-05T16:48:05+00:00
- Post Title: Help with vertices blocks and faces data!!!

> Reply from shakotay2
>
> mita996 wrote:The good news is that it can be open in cm15 and has no crush in game."No crush" is great!   (you usually speak of "crash" or freezing)
 But have some head bugs. Take a lookwell, I'm not surprised; as I wrote, tx and ty are swapped. You need to combine 16 bit and 32 bit data endianess swapping in the vertex block to leave the uvs in tx, ty order.
But that would require some coding; it's easy but I'm too busy atm to care for it.

It's  simple swapping of bytes in a binary file, you seriously should think about learning basic coding.

A function would go like this (parameters): starting offset, FVFsize, vertexCount, sizeofdata, dataPos, dataCount
sizeofdata, dataPos, dataCount for the vertices: 4, 0, 3
for the uvs: 2, 20, 2

Mate, I would try, but please, when you have time. One week, or whatever, all these 2 heads and one big scoreboard. That is all. I will owe you, and I will try afterwards to practise the coding
## Post #16
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2018-11-21T11:59:09+00:00
- Post Title: Re: Help with vertices blocks and faces data!!!

> Reply from shakotay2
>
> mita996 wrote:Actually the fifa 14 head is fifa12, but I converted to fifa14. What can I do precise, sorry I"m noobyeah, I was just "expanding" my post. Do you have any coding skills?
Master, can you please help me with the faces and scoreboard. I know you are very busy.. I was tryin til this time, but not success
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-21T16:34:14+00:00
- Post Title: Re: Help with vertices blocks and faces data!!!

head with uvs 16 bit (word) swap:


 head_115533_0-192190.zip
(101.5 KiB) Downloaded 15 times
## Post #18
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2018-11-21T16:57:48+00:00
- Post Title: Re: Help with vertices blocks and faces data!!!

> Reply from shakotay2
>
> head with uvs 16 bit (word) swap:
head_115533_0-192190.zip
Awesome, i will fix eyes with blender. Very thankful for this, if you can help with other files, when you have time ) Thank you
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-21T20:54:53+00:00
- Post Title: Re: Help with vertices blocks and faces data!!!

> Reply from mita996
>
> Very thankful for this, if you can help with other files, when you have time ) Thank youwell, guess it's better when you try it for yourself:

This is my endianness swapper for binary 3D model files.
The idea is to swap vertex and face index (FI) data from big endian to little endian or vice versa.

Generally you can swap face index data using a hexeditor supporting byte swapping for WORD (16 bit uint).
For combined data as is for head_192190_0_0_0.rx3 (vertex float and uvs half float) it's not so simple.

Here is where Make_obj-swap.exe will come in handy.
Follow the instructions carefully.

A param.txt file is required (one for the vertex block, another for the FIs, see params-FIs folder)

I won't explain in detail how to create params.txt for different model files
but using hex2obj (another tool of mine) with head_192190_0_0_0.rx3 and the belonging H2O file
should give some understanding.

You can find the rx3 file in the HEADS.rar from the opening post here:
[viewtopic.php?f=16&t=19026](http://forum.xentax.com/viewtopic.php?f=16&t=19026)

instructions
------------
Start Make_obj-swap and load head_192190_0_0_0.rx3; params.txt must be present in the same folder!
A swapped.bin will be created.

RENAME it to swappedv.bin and copy it to the folder params-FI.
Start Make_obj-swap and load swappedv.bin,
another swapped.bin will be created with FIs swapped, too.

Finally you can copy (paste/overwrite) the FIs block (size: FIcount x 2) and the vertex block (size vertexCount x FVFsize)
from that swapped.bin to (FIFA12) head_115533_0.rx3.


 Make_obj-swap.zip
(43.96 KiB) Downloaded 15 times
## Post #20
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2018-11-21T22:37:04+00:00
- Post Title: Re: Help with vertices blocks and faces data!!!

> Reply from shakotay2
>
> mita996 wrote:Very thankful for this, if you can help with other files, when you have time ) Thank youwell, guess it's better when you try it for yourself:

This is my endianness swapper for binary 3D model files.
The idea is to swap vertex and face index (FI) data from big endian to little endian or vice versa.

Generally you can swap face index data using a hexeditor supporting byte swapping for WORD (16 bit uint).
For combined data as is for head_192190_0_0_0.rx3 (vertex float and uvs half float) it's not so simple.

Here is where Make_obj-swap.exe will come in handy.
Follow the instructions carefully.

A param.txt file is required (one for the vertex block, another for the FIs, see params-FIs folder)

I won't explain in detail how to create params.txt for different model files
but using hex2obj (another tool of mine) with head_192190_0_0_0.rx3 and the belonging H2O file
should give some understanding.

You can find the rx3 file in the HEADS.rar from the opening post here:
viewtopic.php?f=16&t=19026

instructions
------------
Start Make_obj-swap and load head_192190_0_0_0.rx3; params.txt must be present in the same folder!
A swapped.bin will be created.

RENAME it to swappedv.bin and copy it to the folder params-FI.
Start Make_obj-swap and load swappedv.bin,
another swapped.bin will be created with FIs swapped, too.

Finally you can copy (paste/overwrite) the FIs block (size: FIcount x 2) and the vertex block (size vertexCount x FVFsize)
from that swapped.bin to (FIFA12) head_115533_0.rx3.
Make_obj-swap.zip
So thankful for this message. You are the greatest and very kind man. Thanks very much!
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-22T19:07:49+00:00
- Post Title: Re: Help with vertices blocks and faces data!!!

> Reply from mita996
>
> You are the greatestNope, this title is reserved for one man only:
Muhammad Ali: The Greatest
## Post #22
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-01-04T15:16:12+00:00
- Post Title: Re: Help with vertices blocks and faces data!!!

> Reply from shakotay2
>
> mita996 wrote:You are the greatestNope, this title is reserved for one man only:
Muhammad Ali: The Greatest

Mate, I've try and try, but always I got an error. Can you please, please do just this more head. It will be New year present. Happy New Year to you, all the best!!
[Head 2019.rar](https://xentaxbackup.github.io/file/15413_Head 2019.rar)
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-01-04T19:59:04+00:00
- Post Title: Re: Help with vertices blocks and faces data!!!

Happy New Year to you, too, and all the best, mita996.
Which kind of error?

You need to understand the instructions in my post as of Wed Nov 21, 2018 9:54 pm.

btw: face indices count and vertex count are the same, so I don't see why it should not work with the actual params.txt files?
## Post #24
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-01-05T11:33:55+00:00
- Post Title: Re: Help with vertices blocks and faces data!!!

> Reply from shakotay2
>
> Happy New Year to you, too, and all the best, mita996.
Which kind of error?

You need to understand the instructions in my post as of Wed Nov 21, 2018 9:54 pm.

btw: face indices count and vertex count are the same, so I don't see why it should not work with the actual params.txt files?

Bro, here is what I did:
1) I've copied head_192190_0_0_0_0.rx3 to the make obj swap folder, I have head_192190_0_0_0_0.rx3 and head_192190_0_0_0_0.h2o now.
2) Now I've stared make make obj and load head_192190_0_0_0_0.rx3 and got swapped.bin, renamed it and copied to the  params-FI folder.
3) Started make obj swap and load swappedv.bin and got swapped.bin  with FIs swapped
4) I don't know how to copy (paste/overwrite) the FIs block (size: FIcount x 2) and the vertex block (size vertexCount x FVFsize)
from that swapped.bin to (FIFA12) head_115533_0.rx3. Are I supposed to do that with hex editor or?
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-01-05T15:30:55+00:00
- Post Title: Re: Help with vertices blocks and faces data!!!

> Reply from mita996
>
> 4) I don't know how to copy (paste/overwrite) the FIs block (size: FIcount x 2) and the vertex block (size vertexCount x FVFsize)
from that swapped.bin to (FIFA12) head_115533_0.rx3. Are I supposed to do that with hex editor or?yep.
## Post #26
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-01-05T16:09:57+00:00
- Post Title: Re: Help with vertices blocks and faces data!!!

> Reply from shakotay2
>
> mita996 wrote:4) I don't know how to copy (paste/overwrite) the FIs block (size: FIcount x 2) and the vertex block (size vertexCount x FVFsize)
from that swapped.bin to (FIFA12) head_115533_0.rx3. Are I supposed to do that with hex editor or?yep.

But how to find FIs block, vertex blocks in hex editior, that is the right question
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-01-05T16:35:02+00:00
- Post Title: Re: Help with vertices blocks and faces data!!!

I assumed you knew how to use hex2obj  ;
H2O file for head_115533_0.rx3:

0x2B0 16524
Vb1
32 20
0x98A0 2969
020100
0x0 255

the rest is simple math:
face indices block: 0x2B0 - 0x83C7, vertex block: 0x98A0  - 0x20BBF
## Post #28
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-01-07T10:47:37+00:00
- Post Title: Re: Help with vertices blocks and faces data!!!

> Reply from shakotay2
>
> I assumed you knew how to use hex2obj  ;
H2O file for head_115533_0.rx3:

0x2B0 16524
Vb1
32 20
0x98A0 2969
020100
0x0 255

the rest is simple math:
face indices block: 0x2B0 - 0x83C7, vertex block: 0x98A0  - 0x20BBF

Master I really want to learn, I look into your tutorial, but I need, also I very need these head. It will be easy If you done it for me, I see no light in the street xd Please, I will be start learning, but just help me with these head
