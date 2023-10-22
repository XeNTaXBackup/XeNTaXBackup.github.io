## Post #1
- Username: BeeswaX
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Aug 30, 2006 5:46 am
- Post datetime: 2007-12-17T20:25:28+00:00
- Post Title: RE outbreak textures

i extracted some of the textures from outbreak they were in .sld format which was just a renamed version of a tim2
however there is some damn compression plz someone help me with this
[outbreak texture.zip](https://xentaxbackup.github.io/file/1408_outbreak texture.zip)
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-17T22:59:03+00:00
- Post Title: RE outbreak textures

Well compression is pretty hard to detect.
Can't recognize any technique known to me. Might be a special texture compression.
Best way is to disassemble the exe. Maybe you can upload it and the necessary dlls.

EDIT: Of course only if this is a PC game.
## Post #3
- Username: BeeswaX
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Aug 30, 2006 5:46 am
- Post datetime: 2007-12-18T17:09:32+00:00
- Post Title: RE outbreak textures

> Reply from Rheini
>
> Well compression is pretty hard to detect.
Can't recognize any technique known to me. Might be a special texture compression.
Best way is to disassemble the exe. Maybe you can upload it and the necessary dlls.

EDIT: Of course only if this is a PC game.

nope its a ps2 game
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-18T17:37:03+00:00
- Post Title: RE outbreak textures

Hmm indeed ps2 disassemblers exist. But I don't know how powerful they are. Can you provide the main executable file?
## Post #5
- Username: BeeswaX
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Aug 30, 2006 5:46 am
- Post datetime: 2007-12-18T19:24:08+00:00
- Post Title: RE outbreak textures

> Reply from Rheini
>
> Hmm indeed ps2 disassemblers exist. But I don't know how powerful they are. Can you provide the main executable file?
would that be the .elf ?
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-18T19:33:30+00:00
- Post Title: RE outbreak textures

Yes I guess.
## Post #7
- Username: BeeswaX
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Aug 30, 2006 5:46 am
- Post datetime: 2007-12-18T19:52:53+00:00
- Post Title: RE outbreak textures

i dunno which of these is the usefull one so i packed all files up that could be it
 anyway thnx for trying to help me
[http://tjbp.net/upload/obstuff.zip](http://tjbp.net/upload/obstuff.zip)

EDIT:
i talked with alera, he thinks its a simple RLE compression
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-18T21:18:36+00:00
- Post Title: RE outbreak textures

I don't think so. RLE would prevent long runs like EB EB EB EB or FA FA FA that are present in the file.
## Post #9
- Username: BeeswaX
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Aug 30, 2006 5:46 am
- Post datetime: 2007-12-18T22:41:44+00:00
- Post Title: RE outbreak textures

> Reply from Rheini
>
> I don't think so. RLE would prevent long runs like EB EB EB EB or FA FA FA that are present in the file.

hmm any other ideas then ?
## Post #10
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-18T22:57:28+00:00
- Post Title: RE outbreak textures

Maybe it's some kind of LZ algorithm (look at that TIM2 being uncompressed), but doesn't seem to be LZSS.
## Post #11
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-12-18T23:30:28+00:00
- Post Title: RE outbreak textures

Although the file may not be stricty RLE it does indeed use the technique.

during compression it identifies runs larger than 4 bytes(?) and compreses them into 2 or 4 byte instructions that basicaly fetch the data from a sliding window. I still don't understand it completly but I am positive it works this way, the instructions is what I don't understand. I cna barely fit it in my head and eventualy sometimes it fails when I try to uncompress small blocks manualy to see if I can understand it.

Every 32 bytes is the end of a block and inside this blocks is the instructions encoded as something similar to literal index(first byte) and runlength(second byte) there seems to be more data encoded in the 2 byte intstruction.

instructions look similar and can be put togheter, I can't figure out with precision how does the decompresor tels what is an instructions and what is data. 

the instructions had a maximum runlength(I don't remember how much) so it is normal to see things like fetch[2]run[8]fetch[2]run[8] that explains the runs you mentioned. the minumum literal was like 4 bytes and it then copied those 4 bytes for the run length.

Attached is a picture that if I remember correctly is the compresseed and uncompressed version, one in sld and the other one in dds format so only the data is the same and not the header(forgot the size of the dds header).

BTW the compression achieved is negletable, hence why most files are similar in size to the could be uncompressed version(say always near 65k 16, 32k in size)

I managed to manualy decompress some blocks with my used to be knowledge :P but aparently I dind't writ eit down.. omg I cna't type

BeesWax: Ignore the file I sent you, data there is incorrect.
[Textures.rar](https://xentaxbackup.github.io/file/1411_Textures.rar)
## Post #12
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-18T23:46:57+00:00
- Post Title: RE outbreak textures

So that 41h at the beginning somehow denotes a section with uncompressed data, in this case the FourCC "TIM2".
## Post #13
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-12-18T23:58:07+00:00
- Post Title: RE outbreak textures

Yes it does, all files start with that or 44h I believe :) found some notes:

***************************************
Compressed picture
4104 5449 4D32 0400 0100 0000 0118 3004
UKID                          ITVL
0100 0004 0510 0100 3000 0001 0001 0305
          ITVL

UK = Unknown
ID = counter?
LTR? = Literal? char to copy?(2 bytes)
IT = Instruction
VL = Value(num times)

Value seems to be 8 bits(shift 3 bits)
11111000
1 = repeat count
0 = unk (flags?)

The IT(Instruction):
The it has the number of spaces to go back in the first 5 bits
count 2 bytes before that position to get the literal to copy for the run.
flags(last 3 bits) are still unknown.

if there is no count in the literal or the value then delete and do nothing.
maybe the literal must also exceed the 32 bytes(or 12) or something.

- Spacing is 32 bytes(maximum length of compressed output.)

*************************************

ROLF and don't ask me what it mean! I can't understand what I wrote and is probably incorrect as I write what I discover as I go. the file I recovered from a dead file system and could not retrieve the time stamp so I don't know if it is the latest >.<

Just remembered: that data is wrong, back then I though there where 2 types of data one that was UKID and the ITVL but they are actualy both the same ITVL - instruction and value(2 bytes) is just I didn;t understand the part with the header.

Edit:

At 0x54 in yokotex1.sld and 0xCC in the uncompressed file

Compressed:
0208 080F 0600 1318 0101 0118 0303 0103 0210

ITVL = 1318, 0118, 0210

1318: don't get it but has a run of 3

0118: go back 1(2 byte pairs, first entry in index?) repeat 3 times

 01 index number

 18 = 00011000 shifting to the right 3 times gives us 00000011(3)

0210: select 4 bytes as the literal... ? copy 2 times

the uncompressed file shows this:

0208 080F 0600 0000 0000 0000 0101 0101
0101 0101 0303 0103 0303 0103

it is pretty close  :)

IT must be 4 bits long since it uses pairs of 2, if it was 5 bits the IT will be able to go before the begining of the block that is 32 bytes.

instruction 1318 goes beyond the start of the block... to get 0s? I really don't get it.
## Post #14
- Username: BeeswaX
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Aug 30, 2006 5:46 am
- Post datetime: 2007-12-20T19:37:37+00:00
- Post Title: RE outbreak textures

so any news ?
## Post #15
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-04-24T23:36:23+00:00
- Post Title: RE outbreak textures

> Reply from alera
>
> Yes it does, all files start with that or 44h I believe :) found some notes:

***************************************
Compressed picture
4104 5449 4D32 0400 0100 0000 0118 3004
UKID                          ITVL
0100 0004 0510 0100 3000 0001 0001 0305
          ITVL

UK = Unknown
ID = counter?
LTR? = Literal? char to copy?(2 bytes)
IT = Instruction
VL = Value(num times)

Value seems to be 8 bits(shift 3 bits)
11111000
1 = repeat count
0 = unk (flags?)

The IT(Instruction):
The it has the number of spaces to go back in the first 5 bits
count 2 bytes before that position to get the literal to copy for the run.
flags(last 3 bits) are still unknown.

if there is no count in the literal or the value then delete and do nothing.
maybe the literal must also exceed the 32 bytes(or 12) or something.

- Spacing is 32 bytes(maximum length of compressed output.)

*************************************

ROLF and don't ask me what it mean! I can't understand what I wrote and is probably incorrect as I write what I discover as I go. the file I recovered from a dead file system and could not retrieve the time stamp so I don't know if it is the latest >.<

Just remembered: that data is wrong, back then I though there where 2 types of data one that was UKID and the ITVL but they are actualy both the same ITVL - instruction and value(2 bytes) is just I didn;t understand the part with the header.

Edit:

At 0x54 in yokotex1.sld and 0xCC in the uncompressed file

Compressed:
0208 080F 0600 1318 0101 0118 0303 0103 0210

ITVL = 1318, 0118, 0210

1318: don't get it but has a run of 3

0118: go back 1(2 byte pairs, first entry in index?) repeat 3 times

 01 index number

 18 = 00011000 shifting to the right 3 times gives us 00000011(3)

0210: select 4 bytes as the literal... ? copy 2 times

the uncompressed file shows this:

0208 080F 0600 0000 0000 0000 0101 0101
0101 0101 0303 0103 0303 0103

it is pretty close  :)

