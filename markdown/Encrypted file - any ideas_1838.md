## Post #1
- Username: bgbennyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Oct 15, 2005 6:41 pm
- Post datetime: 2006-04-15T15:12:30+00:00
- Post Title: Encrypted file - any ideas?

[Here](http://quick.mixnmojo.com/temp/BONE_anim_group_colors.prop) is a file from the game Bone: Out from Boneville and [here](http://quick.mixnmojo.com/temp/CSI_anim_group_colors.prop) is a file from CSI: 3 dimensions of murder. Both games are by the same developer and I'm pretty sure that the data for both files is the same.

The Bone file though, is encrypted - the CSI one isnt. If you xor the file from Bone with FF, you'll see that the data is the same. However the head and tail of the Bone file is somehow encrypted differently.

Can anyone work out an algorithm to get the head of the Bone file to match the CSI one?
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-15T22:04:23+00:00
- Post Title: Encrypted file - any ideas?

The data was indeed XORed with 255.

the Tail is not encrypted at all =o ...

and...the header is for now a mystery.  Im not even sure that
the header is really XORed, it seems to strange, and does not
have a pattern. (atleast not for 8bit XORs).

possibly ROL/ROR or XOR 16/32 bit.

if you come up with something more, let me now 

ive tried using "Inverse" aswell instead of XOR, and that does the same as
XOR 255. one good thing here is that the places in CSI file that are "0000"
have similiar values, but has the bytes flipped somehow,
and when looking at the bits, the seems to be inverted.

example: on the 0000 places of the header in the CSI file, there
are instead F83F , 03F8,  8F83 ? see the similiarities?

almost the same values, but is flipped somehow.
## Post #3
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-15T22:10:19+00:00
- Post Title: Encrypted file - any ideas?

could you post more BONE encrypted files? =o
i would need more of them too look at patterns.
## Post #4
- Username: bgbennyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Oct 15, 2005 6:41 pm
- Post datetime: 2006-04-15T23:17:21+00:00
- Post Title: Encrypted file - any ideas?

I can certainly post more bone files, unfortunately the file that I've already posted is the only one common to both games. I've uploaded some more  [here](http://quick.mixnmojo.com/temp/bone1/)

If you want to look at any more, Bone can be downloaded [here](http://www.telltalegames.com/products/bn0102) and the .ttarch archive can be unpacked with my dumper [here.](http://quick.mixnmojo.com/software.php#bonettarch)
## Post #5
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-16T17:33:18+00:00
- Post Title: Encrypted file - any ideas?

Ive downloaded some of the files and started looking,
its kinda interesting hmmms....

so, i decoded one of the splash screens using Inversion on all bytes in the file
and came up with an DDS image. however......while the image
is fully readable, it still seems to be something we dont know ...
because, if you look at the image it looks kinda good,
but has small glitches in a pattern, and i suppose the original image is not
looking like this?.

i have made small notes while decoding, and ive found out that there
seems to be a pattern. all blocks are 4096 bytes.
and the extra encoded block is always 64 bytes, however
the gap between the None-coded and encoded varies in size,
but in the end, the encoded+none encoded blocks
always sum up at 4096. so this might be solved soon.

here is my notes i took while decoding the DDS file
{
8C0 = 2240
6C0 = 1728
040 = 64
040 = 64
= 4096
}

Block1
{
FC0 = 4032 (a)
040 = 64
= 4096
}

Block2 {
DC0 = 3520
1C0 = 448
040 = 64
= 4032 (same as a)
+ 040 = 4096
}


i dont know if it makes any sense, i just keep it as reference later so i can
see what i have been doing 
[ttg_splash1.jpg](https://xentaxbackup.github.io/file/702_ttg_splash1.jpg)
## Post #6
- Username: bgbennyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Oct 15, 2005 6:41 pm
- Post datetime: 2006-04-16T18:46:56+00:00
- Post Title: Encrypted file - any ideas?

Sorry, yes I forgot to mention that the dds images have that corruption, its very odd - see [this](http://www.lucasforums.com/showthread.php?t=152418) thread for more information.

I dont know if the corruption is related to the encrypted file headers. The dds (dxtc) files are the only ones that have this extra encryption.
## Post #7
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-04-18T15:37:26+00:00
- Post Title: Encrypted file - any ideas?

if i could recommend one thing...post all links before expecting infos it may help people who reverse it.
## Post #8
- Username: bgbennyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Oct 15, 2005 6:41 pm
- Post datetime: 2006-04-18T17:07:17+00:00
- Post Title: Encrypted file - any ideas?

Thanks for having a look at this Strobe.  I think the image corruption is a seperate issue from the encoded headers - it may just be something implemented in the image decoder since the font files (which are also dds' have it too).
## Post #9
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-18T18:54:52+00:00
- Post Title: Encrypted file - any ideas?

It is really funny this "format"........i dont understand really one would encrypt the archive header so badly and leave the rest of the file almost
intact with just a Invert byte order, and some patterns encoded?

for the info, some of the patterns are also XOR 255 (or inverted),
, its a combination. i have even tried being desperate and XORed
the encoded blocks with the lenght of the archive. no luck though.

 However decoding the images in a dumb way would be just to follow the
pattern and rewrite it without decrypting it. but thats no fun =o

possible theories:
1.The creator of the format was insane and just wanted to mess
with people trying to extract it.

or

2.The "encrypted" patterns actually serves a purpose?


however, im still voting for theory number 1.

and a sidenote, im actually glad you didnt post any information on this
at first, that would have made me bored. Now when ive started figuring
out this by myself im much more triggered to get it done :X
## Post #10
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-04-19T14:37:05+00:00
- Post Title: Encrypted file - any ideas?

> Reply from Strobe
>
> and a sidenote, im actually glad you didnt post any information on this
at first, that would have made me bored. Now when ive started figuring
out this by myself im much more triggered to get it done :X

its masochism 

i was just speaking about the re-invent the wheel theory.
## Post #11
- Username: saulob
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Mar 02, 2007 2:37 pm
- Post datetime: 2007-03-23T03:13:40+00:00
- Post Title: Encrypted file - any ideas?

Yeah, I was reading the lucasforum post... 

Nice, they find the RIGHT encryption on the Bone data.ttarch file... 

It's Blowfish. I tried but no luck... who can help on this ? 

Thanks.
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-09T15:32:41+00:00
- Post Title: Encrypted file - any ideas?

I have figured the algorithm today while I was working on the TTARCH files in general.
practically this type of encryption works in the following way:
first are read the 4 bytes at the beginning of the file, it's needed to select 3 parameters:
- size of each block
- after how much blocks is performed the blowfish encryption
- after how much blocks the block is in clear-text

so if the parameters are 0x80 0x80 0x50 the first block is decrypted with blowfish using the same key of the archive, the second one is simply XORed with 0xff and the one at offset 0x2800 is clear.
I have implemented everything in a [script](http://aluigi.org/papers/bms/ttarch.bms) altough, obviously, a stand-alone tool is probably a better for this particular complex file format (but I'm too lazy).
## Post #13
- Username: bgbennyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Oct 15, 2005 6:41 pm
- Post datetime: 2009-05-09T17:09:15+00:00
- Post Title: Encrypted file - any ideas?

Wow, this thread is a real blast from the past.
As a sidenote - John_Doe figured out the ttarch and file encryptions in 2006, however Telltale asked that the decryption tool not be made public. See [here](http://quick.mixnmojo.com/telltale-tools-an-update) for more.
## Post #14
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-09T18:39:20+00:00
- Post Title: Encrypted file - any ideas?

> Reply from bgbennyboy
>
> however Telltale asked that the decryption tool not be made public
Who cares?
## Post #15
- Username: saulob
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Mar 02, 2007 2:37 pm
- Post datetime: 2009-05-10T22:20:54+00:00
- Post Title: Encrypted file - any ideas?

> Reply from Rheini
>
> bgbennyboy wrote:however Telltale asked that the decryption tool not be made public
Who cares?

Well, he did
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-16T19:44:16+00:00
- Post Title: Re: Encrypted file - any ideas?

oh about these files at the end I have opted for the stand-alone solution for various reasons (performances, maintainance and so on): [http://aluigi.org/papers.htm#ttarchext](http://aluigi.org/papers.htm#ttarchext)

and take note of the following:

```
the files are extracted exactly as they are inside the archive, indeed although some of them are just containers of common files (for example the d3dtx and font files contain dds images, and aud contain ogg streams) these containers use formats or some particular things which change from game to game and in some cases part of the raw data within them is encrypted too (like the first 0x800 bytes of the dds used in some games, don't worry it's just the same blowfish used in the rest of the archives, take a look to my code).
```
so I have decided to not implement an integrated extraction of the raw data located inside the meta files (like the dds inside the d3dtx files) just because the meta files are very unsteady and game-dependent so it's not possible to create a general rule quickly and easily without additional reversing and without testing over 20 games.

if someone has other ideas and wants to spend time on them (not me) feel free to contribuite :)
and if you have doubts I'm here
## Post #17
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-24T15:06:42+00:00
- Post Title: Re: Encrypted file - any ideas?

for the series "the best solution is the simplest" I have added the -m option to the ttarchext project which does a simple scan of the beginning of each file for finding DDS and OGG signatures in both clean and encrypted mode.
from my tests this solution seems to work very well and universally (which is the most important thing) so I hope it's useful
