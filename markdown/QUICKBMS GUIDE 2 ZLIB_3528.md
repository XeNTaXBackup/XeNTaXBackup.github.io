## Post #1
- Username: Kataah
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-06-09T03:47:31+00:00
- Post Title: QUICKBMS GUIDE 2 ZLIB

Ok so now that you have mastered tutorial 1 I am going to show you how to work with compressed archives.
We will be working with the game [Astro Ranger](http://astroranger.com/)
Here is the full client [http://astro.nefficient.co.kr/astrorang ... client.exe](http://astro.nefficient.co.kr/astroranger/patchdb/astrorangerclient.exe)

ok so set up our c:\temp directory bye extracting our file BoneObject.hsp
1. to c:\temp
2. create a new text document called astro.bms
3. and place the newest version of quickbms in the folder also.

Ok so open up BoneObject.hsp in your hex editor and lets take a look at it.
[](http://img200.imageshack.us/i/tutorial21x.jpg/)
good we have some plain text.
you will notice I highlighted the first 4 bytes 20 50 53 48 or " PSH" that is a space followed bye P S H.
hmm that seems familiar that is the file extension only backwards. this is know as the idstring
so up until now you would think to write in bms
get IDSTRING long
there is nothing wrong with that but there is a better command
idstring " PSH"
make sure you include the quotes.
so open your bms string and on the first line type
idstring " PSH"
the reason this command is better is it will tell the program not to run if it does not find that string don't try to extract that file.
"aka noob proofing it"

Ok so now lets look at what we can read I see 
Datas\Texture\BoneObject\npc_nagoya_octopus01_body.dds , Datas\Texture\BoneObject\Toon.bmp , Datas\Texture\BoneObject\Toon_a.bmp , Datas\Texture\BoneObject\Toon_zero.bmp
so I will assume there are 4 files in this archive.
well lets look at the next 4 bytes and see what it is 01 00 00 00 hmm that is equal to 00 00 00 01 or 1 and we have more files in this archive than that so we do not know what this represents
so lets write that in bms language
get UNK1 long
this saves those 4 bytes as the variable UNK1.

ok the next 4 bytes are 04 00 00 00 hmm this translates into 00 00 00 04 or 4
hey that is the number of files we counted so lets write that in bms
get FILES long
this saves those 4 bytes as the variable FILES.

the next 4 bytes are 00 00 00 00 well that is equal to zero so for now I will write that in bms
get NULL1 long
this saves those 4 bytes as the variable NULL1

ok now we have reached the first file name Datas\Texture\BoneObject\npc_nagoya_octopus01_body.dds
this is 0x36 bytes long but wait there was no indicator like the last file that told us how long the name is how do we write this?
well lets look for a pattern
Datas\Texture\BoneObject\npc_nagoya_octopus01_body.dds is 0x36
Datas\Texture\BoneObject\Toon.bmp is 0x21
Datas\Texture\BoneObject\Toon_a.bmp is 0x23
Datas\Texture\BoneObject\Toon_zero.bmp is 0x26
hmm I don't see anything that makes that a pattern.
but I do see all the names are followed bye a lot of zero's. how long is the name + the zeros of each file?
Datas\Texture\BoneObject\npc_nagoya_octopus01_body.dds + 0's is 0x80
Datas\Texture\BoneObject\Toon.bmp + 0's is 0x80
Datas\Texture\BoneObject\Toon_a.bmp + 0's is 0x80
Datas\Texture\BoneObject\Toon_zero.bmp + 0's is 0x80
hey they are all the same size when I include the 0's
so in bms I would write this as
getdstring NAME 0x80
this tells it to grab 0x80 bytes and store the text value of it
and as an added feature it will automatically remove trailing 0's 

ok so now we have 0xC bytes before I see the next file name
which is 3 long values
so lets write those in and we will figure out what they represent later.
get UNK2 long
get UNK3 long
get UNK4 long

ok so now we see the name again
we have our pattern so lets write our script based on what we learned
so it would look like this up until now

```
get UNK1 long
get FILES long
get NULL1 long
for i = 0 < FILES
getdstring NAME 0x80
get UNK2 long
get UNK3 long
get UNK4 long
clog NAME OFFSET ZSIZE SIZE
next i
```


ok this may look complex but it is almost identical to the first tutorial file except we added 1 more variable
ZSIZE this represents the compressed file size while SIZE represents the decompressed file size
and we also changed the log command to clog to represent it is a compressed file.

ok so now we have our loop and the commands to extract our files but we still need to fill in the variables
OFFSET ZSIZE SIZE
so that means our 3 unknown values must represent that but how do we know what order they are in?

Well ill let you in on a cool trick follow the file loop to the end start at Datas\Texture\BoneObject\npc_nagoya_octopus01_body.dds and highlight the whole 0x80 length
then add our 3 unknown variables so that means we are highlighting 0x8C for our length. the first file is from 0x10 - 0x9B
so now do this for the rest of the files and you end up at highlighting 0x1B4 - 0x23F
[](http://img30.imageshack.us/i/tutorial22.jpg/)
ok so we reached the end of our loop now what?
well the next 2 bytes are 78 9C and this is an archive extractors best friend when you see this at the start of a file.
78 9C represents the standard zlib compression header 
ok so this means our first file starts there which is at offset 0x240

well lets go back to our first file in the list and look at those unknown variables.
24 72 00 00 is = 00 00 72 24 = 0x7224
80 00 02 00 is = 00 02 00 80 = 0x20080
40 02 00 00 is = 00 00 02 40 = 0x240
I think we have a winner so the third variable is 0x240 aka the offset
so lets update our script

```
get UNK1 long
get FILES long
get NULL1 long
for i = 0 < FILES
getdstring NAME 0x80
get UNK2 long
get UNK3 long
get OFFSET long
clog NAME OFFSET ZSIZE SIZE
next i
```


now that just leaves ZSIZE and SIZE
well bye process of elimination the decompressed file must be bigger than the compressed file so we compare the 2 variables
24 72 00 00 is = 00 00 72 24 = 0x7224
80 00 02 00 is = 00 02 00 80 = 0x20080
well 0x20080 is definitely bigger so we now know the last 2 variables

```
get UNK1 long
get FILES long
get NULL1 long
for i = 0 < FILES
getdstring NAME 0x80
get ZSIZE long
get SIZE long
get OFFSET long
clog NAME OFFSET ZSIZE SIZE
next i
```


now try our code out on the file
open the command prompt and change to the directory
c:\temp
now type
quickbms.exe -l astro.bms BoneObject.hsp .
yay it listed our files without any errors now lets try extracting them
create a folder called extract
and type
quickbms.exe astro.bms BoneObject.hsp extract
if we look in there we now have folders and in those folders are 4 pictures 
we did it.

Let me know if you want more pictures or any way I can improve the tutorials.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-09T11:13:36+00:00
- Post Title: QUICKBMS GUIDE 2 ZLIB

> Reply from chrrox
>
> Let me know if you want more pictures or any way I can improve the tutorials.As I already commented, you could polish its look a bit, e.g. a neat little pdf
## Post #3
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2009-06-09T12:17:36+00:00
- Post Title: QUICKBMS GUIDE 2 ZLIB

You sure are a pdf junkie
## Post #4
- Username: revelation
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-09T12:25:58+00:00
- Post Title: QUICKBMS GUIDE 2 ZLIB

Not really, I'd prefer djvu ([http://djvu.sourceforge.net/](http://djvu.sourceforge.net/)), but unfortunately it's not really well supported
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-09T13:41:30+00:00
- Post Title: QUICKBMS GUIDE 2 ZLIB

imho it's only needed a bit of usage of phpbb code without useless pdf stuff
## Post #6
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-06-09T15:07:35+00:00
- Post Title: QUICKBMS GUIDE 2 ZLIB

instead of commenting the format or typos i'm gonna say:

good tutorial! I am impressed of how much you have learnt in such a small time!
## Post #7
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-06-09T16:24:11+00:00
- Post Title: QUICKBMS GUIDE 2 ZLIB

I Love this Tuts   

I can't imagine what would happen if you make the tut on the Assassin's forge files - if it will happen i'd be in shock!
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-09T16:34:33+00:00
- Post Title: QUICKBMS GUIDE 2 ZLIB

I just remembered, I also tried to create a tutorial some time ago, in fact a video tutorial, but I couldn't finish it.
Maybe this is some inspiration or whatever 

[http://ul.to/v1ms63](http://ul.to/v1ms63)

Edit: This was the original topic: [viewtopic.php?f=22&t=2867](http://forum.xentax.com/viewtopic.php?f=22&t=2867)
## Post #9
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-06-10T16:45:37+00:00
- Post Title: QUICKBMS GUIDE 2 ZLIB

excuse me ! Mr chrrox , bugtest
one question remind me ! about works that facilitated by QUICKBMS ?
is it possible to invoke an individual decomperession method ? like inflate !
for example i have : 
A[DATA] : compressed with deflate .
how can i execute an inflate decompression on A[DATA] ?
if it is possible please write an example line ! thanks a lot for your exhilarate
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-10T17:07:21+00:00
- Post Title: QUICKBMS GUIDE 2 ZLIB

you can specify the desired compression method using the comtype command.
by default it's the zlib one (RFC 1950, windowbits 15) so if you need the raw inflate (RFC 1951, windowbits -15) it's enough to use: comtype inflate

then the decompression can happen in the classical "clog FILENAME OFFSET ZSIZE SIZE" way but in case you need something in memory (from memory, to memory or both) you can do it through the usage of the memory files supported by quickbms.

you can find an example of the usage of inflate with the zip files [here](http://aluigi.org/papers/bms/zip.bms).
## Post #11
- Username: shekofte
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-23T22:41:14+00:00
- Post Title: QUICKBMS GUIDE 2 ZLIB

here is a list i found of zlib headers.

> Here is the full set of 64:
>
> 
>
> Common:
>
> 
>
> 78 01, 78 5e, 78 9c, 78 da
>
> 
>
> Rare:
>
> 
>
> 08 1d, 08 5b, 08 99, 08 d7, 18 19, 18 57, 18 95, 18 d3,
>
> 28 15, 28 53, 28 91, 28 cf, 38 11, 38 4f, 38 8d, 38 cb,
>
> 48 0d, 48 4b, 48 89, 48 c7, 58 09, 58 47, 58 85, 58 c3,
>
> 68 05, 68 43, 68 81, 68 de
>
> 
>
> Very rare:
>
> 
>
> 08 3c, 08 7a, 08 b8, 08 f6, 18 38, 18 76, 18 b4, 18 f2,
>
> 28 34, 28 72, 28 b0, 28 ee, 38 30, 38 6e, 38 ac, 38 ea,
>
> 48 2c, 48 6a, 48 a8, 48 e6, 58 28, 58 66, 58 a4, 58 e2,
>
> 68 24, 68 62, 68 bf, 68 fd, 78 3f, 78 7d, 78 bb, 78 f9
## Post #12
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2010-08-14T09:37:40+00:00
- Post Title: QUICKBMS GUIDE 2 ZLIB

Hi chrrox,
nice tutorial, comes in very handy 
So, yeah. I tried this but I am insecure what I am doing wrong. I use this file:
[](http://img251.imageshack.us/i/140810bmsscript.jpg/)

And wrote this script so far:

```
get IDNO short
get FILES short
for i = 0 < FILES
getdstring NAME 0x40
get UNK1 long
get ZSIZE long
get SIZE long
get OFFSET long
clog NAME OFFSET ZSIZE SIZE
next i

```


The compressed files always start at offset 0x8000, so there is much nullspace. Is there anything I have to add? Because BMS is spitting out an error   
I uploaded the example files here, btw: [http://vuze.celes-network.de/tempfiles/ ... rk_arc.zip](http://vuze.celes-network.de/tempfiles/mhfbenchmark_arc.zip)

(This is my first BMS script so forgive me   )
## Post #13
- Username: eycaramba
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-08-14T11:31:03+00:00
- Post Title: QUICKBMS GUIDE 2 ZLIB

To help you start off always use offzip.exe to scan a small file so you know what values you are looking for.
In the file you sent take title.arc.
the files extracted give the output.

```
- enter in directory: G:\
- zip data to check:  32 bytes
- zip windowBits:     15
- seek offset:        0x00000000  (0)

+------------+-------------+-------------------------+
| hex_offset | blocks_dots | zip_size --> unzip_size |
+------------+-------------+-------------------------+
  0x00008000 ....... 13982 --> 460844
  0x0000b69e . 649 --> 1951


- 2 valid zip blocks found
```


So based on this our bms script would be


```
get version short
get files short
goto 0x8
for i = 0 < files
getdstring name 0x40
get extension long
get zsize long
get size THREEBYTE
get fourty byte
get offset long
string name + .
string name + extension
clog name offset zsize size
next i

```


what pc game is this from capcom monster hunter?
## Post #14
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2010-08-14T15:37:26+00:00
- Post Title: QUICKBMS GUIDE 2 ZLIB

Ah, I see! Thanks! Working like a charm 
It is actually from the benchmark of Monster Hunter Frontier Online (Japan/Korea/Taiwan only).
## Post #15
- Username: fire29demon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 12, 2012 2:26 am
- Post datetime: 2013-12-15T07:17:51+00:00
- Post Title: QUICKBMS GUIDE 2 ZLIB

To start off i didn't want to post on an old topic but i'm not sure where i would post this to get a reply from OP.

I want to extract an archive "xml.dat" [http://rghost.net/50975532](http://rghost.net/50975532) 
It is encoded and any readable language in a hex editor is nonexistent since the text is in Chinese.

I have a snippet from the hex editor:


My current quickBms script is pretty sad 

```
get UNK1 byte
get NULL1 long
get NULL2 long
get NULL3 long
get FILES long
get UNK2 byte
get UNK3 byte
get NULL4 long
get NULL5 long
get NULL6 long
get NULL7 long
get NULL8 long
get NULL9 long
get NULL10 long
get NULL11 long
get NULL12 long
get NULL13 long
get NULL14 long
get NULL15 long
get NULL16 long
get NULL17 long
get NULL18 long
get NULL19 short
for i = 0 < FILES
getdstring NAME 

clog NAME OFFSET ZSIZE SIZE
next i

```


Obviously i'm missing a lot, my question is...on a type of file like this how do i go about figuring out the name of the files and where they stop/new offsets begin etc. since it is all unreadable. I know there's some extractor around these forums for this file type or similar but i want to learn how to do it myself. I have just started to take interest in reverse engineering and the like, so any help or nudge in the right direction would be appreciated, Thanks!
## Post #16
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-12-27T14:42:50+00:00
- Post Title: Re: QUICKBMS GUIDE 2 ZLIB

> Reply from fire29demon
>
> 
Obviously i'm missing a lot, my question is...on a type of file like this how do i go about figuring out the name of the files and where they stop/new offsets begin etc. since it is all unreadable. I know there's some extractor around these forums for this file type or similar but i want to learn how to do it myself. I have just started to take interest in reverse engineering and the like, so any help or nudge in the right direction would be appreciated, Thanks!
This UOSEDALB encrypted and for unpack use [this](https://forum.zone-game.info/showpost.php?p=322114&postcount=27) tool.
## Post #17
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2014-02-26T18:38:36+00:00
- Post Title: Re: QUICKBMS GUIDE 2 ZLIB

chrrox I need help making a quickbms script for the game Code Lyoko: Quest for Infinity.

The file formats are .gcn .cp2 .pc & .psp

[https://dl.dropboxusercontent.com/s/un7 ... 04gsx3qvAg](https://dl.dropboxusercontent.com/s/un7uu11a4vav8iu/Code%20Lyoko%20Quest%20for%20Infinity%20PSPArchives.zip?dl=1&token_hash=AAH9dd7iputi1NsAVIfgLzl_WFTJoigTjdsG04gsx3qvAg)
## Post #18
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2014-03-11T09:19:17+00:00
- Post Title: Re: QUICKBMS GUIDE 2 ZLIB

as i am aware by demand of one of members the sample files for these tutorials there not exist anymore !
by the way i have the chance to recover those files from my old PC and finally i uploaded all samples in such tutorials ...
[http://tbf.me/a/BZAsFR](http://tbf.me/a/BZAsFR)
i hope it be useful !
if there is problem yet let me know can i help ?
