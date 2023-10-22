## Post #1
- Username: nightFlarer
- Rank: beginner
- Number of posts: 33
- Joined date: Thu May 13, 2010 3:25 pm
- Post datetime: 2010-05-29T05:20:21+00:00
- Post Title: [X360] Star Ocean The Last Hope

Hi, just making a request here, hoping someone will help me.

I want to rip the models from this game, in the disc there are two 2-3.5gig .bin files and the default.xex file. I have done some searching for information and the only thing I've found was a bms script for .slz files, which I'm assuming is inside these bin files.

I've cut the first 256000 bytes of both of the .bins with Watto's file cutter as the one in the tool blog didn't work for me. The following link is a zip with both cut .bin files and the default.xex

* snip *

Hope someone can help
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-29T08:46:53+00:00
- Post Title: [X360] Star Ocean The Last Hope

[http://aluigi.org/papers/bms/slz.bms](http://aluigi.org/papers/bms/slz.bms)

it works with both single SLZ files and the whole PACK archives
## Post #3
- Username: nightFlarer
- Rank: beginner
- Number of posts: 33
- Joined date: Thu May 13, 2010 3:25 pm
- Post datetime: 2010-05-29T09:24:45+00:00
- Post Title: [X360] Star Ocean The Last Hope

Hmmm, I'm probably not doing this right.

I've tried the script on soz0.bin and no files were extracted. I tried it on soz1.bin, and it extracted a bunch of .xbcompress files and two .unslz files.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-29T10:29:12+00:00
- Post Title: [X360] Star Ocean The Last Hope

because soz0 is not a slz/pack file
## Post #5
- Username: nightFlarer
- Rank: beginner
- Number of posts: 33
- Joined date: Thu May 13, 2010 3:25 pm
- Post datetime: 2010-05-29T12:19:21+00:00
- Post Title: [X360] Star Ocean The Last Hope

so soz1 is a slz/pack file? what do I do with those .xbcompress and .unslz files that were extracted? They only total up to 78kb.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-29T15:59:04+00:00
- Post Title: [X360] Star Ocean The Last Hope

yes soz1 is a classical pack archive.
the files with the xbcompress extension must be unpacked with the xbdecompress tool (xbox sdk: xbdecompress.exe filename) while for those with the unslz extension are already unpacked
## Post #7
- Username: nightFlarer
- Rank: beginner
- Number of posts: 33
- Joined date: Thu May 13, 2010 3:25 pm
- Post datetime: 2010-05-29T22:56:17+00:00
- Post Title: [X360] Star Ocean The Last Hope

Thanks, it kinda looks like I'm getting somewhere. I'm using xbdecompress 7645 to decompress some of the files and it looks like its working, changing from a few bytes to a few kilobytes. But I still think it's not extracting properly, it has only extracted 14 files, and it's only 70kb.

It's listed like this:
0.xbcompress
1.unslz
2.unslz
3.xbcompress
and continues the pattern all the way down to 13.xbcompress

So it only gives me 12 xbcompress files and 2 unslz files and they're all small compared to the soz1 file which is 2.38gig.
Is there something I'm missing/doing wrong here?
## Post #8
- Username: nightFlarer
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-05-29T23:21:34+00:00
- Post Title: [X360] Star Ocean The Last Hope

the script does work you just need to seperate the pac files its really a game thats more trouble then its worth.

```
#locate first header
findloc RES_START string "PACK\0"
goto RES_START
savepos RES_START
math FILES += 0xFFF

for i = 0 < FILES
math NAME += 1
savepos OFFSET
getdstring BRES 0xC
get SIZE long
string NAME += ".PACK"
log NAME OFFSET SIZE
findloc RES_START string "PACK\0"
goto RES_START

next i

```


```
idstring "PACK"
get unk01 long
get FILES long
get totalsize long
get NAME1 basename
for i = 0 < files
math counter += 1
string NAME += COUNTER
get unk02 long
get unk03 long
get size long
get offset long
log NAME offset size
set NAME string NAME1
next i

```


and after that you still need to run xbe decompress
then the model format is .asf
and that is also like a container.
## Post #9
- Username: nightFlarer
- Rank: beginner
- Number of posts: 33
- Joined date: Thu May 13, 2010 3:25 pm
- Post datetime: 2010-05-30T06:46:39+00:00
- Post Title: [X360] Star Ocean The Last Hope

heh I see what you mean, I've got files all over the place now. But I really want to see this through.

Now I think I'm doing it right now.
First I have extracted the PACK files out of soz1.bin with the first script you've posted, I got about 700 PACK files from that. Then I used aluigi's slz script on the biggest PACK file (which was around 40meg), that extracted a bunch of .xbcompress and .aac files. I took 0.xbcompress and decompressed it, checked it in a hex editor and it had the ASF header. So I guess it's safe to say that this file is a model/container?

Do you have a Max script for the ASF or something? and what do I use the second script you posted on?
Thanks for your time and help!
## Post #10
- Username: nightFlarer
- Rank: beginner
- Number of posts: 33
- Joined date: Thu May 13, 2010 3:25 pm
- Post datetime: 2010-05-31T09:40:34+00:00
- Post Title: [X360] Star Ocean The Last Hope

I'm gonna post a ASF sample, see if anyone wants to have a crack at it.
[http://www.sendspace.com/file/clzubd](http://www.sendspace.com/file/clzubd)

I've already decompressed it, so ignore the .xbcompress file extension. The header says ASF, which should be the model/container format as Chrrox had said and it looks like it has textures in it as well (.AIF?).
## Post #11
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-28T12:10:38+00:00
- Post Title: [X360] Star Ocean The Last Hope

I very quickly maped out the basic format info


```
AIF  - AIF  section textures

ml__ - Material info
used size long
null long
total size long
subid mats long
size of mats long
null long
null long

bnpl - bnpl section

mess -- total info about mesh section
used size long
null long
total sect size long
unk1 long
unk2 long
unk3 long
null long

bnpi - bnpi section

idxl - Face section
vertex size long
null long
total section size long
start offset of first face

vlas - vertex section
vertex size long
null long
null long
null long
unk long
vert size short
null short
start offset of first VERT

rl__ - rl__ section / textures / material


tree - master bone info
attr - boneheader/ bones

```
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-29T04:14:59+00:00
- Post Title: [X360] Star Ocean The Last Hope

Here is  a sample
[so4.png](https://xentaxbackup.github.io/file/3733_so4.png)
## Post #13
- Username: nightFlarer
- Rank: beginner
- Number of posts: 33
- Joined date: Thu May 13, 2010 3:25 pm
- Post datetime: 2010-12-30T05:15:57+00:00
- Post Title: [X360] Star Ocean The Last Hope

Whoa, nice.

How did you find the character files, the last thing I remember is that there were a lot of files and folders that had no extensions, and had only numbers for file names.
## Post #14
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-30T11:54:57+00:00
- Post Title: [X360] Star Ocean The Last Hope

None of that changed. This is just the sample file he posted. the asf files contain a model and anything needed by that model like textures. The costumes and faces seem to be seperated also.
## Post #15
- Username: nightFlarer
- Rank: beginner
- Number of posts: 33
- Joined date: Thu May 13, 2010 3:25 pm
- Post datetime: 2010-12-31T04:24:39+00:00
- Post Title: [X360] Star Ocean The Last Hope

Oh, is that the file I posted a long time ago?
## Post #16
- Username: orbbu
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 20, 2010 5:36 pm
- Post datetime: 2010-12-31T11:26:07+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

@chrrox:

I though that the triaces games were encypted ? any chance this would work on End of Eternity ?
## Post #17
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-31T11:31:34+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

End of Eternity is encrypted
## Post #18
- Username: orbbu
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 20, 2010 5:36 pm
- Post datetime: 2010-12-31T11:46:26+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

k, too bad -.-
## Post #19
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-31T12:48:32+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Star Ocean 3 also used this encryption key and so did star ocean 4 but in those games it was only a few files that did it.
So if someone were good at ps2 reversing they could get the key to decrypt EoE
## Post #20
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-01-05T06:45:31+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Some progress here, chrrox?
## Post #21
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-06-03T14:28:43+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

I'm going to play with this and see what happens.

Edit 24Jun11: Got the vertices/faces figured out. Working on textures.
## Post #22
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-06-28T17:53:06+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Started learning a little OpenGL and about textures in general.
I cut out the largest AIF section so I can look at it on it's own.
5 minutes of learning OpenGL and I realized those 6 imgX sections under the AIF header appear to have something to do with mipmaps, i.e.,
the same 2 bytes in the same area of each successive imgX section is half the value of the previous ranging from 1024-32.
Also I found 21 small chunks of data that stand out amidst the chaos.
Does this have something to do with the texture swizzling or are these compression tables of some sort?
(don't laugh chrrox, I'm just thinking out loud here)
## Post #23
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-28T19:16:52+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Swizzling is the bain of every reverses existence. This is a tool used for speeding up texture loading on the xbox by swapping the bytes around so the console does not have to.
The thing is the swapping is not one set situation it depends on the image type and the image dimensions.
each ao__ section is one model part. that contains all the needed info for that model including its textures. most things have one or 2 textures and the rest of the textures there are the mips.
Also the model format is very complex. They are using bit masking to structure the vertex format.
## Post #24
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-06-29T16:36:39+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from chrrox
>
> Swizzling is the bain of every reverses existence. This is a tool used for speeding up texture loading on the xbox by swapping the bytes around so the console does not have to.
The thing is the swapping is not one set situation it depends on the image type and the image dimensions.
each ao__ section is one model part. that contains all the needed info for that model including its textures. most things have one or 2 textures and the rest of the textures there are the mips.
Also the model format is very complex. They are using bit masking to structure the vertex format.

Thanks for the information. I don't know what I was thinking with the OpenGL thing. DirectX would make more sense.
I noticed some things that would translate there. I looked at how swizzling works.
It looks like it's up to the developer to decide exactly how it's implemented. It's fun learning all this stuff though.
Maybe in a year or two I'll know as much as you. In the mean time......
## Post #25
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-07-06T08:43:16+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Will this script work to rip the models from the PS3 version or Xbox 360 ISO?

[http://www.aluigi.org/papers/bms/slz.bms](http://www.aluigi.org/papers/bms/slz.bms)
## Post #26
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-07-07T03:49:07+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from Aurangzeb56
>
> Will this script work to rip the models from the PS3 version or Xbox 360 ISO?

http://www.aluigi.org/papers/bms/slz.bms
That's something weird I noticed. I can get the newer .2 version to work on the PS3 files, but not the 360.
The older version of that script will work on the 360, but not the PS3.
## Post #27
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-07-07T07:42:05+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from TheDude
>
> Aurangzeb56 wrote:Will this script work to rip the models from the PS3 version or Xbox 360 ISO?

http://www.aluigi.org/papers/bms/slz.bms
That's something weird I noticed. I can get the newer .2 version to work on the PS3 files, but not the 360.
The older version of that script will work on the 360, but not the PS3.

Oh,can you give me the newer version of the script then? ^^
Since i have star ocean the last hope international for PS3. ^^"

EDIT: I found out the link i posted WAS the version 2. ^^" Anyway can you tell me that which file do we have to choose in quick BMS script with this script that it will let me extract the models,worlds,weapons and etc?
## Post #28
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-07-09T19:41:13+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from Aurangzeb56
>
> TheDude wrote:Aurangzeb56 wrote:Will this script work to rip the models from the PS3 version or Xbox 360 ISO?

http://www.aluigi.org/papers/bms/slz.bms
That's something weird I noticed. I can get the newer .2 version to work on the PS3 files, but not the 360.
The older version of that script will work on the 360, but not the PS3.

Oh,can you give me the newer version of the script then? ^^
Since i have star ocean the last hope international for PS3. ^^"

EDIT: I found out the link i posted WAS the version 2. ^^" Anyway can you tell me that which file do we have to choose in quick BMS script with this script that it will let me extract the models,worlds,weapons and etc?
Use it on aska0000.bin (incidentally that file's named after their game engine "ASKA")
then you should get a bunch of PACK files. Use the same script on whichever one of those you want and you'll get a bunch more files.
## Post #29
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-07-10T11:19:20+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from TheDude
>
> Use it on aska0000.bin (incidentally that file's named after their game engine "ASKA")
then you should get a bunch of PACK files. Use the same script on whichever one of those you want and you'll get a bunch more files.

Well i tried the script on aska0000.bin and this is what i got. 




I also tried the over 4_GB Quick BMS program and it showed this message:




Also I'm using the script that i posted and i think that one is for 360 version,do you have the PS3 version?
Could you help me?
## Post #30
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-07-10T21:13:08+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

This should be the one I used:
[http://aluigi.altervista.org/papers/bms/slz.bms](http://aluigi.altervista.org/papers/bms/slz.bms)
## Post #31
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-07-11T04:23:05+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from TheDude
>
> This should be the one I used:
http://aluigi.altervista.org/papers/bms/slz.bms

Hmm this is the one i'm using but it's giving me the same error. :/
## Post #32
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-07-11T18:33:40+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Do you have the latest version of QuickBMS?
I'm using 0.3.14c.
(I would probably be more help if I hadn't deleted the file.  )
## Post #33
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-07-12T10:17:32+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from TheDude
>
> Do you have the latest version of QuickBMS?
I'm using 0.3.14c.
(I would probably be more help if I hadn't deleted the file.  )

Hmm does that version has a above 4gb file extractor?Besides i'm using the latest one with support for over 4Gb files too since aska0000.bin is a 22 GB file how were you able to open it in QuickBMS?Also i tried this script into extracting the files from star Ocean 3 Till the end of time since i figured even that uses SLZ file type format but it gave me the same error saying:

Signature of 4 bytes doesn't match the one expected by the script"

this one:  "random number"                        (random sign)
(random string)

expected: "PACK"                                        PACK
50 41 43 4b


I think there is an error in the script? 

EDIT: Well i used the first script posted by Chrrox on aska0000.bin and it extracted alot of .pack files.I used the slz script on thos pack files and i got lot of .unslz and .ADTS files,well i can say that ADTS files are audio file but how do it extract models from the unslz file to view them on 3DS Max?
## Post #34
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-07-13T03:15:34+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Whoops. Sorry. I forgot about that step. I haven't dumped any files in a while... 
The files you want have a ASF header. Try PACK 9, file 3 for instance.
As far as extracting the models go, watch these:
[http://www.youtube.com/watch?v=1ORnfYnlXOw](http://www.youtube.com/watch?v=1ORnfYnlXOw)
## Post #35
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-07-13T17:41:07+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from TheDude
>
> Whoops. Sorry. I forgot about that step. I haven't dumped any files in a while... 
The files you want have a ASF header. Try PACK 9, file 3 for instance.
As far as extracting the models go, watch these:
http://www.youtube.com/watch?v=1ORnfYnlXOw

It's alright,i saw the video and well it was complicated for me to understand. :/
Isn't their like a script already made to extract the models from the unslz files? :/
## Post #36
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-07-13T23:35:36+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from Aurangzeb56
>
> TheDude wrote:Whoops. Sorry. I forgot about that step. I haven't dumped any files in a while... 
The files you want have a ASF header. Try PACK 9, file 3 for instance.
As far as extracting the models go, watch these:
http://www.youtube.com/watch?v=1ORnfYnlXOw

It's alright,i saw the video and well it was complicated for me to understand. :/
Isn't their like a script already made to extract the models from the unslz files? :/
I'm not aware of any that have been released. I'm trying to do it myself,
but between my other projects and just not having the energy, I'm a bit behind schedule.
## Post #37
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-07-14T06:54:34+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from TheDude
>
> Aurangzeb56 wrote:TheDude wrote:Whoops. Sorry. I forgot about that step. I haven't dumped any files in a while... 
The files you want have a ASF header. Try PACK 9, file 3 for instance.
As far as extracting the models go, watch these:
http://www.youtube.com/watch?v=1ORnfYnlXOw

It's alright,i saw the video and well it was complicated for me to understand. :/
Isn't their like a script already made to extract the models from the unslz files? :/
I'm not aware of any that have been released. I'm trying to do it myself,
but between my other projects and just not having the energy, I'm a bit behind schedule.

Lol,i think i remember seeing a thread where choroxx posted a picture of a model he had extracted,then maybe it's possible that he also might have released a script to extract the models?
## Post #38
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-07-14T18:12:21+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from Aurangzeb56
>
> 
Lol,i think i remember seeing a thread where choroxx posted a picture of a model he had extracted,then maybe it's possible that he also might have released a script to extract the models?
I'm afraid you'll have to ask him yourself; I don't know.
This is what I've got so far:


I can see something that resembles a matrix in the object headers. Maybe that's the body part transforms?
A matrix stack maybe?: [http://msdn.microsoft.com/en-us/library ... 85%29.aspx](http://msdn.microsoft.com/en-us/library/bb147181%28v=vs.85%29.aspx)
Also chrrox mentioned it's using a bitmask.
If it's both, I'll fly over to tri-Ace's headquarters and kick Mr. Yoshinori Yamagishi in the mouth!
## Post #39
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-07-15T10:34:21+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from TheDude
>
> Aurangzeb56 wrote:
Lol,i think i remember seeing a thread where choroxx posted a picture of a model he had extracted,then maybe it's possible that he also might have released a script to extract the models?
I'm afraid you'll have to ask him yourself; I don't know.
This is what I've got so far:


I can see something that resembles a matrix in the object headers. Maybe that's the body part transforms?
A matrix stack maybe?: http://msdn.microsoft.com/en-us/library ... 85%29.aspx
Also chrrox mentioned it's using a bitmask.
If it's both, I'll fly over to tri-Ace's headquarters and kick Mr. Yoshinori Yamagishi in the mouth!

Hmm i think i'll wait a little longer and see if Chroxx releases his script. ^^"

Well i don't know how you did that or about the matrix stack or bitmask but goodluck and i hope you can complete it. ^^
## Post #40
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-07-18T00:26:17+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Per chrrox's suggestion I've been poking around the PS3 version and it turns out the textures aren't swizzled at all!
## Post #41
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-07-18T18:48:33+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from TheDude
>
> Per chrrox's suggestion I've been poking around the PS3 version and it turns out the textures aren't swizzled at all!

Awesome.  Were you able to solve the model mushball problem?
## Post #42
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-07-19T03:07:37+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from Aurangzeb56
>
> 
Awesome.  Were you able to solve the model mushball problem?
I was curious what some numbers in the object header were for so I used them and
managed to spread all the body parts out in a perfect 45° diagonal line.
That's gotta count for something right?
## Post #43
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-07-19T06:38:16+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from TheDude
>
> Aurangzeb56 wrote:
Awesome.  Were you able to solve the model mushball problem?
I was curious what some numbers in the object header were for so I used them and
managed to spread all the body parts out in a perfect 45° diagonal line.
That's gotta count for something right?

Hmm probably they are,maybe experimenting more with the number will put the model in the correct form?
## Post #44
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-07-23T08:55:33+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Any advancement on how to rip the models off PS3 files? ^^"
## Post #45
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-07-25T17:47:44+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from Aurangzeb56
>
> Any advancement on how to rip the models off PS3 files? ^^"
I got distracted playing Final Fantasy XII  (never played it before)
I'm taking the textures from the PS3 version and everything else from the XBox 360 version.
## Post #46
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-07-27T04:43:28+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Friends help one please

then I extract the bin, and several. pak numbered, is it? the pak has no name just number?

Sabbe someone else where are the texts?

Hug.
## Post #47
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-07-30T01:27:01+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from timartinelli
>
> Friends help one please

then I extract the bin, and several. pak numbered, is it? the pak has no name just number?

Sabbe someone else where are the texts?

Hug.
By "texts" do you mean names or just how to extract the PACK files?
## Post #48
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-30T02:07:08+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

I think he wants to translate the game.
## Post #49
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-07-31T21:55:41+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

That's right I want to translate the game, does anyone know which. Pak texts?

Hug.
## Post #50
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-08-02T02:49:33+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from timartinelli
>
> That's right I want to translate the game, does anyone know which. Pak texts?

Hug.
The closest thing I've found so far is a list of all the trophies/achievements.
I'm still looking through all the data though. I'll post something here if I find it.
## Post #51
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-08-02T12:49:40+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Thank you friend.


Tell me where the file of the trophies, I want to take a look.

Hug.
## Post #52
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-08-03T18:49:28+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from timartinelli
>
> Thank you friend.


Tell me where the file of the trophies, I want to take a look.

Hug.

I believe I used X360GameHack v5.2 on default.xex and created a new 12.6 MB xex file.
(X360GameHack might show as false positive with anti-virus)
The trophy info starts at 0xC16334.
## Post #53
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-08-04T00:34:06+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Arumat: The Solid Gold Standard Collectors Figurine from The Bradford Exchange.

Limited-edition figurine of Arumat P. Thanatos® featuring 22K gold accents.
Sculpted by Morgan Weistling, Bruce Emmett and Nate Giorgio.   



-The Dude AKA MrFuzzlebum
## Post #54
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-08-05T00:13:06+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Dude, that is awesome!!!
## Post #55
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-08-07T01:18:35+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope


## Post #56
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-08-07T04:36:33+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Is this from the PS3 version or the 360? ^^"
## Post #57
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-07T10:54:21+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

textures are from the ps3 models are from the 360
## Post #58
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-08-08T00:17:22+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from chrrox
>
> textures are from the ps3 models are from the 360
Yeah I'm still looking through the PS3 files. I got lucky with the XBox 360.
All of the player characters were in one of the first PACK files I extracted.
As far as PS3 data goes, I've found Captain Grafton, Eleyna Farrence, Cardianons,
and a couple Bosses and other enemies I can't remember the name of. Blah.
## Post #59
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-08-08T05:40:51+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Thanks Chroxx and thedude,i think I'll have to buy the 360 version and then rip models from that. :/
Btw,do i have to rip the models from all the three-four disc or is only the first one necessary like FF-XIII?
## Post #60
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-08-08T16:40:33+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

That's a good question.  
I've basically only looked at that one PACK file that had all the PCs in it.
It's not like FFXIII where you can just double-click on files and open them in Noesis.
At least with IceBerg's Texture Finder I can look at the textures in the PS3 files and see what's there,
but with the XBox 360 version you can't even do that.  
Maybe chrrox knows if it's possible to get a file index out of the xex file......?
## Post #61
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-08-10T05:35:48+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Hmmm,i remember that first there was no Noesis plugin for FFXIII so we have to manually place texture on a character through 3DS Max. ^^" Though,star ocean is the same right?Still i don't know if i should rip the models from all four disks or only the first one. :/
## Post #62
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-08-10T16:30:55+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from Aurangzeb56
>
> Hmmm,i remember that first there was no Noesis plugin for FFXIII so we have to manually place texture on a character through 3DS Max. ^^" Though,star ocean is the same right?Still i don't know if i should rip the models from all four disks or only the first one. :/
Yes, exactly.
I would just extract the first disk. You'll get 2,071 PACK files. That should keep anyone busy for a while. 

Also, in case anyone else is working on a game produced by a Japanese company,
here's a bunch of words I had to translate (online translators and dictionaries leave a lot to be desired BTW):

Kami      Head
Kubi      Neck
Hada      Body
Gake      Cliff
Matuge      Eyelashes
Udewa      Bracelet
Ude Yobi      Arm Preliminary
Ude wa Oya      Arm Parent
Fuku      Clothing
Tue      Cane
Tue Oya      Cane Parent
Eri      Collar
Mune	      Chest
Tare      droop,suspend,hang,slouch
Himo      Ribbon
Himo Oya      Ribbon Parent
Shiri      Buttocks
Sode      Sleeve
Reesu      Lace
Kata      Shoulder
kazari      Ornament
Nuno      Cloth
Komono      Accessories
Mono	      Object
Yubi      Finger

**What is it with this forum and tabs/spaces?***
## Post #63
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-08-17T04:29:37+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

These files are 2 faces.
9 I can get to work without any trouble. 33 however is doing something different.  
[http://www.mediafire.com/?nrnvibdbaaqbis3](http://www.mediafire.com/?nrnvibdbaaqbis3)
## Post #64
- Username: Kikoeru
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 31, 2011 2:57 pm
- Post datetime: 2011-08-18T05:52:10+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

how to unpack asf file?i can't write bms script.
## Post #65
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-08-19T20:07:21+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from Air
>
> how to unpack asf file?i can't write bms script.
1. Take the script chrrox posted on the first page
   ( Posted: Sun May 30, 2010 12:21 am ) and place the two
  parts of the code in a text file with the extention .bms.
  Use that with quickbms_4gb_files.exe on file aska.bin (PS3) or
  quickbms.exe on files soz0.bin/soz1.bin (Xbox 360).

2. Use Aluigi's Star Ocean (Tri-ace SLZ/PACK)QuickBMS script:
[http://aluigi.org/papers/bms/slz.bms](http://aluigi.org/papers/bms/slz.bms)
on the resulting PACK files. That's all for the PS3 version.

3. Like chrrox said, you'll need to use xbdecompress on the Xbox 360's
files. With Aluigi's newer script (script 0.2b) the file extentions
will be .unslz. What I do is copy (not cut)xbdecompress and xbdm.dll
to whatever folder that I just extracted then delete them when I'm done.
(I didn't feel like adding the path to Window's environment variables)
Open a command window to use xbdecompress.
Example: xbdecompress 15.unslz 15_out

"That's the news, goodnight and have a pleasant tomorrow."
## Post #66
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-08-22T03:24:48+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Hello friends, the file has the file 1.pack 31.unslz, inside it has some of the PS3's text is a file. EXD anyone can be a tool for this type of text, I am trying to translate the game.

Hug.

following two sample files.
[exd.rar](https://xentaxbackup.github.io/file/4652_exd.rar)
## Post #67
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-08-23T02:50:14+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Just a small progress update.



Arumat and Edge's faces are the only ones to work as-is so far.
There's some inconsistencies in the files with the character faces which is rather confusing.
Do the other positions have something to do with the bone hierarchies?

Also so far I have the textures for Eleyna Farrence, The Black Eagle, Reimi, Bacchus, and Welch.
 The search goes on...
## Post #68
- Username: Kikoeru
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 31, 2011 2:57 pm
- Post datetime: 2011-08-24T11:11:20+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from TheDude
>
> 
1. Take the script chrrox posted on the first page
   ( Posted: Sun May 30, 2010 12:21 am ) and place the two
  parts of the code in a text file with the extention .bms.
  Use that with quickbms_4gb_files.exe on file aska.bin (PS3) or
  quickbms.exe on files soz0.bin/soz1.bin (Xbox 360).

2. Use Aluigi's Star Ocean (Tri-ace SLZ/PACK)QuickBMS script:
http://aluigi.org/papers/bms/slz.bms
on the resulting PACK files. That's all for the PS3 version.

3. Like chrrox said, you'll need to use xbdecompress on the Xbox 360's
files. With Aluigi's newer script (script 0.2b) the file extentions
will be .unslz. What I do is copy (not cut)xbdecompress and xbdm.dll
to whatever folder that I just extracted then delete them when I'm done.
(I didn't feel like adding the path to Window's environment variables)
Open a command window to use xbdecompress.
Example: xbdecompress 15.unslz 15_out

"That's the news, goodnight and have a pleasant tomorrow."
I mean that I have got some asf files. And I want to separate the asf files from textures and models. I can't make programming. Could you please offer me a tool which can do it?
## Post #69
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-08-26T02:38:52+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from Air
>
> 
I mean that I have got some asf files. And I want to separate the asf files from textures and models. I can't make programming. Could you please offer me a tool which can do it?
I'm working on it......kind of.
Only have 4 out of the 9 players faces attached so far.
Still haven't figured out how some of the objects are positioned.
Plus my code is too specific right now to be used in a general sense.
I'll fix that someday. Maybe make a importer for Blender, but that's a long ways off I think.
## Post #70
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-08-26T05:03:08+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Well the Dude is doing a great job!  I love the pictures you put up
## Post #71
- Username: Rayved
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Jun 21, 2011 10:46 am
- Post datetime: 2011-09-18T16:57:42+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

I'm using the ps3 version of the game and the result when I unpack the .PACK files are mostly .unslz or .aac.
If I understood correctly, the files should come out straight as ASF for the ps3 version without using any further decompressor right?
## Post #72
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-18T18:27:09+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

if you get a .unslz file, it means that file is no longer Tri-Ace SLZ compressed.

unslz is not a 'format' at all; it is simply a placeholder for the extension, which Quickbms does not know. The script only decompresses, it doesn't read what the name or extension of the compressed file is.

If you want to try the file as an ASF, try opening it in the blender ASF script somewhere in one of the SO4 threads around here.
## Post #73
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-18T18:33:52+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

the ps3 and 360 formats are completely different.
## Post #74
- Username: Rayved
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Jun 21, 2011 10:46 am
- Post datetime: 2011-09-18T22:05:31+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from Satoh
>
> if you get a .unslz file, it means that file is no longer Tri-Ace SLZ compressed.

unslz is not a 'format' at all; it is simply a placeholder for the extension, which Quickbms does not know. The script only decompresses, it doesn't read what the name or extension of the compressed file is.

If you want to try the file as an ASF, try opening it in the blender ASF script somewhere in one of the SO4 threads around here.

Alright, I got all the tools needed now. I have Maya, 3dsMax, Blender, I got the script, I got all the unslz files. I'm not really familiar with running scripts, I usualy just copy paste the whole thing and press enter and I get a popup asking to load a file and stuff, but with this script, I get synthax error in all the programs I just mentionned. Do I need to fill in some stuff like path and filename in the script manualy? If so, I'd like to know where
## Post #75
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-18T22:14:51+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

The blender script seems to only work in 2.4x versions of blender, it doesn't run properly in the newer 2.5x, at least it didn't in mine. (I keep both installed for this reason)

The blender script should already be loaded if you open the .blend in blender 2.4x. To run it, hover the mouse over the script window and press ALT P (just like it says to do)

I haven't tried the script on any non ASF files, so you may need to rename the unslz to asf in order for the script to look at them, or it may be that the files simply aren't the right ones and you need to keep trying different files...


As chrrox said, it may be that the files you have, are the wrong format, as the 360 and PS3 files are different... ( I haven't looked, so I have to assume he's correct on that )
## Post #76
- Username: Rayved
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Jun 21, 2011 10:46 am
- Post datetime: 2011-09-20T14:28:52+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

I succeeded in making the script work but only with the xbox version of the game. The header in the ps3 files I was trying was ASF too and I tried a couple ones but none of them worked. It's a shame, I wanted to modify the models and pack them back for playing in my ps3.
## Post #77
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-20T16:56:31+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

You wouldn't be able to re-import the models into the game anyway with the current level of progress. Bones aren't properly supported yet, and there is no ASF exporter yet.
## Post #78
- Username: Rayved
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Jun 21, 2011 10:46 am
- Post datetime: 2011-09-20T21:14:22+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Can anyone tell me in which PACK the character models are located? All I've found so far are models of the Calnus or another similar ship.

Edit: I'm talking about the playable characters of course, but NPCs would be appreciated too
## Post #79
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-20T23:14:55+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

9... I think.
## Post #80
- Username: Rayved
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Jun 21, 2011 10:46 am
- Post datetime: 2011-09-21T01:21:11+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Pack 9 contains 7 unslz files that are from 2 to 26 kb only (xbox version). I have the ps3 version too but I can't extract the models (blender script doesn't work on it). I'm starting to wonder if the character files are spread out in many different packs for the xbox version since I can't seem to find one with the same number of files and similar file sizes as the pack 9 from ps3 version.
## Post #81
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-21T01:47:00+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

oops my bad, it might be 2... but I don't think the blender script works on PS3 version models... or so I've read...

I think 9 is in fact their textures rather than their models. They should be archived DXT formats, some are DXT1 some are DXT3 as I recall...

From what I understand, PS3 version is where to go for textures, and 360 is the one to look at for models.

I have my models in a rar labeled something with a 2 at the end... so try looking in 2?
## Post #82
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-09-21T02:59:28+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

As a side note, notice the identifiers. They're in chronological order.
i.e., when you first meet that character/they join your party.
## Post #83
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-09-21T03:15:50+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

The contents of this post was deleted because of possible forum rules violation.
## Post #84
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-09-21T23:00:44+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

I tried figuring out the ps3 files' offsets, but it was giving me a headache.   
So here's this instead:
## Post #85
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-09-22T00:47:10+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

That's just great, you're helping a lot. Thank you for taking the time for doing it Now I know where Eleyna textures are (she was the only one I hadn't found yet).
Thanks.
## Post #86
- Username: Rayved
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Jun 21, 2011 10:46 am
- Post datetime: 2011-09-22T03:44:03+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Oh man, thank you very much. Can't wait to do animation with these characters
## Post #87
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-22T04:30:54+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Animation eh? Be sure to post back something when you get it done. TheDude's renders are pretty awesome, I'd like to see what kind of animation talent there is at Xentax too.

Oh, btw, you'll have to rig everything yourself, the bones don't work properly yet as far as I'm aware. I've been stalling rigging my set >.>
(But I've also been working on Xenosaga3 and Megaman Legends 2 models and doing some scratch modeling and texturing too, so I guess that's not really "stalling")

Can we get a merger of the two SO4 threads?
## Post #88
- Username: Rayved
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Jun 21, 2011 10:46 am
- Post datetime: 2011-09-22T15:01:33+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

I hate rigging and weight painting but I guess I just need more practise. I study 3d animation at school btw, so this'll be like a cool homework for me 

EDIT: I just noticed it's soz0 we have to run the script on. I thought I read somewhere that it was soz1. Oh well.

Edit2: I'd like some help on using texture finder. It seems I can only save the image I currently see when I click the camera button, but I'd like to save the whole image (because it's too big for my resolution to scale the window big enough for the whole thing)
## Post #89
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-22T17:02:53+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from Rayved
>
> I hate rigging and weight painting but I guess I just need more practise. I study 3d animation at school btw, so this'll be like a cool homework for me 

EDIT: I just noticed it's soz0 we have to run the script on. I thought I read somewhere that it was soz1. Oh well.

Edit2: I'd like some help on using texture finder. It seems I can only save the image I currently see when I click the camera button, but I'd like to save the whole image (because it's too big for my resolution to scale the window big enough for the whole thing)

That is an issue, but your image is saved as a 32bit Alpha enabled BMP, so if you open it in a competent image editor like photoshop, you can splice the images together and re-save them as a full alpha-enabled image.
Personally I just opted to use the 512^2 textures since they're less defined, but not really noticeably so for most applications.

I too studied animation and modeling in college, never got around to rendering though, since my course was geared directly for game development. I was the guinea pig for the course, as I was in the first class that they offered it... so my training was a bit... self-service. But with the books and mandatory in class practice I did learn quite a bit.

Have you messed with Unity at all? You might be able to make a living with it. Animators are hard to come by cheap, and I personally hate it... I can never make it look... perfect.
Modeling I like though.

Anyway, The Dude has told me that you can find the texture data offset with texture finder(there's an obvious statement...) and then attach a DDS header to it and it should work as a proper file. However you have to know a bit about hex editing... and DDS file headers.

Most files are DXT1 with no alpha, but some are DXT3, and very very rarely you might find a DXT5. (Meracle's ears seem to be DXT5, but they're used for some sort of displacement transparent fur shader...)
## Post #90
- Username: Rayved
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Jun 21, 2011 10:46 am
- Post datetime: 2011-09-22T21:26:53+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Our course sucks too. The teacher we get the most in our classes is so lame, he checks your work once and gives a mark on his feeling, he doesn't really check anything technical about it, and he doesnt help students much, instead he chills with the best students and compliments them instead of checking on the ones with more difficulty.

Anyway, for the texture thing, I don't know much about hex editing but I checked a few of the videos posted in this thread and I'll get around it, I just need to know what the correct header should be so I can replace in the file.

I have Unity on my pc but I didnt get a chance to play with it much since I'm always busy with school and life.

Like right now, I'm doing a 3D amusement park for my demo. Very time consuming.
## Post #91
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-09-23T18:27:23+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Paddle Boat:
X360......soz0___PACK 1035___File 95___2,871 KB___io005
PS3......PACK 2614___File 49___2,677 KB___io005

Doggie:
X360......soz0___PACK 1194___File 0___1,909 KB___cn009
PS3......PACK 1022___File 14___1,497 KB___cn009

Amina's Grandfather:
X360......soz1___PACK 198___File 1___2,235 KB___cn017
PS3......PACK 1039___File 174___1,771 KB__cn017

Ghimdo:
X360......soz0___PACK 770___File 8___3,092 KB___cn008
PS3......PACK 2156___File 24___2,207 KB__cn008

Bunny:
X360......soz0___PACK 623___File 5___1,021 KB___cn095
PS3......PACK 1039___File 180___958 KB___cn095

Meracle - cat form:
X360......soz0___PACK 1207___File 0___2,544 KB___cp006
PS3......PACK 1761___File 18___2,406 KB___cp006

Commander Stephen D. Kenny:
X360 (Body)soz0___PACK 1311___File 6___1,892 KB___cn003
X360 (Face)soz0___PACK 1311___File 10___1,136 KB___cn003
PS3......PACK 2135___File 0___2,067 KB___cn003

Still trying to find weapons...

EDIT: Am I the only person who didn't realize Lymle has 4 sets of clothing?!


Pack 1300 file 9 has the 2 you see on the right (PS3)
## Post #92
- Username: Rayved
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Jun 21, 2011 10:46 am
- Post datetime: 2011-09-23T23:15:18+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Now that you mention it, I remember she had different clothes before she joined (I think) but afterwards, I had never noticed.
## Post #93
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-24T00:23:17+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

At least one of those is a specular map, it determines the color and amount of reflected light that hits the material. It's basically what make's Meracle's clothes look purple in the light (because on the texture they're midnight blue) and apparently does similar with Lymle...

Unless you mean there are 4 sets of Texture, Specular, Normal, etc[other detail map types] in the file. 
I was a bit confused by the textures at first but eventually figured it all out.

There should be a specular map for the hair as well.

EDIT: Looked at Lymle's files, the 'second color' for each of those clothing sets is indeed the specular map, and the #1 and #3 colors appear to be authentic; At least the 3rd one isn't in the texture set I have for her.

So she has 2 outfits... even this is interesting... I don't recognize the white one.

EDIT2: Also I figured out what the 'blue sparkle' is. Its the environment map, it seems to be a rudimentary cube map or something, the dot in the center is the sun or moon, and the spiky things around the outside are trees. Thus the center represents the up direction of the environment.
## Post #94
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-09-24T04:55:32+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Yes, given the difference in texture sizes that would make sense.
I've never seen a colored specular map that could pass for a diffuse though,... strange.
It must be.........wait for it........................................an Advanced Specular Map! LOL!
## Post #95
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-24T05:53:16+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Well if you consider that the regular textures are all flat with no painted shadows, and specular lighting is generally pure white. But if you think about it, characters' clothes reflect a variety of different colors: Meracle's clothes are blue but reflect a bright purple, Arumat's cape is flat gray but reflects with a dull reddish color.

Specular maps used to be pretty similar to the outdated bump map style, grayscale with (roughly) high spots being lighter (thus more reflective) and low spots being usually black or dak gray (less reflective). 

Hang in for a bit I'ma school you guys on something I learned as a modeler...
Specular maps don't modify the amount of reflection a model has, as you might expect. Rather, specular maps change the -color- of the reflected light. Reflected light is normally pure white. Black is the absence of light, or in this case, of white, and thus does not reflect at all. The darker the color, the less it reflects, obviously.

Somebody eventually discovered that making something reflect in technicolor was exactly the same technology as white. The same is true of glow maps in the rare instances you need them. Most games when it was new technology, used white, but colors work too.

Also, the reason the spec-maps are all grainy, is to simulate the very fine texture of things like skin, which reflects in some places, and not in others, at any given moment.

For those that knew this, sorry for the wasted time, for those that didn't, grats, I've taken away some of your knowledge space.
## Post #96
- Username: Rayved
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Jun 21, 2011 10:46 am
- Post datetime: 2011-09-24T18:08:21+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

I've seen an exemple at school where the specular of a 3d face is applied to a real photo and then the teacher could make the face look like it was wet and stuff by selecting the right color (pink or green) and applying an effect to that area but on the photo instead.
## Post #97
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-09-24T21:51:54+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

The Dude has been schooled by Satoh.  
I played the part of the game where you meet Lymle for the first time and noticed
the coloring on her clothing didn't look nearly as flat compared to that render.
I guess that proves it right there. 
Now I'm wondering why all I've seen before are the grayscale versions....

Well anyway, while I'm at it, here are some more peoples:


EDIT: Here's the final list. (cause I'm sick of searching for things   )
[http://www.mediafire.com/?0yk3sch8ir368ai](http://www.mediafire.com/?0yk3sch8ir368ai)
## Post #98
- Username: Rayved
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Jun 21, 2011 10:46 am
- Post datetime: 2011-09-24T23:46:26+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Can someone post an exemple of a good header for a dxt file? I can't find any dxt files at all anywhere to take it from.

Oh, and when I open Arumat's texture file with texture finder, I can't find any good setting to view it well. If i use the headers trick, will it work?

One last thing. I'd like to know what application can edit DXT files. I found a plugin for photoshop online but it doesn't seem to work with CS4 so maybe there's something else.
## Post #99
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-09-25T19:38:30+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from Rayved
>
> Can someone post an exemple of a good header for a dxt file? I can't find any dxt files at all anywhere to take it from.

Oh, and when I open Arumat's texture file with texture finder, I can't find any good setting to view it well. If i use the headers trick, will it work?

One last thing. I'd like to know what application can edit DXT files. I found a plugin for photoshop online but it doesn't seem to work with CS4 so maybe there's something else.

Here's some samples:

```

444453207C00000007100000000200000002000000000000000000000000000000000000000
000000000000000000000000000000000000000000000000000000000000000000000000000
002000000004000000445854310000000000000000000000000000000000000000001000000
0000000000000000000000000000000


1024x512 DXT1 RGB8888

444453207C00000007100000000200000004000000000000000000000000000000000000000
000000000000000000000000000000000000000000000000000000000000000000000000000
002000000004000000445854310000000000000000000000000000000000000000001000000
0000000000000000000000000000000


2048x1024 DXT1 RGB8888

444453207C00000007100000000400000008000000000000000000000000000000000000000
000000000000000000000000000000000000000000000000000000000000000000000000000
002000000004000000445854310000000000000000000000000000000000000000001000000
0000000000000000000000000000000




512x512 DXT3 RGB8888

444453207C00000007100800000200000002000000000400000000000000000000000000000
000000000000000000000000000000000000000000000000000000000000000000000000000
002000000004000000445854330000000000000000000000000000000000000000001000000
0000000000000000000000000000000


1024x512 DXT3 RGB8888

444453207C00000007100800000200000004000000000800000000000000000000000000000
000000000000000000000000000000000000000000000000000000000000000000000000000
002000000004000000445854330000000000000000000000000000000000000000001000000
0000000000000000000000000000000


2048x1024 DXT3 RGB8888

444453207C00000007100800000400000008000000002000000000000000000000000000000
000000000000000000000000000000000000000000000000000000000000000000000000000
002000000004000000445854330000000000000000000000000000000000000000001000000
0000000000000000000000000000000
```


Also, this site has all you info you need + a link to a C program for writing DDS headers:
[http://atlantica.wikia.com/wiki/Forum:N ... dissection](http://atlantica.wikia.com/wiki/Forum:Ndoors_DDS_image_format_dissection)
## Post #100
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-09-29T17:37:43+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Here's how to give all the files their proper file extensions.
[http://mrfuzzlebum.deviantart.com/art/M ... -260811194](http://mrfuzzlebum.deviantart.com/art/Mass-rename-using-file-headers-260811194)
## Post #101
- Username: Rayved
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Jun 21, 2011 10:46 am
- Post datetime: 2011-10-04T03:49:19+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Lots of thanks !
## Post #102
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-10-21T02:04:38+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

I finally got the the 360 version of Star Ocean The Last Hope.  It's a PAL version though,so could you guys tell me how to extract the model from the 360 ISO file?
## Post #103
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-10-24T18:38:35+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from Aurangzeb56
>
> I finally got the the 360 version of Star Ocean The Last Hope.  It's a PAL version though,so could you guys tell me how to extract the model from the 360 ISO file?

Use XBOX 360 ISO Extract by somski on the disc image

Copy the 2 sections of code that chrrox posted on the first page
(Posted: Sun May 30, 2010 12:21 am)
into a text file and give it a name like bin.bms

Run quickbms and choose soz0.bin when asked followed by the bin.bms script 

Get Aluigi's slz bms script:
[http://aluigi.altervista.org/papers/bms/slz.bms](http://aluigi.altervista.org/papers/bms/slz.bms)

Run quickbms on the PACK files using slz.bms
If you wish to extract all of the files then open a command prompt and type:
for %x in (*.PACK) do quickbms slz.bms "%x" "%CD%"
Otherwise you can just use the list I posted above for specific characters.
Also it's formated to work with Damned NFO Viewer so it probably looks wrong in other text viewers.
Then you'll either have to have quickbms in the same location or add it to
Windows' environment variables.
I just copied all the quickbms stuff to the same location where I was going to use it then deleted the copy.

And then......

Get a copy of xbdecompress and in a command promp type:
xbdecompress file newfile
or use
for /r %x in (*.xbcompress) do xbdecompress "%x" "%x.new"
if you want to decompress all the files

And then......

If you extracted all the files and want them to have the proper file extension,
I made a guide for that:
[http://mrfuzzlebum.deviantart.com/galle ... /#/d4ba37e](http://mrfuzzlebum.deviantart.com/gallery/?catpath=/#/d4ba37e)

And if you can make sense of all that and somehow succeed, then there's something wrong with you.
No, just kidding.    I think that's how I did it.
## Post #104
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-10-26T04:21:53+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

The contents of this post was deleted because of possible forum rules violation.
## Post #105
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-10-26T10:33:54+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

xbdecompress is command line.
xbdecompress.exe c:\compressed.pak c:\extract\file.ext
## Post #106
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-10-26T21:52:30+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

You left out the "for".
Plus you'll have to do that from whichever directory you have the files in.
Or you can always add the /r switch after the "for" command and execute it from the parent directory.

I might make a pdf with detailed step-by-step instructions at some point, but it'll be a while.

[http://www.mediafire.com/imageview.php? ... u3&thumb=4](http://www.mediafire.com/imageview.php?quickkey=ik853yprlo7ndu3&thumb=4)
## Post #107
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-10-27T03:24:23+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from chrrox
>
> xbdecompress is command line.
xbdecompress.exe c:\compressed.pak c:\extract\file.ext

Xbdecompress closes right after i open it.

> Reply from TheDude
>
> You left out the "for".
Plus you'll have to do that from whichever directory you have the files in.
Or you can always add the /r switch after the "for" command and execute it from the parent directory.

I might make a pdf with detailed step-by-step instructions at some point, but it'll be a while.

http://www.mediafire.com/imageview.php? ... u3&thumb=4

Thanks. ^^ Well i got SLZ files from Pack 2 (360 ISO).COuld you tell me what do to now? ^^"
## Post #108
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-10-27T10:48:06+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

command line means open a command prompt.
you can not just double click on xbdecompress.
please google what command line is.
## Post #109
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2011-10-27T14:34:11+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from Aurangzeb56
>
> chrrox wrote:xbdecompress is command line.
xbdecompress.exe c:\compressed.pak c:\extract\file.ext

Xbdecompress closes right after i open it.
TheDude wrote:You left out the "for".
Plus you'll have to do that from whichever directory you have the files in.
Or you can always add the /r switch after the "for" command and execute it from the parent directory.

I might make a pdf with detailed step-by-step instructions at some point, but it'll be a while.

http://www.mediafire.com/imageview.php? ... u3&thumb=4

Thanks. ^^ Well i got SLZ files from Pack 2 (360 ISO).COuld you tell me what do to now? ^^"

Do you know how to use DOS? because you have to run xbdecompress from DOS and from the folder path you have your files.
## Post #110
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-10-28T03:43:26+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from chrrox
>
> command line means open a command prompt.
you can not just double click on xbdecompress.
please google what command line is.

Oh,thanks.  I'll try doing it. ^^"

> Reply from Darko
>
> Aurangzeb56 wrote:chrrox wrote:xbdecompress is command line.
xbdecompress.exe c:\compressed.pak c:\extract\file.ext

Xbdecompress closes right after i open it.
TheDude wrote:You left out the "for".
Plus you'll have to do that from whichever directory you have the files in.
Or you can always add the /r switch after the "for" command and execute it from the parent directory.

I might make a pdf with detailed step-by-step instructions at some point, but it'll be a while.

http://www.mediafire.com/imageview.php? ... u3&thumb=4

Thanks. ^^ Well i got SLZ files from Pack 2 (360 ISO).COuld you tell me what do to now? ^^"

Do you know how to use DOS? because you have to run xbdecompress from DOS and from the folder path you have your files.

Nope,sorry but i don't know how to use DOS.
## Post #111
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-10-28T18:16:59+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

I found these on Youtube. Hope it helps...
Windows Command Prompt 01 Basic Navigation:
[http://www.youtube.com/watch?v=wgKWJmzjrKA](http://www.youtube.com/watch?v=wgKWJmzjrKA)

Windows Command Prompt 02 Scrolling Output and Redirection:
[http://www.youtube.com/watch?v=L25EN15MMKQ](http://www.youtube.com/watch?v=L25EN15MMKQ)

Windows Command Prompt 04 Customizing your Shell:
[http://www.youtube.com/watch?v=1cdeJwzGq1Q](http://www.youtube.com/watch?v=1cdeJwzGq1Q)

Furthermore,
C:\dos
C:\dos\run
RUN\DOS\RUN!
## Post #112
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-10-29T04:43:04+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from TheDude
>
> I found these on Youtube. Hope it helps...
Windows Command Prompt 01 Basic Navigation:
http://www.youtube.com/watch?v=wgKWJmzjrKA

Windows Command Prompt 02 Scrolling Output and Redirection:
http://www.youtube.com/watch?v=L25EN15MMKQ

Windows Command Prompt 04 Customizing your Shell:
http://www.youtube.com/watch?v=1cdeJwzGq1Q

Furthermore,
C:\dos
C:\dos\run
RUN\DOS\RUN!

Ummmm theDude,hope it's not too much but could you make a video for this?

"Get a copy of xbdecompress and in a command promp type:
xbdecompress file newfile
or use
for /r %x in (*.xbcompress) do xbdecompress "%x" "%x.new"
if you want to decompress all the files"

Since i can't understand this or how to use xbdecompress with command prompt.
## Post #113
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-10-29T22:55:00+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

OK. Hold my beer, I'm gonna try somethin'.
## Post #114
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-10-29T23:04:37+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

just click start
then click run
then in the run box type cmd
hit enter
now
drag xbdecompress into the black box that showed up
now add a space
now drag the file you want to decompress
now add another space
now drag that same file into the black box again and add .uncompressed
after it
hit enter
now you will have a new file thats uncompressed.
if you can not follow this just stop now and learn some computer basics first.
## Post #115
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-10-30T03:51:49+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from chrrox
>
> just click start
then click run
then in the run box type cmd
hit enter
now
drag xbdecompress into the black box that showed up
now add a space
now drag the file you want to decompress
now add another space
now drag that same file into the black box again and add .uncompressed
after it
hit enter
now you will have a new file thats uncompressed.
if you can not follow this just stop now and learn some computer basics first.

Thanks Chrrox that helped alot.  Now i got 2.unslz.uncompressed,can you tell me how to view this file now? ^^"
## Post #116
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-11-04T15:02:28+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Anyone?
## Post #117
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-11-05T04:33:29+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

The Dude is here to hook you up.
YouTube:
   Part 1:
[http://www.youtube.com/watch?v=ELc45fBO ... re=related](http://www.youtube.com/watch?v=ELc45fBOqIg&feature=related)

   Part 2:
[http://www.youtube.com/watch?v=bPbdNHNa33g](http://www.youtube.com/watch?v=bPbdNHNa33g)

   Part 3:
[http://www.youtube.com/watch?v=lzBRrv6m5s0](http://www.youtube.com/watch?v=lzBRrv6m5s0)

MediaFire mirror:
   Part 1:
[http://www.mediafire.com/?2kwvftu0c661s3d](http://www.mediafire.com/?2kwvftu0c661s3d)

   Part 2:
[http://www.mediafire.com/?7hrtk2qjvm2l756](http://www.mediafire.com/?7hrtk2qjvm2l756)

   Part 3:
[http://www.mediafire.com/?94ny21pdkv7xmdb](http://www.mediafire.com/?94ny21pdkv7xmdb)

[http://www.youtube.com/watch?v=Be7Og9Gc_KY](http://www.youtube.com/watch?v=Be7Og9Gc_KY)
## Post #118
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2011-11-07T12:18:24+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Hey the dude, how did you get the textures??
## Post #119
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-11-07T17:49:40+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from Darko
>
> Hey the dude, how did you get the textures??
Ha-ha, that's another set of videos right there!
The short of it is, I used IceBerg's TextureFinder [http://www.nba2kstuff.org/mua/TextureFinder.v21.zip](http://www.nba2kstuff.org/mua/TextureFinder.v21.zip)
on the ps3 files because I don't feel like messing around with the XBox 360's texture crap o' rama.   
Plus, if I work on anything, it'll be importing the animations.

Also, it's just "Dude" unless being referred to offhand or indirectly. Or something.
OK, I'm not sure what the exact grammar rule is. That's what that final video was for.  
Maybe I should've thought that through more when I created my account......
## Post #120
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2011-11-08T00:33:10+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from TheDude
>
> Darko wrote:Hey the dude, how did you get the textures??
Ha-ha, that's another set of videos right there!
The short of it is, I used IceBerg's TextureFinder http://www.nba2kstuff.org/mua/TextureFinder.v21.zip
on the ps3 files because I don't feel like messing around with the XBox 360's texture crap o' rama.   
Plus, if I work on anything, it'll be importing the animations.

Also, it's just "Dude" unless being referred to offhand or indirectly. Or something.
OK, I'm not sure what the exact grammar rule is. That's what that final video was for.  
Maybe I should've thought that through more when I created my account......

Lol it's just that your nickname is "The dude" XD
## Post #121
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-11-08T17:16:27+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from Darko
>
> TheDude wrote:Darko wrote:Hey the dude, how did you get the textures??
Ha-ha, that's another set of videos right there!
The short of it is, I used IceBerg's TextureFinder http://www.nba2kstuff.org/mua/TextureFinder.v21.zip
on the ps3 files because I don't feel like messing around with the XBox 360's texture crap o' rama.   
Plus, if I work on anything, it'll be importing the animations.

Also, it's just "Dude" unless being referred to offhand or indirectly. Or something.
OK, I'm not sure what the exact grammar rule is. That's what that final video was for.  
Maybe I should've thought that through more when I created my account......

Lol it's just that your nickname is "The dude" XD
## Post #122
- Username: amano
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 11, 2011 6:46 pm
- Post datetime: 2011-11-20T07:00:00+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

I want to know how to get the model file, or you can send to me?
## Post #123
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-11-20T17:50:40+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from amano
>
> 
I want to know how to get the model file, or you can send to me?

Read through the thread, and use the search tool.  There is another Star Ocean thread out there which will provide you with the information you're seeking.
## Post #124
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-11-20T18:04:34+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from LUBDAR
>
> amano wrote:
I want to know how to get the model file, or you can send to me?

Read through the thread, and use the search tool.  There is another Star Ocean thread out there which will provide you with the information you're seeking.
That and the 3 part video walkthrough I posted on the previous page. Rexil was porting them over to XNALara, but he's busy with Skyrim right now.
I was going to do the same (as well as Cryengine 3), but I just really don't feel like rigging characters right now.
## Post #125
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-01-04T18:24:11+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Wow! There are tons of offsets in these PS3 files.
## Post #126
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-01-04T19:51:11+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

its not the offsets that are the problems its the face indecies.
## Post #127
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-01-05T16:13:01+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Maybe for you they're not    I'm the new guy remember?   
But seriously, I can follow the data now I think, it just seems really convoluted compared to the X360 version.
I noticed the faces were strange, but I'm not ready to wade neck deep into that mess yet.
My only aim is to create a texture extractor right now.
I just haven't gotten to the point where I can code it to work on every ASF file.

EDIT: Dang-it!
    ASF --> AMF
    ASF + AMF = end of address blocks
    ASF + AMF + 1st buffer = start of texture data
    and of course ASF + AMF + 1st and 2nd buffers = file size
Well now I feel stupid. I should start paying attention more.  
(I'm blaming MarioKart64n. His YouTube videos are what got me started with this stuff)   

Furthermore,
  poop.
## Post #128
- Username: arthur1042
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 07, 2012 3:48 pm
- Post datetime: 2012-01-07T12:09:52+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Hey Thedude

Kudos on your awesome guide. I tried following it step by step, after extracting the packs, unslz and xbdecompressing. When using grep and checking the folders for ASF i can't seem to find any in the xbox extraction, whereas I can find too many in the PS3 extract folder.

Been using winhex to check out the files but all i stumble on are EXD files.

You have any clue what I have been doing wrong?

Been trying to get Sarah's model~~~
## Post #129
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-01-07T17:41:19+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from arthur1042
>
> Hey Thedude

Kudos on your awesome guide. I tried following it step by step, after extracting the packs, unslz and xbdecompressing. When using grep and checking the folders for ASF i can't seem to find any in the xbox extraction, whereas I can find too many in the PS3 extract folder.

Been using winhex to check out the files but all i stumble on are EXD files.

You have any clue what I have been doing wrong?

Been trying to get Sarah's model~~~

I might have done something wrong in the video.
Lets see here......
First, if all you're looking for is Sarah, all the PCs (Player Characters) are in soz0 - PACK 2 (Xbox 360) / PACK 9 (PS3)
Open one of your XBox 360 files and make sure it starts with ASF (otherwise it's still compressed)
As far as grepWin goes, under "Search" set to text search.
Make sure "Limit search" is set to all sizes and check "include binary files"
Set "Files which match:" to *.*

"Also, Just a heads up, we're gonna have a super conductor turned up full blast and pointed at you for the duration of this next test.
I'll be honest, we're throwing science at the walls here to see what sticks. No idea what it'll do."
  -Cave Johnson
## Post #130
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-01-07T19:32:47+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

The contents of this post was deleted because of possible forum rules violation.
## Post #131
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-01-23T01:42:46+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

I can't figure out why Astral City (PACK 1034) is missing some houses.
The part that is really driving me crazy though is half of the moss (koke) is in screwy places
and for the life of me I can't figure out why.   
I thought it might have something to do with these 3 sets of numbers in the bone data:


I was messing around and thought I noticed some correlation with the object-offset/pivot, but the numbers might
have been a coincidence.
## Post #132
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-04T20:13:52+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from TheDude
>
> Air wrote:how to unpack asf file?i can't write bms script. 
1. Take the script chrrox posted on the first page
   ( Posted: Sun May 30, 2010 12:21 am ) and place the two
  parts of the code in a text file with the extention .bms.
  Use that with quickbms_4gb_files.exe on file aska.bin (PS3) or
  quickbms.exe on files soz0.bin/soz1.bin (Xbox 360).

2. Use Aluigi's Star Ocean (Tri-ace SLZ/PACK)QuickBMS script:
http://aluigi.org/papers/bms/slz.bms
on the resulting PACK files. That's all for the PS3 version.

3. Like chrrox said, you'll need to use xbdecompress on the Xbox 360's
files. With Aluigi's newer script (script 0.2b) the file extentions
will be .unslz. What I do is copy (not cut)xbdecompress and xbdm.dll
to whatever folder that I just extracted then delete them when I'm done.
(I didn't feel like adding the path to Window's environment variables)
Open a command window to use xbdecompress.
Example: xbdecompress 15.unslz 15_out

"That's the news, goodnight and have a pleasant tomorrow."

Thanks by the Tutorial, i download the game, and i extract the files soz0.bin and soz1.bin from the DVD1.
Then i use quickbms with slz.bms to extract, and i get this window first wit soz0.bin



Then i test with soz1.bin
and i get this window


And this its the files u test do this (qucikbms and .bms file)
[https://rapidshare.com/files/289542875/EXTRAIDOS.rar](https://rapidshare.com/files/289542875/EXTRAIDOS.rar)

This its the size of the files extracted from Xbox360 game
soz0.bin	3,468,728kb
soz1.bin	2,528,532kb

I hope somebody help me coz its 21GB of trash i dowloaded if i cant fix this. cheers.
## Post #133
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-06T02:28:07+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

TheDude i follow all your videotutorials and finally i get the models, something news abouth texture extractor? cheers. Or con please up a video abouth how you keep out with TextureFinder? i working with x360 files.
## Post #134
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-02-06T20:26:17+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from Rimbros
>
> TheDude i follow all your videotutorials and finally i get the models, something news abouth texture extractor? cheers. Or con please up a video abouth how you keep out with TextureFinder? i working with x360 files.
Sorry 'bout that. I'm really behind. I was going to use C#, but visual studio was having problems so I said 
"Microsoft can suck it! I'm going with Python."  
I've got a Maya training video I've got to finish making first: [http://finalfantasy-xiii.net/forums/sho ... tcount=132](http://finalfantasy-xiii.net/forums/showpost.php?s=66a6ffe0cba49cad91b5fe83151f54a4&p=363428&postcount=132)
FFXIII-2 took up my weekend. ( decorating your Feral Behemoth by placing a scoop of Rum Raisin Ice Cream on his head is hilarious!   )

Update: I'm working on translating the imgX headers to proper DDS headers. Going slow though; FFXIII-2 still taking up most of my free time.
## Post #135
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-15T06:43:19+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Update: I'm working on translating the imgX headers to proper DDS headers. Going slow though; FFXIII-2 still taking up most of my free time.  [/quote]

Hope you not leave your greath work with Star Ocean bro and finish the extractor, cheers.
## Post #136
- Username: Samu
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 02, 2011 3:57 am
- Post datetime: 2012-03-06T01:36:54+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

I made this program to extract the textures. As far as I tested, it is working properly, but if it doesn't work with a specific file, contact me.

Just use it as following:
aifdump.exe [Option] <ASF_path> <Texture_dump_path>

Avaliable Options:
-hr : Dumps the sample with the highest resolution for each texture.

I heavily recommend the -hr option, since you may not want to have the low resolution samples (from the mipmaps).

Also, thank you Dude for the information you had regarding the headers.

EDIT 20/03/2012:
There was a problem regarding certain texture's dimensions and it was corrected.
[aifdump.rar](https://xentaxbackup.github.io/file/5215_aifdump.rar)
## Post #137
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-03-07T22:48:08+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Why i dont see this before?   Thanks so much samu.
## Post #138
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-03-24T01:02:37+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

I tested it out and it's flawless!
Good job!
## Post #139
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-24T01:04:49+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Source would be great.
## Post #140
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-03-24T19:28:28+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Source code!?
We don't need no stinkin' source code!
## Post #141
- Username: catchra
- Rank: Banned
- Number of posts: 4
- Joined date: Wed Aug 03, 2011 6:20 pm
- Post datetime: 2012-04-03T09:02:22+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

I don't  know if any 1 has found this 1 yet. here is where to find the textures and models for [Reimi's Shower PA Scene](http://www.youtube.com/watch?v=P4Vej1p1nhI).     

Textures \Star Ocean International\PS3\Extracted\1080\162.unslz
Models \Star Ocean International\XBOX_360\(Disk 1) Extracted\1262\0.unslz

I'm still new to 3d modeling but went i try to render the scene it shows the character backwards and the faces are missing not sure what to do
I'm using 3ds max 2010 64 bit

And thanks Samu for aifdump great tool
## Post #142
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-04-05T20:25:40+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Yeah, that model and some others still have problems.
Me and Samu are still trying to figure out what the rest of the bone data is for.

In other news here's an updated file list. (looks best using DAMN NFO Viewer)
[http://www.mediafire.com/?lw3w3c98ufmw33m](http://www.mediafire.com/?lw3w3c98ufmw33m)
As Samu pointed out, this may only be accurate for the NTSC version, I'm not really sure.
## Post #143
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-04-16T01:03:07+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

OK, fixed.
[http://www.putlocker.com/file/FDDD3876A7F20DBB](http://www.putlocker.com/file/FDDD3876A7F20DBB)
Everyone be sure and thank Samu for figuring out the skinning! 

UPDATE: Whoops, I messed up the character's faces. 
Updated the link to the fixed version.



EDIT: Fixed link
## Post #144
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-04-19T17:26:24+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from TheDude
>
> OK, fixed.
http://www.mediafire.com/?qvje50bx2wmkbv3
Everyone be sure and thank Samu for figuring out the skinning! 

UPDATE: Whoops, I messed up the character's faces. 
Updated the link to the fixed version.

Amazing job on this. Thanks everyone who contributed to this 

-
Is the texture extractor extracting the eyes diffuse correctly for anyone? It's wrong for me.
They all come out like this:
[](http://postimage.org/)

Also, did anyone managed to find Eleyna face? I search for every relevant term inside the files but couldn't find anything  

Edit: Looks like the weights aren't working with the new version of the script.
## Post #145
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-04-19T23:32:44+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Which files is that happening with?
I'll try and look for people's faces once I figure out where I put my game.  
I forgot I had that code commented out. I updated the link again.
## Post #146
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-04-20T01:23:53+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from TheDude
>
> Which files is that happening with?
I'll try and look for people's faces once I figure out where I put my game.  
I forgot I had that code commented out. I updated the link again.

Every main character extract the eyes diffuse like that oh and Edge didn't extract the eye diffuse. The NPC's extract them fine.
Thank you   again.
## Post #147
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-04-20T02:28:57+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

The eye textures are in the files with the face geometry, whereas the files with the body geometry contain all the other textures but the eyes.
Totally forgot about that actually....
## Post #148
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-04-20T03:35:49+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from TheDude
>
> The eye textures are in the files with the face geometry, whereas the files with the body geometry contain all the other textures but the eyes.
Totally forgot about that actually....

Oh, I should have thought about that :\ Well they have the same numbers as the geometry ones.

Another question, are you still going to work on the facial weights and weapons support in the current script? Importing weapons gives a runtime error.
Anyway I'm thankful for all the work you and everyone else has put into it!
## Post #149
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-04-21T14:46:10+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

I'll try, but I'm still learning all this from scratch so I can't guarantee it'll happen anytime soon.
First up though, is fixing Sarah's face and the zones. The zone objects and her face seem to have the same issue.
## Post #150
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-04-21T15:49:36+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from TheDude
>
> I'll try, but I'm still learning all this from scratch so I can't guarantee it'll happen anytime soon.
First up though, is fixing Sarah's face and the zones. The zone objects and her face seem to have the same issue.
Oh, no worries, I already started rigging their faces. 
What's the problem with Sarah's face? Her face seems fine to me, but her corset and some of her "accessories" has UV problems.
Anyway, thanks.
## Post #151
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-04-21T22:35:59+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from rexil
>
> TheDude wrote:I'll try, but I'm still learning all this from scratch so I can't guarantee it'll happen anytime soon.
First up though, is fixing Sarah's face and the zones. The zone objects and her face seem to have the same issue.
Oh, no worries, I already started rigging their faces. 
What's the problem with Sarah's face? Her face seems fine to me, but her corset and some of her "accessories" has UV problems.
Anyway, thanks.



I'll look at the UVs and see what's going on.
## Post #152
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2012-04-22T07:01:39+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Can someone tell me how can i view the .unslz file in 3DS Max that i extracted from Disk 1 of the 360 version?
## Post #153
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-04-22T16:17:26+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from Aurangzeb56
>
> Can someone tell me how can i view the .unslz file in 3DS Max that i extracted from Disk 1 of the 360 version?
You need to decompress it with xbdecompress.
## Post #154
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-04-22T17:17:26+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

I made a video series on how to do all that stuff, but I didn't have a microphone at the time.
I'll redo them at some point. In the mean time, here's the fix for Sarah's UVs.
It might break some UV mapping in other characters though, I'm not sure.
Replace lines 301-303 with:
tu = ReadBEfloat f
tv = ReadBEfloat f *-1 +1
## Post #155
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-04-22T19:17:37+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from TheDude
>
> I made a video series on how to do all that stuff, but I didn't have a microphone at the time.
I'll redo them at some point. In the mean time, here's the fix for Sarah's UVs.
It might break some UV mapping in other characters though, I'm not sure.
Replace lines 301-303 with:
tu = ReadBEfloat f
tv = ReadBEfloat f *-1 +1

[img]http://th00.deviantart.net/fs71/PRE/f/2 ... 4xbc13.jpg[/img

Great job. Thanks.
## Post #156
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-22T20:41:20+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

i hope to have something new soon related to this.
## Post #157
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-04-22T23:58:30+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

/jaw drops. Did you figure out the encryption?
That's crazy chrrox.
## Post #158
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2012-04-23T10:22:45+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from chrrox
>
> i hope to have something new soon related to this.
[ig]http://img210.imageshack.us/img210/3849/rof.png[/img][ig]http://3.bp.blogspot.com/_UAfxTNYxQGw/T ... 2Breal.png[/img]
[ig]http://img850.imageshack.us/img850/4881/girldc.png[/img]
My god....this is so epic o.o 
I freaking love this game!

Is this really decrypted? Or the ram dump mk64n did?
## Post #159
- Username: Samu
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 02, 2011 3:57 am
- Post datetime: 2012-04-23T15:59:33+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Wow chrrox, you are sick!
Aside from encryption, are the files different? ASF, AIF, etc?
## Post #160
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-23T16:29:36+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

the format is asf amf aif but the structure is more like the ps3 version and they changed some things to make it more of a pain but that will not stop me.
## Post #161
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-04-24T04:24:18+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope


## Post #162
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2012-04-24T06:08:50+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

This is awesome! 
So excited for this.
## Post #163
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2012-04-25T04:36:31+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from rexil
>
> Aurangzeb56 wrote:Can someone tell me how can i view the .unslz file in 3DS Max that i extracted from Disk 1 of the 360 version?
You need to decompress it with xbdecompress.
I already used sbdecompress and i got an ASF file,but when i tried to load that ASF file in 3DS Max it wasn't loading.
## Post #164
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-04-26T16:29:26+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from Aurangzeb56
>
> rexil wrote:Aurangzeb56 wrote:Can someone tell me how can i view the .unslz file in 3DS Max that i extracted from Disk 1 of the 360 version?
You need to decompress it with xbdecompress.
I already used sbdecompress and i got an ASF file,but when i tried to load that ASF file in 3DS Max it wasn't loading.
My guess is that what you are trying to import isn't an ASF, does it happens with every file? Have you tried one of the files listed in The Dude's list? If Max isn't "erroring" out then it's no a valid ASF file.
## Post #165
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2012-04-27T18:02:41+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from rexil
>
> Aurangzeb56 wrote:rexil wrote:You need to decompress it with xbdecompress.
I already used sbdecompress and i got an ASF file,but when i tried to load that ASF file in 3DS Max it wasn't loading.
My guess is that what you are trying to import isn't an ASF, does it happens with every file? Have you tried one of the files listed in The Dude's list? If Max isn't "erroring" out then it's no a valid ASF file.
Yeah i have and it doesn't loads any of the ASF files that it converts.
## Post #166
- Username: catchra
- Rank: Banned
- Number of posts: 4
- Joined date: Wed Aug 03, 2011 6:20 pm
- Post datetime: 2012-04-28T06:00:22+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Hear Aurangzeb56 try these [http://www.mediafire.com/download.php?bw2hcri8aqo6pgy](http://www.mediafire.com/download.php?bw2hcri8aqo6pgy)
i assume you are using TheDude's ms script import the models. I know these one's work
if it fails you might try reinstall 3ds max
## Post #167
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-04-29T18:49:52+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Also, if you open the MAXScript Listener, does it show an error?
## Post #168
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2012-05-04T09:35:37+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Yes,the two models of Meracle you gave me work.
@Dude:No it doesn't shows any error.
## Post #169
- Username: catchra
- Rank: Banned
- Number of posts: 4
- Joined date: Wed Aug 03, 2011 6:20 pm
- Post datetime: 2012-05-04T09:49:20+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

That's good maybe you didn't extract the files correctly or your copy of the game is damage
## Post #170
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2012-05-05T04:05:28+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Hmm or maybe i'm not extracting it the right way. :/
## Post #171
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2012-05-16T03:07:35+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

So can someone help me to extract these files?Since the way i'm doing it can't let me view them in 3DS Max. :/
## Post #172
- Username: catchra
- Rank: Banned
- Number of posts: 4
- Joined date: Wed Aug 03, 2011 6:20 pm
- Post datetime: 2012-05-16T14:29:28+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Ok hear is a guide for u Aurangzeb56

Hope this helps

[Star Ocean Extraction part 1](https://vimeo.com/42271516)
[Star Ocean Extraction part 2](https://vimeo.com/42271517)

And hear are some tools you may need

* snip *
## Post #173
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-07-20T18:30:24+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

I'm trying out 3ds Max 2013 and if anyone else gets this error when running this importer:

coCreateInstance() failed
Please check your registry entries
CLSID{F088EA74-2E87-11D3-BIF3-00C0F03C37D3} and make sure you are logged in as an administrator.

Open a command prompt as an Administrator ( right click - Run as administrator) and copy/paste the following
(right click in command prompt - paste)
regsvr32 “C:\Program Files\Autodesk\3ds Max 2013\MAXComponents.dll"

Should fix it.

Thanks to eicronie over at [http://area.autodesk.com/forum/autodesk ... er-applied](http://area.autodesk.com/forum/autodesk-3ds-max/autodesk-3ds-max--3ds-max-design-2011/cocreateinstance4041-failed-error-when-skin-modifier-applied)

EDIT:
   Autodesk, in their infinite wisdom, decided to change the way bones are sorted in 3ds Max 2013. Here's an updated importer.
[http://www.putlocker.com/file/FDDD3876A7F20DBB](http://www.putlocker.com/file/FDDD3876A7F20DBB)

A big thanks to sunnydavis at the Tomb Raider forums for the info.
[http://www.tombraiderforums.com/showpos ... tcount=334](http://www.tombraiderforums.com/showpost.php?p=6223014&postcount=334)

EDIT #2: Fixed link

EDIT #3: File List - [http://www.putlocker.com/file/11453AA4AABAF222](http://www.putlocker.com/file/11453AA4AABAF222)
## Post #174
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-04-24T03:01:46+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Just for kicks I thought I'd try and learn Noesis.


EDIT: I'll work on this some more after I finish learning the Softimage API.
[http://www.mediafire.com/download/3uyrt ... 1q5/SO4.py](http://www.mediafire.com/download/3uyrt39f8d6x1q5/SO4.py)

Yeah, I double posted. So what? Big whoop! Wanna fight about it?!
## Post #175
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2013-07-26T01:28:58+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from mariokart64n
>
> 
so nice 
can you share this model?
## Post #176
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-08-22T02:27:07+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

This only works correctly with that one file atm.
I still have to finish figuring out the mipmap headers.
## Post #177
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2013-08-22T15:09:02+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Appreciate the progress on this =) The Noesis tools would make it a lot easier to extract xD
Textures are still ps3 version and models xbox?
## Post #178
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-08-24T01:42:24+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Yeah, I haven't been too keen to mess with the PS3 format's index compression.
## Post #179
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-08-24T08:58:59+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Noesis supports PS3 index buffer decompression (though if I remember right it didn't work with some games). The first eight bytes of index buffer data (the compression header) is fairly easy to recognize.
## Post #180
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-08-24T12:55:59+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Yeah, chrrox showed me his Playstation All Stars code over here [https://code.google.com/p/noesis-plugin ... sa.py?r=15](https://code.google.com/p/noesis-plugins-official/source/browse/trunk/chrrox/import/beta/fmt_chrrox_psa.py?r=15), but I've been mired in other things.
## Post #181
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-08-24T19:18:47+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Cool, yep, that's the one. Then hip-hop, chip-chop, delete that redtube bookmark and get-to-get!
## Post #182
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-08-24T19:54:18+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Whoa, hey, I don't know anything about THAT!
## Post #183
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2013-08-24T23:02:48+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from howfie
>
> Cool, yep, that's the one. Then hip-hop, chip-chop, delete that redtube bookmark and get-to-get!

LOL.
## Post #184
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-08-25T02:18:59+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Oh man! Even Mr.Mouse is watching this thread.
I guess I better get going then.......
## Post #185
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2013-08-25T08:23:46+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope


## Post #186
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-25T12:04:53+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope


## Post #187
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-08-25T20:00:53+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Yes, my thoughts exactly.
## Post #188
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-08-26T04:01:22+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Let me know if you run into any trouble with indices. Noesis should support everything now, short of totally custom implementations.
## Post #189
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-08-26T14:54:45+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from MrAdults
>
> Let me know if you run into any trouble with indices. Noesis should support everything now, short of totally custom implementations.
OK, cool.
Per usual, I want to do it in straight code first - no help from Noesis,i.e., I want to actually learn how it all works first by coding in Maya/Softimage.
That's what I'm doing with the textures BTW.
chrrox pointed me to one of his Playstation All Stars plugins that does just that, so I think I'm good.
I have to finish wrangling textures first.
## Post #190
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-08-26T20:53:45+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

for edge decompression you need code to read n-bit numbers to a binary stream. id use noesis.
## Post #191
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-09-02T22:04:38+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

This should handle the X360 textures.
[http://www.mediafire.com/download/dl5ue ... _Noesis.py](http://www.mediafire.com/download/dl5uer6af5trqz5/SO4_tex_Noesis.py)
## Post #192
- Username: ils
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Sep 25, 2010 12:36 pm
- Post datetime: 2013-09-15T01:56:44+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

anyone can upload slz.bms?
i'm having trouble downloading from [http://aluigi.altervista.org/papers/bms/slz.bms](http://aluigi.altervista.org/papers/bms/slz.bms)
it looks like the file removed or something

Thank You
## Post #193
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-09-15T02:00:00+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

just paste it again in the url bar.
the site just has anti leech turned on.
## Post #194
- Username: ils
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Sep 25, 2010 12:36 pm
- Post datetime: 2013-09-15T02:39:37+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from chrrox
>
> just paste it again in the url bar.
the site just has anti leech turned on.

i still can't download the file
i even go to the main page [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
and manually click the link. but the Star Ocean one return error (i tried another link and it shows the bms/text file)

EDIT: OK solved.. it looks like my browser/ISP load from their cache. i managed to download using my Android phone 

Thank You
## Post #195
- Username: orbbu
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 20, 2010 5:36 pm
- Post datetime: 2013-09-16T20:09:00+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Any news about "Resonance of Fate / End of Eternity" from tri-aces ? I've tryed the script for extracting the .bin (from the first page) and it is not working...
## Post #196
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-09-27T00:41:17+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

@orbbu
It's encrypted so you'll have to do a RAM dump.

In other news, I found Eleyna's face in the XBox 360 data.
Thanks to rexil for reminding me.
I guess I never bothered to dump the second disc.
As usual there's a dozen or so duplicates so just use grepWin on the extracted/decompressed contents of disc 2,
search for  cn015   ,and you'll find it/them. File size should be just under 1MB.
grepWin: [http://stefanstools.sourceforge.net/grepWin.html](http://stefanstools.sourceforge.net/grepWin.html)
## Post #197
- Username: orbbu
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 20, 2010 5:36 pm
- Post datetime: 2013-09-30T17:35:15+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

@TheDude: Thanks for the information. I don't have a JTAG Xbox 360, so not possible for me -.- Too bad, I wanted Reanbell model so much T.T
## Post #198
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2013-09-30T18:58:03+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from orbbu
>
> @TheDude: Thanks for the information. I don't have a JTAG Xbox 360, so not possible for me -.- Too bad, I wanted Reanbell model so much T.T
You don't need a JTAG to get the models, you can dump the game disk to get the files.
## Post #199
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-10-01T16:32:12+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

I updated the links on page 12.
The Noesis importer there is a rough, half-broken WIP that will kick your dog when you're not looking so better stick with the max importer.
## Post #200
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2013-10-10T23:02:28+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Hey,

i recently tried to extract the game (Xbox360) again and got stuck on the last step of getting the ASF files. Is there any particular version of xbdecompress i need? I only get EXD files (screenshot of my folder and file in attachment if it helps in any way).

Can anybody help with this?
[Untitled-1.jpg](https://xentaxbackup.github.io/file/6690_Untitled-1.jpg)
## Post #201
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-10-11T01:50:09+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Is this the USA NTSC version?
Someone mentioned other versions have a different file layout.
## Post #202
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2013-10-11T11:13:06+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Yesah it is >< Was this worked on the JP or the EU version?
## Post #203
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-10-11T16:40:59+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

I can't even remember any more. Try folder 9.
## Post #204
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-12-07T16:24:26+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

PS3 geometry is flagrantly rude.
But that notwithstanding, I'm banging it out.






Update: The skinning works fine on the meshes with uncompressed index data, but fails miserably with the PS3 Edge data.
No idea why. The weights and bone pallet indices are stored identically.
## Post #205
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2014-06-09T07:49:37+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Has anyone ever cracked the encryption (or obfuscation?) of the PS3 version's aska0000.bin file?
This is what it looks like:
[](http://imgbin.org/index.php?page=image&id=17907)
The SLZ script from aluigi obviously won't work on this.

The "encryption" looks rather weak since there's patterns everywhere in the header, but it's not a simple XOR (at least not with a 8/16/32-bit value).
[](http://imgbin.org/index.php?page=image&id=17908)

Any way I can use this, instead of grabbing an XBox360 copy of the game off eBay? Doesn the Japanese PS3 version have a different format for this file? Maybe I can grab a copy next time I'm in Japan...

-Darkstar
## Post #206
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2014-06-09T14:26:15+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

I don't recall there being any encryption, but then again, I ftp'ed the file to my computer from my jailbroken PS3 so try that if you haven't already.
It's been a while so I don't remember anything beyond that. Also, I didn't save the bin file, only the contents.

Also, I might have figured out why the skinning isn't working right for the PS3 EDGE data, but I've got to make a PlayStation All-Stars Battle Royale importer first to test that out.
## Post #207
- Username: yoshi
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 26, 2011 4:41 pm
- Post datetime: 2014-08-12T09:53:11+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from Darkstar
>
> Has anyone ever cracked the encryption (or obfuscation?) of the PS3 version's aska0000.bin file?
This is what it looks like:

i'd wager a guess it's similar to encryption of the toc on ps2 tri-ace games. Check cue's code on how to generate decryption keys for tri-ace ps2 games, it might still apply to ps3 : 

[http://www.romhacking.net/forum/index.p ... #msg196448](http://www.romhacking.net/forum/index.php/topic,7790.msg196448.html#msg196448)  (the quoted code)
## Post #208
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2014-11-18T00:47:45+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

For what it's worth, here's a (slightly) broken PS3 importer that I was going to post in May, but I guess I forgot to.
[http://1drv.ms/11m42XR](http://1drv.ms/11m42XR)
"TA_SI_PS3.py" or "tA_Maya_PS3.py" /also needs Numpy_Maya2015x64)


Issues:
I never got the Playstation EDGE format skin to work.
Trying to import someone's head will crash Maya.
Sometimes objects are scattered all over the place.
 


[](http://fc04.deviantart.net/fs71/f/2014/321/8/3/srf_003_calnus_ii_by_mrfuzzlebum-d86rznx.jpg)
## Post #209
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2015-04-15T01:23:34+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Star Ocean 5 announced for PS4, PS3.
[http://gematsu.com/2015/04/star-ocean-5 ... or-ps4-ps3](http://gematsu.com/2015/04/star-ocean-5-announced-for-ps4-ps3)
## Post #210
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2016-04-03T14:46:04+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Did anyone manage to extract anything from aska0000.bin in the PS3 version?
Edit: Nevermind, I got it. However, would anyone have any idea as what the sound  (not BGM) files are?
## Post #211
- Username: Bryan
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Feb 22, 2017 10:17 am
- Post datetime: 2018-02-03T10:21:33+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Now that the game was released on PC, is there an easier way to extract the models?
## Post #212
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-03T19:16:36+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

> Reply from TheDude
>
> I'll work on this some more after I finish learning the Softimage API.
http://www.mediafire.com/download/3uyrt ... 1q5/SO4.py

> Reply from TheDude
>
> This should handle the X360 textures.
http://www.mediafire.com/download/dl5ue ... _Noesis.py

> Reply from TheDude
>
> ....here's a (slightly) broken PS3 importer that I was going to post in May, but I guess I forgot to.
http://1drv.ms/11m42XR
"TA_SI_PS3.py" or "tA_Maya_PS3.py" /also needs Numpy_Maya2015x64)
links are busted, do you still have these scripts lying around? specifically the XSI and Noesis python scripts
## Post #213
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2018-02-13T22:11:05+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

This is all I could find: [https://app.box.com/s/5plmvyxid2fyp283jxnyx3bwma6w9z52](https://app.box.com/s/5plmvyxid2fyp283jxnyx3bwma6w9z52)
So I included some junk as a consolation ....or something.
## Post #214
- Username: alduin2000
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 30, 2019 8:34 pm
- Post datetime: 2019-05-01T13:18:23+00:00
- Post Title: Re: [X360] Star Ocean The Last Hope

Any way to unpack the BIN files of the PC version? 
0000.bin  12 GB
0001.bin  35 GB

I tried all the method in this topic, but nothing work with the PC version.
I wonder how are the files inside
