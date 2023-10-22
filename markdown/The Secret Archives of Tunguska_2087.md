## Post #1
- Username: ChaDeaM
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Sep 09, 2006 9:06 pm
- Post datetime: 2006-09-10T07:03:34+00:00
- Post Title: The Secret Archives of Tunguska

In the game "The Secret Files: Tunguska", there are archives with SPR extension.
They are uncompressed archives, and each one has a header of 0x40(64) bytes. In the begining of the header there are 4 bytes that contains SPCD.

You can download the demo of the game and see.

The first question is: how to know where is the begining and the and of each file in the archives?

In some of the archives there are files that begins with SLZX, which are compressed archives.
So the second question is: how to uncompress them and extract their contents?

There is already a topic about it in "game request" forum, but I thought the conversation has to move here.
## Post #2
- Username: ChaDeaM
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Sep 09, 2006 9:06 pm
- Post datetime: 2006-09-11T05:48:11+00:00
- Post Title: The Secret Archives of Tunguska

So, SLZX is an archive format of the Amiga.   

It wouldn't be a big problem if the sources of the unpacker (XPK) where only in C, but there are some files there in assembly... 
Is there a way to convert or translate Amiga's ASM to ASMx86?
## Post #3
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-11T06:41:56+00:00
- Post Title: The Secret Archives of Tunguska

I highly doubt they are in the SLZX amiga packing format.

why would a pc developer use an old amiga packer for their data?

currently makes no sense from my point of view..........

but it would be fun if they really is. =)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-11T07:42:45+00:00
- Post Title: The Secret Archives of Tunguska

> Reply from Strobe
>
> I highly doubt they are in the SLZX amiga packing format.

why would a pc developer use an old amiga packer for their data?

currently makes no sense from my point of view..........

but it would be fun if they really is. =)

That wouldn't be the first time. In the past developers have used packing methods from other platforms, even old ones. Amiga crunching methods are as valid as todays methods. Most platforms use similar crunching methods. Sometimes a developer tasked with the packing of files uses an old (and therefore FREE) method for fun, and because it's old, not many will know how it works.
## Post #5
- Username: reima
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 12, 2006 2:53 am
- Post datetime: 2006-09-11T19:09:42+00:00
- Post Title: The Secret Archives of Tunguska

Hi there,

the LZX compression algorithm is not as uncommon today as you might think. Compiled HTML Help files (*.chm) use LZX compression to keep file size down. The brand-new Windows Imaging Format (WIM), a form in which Windows Vista will be deployed, can use a LZX algorithm for compression (amongst others).

Therefore I believe it is quite possible that a game developer might utilise this form of compression today. Although the file format will most certainly not be compatible to the one used on Amiga.

However, I'm off to analyze the header of these SLZX chunks... let's see what we can find out.

Greetings,
reima
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-11T19:50:20+00:00
- Post Title: The Secret Archives of Tunguska

Someone kick me in the head.

I didnt read the LZX out of the SLZX. i took it as the whole word.

i need a vacation........

EDIT: World changed to word.  =/ ....jesus.
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-11T19:59:29+00:00
- Post Title: The Secret Archives of Tunguska

> Reply from reima
>
> Hi there,

the LZX compression algorithm is not as uncommon today as you might think. Compiled HTML Help files (*.chm) use LZX compression to keep file size down. The brand-new Windows Imaging Format (WIM), a form in which Windows Vista will be deployed, can use a LZX algorithm for compression (amongst others).

Therefore I believe it is quite possible that a game developer might utilise this form of compression today. Although the file format will most certainly not be compatible to the one used on Amiga.

However, I'm off to analyze the header of these SLZX chunks... let's see what we can find out.

Greetings,
reima

Exactly, LZX, among other compression formats of today were actually born on yesterday's machines. More then today was there the need to compress files, as the internal memory was often the rate limiting factor, coders had to squeeze the maximum out of the memory that was there. So they created sophisticated compression algorhitms, that were also fast enough to decompress at run-time without interfering with the screen synchronization (there will be those among you who know what I mean  ).
## Post #8
- Username: reima
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 12, 2006 2:53 am
- Post datetime: 2006-09-17T16:00:05+00:00
- Post Title: The Secret Archives of Tunguska

Hi there!

I finally had some time to take a thorough look at those SLZX files. Here's what I've found out:

The actual data is compressed with a LZSS-ish algorithm, which it a variation of the classical LZ77. LZSS is a dictionary encoding technique. This means that the encoder replaces parts of the data with references to matching data in the dictionary. The dictionary is a history of a fixed number of bytes which already passed through the encoder. A dictionary reference is just a offset/length pair.

This leads to the following, quite simple decoding algorithm:
Get the next chunk from the encoded stream
Determine if this chunk is a literal symbol or a reference

If it is a literal symbol, just write it straight to the output stream
If it is a reference, extract offset O and length L. Then copy L bytes from the dictionary to the output stream, starting at position O.
If there are still unread bytes in the input stream, return to 1.While decoding, the dictionary is a history of a fixed number of bytes which already left the decoder (i.e. the bytes already written to the output stream). Initially its content is undetermined. In the decoding process it is first filled up from front to end until it is full and then it begins to "slide". This means that for each byte appended to the end of the dictionary a byte from the beginning gets popped off, thus retaining it's fixed size. That's why LZ77 is also called "sliding window compression". Let me illustrate this:

Legend:
```
             /
           ########
O: 0123456789abcdef -- Output stream
D: 89abcdef
     \
      +-- Dictionary content (? means undetermined)
```


Now watch what happens while decoding:
```
O: 
D: ????????

   ########
O: 0123
D: 0123????

   ######## -- dictionary is full
O: 01234567
D: 01234567

    ######## -- window beginning to slide
O: 012345678
D: 12345678

        ########
O: 0123456789abc
D: 56789abc

           ########
O: 0123456789abcdef
D: 89abcdef
```
etc.