IT must be 4 bits long since it uses pairs of 2, if it was 5 bits the IT will be able to go before the begining of the block that is 32 bytes.

instruction 1318 goes beyond the start of the block... to get 0s? I really don't get it.

Hmm, i'm sort of way over my head, but i like math :P.
I'm thinking the instruction is actually 4 bit values and not a byte.
let me explain

Compressed:

```

```


```
what if it's actually: 

true is 0 cushion, false is repetition = 1 /*from what I've seen, consistent*/
how many pairs of bytes = 3    /*consistent*/
loop how many times = 1  /*consistent but fishy, again i'm over my head*/
how many bits?* = 8   /*see below*/

*I'm not sure about this one, by this i mean, how many bits it's reading, if we have two bytes that are this
0000 1111 0000 1011, the first 4 bits of each byte is unused, maybe it cancels it out?
unlikely seeing as the 0101 is kept the same, but still plausible
```


Uncompressed:

```
0101 0101 0303 0103 0303 0103
```


Everything i said is consistent for what i've been supplied with :\.
Feel free to correct me if i'm wrong :)

Also, sorry if i confuse anyone, i have a poor way of explaining myself.
## Post #16
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2008-04-30T00:08:19+00:00
- Post Title: Re: RE outbreak textures

Hello Jamesuminator thanks for the interest 

