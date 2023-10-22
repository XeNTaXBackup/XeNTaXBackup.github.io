## Post #1
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-08-03T01:54:15+00:00
- Post Title: Megaman Powered-Up

"SPUMAPDT"
 Wonder if someone wouldn't mind look at this.

[http://dl.dropbox.com/u/32409323/Rips/MMPU.7z](http://dl.dropbox.com/u/32409323/Rips/MMPU.7z)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-03T02:47:33+00:00
- Post Title: Megaman Powered-Up

Here is a quickbms script to extract this.
what system is this for got a link to the game info?

```
comtype PUYO_LZ01
for
findloc start string "CPK0"
goto start
get cpk long
get zsize long
get size long
get null long
savepos offset
math zsize - 0x10
clog "" offset zsize size
math offset + zsize
goto offset
next

```
## Post #3
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-08-03T03:01:16+00:00
- Post Title: Megaman Powered-Up

It's on PSP. What do you mean link to the game's info? Do you mean the .loc file?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-03T03:13:04+00:00
- Post Title: Megaman Powered-Up

nah i dint know if you had any info on the game is it 3d or is it 2d side scrolling but now that i know its psp i can look it up.
## Post #5
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-08-03T07:48:49+00:00
- Post Title: Megaman Powered-Up

It's 2D.5. 3D Objects, 2D Backgrounds.
 I noticed that the PTE file seems to be graphic files. I look at them ina  tile editor and saw some images, but I think they are somewhat compressed.

 I noticed that the PTE file seems to be graphic files. I look at them ina  tile editor and saw some images, but I think they are somewhat compressed.

[http://dl.dropbox.com/u/32409323/Rips/MMPU_**.7z](http://dl.dropbox.com/u/32409323/Rips/MMPU_**.7z)
[http://dl.dropbox.com/u/32409323/Rips/MMPU_Other.7z](http://dl.dropbox.com/u/32409323/Rips/MMPU_Other.7z)
Formats Just replace the ** with the following:

D5
DAT
DBS
HEA
HIT
IMG
NFC
PTE Possibility of being graphic file or archive files.
SDB
VAP
WAV *(It has a RIFF Wavfmt header, but doesn't play in any audio player or editor.)
XML  *(Doesn't seem to be an actual XML file.)
