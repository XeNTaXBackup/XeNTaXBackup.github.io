## Post #1
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2006-10-06T23:15:43+00:00
- Post Title: Biohazard/Resident Evil Outbreak(playstation2)

Hi I am interested in the 3d(model) data and textures of this game
but I can't even figure out which files contain them >.<

From what I have been able to gather the .NBD apears to be
a container it has "momo" and "IECS" like the snp files  but also
"tex" sometimes so I don't know what it is

TIM2(.tm2 and variants .tex .sld) seem to be a picture formats

there are .dat files that could be indexes but mainly they have text
(item desciption) I don't know why but the japanese .dats are
XOR'ed >.< (first time I succesfuly "de'XOR" something :P)

I am not sure what the files are thought
Hope someone can understand more
[File1.rar](https://xentaxbackup.github.io/file/890_File1.rar)
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-10-06T23:42:22+00:00
- Post Title: Biohazard/Resident Evil Outbreak(playstation2)

> Reply from alera
>
> Hi I am interested in the 3d(model) data and textures of this game
but I can't even figure out which files contain them >.<

From what I have been able to gather the .NBD apears to be
a container it has "momo" and "IECS" like the snp files  but also
"tex" sometimes so I don't know what it is

TIM2(.tm2 and variants .tex .sld) seem to be a picture formats

there are .dat files that could be indexes but mainly they have text
(item desciption) I don't know why but the japanese .dats are
XOR'ed >.< (first time I succesfuly "de'XOR" something )

I am not sure what the files are thought
Hope someone can understand more
Any chance you could create a screenshot or a list of what files and folders are on the DVD.
.DAT on PS2 normally contain models and textures, audio aswell.
How did u de - XOR something.
Btw HOW did u know it was XOR anyways?
As i got a PS2 game im TRYIN to figure out for ages now
## Post #3
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2006-10-07T00:00:50+00:00
- Post Title: Biohazard/Resident Evil Outbreak(playstation2)

Sorry I messed up with the attached file size


> Btw HOW did u know it was XOR anyways?
>
> As i got a PS2 game im TRYIN to figure out for ages now

the file itmsge.dat had text string in it and I thought the "e" at the
end could stand for english :) I looked at a similar file itmsg001.dat
but the data was mangled so that is how I knew(more like had a clue)
it was encrypted somehow

the file size was the same so that ruled compression out
it might sound ridiculos but it had FF near the string so I thought that
 might be it :P