I don't understand the first part about the cushion. What do you mean with cushion?

I am using the files from Textures.rar. it has 3 files, the compressed sld texture the
uncompressed dds version and a bookmark for hex workshop(the .hbk).

The compressed sld file has a TIM2 header while the dds has a dds header, the only
data that is similar is the picture data that exists in both files. I don't remember the
size of the dds header or for that matter exacly where in the sld file did the header end.
I tend to use the "0x0606 0606" at offset 32h in the sld and 88h in the dds as reference of where the similar data starts 

I know I am repeating myself, just trying to get that clear.

> Hmm, i'm sort of way over my head, but i like math .
>
> I'm thinking the instruction is actually 4 bit values and not a byte.
>
> let me explain

I say it is a byte(2 actualy) because the data is still aligned to a byte, otherwise the
entire file will be offset by a said number of bits and will be unrecognisable.

Hmmm... I think understand what you mean. the instruction is 4 bits inside 2 bytes lol
that is why the "value" "floats"(not always in the same place) inside these 2 bytes am
I correct?

That would make the first 2 bytes(IT) 1318 to be 4 diferent instructions right?
1 0001 I don't understand what you mean by cushion 
2 0011 Pair Count(3)
3 0001 Loops(1)
4 1000 Number of bits(8)

This makes ALOT of sense! Great work 

Problem is I still don't understand how the program will know where to fetch the data.
the 0417 instruction at 66h for exsample I simply don't understand and ignore it. I think it may be an
"end of block"(32 bytes) variable but I have no orientation in the file ot know where the
blocks end or start.

I don't know where this one is located "0000 1111 0000 1011" what or where is this?

Again thanks alot for your interest  it was very helpful.

BTW I know there is little to work with but I am unable to get anything else  for some reason
I am unable to run PCSX2 even though I did a clear install of the OS and everything it just no
longer runs the games. I don't know if beeswax can get more dumps of the textures using that dx
capture program.
## Post #17
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-04-30T03:22:46+00:00
- Post Title: Re: RE outbreak textures