So much for the basics. But now lets get down to the nitty-gritty details (the fun part!). I'll describe them in a FAQ like manner (because I frequently asked this questions to my dear self :))

Q1: What does a reference in the encoded stream look like?

A1: A reference consists of two bytes (R[0] being the first and R[1] being the second one from now on). To extract offset O and length L of the corresponding part of the dictionary, you must split up R[1] into two fields. The five most significant bits are L, the three least significant bits put in front of the eight bits of R[0] are O. You can use the following algorithm to do that:

  O = (R[0] + (R[1] << 8)) & 0x7ff
  L = R[1] >> 3

Update: Thinking about it, it would be much simpler if you just interpreted these two bytes as a single 16 bit word (in little endian/Intel byte order). Then the leftmost 5 bits are the length while the rest (the rightmost 11 bits) are the offset.


Q2: What size does the dictionary have?

A2: Looking at Q1 one can see that the offset part of a reference is a 11-bit value ranging between 0 and 2,047. This indicates that the dictionary might be 2,048 bytes (or 2 KB) wide--which it actually is :)


Q3: How do you determine if a chunk is a literal or a reference?

A3: The first byte of the encoded stream is always a flag byte. It describes the layout of the octuplet immediately following it. An octuplet consists of eight parts (hence the name), each of which can be one of the following:
A single literal: L (= 1 byte)
A reference followed by a single literal: RRL (= 3 bytes) (two Rs due to the fact that a reference is two bytes wide (see Q1))

Let P[n] be the n-th part of the octuplet (null indexed). Then bit n of the flag byte (bit 0 being the least significant bit) determines the type of P[n]. An unset bit means it's of type a, a set bit indicates it's of type b. 

Therefore an octuplet has a size ranging between 8 bytes (only parts of type a) and 24 bytes (only parts of type b).

Some examples for flag bytes and corresponding octuplet byte layouts:
```
O: LLLLLLLL

F: 00000001b
O: RRLLLLLLLL

F: 00000010b
O: LRRLLLLLLL

F: 00100000b
O: LLLLLRRLLL

F: 10011010b
O: LRRLLRRLRRLLLRRL

F: 11111111b
O: RRLRRLRRLRRLRRLRRLRRLRRL
```

The encoded data stream consists of an arbitrary number of flag byte/octuplet pairs immediately following each other.


Q4: Where does the encoded data start?

A4: The encoded data begins immediately after the file header.


Q5: How is the file header structured?

Q5: Each SLZX encoded file starts with the 4 byte sequence 0x53 0x4C 0x5A 0x58 ('SLZX' in ASCII). After that there are two identical DWORDs each of which stands for the size of the original data (i.e. the decoded data). I don't really know why it's there twice. Anyway, this totals to a file header size of 12 bytes, in case you didn't notice.


Q6: What if the encoder hits the end of the input stream while being in the middle of a octuplet?

A6: In that case the remaining parts of the octuplet are marked as literals in the flag byte and can be filled with whatever you like. The decoder knows these padding bytes are to be ignored because of the original data size stored in the header.


Well... I think that's it! Now you should be able to implement a simple decoder for SLZX files. Please feel free to ask any questions which might come up.


As for the format of the SPR container files... didn't have a closer look at them yet. But I will.


Greetings,
reima
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-17T16:31:58+00:00
- Post Title: The Secret Archives of Tunguska

Nice work!!
## Post #10
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-09-22T16:09:01+00:00
- Post Title: The Secret Archives of Tunguska

lzx...it remember times ago when i was young checking warez on amiga..but thats another story
## Post #11
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-09-22T19:34:21+00:00
- Post Title: The Secret Archives of Tunguska

Nice work, reima... Think you could post it on [the WIKI?](http://wiki.xentax.com)
## Post #12
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-09-23T09:38:21+00:00
- Post Title: The Secret Archives of Tunguska

AMAZING!
## Post #13
- Username: john_doe
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2006-09-27T14:20:02+00:00
- Post Title: The Secret Archives of Tunguska

Not bad 
I really should have taken the time to write the specs for this format.

I've figured out most of the format and made a tool for it some time ago (You can download it from [http://gamefileformats.the-underdogs.in ... orer11.zip](http://gamefileformats.the-underdogs.info/files/tunguskaexplorer11.zip) - it's in German but it's not that complicated I think )

I'll try to write down the specs when I have some free time.

To Q5: The size is there twice because the first one belongs to the archive reader that calls the correct decompression funtion according to the ID (SLZX etc.). The second size DWORD then is used by the decompression code itself.
## Post #14
- Username: mikehood
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Jun 20, 2006 1:45 pm
- Post datetime: 2006-10-14T11:27:36+00:00
- Post Title: The Secret Archives of Tunguska

how to build a spr file ?
## Post #15
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-10-14T13:03:07+00:00
- Post Title: The Secret Archives of Tunguska

You don't need build a spr file the game works without that, only need to change a ini file
## Post #16
- Username: Rapid
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 20, 2006 11:32 pm
- Post datetime: 2006-10-24T13:20:40+00:00
- Post Title: 

But to make an installer to the translation, and the gamers can't modify the translation, we need a builder. Please, somebody make one!
## Post #17
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2006-10-24T14:05:41+00:00
- Post Title: 

Even with a Spr builder they could just unpack the Spr and create a new one like you did
## Post #18
- Username: Rapid
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 20, 2006 11:32 pm
- Post datetime: 2006-11-02T08:06:28+00:00
- Post Title: 

I wrote emailts to the creators, but they don't want to answer me! This is ridiculous. They don't want to translate their game, and they can sell more from it?