What game is it you are trying to figure out?
[File2.rar](https://xentaxbackup.github.io/file/891_File2.rar)
## Post #4
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2006-10-07T00:21:14+00:00
- Post Title: Biohazard/Resident Evil Outbreak(playstation2)

Last attachment

Sorry it seems I misunderstood your question about Xoring

I created a small program that XOR'ed every byte with 0xFF
and saved it to another file(some hex editor can do that thought)
[File3.rar](https://xentaxbackup.github.io/file/892_File3.rar)
## Post #5
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-10-07T09:22:16+00:00
- Post Title: Biohazard/Resident Evil Outbreak(playstation2)

> Reply from alera
>
> Sorry I messed up with the attached file size


Btw HOW did u know it was XOR anyways?
As i got a PS2 game im TRYIN to figure out for ages now 


the file itmsge.dat had text string in it and I thought the "e" at the
end could stand for english  I looked at a similar file itmsg001.dat
but the data was mangled so that is how I knew(more like had a clue)
it was encrypted somehow

the file size was the same so that ruled compression out
it might sound ridiculos but it had FF near the string so I thought that
 might be it 

What game is it you are trying to figure out?
Im tryingt o do MGS3 Snake Eater(the topic is in this forum  if ud like to check it).
Thanks, il look at the XOR thing u posted, see if i cna understand it well enough.
## Post #6
- Username: ech
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Oct 06, 2006 12:04 pm
- Post datetime: 2006-10-08T03:12:32+00:00
- Post Title: Biohazard/Resident Evil Outbreak(playstation2)

a question, what's xor? kinda curious to know.
## Post #7
- Username: Acewell
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-08T07:41:37+00:00
- Post Title: Biohazard/Resident Evil Outbreak(playstation2)

> Reply from ech
>
> a question, what's xor? kinda curious to know.

eXclusive OR. Binary operation. Like AND, OR, NOT. Each bit in a target byte is compared with the bits in a byte to XOR the target byte with. 

The operation sets the resulting bit to 1 only if one of both operators is true. 0 XOR 0 = 0 
1 XOR 0 = 1 
0 XOR 1 = 1 
1 XOR 1 = 0 

Example: 12 XOR 123 00001100 (12) 01111011 (123) 01110111 (119)

Sometimes people XOR data to make it look less like what it would look if they hadn't XORed it. When ever you XOR a byte with another, if you XOR the resulting byte again with the value you previously XORed with, the result will be the original byte. Handy eh?
## Post #8
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-10-11T00:14:34+00:00
- Post Title: Biohazard/Resident Evil Outbreak(playstation2)

> Reply from Mr.Mouse
>
> ech wrote:a question, what's xor? kinda curious to know.

eXclusive OR. Binary operation. Like AND, OR, NOT. Each bit in a target byte is compared with the bits in a byte to XOR the target byte with. 

The operation sets the resulting bit to 1 only if one of both operators is true. 0 XOR 0 = 0 
1 XOR 0 = 1 
0 XOR 1 = 1 
1 XOR 1 = 0 

Example: 12 XOR 123 00001100 (12) 01111011 (123) 01110111 (119)

Sometimes people XOR data to make it look less like what it would look if they hadn't XORed it. When ever you XOR a byte with another, if you XOR the resulting byte again with the value you previously XORed with, the result will be the original byte. Handy eh?
Ahhhhh.
Thanks Mr. Mouse
I have bin WONDERING HOW and what an XOR file would look like now.
Im pretty sure i understand it
thanks again
 *Happy he has leant a new thing*
## Post #9
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2006-10-15T08:51:02+00:00
- Post Title: Biohazard/Resident Evil Outbreak(playstation2)

finaly found the time to post an update :)

I have managed to open the nbd files 

This format is quite complicated due to it being chunk based, I have found around 30 chunk ids so far

after spending 2 whole days looking at the compressed tim2 I decided give up and look for the 3d data that I spoted earlier

the nbd files are chunk based... meaning that unless you know all the basic chunks, traversing the file will be either a pain or imposible and It is also dificult for me to document it :P

---

```

string ID[4] forth byte is padding
int32 Offset
int32 Size
int32 Numobj only used in the texture chunk so far

the main headers ids so I've come across are:
TID = unknown, just found it
TEX = texture
AMO = model(animated model object? :P)
AHI = Bone definitions?
SDW = Animation data?

The main headers are found only at the start of the file :)

The texture chunk is arranged like this
int32 size/offset(relative)-tim2 image(compressed)-int32 size-tim2 image in other words: int32 then image
picture is compressed with I don't know what.. it dosn't do a good job and it though

the model chunk has around 30 subchunk from what I have been able to gather

The main problem with this subchunks is that the header is tiny.. only 12 bytes
with a 4 byte id that can be confused with anything...

SubHeader:
int32 Id
int32 Aux // count of subchunks or objects
int32 offset

here is a list of chunk ids from the model chunk

I have divided the headers in a must enter/ must ignore basis
this should make goinh through the file easier

Must enter(use the offset in the header or read the data)
// Note the model file is divided in objects so you will encounter many of these chunks!
TriStripData1 = 0x00030000  // Triangle strip - run length then indices(int32)
TriStripData2 = 0x00040000  // for what ever reason the chunk is sometimes divided in two.. ugly
stripTexHeader= 0x00050000  // Defines the texture the strips use, aux = numtextures
one int32 per texture, usualy just two number 0 and 1 :P
stripTexData  = 0x00060000  // strip Texture assigments, one int32 per strip Aux=numstrips
Vertex array  = 0x00070000  // 3 float x y z, Aux is the number of vertecies in the chunk
Vertex normals= 0x00080000  // 3 float x y z correspondant to the vertex array chunk
Vertex UV     = 0x000A0000  // 2 floats :) aux = numverts just as above
verts unknown = 0x000B0000  // Unknown vertex chunk four int32 aux is numverts
verts unk 2   = 0x000C0000  // bone wheight? data is inconsistent- 1 or 2 int32 + float aux=numverts
unknown chunk = 0x00100000  // aux = num??? array of int32 - appears in between verts unk2 and tristrips
unk chunk     = 0x00000009  // Aux =num chunks - Leads to matchunk unk2
matchunk unk  = 0x00130000  // look like matrices
matchunk unk2 = 0x0000000A  // UNK AUX = Num Chunks 
unk           = 0x00000000  // UNK AUX = UNK, data 3 or 2 int32
unk           = 0x000f0000
unk           = 0x00120000
unk           = 0x00020000


Must ignore(Read pass this headers, another header should follow)
AMO entry     = 0x00000001  // offset is the size of the entire model chunk
TriStripHeader= 0x00000005  // offset leads to the END of the chunk, use this if you want to read past it
unk           = 0x00000002  // offset is the reminding of the chunk
next object   = 0x00000004  // Points to the Next Object chunk(inside the model chunk)
AHI entry     = 0x0C000000  // aux = size, the ahi and the model chunk have ids with same
number but diferent use so it has to be treated diferently, good idea to stop reading here :P

these are the main headers as ints for easy comparation
(read the headers as ints)
HEADERTEX = 0x00584554
HEADERAMO = 0x004F4D41
HEADERAHI = 0x00494841
HEADERSDW = 0x00574453


```

I'm Sorry if this post is a mess, I just wanted to post it before going to sleep. :)
[hn06.jpg](https://xentaxbackup.github.io/file/921_hn06.jpg)
## Post #10
- Username: ech
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Oct 06, 2006 12:04 pm
- Post datetime: 2006-10-15T09:02:48+00:00
- Post Title: Biohazard/Resident Evil Outbreak(playstation2)

wow, that's good to hear that.
## Post #11
- Username: BillyRubin
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 16, 2007 8:28 am
- Post datetime: 2007-05-17T00:06:09+00:00
- Post Title: Biohazard/Resident Evil Outbreak(playstation2)

Wow.  That's awesome.  Any chance you can upload the models in lwo or 3ds?
## Post #12
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2012-08-22T02:57:41+00:00
- Post Title: Biohazard/Resident Evil Outbreak(playstation2)

so, hey, are you going to show the script mate?