The contents of this post was deleted because of possible forum rules violation.
[TM2 ob.rar](https://xentaxbackup.github.io/file/1499_TM2 ob.rar)
## Post #18
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2008-05-01T02:37:00+00:00
- Post Title: Re: RE outbreak textures

Excuse me  I would like to thank you for your help(and answear your post)
but my mind is just PUT at the moment (as in kaput but I don't know how to spell that) 
I did however "advanced a little bit" and wanted to post it on the board.

********************************************************************************************

I'm not sure how many bit fields are there inside these 2 bytes but I did find it to be
diferent from what was posted before.

first byte contains somewhere the "copy buffer size" basicaly the program simply creates
an infinite buffer that repeates the same pattern over and over again and then prints it
into the file.

the print size is in the 2nd byte and starts at bit 5. I have seen up to 3 bits of the
second byte being used for the size.
00111000
the ones represent the location of the print size inside the 2nd byte.

in the print size value the value 0 means 1, so if the print size is 0 atleast 2 bytes are
printed.(we represend 4 as 3 since 4 will need an extra bit)

the printsize represents the size of the buffer to paste into the file. as I mention before,
the buffer is an infite space with what ever the chosen literal is reapeating itself for
infinity

so if we choose 0505 as the literal the buffer will contain 0505050505050505050505 forever
we then specify the size in pairs to paste.

0118 this instructions specifies a 1 pair buffer(1 pair uploaded to the copy buffer)
and 3 as the size of the buffer to paste. bit 5 and 4 are on that is why it appears as 18 
the paste buffer size includes the current literal I think.. or maybe not lol maybe it 0 is
0 and not 1 

sooooooo in other words if what we have is
0505 0118
the decompressed version would be
0505 0505 0505 0505
it adds 3 more pairs of the buffer that is a repeating 0505 infinite string

if we had chosen a 2 pair buffer then it would be like this:
1234 0505 0218
that would be:
1234 0505 1234 0505

as you can see it just pastes the pairs until it reaches the specified number
and does not copy the literal N number of times as I guess we thought.. or at least I
thought before.

0417 at 0x66 is indeed a end of block variable

I know the position of the first 5 blocks, here they are:
0x02 block start 4104
0x24 6106
0x46 2900
0x68 0417
0x8A 0010

I can't make any sense of those instructions and they seem not to affect the uncompresed
result at all. I am guessing that they somehow help the program know what are the instructions.

When a literal is specified(not filling with 0s) the literal is always 2 bytes long

Known fields end up being
0000011 0011100
=====*1== *2
*1 size of data in pairs to upload to the paste buffer
*2 size of data in pairs to paste into the file from the paste buffer

there are more flags arround like the one that tells it not to fill the buffer with anything
but 0s but I can't figure them out atm 

Update:
the first byte is
00001111 - 4 bits
at 0x74 there are 2 instructionss, the first one specifies a 12 pair buffer and pastes just 2
this buffer reads backwars in the file and even passes another instruction on its way at 0x6E(0118)
so that means the file in not read backwards since this instruction is dependend on the result of 0x6E

```
0303 0103 0210 0417 0103 0101 0301 0118*2
0303 0110 0C10*0118 0701 0409 1B10 1414

```

0C10 grabs 12 pairs before itself into the paste buffer then pastes only 1 pair
*2 0118 pastes 3 extra pairs of 0301 and is need sto be done before 0C10
the isntruction right next to 0C10 another 0118, uses the data from 0C10 and adds 3 more instances.

The output data matches the one from the uncompressed file.
## Post #19
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-05-01T21:42:24+00:00
- Post Title: Re: RE outbreak textures

Cool, Nice how you found that out :D

I tried it out the header, and i managed to decompress the TIM2 header.
And if i understand what you said about 0C10, they're two different sets of instructions on one set of bytes?
taking certain bytes?

hmm, gets pretty complicated.
I've reread over and over, and I just don't get where it's getting the bits or bytes to copy?
I mean for the dual instruction, how does it know which bytes to exactly copy.
And, it's always grouped in pairs right?  Any instances of it not?
I think we're pretty close to getting it all down pat.

Let's hope you can get the last bit :P, i'm not too good at formats.
I just like math ^_^.
## Post #20
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2008-05-02T02:35:28+00:00
- Post Title: Re: RE outbreak textures

The contents of this post was deleted because of possible forum rules violation.
[Msg.zip](https://xentaxbackup.github.io/file/1500_Msg.zip)
## Post #21
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-05-02T21:47:46+00:00
- Post Title: Re: RE outbreak textures

I'm not really sure how to identify these block instructions (the sets that tell us where the instructions are (if i read you right)).
But I'm sure if you can maybe post up one or two samples, i may be able to siphon through it.
I'm thinking the 2 bytes at the beginning may be a block instruction, right?
if so, this would probably be the easiest one to check on, as we already know the header (at least i do :P)
Any way, i'll check it out and post up any findings.

I didn't know that was what you uploaded, mario just told me to give it to you :P.

I'm glad the TIM2TGA converter helped.  I used a lot of static variables so it's pretty amateur, but it works for the most part (not on 4 bit files though).

EDIT:
I read the bit the MSG.txt and it helped alot with the 0c10 instruction bit.
So it reads it almost like ("0310"*5)*8, just inserting brackets in the equation.
thanks, it really did answer my question.

EDIT2:
41 04 :: 65 04  :: 1089
this is the signing of the yoko SLD.
Here's a list of things i've uncovered

compressed header = 0x30 bytes
uncompressed = 0x40(64) bytes
5 instructions     /*Default could be 1, so the instruction count is always one more*/

```

```

becomes

```

```

(I used a known TIM2 header, they're always the same with the same dimensions)

i think the 2 instructions 03 10 61 06  are repeating this part

```

```

but I'm not certain.
When i first decompressed it, i did it really quick and i didn't really notice that.
Hmm, unless i'm missing something...
and the instruction 61 06 doesn't start with 0 or 1 like all the other ones O_o.
Perhaps the 0/1 are actually like string slices or something, not really sure.
Unless all that i'm saying has already been covered and i'm totally lost :P.
## Post #22
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2008-05-02T23:49:28+00:00
- Post Title: Re: RE outbreak textures

Wow.. your right..

The block instruction always has the number of instructions plus one. this could be bacause
we are ignoring the block instruction itself 

I did notice that this consistency stop right when we leave the header... at 0x44 block
instruction 2900 has 3 instructions in its block but it has 00 as the number of instructions.
everthing before that seems to be consistent, including the size(0x40).

The interesting thing about 6106 is that the size it specifies takes into account data
beyond its block... passing 2900... it passes 2900 only until the next 8 byte alingment.
that makes sense as it seems the block instruction can not give odd number or for
that matter any number that is not 8 byte aligned. that is just a theory though(in both
4104 and 6106 bit 1 is not part of the size, it must mean something else then)

After the header everything becomes... bizzare.. I guess all the hidden flags inside the
block instruction suddenly kick in because the picture data is more complicated..
is like going from shallow pool water right into the middle of the ocean...

2900.. if my theory is correct then it has a size of just 32 and
bit flags 8 and 1 are set... don't know its meaning 
hmm I'm thinking 8 and 1... no.. the last 4 bits may be some sort of
"skip" telling it to ignore the next 9 pairs and mark them as data..
080B(at 0x48) can be intepreted as an instruction but its not. so skipping 9 pairs
fixes that. something tells me the program ignores the first pair after
the block instruction by default so that makes 9 actualy 10 and also
positions us where the first instruction in that block is.

the default number of instructions in the block may be 3 and anything
above it needs to be specified. first block(4104) has 4 then next is 6
and the next(2900) has 3 but it is not specified.

> i think the 2 instructions 03 10 61 06 are repeating this part
>
> Code: Select all[00 01 00 01] 03 05 03 10 61 06                   
>
> 
>
> 
>
> but I'm not certain.
>
> When i first decompressed it, i did it really quick and i didn't really notice that.
>
> Hmm, unless i'm missing something...
>
> and the instruction 61 06 doesn't start with 0 or 1 like all the other ones O_o.
>
> Perhaps the 0/1 are actually like string slices or something, not really sure.
>
> Unless all that i'm saying has already been covered and i'm totally lost .
The 6106 instruction is a block instruction so it does not follow the rules of a normal
instruction like 0310

> I'm not really sure how to identify these block instructions (the sets that tell us where the instructions are (if i read you right)).

Identifing block instructions is truely simple.. read 4104 and count 32 bytes after that...
you should be now at 6106.. repeat.. count 32 bytes and you find 2900 etc etc.. block
instructions are always 32 bytes from each other in the compressed file.

I wish I know how to do those fancy colour coded pictures but I don't know how to 

I have attached a file where I uncompress the tim2 header  it has all instructions and block instructions highlighted but it uses brackets so the forum won't allow me to post it again  its rather long so I hope its not dificult to follow.

GRR I keep getting "submitted form was invalid" all the time when I try to post.
[HEADER.zip](https://xentaxbackup.github.io/file/1502_HEADER.zip)
## Post #23
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-05-03T00:43:31+00:00
- Post Title: Re: RE outbreak textures

Thanks man ^_^, I hate chasing my tail some times and getting redundant.
I wasn't sure on the header thing, but it seemed consistent.
I get these block instructions now :P, they seem a bit weird though.
Almost like a waste of space :\. I'll see if i can find more consistencies with 'em.

EDIT:
This may be an odd thing to post, but is this the proper way to approach this decompression.

```
	int bits = cmprssd[-1] & 0x0F;        //00001111
	int rpt = (cmprssed[-1] & 0xF0)>>4;   //11110000
	int size = cmprssd[-2] & 0x0F;        //00001111
	int cush = (cmprssd[-2] & 0xF0)>>4;   //11110000
	int i, x; //forloop
	
	fwrite(cmprssd, 1, size*2, fo);       //size is pair of bytes
	for (i=0;i<rpt;i++) {                 //rpt is how many more times to add it
		if (cush) {                       //if it's a cushion
			for (x=0;x<size;x++){         //repeat for size
				fprintf(fo, "\00\00");    //write null/cushion
			}
		} else {                          //else it's not
			fwrite(cmprssd, 1, size*2, fo);  //write same as before
		}
	}
	return(0);
}

```
?
of course, it wouldn't actually be
cmprssd[-1]
but 
(cmprssd + position_of_instruction + 1)
but i just wrote it like that for short.

The reason I ask is because i'm curious in how this would properly be decompressed.
I was a little timid on the second forloop, but i figured it was simple enough ^_^.

Also, I haven't had any luck with the block instructions.
I'm still working on it though.

PS: sorry if you don't like the way i put my braces.
It seemed to be standard with perl, and i used perl first :P.
## Post #24
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2008-05-07T08:46:48+00:00
- Post Title: Re: RE outbreak textures

I went without internet access for some time  sorry for the late reply

JAVA and K&R(I think) also use that style & I've used it too  I now use an ANSI style I think

```
{
    return;
}

```




,,, is that a working source code?! .. you are addressing an array with a negative number..
what for(Never seen that)?

This is completely theorical.. never compiled.

```
// Program calls function until function returns true.

// check for incorrect instruction syntax
if(!ValidateInstruction(cmprssd)) // Invalid instruction, Skip.
{
   fwrite(cmprssd, 2, fo); // write the data to the output file
   CurPos += 2; // Skip, its just data
   return(false); // we found data & delt with it. continue with next instruction
}

/* Alot of unused/unknown space we have here */
bool Cushion = cmprssd[CurPos - 1] & 0x10 // 00010000 Cushin bit
int SStrSize = (cmprssd[CurPos - 1] & 0x0F) // 00001111 Source String size
int PStrSize = (cmprssd[CurPos] & 0x3C) >> 2 // 00111100 Paste String size

// We use pairs
SStrSize *= 2;
PStrSize *= 2;

// Sorry forgot the syntax for malloc. new is the same, just allocates heap memory
char* SrcBuffer = new char[SStrSize];
char* PsteBuffer = new char[PStrSize];

if(Cushion)
{
    for(int i(0); i < PStrSize; i++) // Fill paste buffer with 0s
    {
        PsteBuffer[i] = 0x00;
    }
fwrite(PsteBuffer, PStrSize, fo); // write to output file
CurPos += 2; // Move on
return(false); // Success
}

// I dont know what the syntax is to read from fo.. 
// Need to move the get pointer for fo back for this to work.
fo -= SStrSize; // position ourselfs
for(int i(0); i < SStrSize; i++) // Fill Source Buffer
{
    SrcBuffer[i] = fo[+i]; // Move fo as we go...
    // ScrBuffer must read from the UNCOMPRESSED(fo) result that we have
}

// copy SrcBuffer into PsteBuffer until PsteBuffer is full
int Offset(0); bool Done(false);
while(!Done)
{
    for(int i(0); i < SStrSize; i++) // Copy pairs from Source to paste buffer
    {
        if((i + offset) > PStrSize) // Make sure we are within PsteBuffer memory
        {
            Done = true;
            break; // finished filling the buffer
        }
        PsteBuffer[i + Offset] = SrcBuffer[i]; i++;
        PsteBuffer[i + Offset] = SrcBuffer[i];
    }
    Offset += SStrSize; // One iteration completed
}

fwrite(PsteBuffer, PStrSize, fo); // write to output file
CurPos += 2; // Move on. notice we move only 1 pair ahead :)
return(false); // Success

```


ValidateInstruction(char*) should tell the program if the instruction has correct syntax by
checking bitfields and range checking the numbers.

for eg. if the instruction is 0x0000 it is invalid as it says nothing.. so it is probably data 

Remember that we don't actualy repeat pairs but buffers or 'windows'. also we don't
paste pairs for a N number of times but instead use a "paste size" that is the size of the
output buffer and we paste our window until the buffer is filled... croping the window if needed.

The block instructions have a fixed position in the file.. 32 bytes apart from each other.

that is.. read 4104(2 bytes.. count FROM THERE(position 2 + 32 bytes) 32 bytes.. read 2 bytes.. skip 2 bytes.. etc

pseudo code:

```
{
    Read(2); // Block instruction
    Skip(32);
    readblockInstruction();
}

```


Its late here and I think I'm getting sick  going to call it a night. hope this helps clear
things for u atlest a little bit.

I will try to make a working program 2morrow for testing.. it won't decompress all the file
ofcourse 

Edit:
hehehehe I never filled the source buffer(SrcBuffer).. Added that
## Post #25
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-05-07T21:32:17+00:00
- Post Title: Re: RE outbreak textures

no it wasn't a working source.
I talked about what i'd have to change (the negative array/pointer indicing, which was actually the 4 bit values of each instruction).
It was just an idea of how the decompression would be done ^_^.
I wasn't really sure as to how you'd go about programming this, and I'm always up for learning.

also, the syntax for malloc is just:

```
int size = getFileSize(fi);   //just a file size function, nothing complicated
buffer = malloc(size);    //allocate this much space @ buffer.

```


Hmm, I hope you can get the source working.
Pm/E-mail me if you need any help, I'm never busy :P.

PS:
No luck yet with the block instructions :(.
## Post #26
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2008-05-08T07:01:17+00:00
- Post Title: Re: RE outbreak textures

WEll here is the code.. its c++ well sort of. I guess I could convert it to c if you need it.. but it is just a prototype atm

I tried to clean it from the mess I made trying to figure out some parts of the file..


The program works fine but it is recognising some data as instructions so the output is still wrong 
I'm sure the block IT is the last thing to fire out.. I just can't figure them out right now..

It decompresses the header just fine but once it gets to the data we NEED those blockITs figured out.
too many collision between data and instructions..

It has absolutly no implementation of the blockIt so not even what we know is being checked with this program.
when it comes to the BlockITs the only thing implemented is a way to know where they are so we can skip it.

Block_Min_It is unverified... infact I think its wrong.. anyway I don;t use it.
[Main.zip](https://xentaxbackup.github.io/file/1509_Main.zip)
## Post #27
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-05-08T22:00:09+00:00
- Post Title: Re: RE outbreak textures

It's All right, I know enough C++ to convert it myself (I'll be sure to credit you for the whole source (sometimes source codes just fly around)).
Nice Job man, ;). I understand how you approached it too ^_^.

I hope you don't mind me editing the method a bit ^_^.
I removing the rereading in Decom; instead i'm just adding "buffer" as an argument.

EDIT:
Pretty much done, not too hard.
I made mine a lot simpler then yours ^_^, I took out the whole struct.
I just don't like working with them is all, don't know enough about properly using them.
It works pretty well, I'll post it up when I clean it up and get it working overall :).

EDIT2:
Alright, all done.
It's still buggy (not surprised), I think yours may still work better ^_^.
It's always nice to have it in C though, I feel it's better then C++.


 SLDx.zip
(1.95 KiB) Downloaded 46 times



Oh also, I thought I'd add this:

```
        OutputSize = (Data[1] & 0x7C) >> 2; // 01111100 Output Buffer size
        InputSize *= 2; // Convert to pairs
        // Output size is in bytes not pairs
        // Validation Checks
        if((Data[0] & 0xE0) != 0) Valid = false;...
```


I got better results with this:

```
        OutputSize = (Data[1] & 0x7C) >> 2; // 01111100 Output Buffer size
        // Output size is in bytes not pairs
        // Validation Checks
        if((Data[0] & 0xE0) != 0) Valid = false;...
```


It seems odd, perhaps a coincidence?
on my source it got rid of 4 more instructions in the first big block of data. (100 bytes or so)

EDIT again:
I was wondering if it's smart on adding a block limiter?
Like counting how many ITs have gone through and making sure it's not over the limit of ITs in that block?
something like

```
...do the decompression...
}

```

I know this can be risky if it's finding wrong values more then right values
but if it's not, it's really useful no?
## Post #28
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2008-05-12T23:56:58+00:00
- Post Title: Re: RE outbreak textures

Smiles  hehehe. it feels nice to see the source in c ^_^;

I use c++ because I feel at ease when prototyping. Encapsulating code and not having to
worry about memory allocation is great. but I must admit it makes following program flow
dificult and some times imposible to read.

> I hope you don't mind me editing the method a bit ^_^.
>
> I removing the rereading in Decom; instead i'm just adding "buffer" as an argument.

- Its your file ^_^; do what ever you want with it 

- There is no need to read from the compressed file in decom as only the instruction
is needed, the rest it reads from the uncompressed file as we go.

Notice what I pass to Decom is OFile(the .tm2 file) and not IFile(the sld file).

so it should be something like this

```
	// Make offset = size of fo
	
	if (!(cushion)) {  //if it's not a cushion
		output = o_buffer+(o_offset-input_size);   //output gets the value
		for (i=0; i<output_size; i+=input_size) {  //for loop for the repetition
			fwrite(output, 1, input_size, fo);  //write to file
		}
	}

```


I don't know if you already fixed this or if they aren't errors at all 
but here are some things I found confusing

In decompress

```
	int cushion = IT[0]&0x10;  //00010000 Cushion Flag
	int input_size = IT[0]&0x0F; //Input buffer size 00001111
	int output_size = (IT[1]&0x7c)>>2; //01111100 Output Buffer size
	//input_size *= 2; //counted by bytes, always in pairs

```


by using input_size in bytes aren't you going halfway in the input buffer?
I don't see any compensation anywhere arround. not only that but now it won't
be aligned to 2.. that would cause serious alignment problems in the output.

also here, inside decompress

```
		output = buffer+(offset-input_size);   //output gets the value
		for (i=0; i<output_size; i+=input_size) {  //for loop for the repetition
			fwrite(output, 1, input_size, fo);  //write to file
		}
	}

```


the forloop arguments could cause trouble since it adds more data in the worst case.

```
i = 0 fwrite...
i = 16 fwrite...
i = 24 condition is now false, break;

```

this way you write 24 bytes instead of 22.. it seems to me like you need to clip the value.

Input size is as far as I know not always evenly divisible by the output size. infact it is sometimes
bigger


As for the block limitere, yes it is a good idea to atleast count them and see if they match
the number in the blockIT. it will get too complicated on my source so I will rewrite it to
treat data block by block instead of the whole file.

One of the more important checks would be the size of the block uncompressed. some blockITs
don't specify this but Ill check that regardless.

at any rate, Great work ! I will begin to manualy uncompress atleast 4 blocks of the data portion of the
file to  make it easier to know what the blockIT values could be.

Edit:

Ha... hahaha.... HAHAHAHAH! .,.. I've been trying to post that thing for 2(or 3) days now!!! HAHAHAHA LOLROLFSLOL ... uuugh.... I feel bad

"The submitted form was invalid. Try submitting again." < -- just what is this anyway? sever busy?
## Post #29
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-05-13T03:04:06+00:00
- Post Title: Re: RE outbreak textures

Thanks for the tips ^_^.

on the matter of 

```

```

I commented it out because I seemed to be getting closer results.
I wasn't sure why, so I had left it like that :\.
I don't think it's right though :P.

I'm not really sure what you mean by 

```

```


isn't output_size always an element of input_size?
so would I do some kind of modulus operator?
or something like:

```

```


or is that too complex?
I added the block counting, it wasn't too hard, just an extra if statement ^_^.

Also, sorry about changing the struct idea you had going on.
I never took the time to fully understand struct.
Beyond ANSI C's tree node struct, I've never really used it. (let alone typedef struct)

PS:
No problem about not posting, never a big deal.
XeNTaX is usually pretty dead anyway, I'm used to waiting for replies.

PPS:
I was thinking of another way to test, but I'm not sure of a good way of fixing it.
Every copied value should be put through Validate, and if it's false, continues.
If it's true, it should some how be excepted and fixed, cept I unno how :(.
mebbe you can think of something ^_^.
## Post #30
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2008-05-13T22:56:13+00:00
- Post Title: Re: RE outbreak textures

> Reply from Jamesuminator
>
> Thanks for the tips ^_^.

on the matter of 
Code: Select all//input_size * =  2

I commented it out because I seemed to be getting closer results.
I wasn't sure why, so I had left it like that :\.
I don't think it's right though .
100% certain input size is in pairs 
the main or should I say the only problem with the decompressor is that it confuses instructions with data. since instructions are so simple and is floating arround rather than on a fixed place like the blockITs, it "collides" with data. we have picture data that is COMPLETELY arbitrary data. the picture will use 0 to 256 to address the pallete. ALL posibilites for an instruction are then also a valid pixel on screen. there HAS to be something that will tell us what data NOT to take within a block.. I believe that is the blocks sole purpose.


> Reply from Jamesuminator
>
> 
I'm not really sure what you mean by 
Code: Select alloutput_size = 22, input_ size = 16;


isn't output_size always an element of input_size?
so would I do some kind of modulus operator?
or something like:
No. It isn't.
Output size is just the size in bytes of what we have to put on the output file. with no regard what so ever
to its input size. its just a buffer size,. in bytes  Notice how input size is 4 bits while output size is 5 bits.. input size is in pairs and output is in bytes.

the outputsize = 22 blabla was just an exsample of how the for loop can fail by adding 2 extra bytes.

The idea here is that we take a string the size of the input size(* by 2!) and create ATLEAST 32 bytes of that. then we paste that into the output file BUT we resize.. in other words we clip or cut the constructed
32 byte string to what ever the output size is. we are not copying pairs here.. atleast not the traditional way.

The thing with c++ is that I used the class vector, which allocates memory on its own(and collects is too)
so its like java in that we can have arrays that resize dynamicaly. obuf and ibuf are just that. ibuf does not
get modified here, only obuf.

```
        {
            OBuf.insert(OBuf.end(), IBuf.begin(), IBuf.end());
            // each insert basicaly adds ibuf at the end of obuf.
            OBuf.insert(OBuf.end(), IBuf.begin(), IBuf.end());
            OBuf.insert(OBuf.end(), IBuf.begin(), IBuf.end());
            OBuf.insert(OBuf.end(), IBuf.begin(), IBuf.end());
        }
        // so by the end obuf is simply filled with ibuf repeated many many times.
    }
    // we then write obuf to the output file but not the entire buffer.. only the size outputsize specified.
    OFile.write(&OBuf[0], IT.OutputSize); // write to output file
    // this way we write what ever outputsize specified.. even if is not aligned to 2 bytes.t
    // that is why we check that on Validate() - input size is a count of pairs(need to * by 2) not bytes
    // output size is a count of bytes.. size of the output :P
    // &OBuf[0] is just an 'idiomatic expression' don't mind it :P

```


What I am doing here is filling a big enough buffer but I only write what is specified in output size.
output size is only a 5 bit number so we know how big the buffer needs to be so it does not underflow.

I'm not sure how to describe this but it is actualy a very simpple concept.
What I did is just a lazy hack.. fill obuf with enough instances of ibuf so that is will fill the 32 bytes.

when I say instances of ibuf I do mean it. ibuf is not a single pair but a full string... a buffer.
inputsize *2 is the size of said buffer in bytes. this needs to be pasted.. inserted in the output file until
outputsize(that is in bytes) is reached. Output size is the EXACT size of the data we have to write to the output file. now that is a rule.. you write what ever is on the buffer until you have written all the bytes specified in output size.

Now I don't know if you understood this part last time but since it is important I will repeat myself again lol

the string(bytes) input size needs to fetch is IN THE OUTPUT. it is not in the original .sld file but what data
you made from the file.. the uncompressed version is where you fetch you data for your input buffer.

In other words we are using data from our output to extend our output. that is why I write everthing that is
not an instruction into the output file. we are going to need it.

I will be posting another source soon. it will be more c like but still c++(prototyping again )

No prob about the struc things.. I'm was going to get rid of it anyway
## Post #31
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-05-14T00:35:33+00:00
- Post Title: Re: RE outbreak textures

I know what you mean, so as to not to accidentally duplicate instructions.
I knew that's why you had the read part.
I think it could work if we just read each block though, then created a string of proper data from that, then wrote it.
But that may be too string/object oriented for something like C :P.

Hmm, I'm not sure how to approach it without rereading the file.
heh, odd.
## Post #32
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2008-05-28T05:08:05+00:00
- Post Title: Re: RE outbreak textures

Attached is a new program that should tell you just how much I have advanced !(nothing!) and the output file offsets.txt that
is the output of the program and interesting bit 

It is a "simple" program that automaticaly prints out the ITs and blockIT by comparing the compressed
and uncompressed data. sadly at 2054 there are 2 very wierd instructions that do not allow the program to continue.

I will analyse the data with care later. I just thought I'll post this here 

BlockIT with all 0s does seem to mean the data is uncompressed 

Warning: Source is a big mess 
[Bin.rar](https://xentaxbackup.github.io/file/1528_Bin.rar)
## Post #33
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-05-28T20:35:06+00:00
- Post Title: Re: RE outbreak textures

Cool, man!

Sorry I haven't replied much.  I've been busy with exams and what not (ick school :P).
All though, I have checked the ITs again.  I do have some suspicion as to how to identify one.
But I'm not 100% certain.  I'll try and get back to you on it ;D.
## Post #34
- Username: BeeswaX
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Aug 30, 2006 5:46 am
- Post datetime: 2009-05-20T18:12:14+00:00
- Post Title: Re: RE outbreak textures

anyone still interested in this ?
