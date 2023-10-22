## Post #1
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-02-04T12:31:32+00:00
- Post Title: Brute Force (XBOX 2003) - .tex files format

Hello everyone!

I've been digging through the files of a very underrated yet amazing game called Brute Force for the original Xbox back in the day.
 I managed to rip the sounds, but the problem now is obtaining textures for the HUD, characters, effects and even environment. 

As I searched, I stumbled upon .tex files that must have the data needed.
I uploaded a sample [here](https://www.dropbox.com/s/mj0vgyyvokgpdio/textures-common.tex?dl=0). Thanks for reading and I'm looking forward to a solution!
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-04T19:08:01+00:00
- Post Title: Brute Force (XBOX 2003) - .tex files format

headerless archive containing varying formats and sizes, 
there must be an index file somewhere with offsets etc.
or just use TextureFinder and patience to split it.
## Post #3
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-02-04T20:39:54+00:00
- Post Title: Brute Force (XBOX 2003) - .tex files format

I found a .xmb files with what might be needed for the common textures: [here](https://www.dropbox.com/s/yote6uywhgj4d1f/textures-common.xmb?dl=0).
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-05T03:08:33+00:00
- Post Title: Brute Force (XBOX 2003) - .tex files format

for now here is a bms script that will split and name the texture data from tex according to the info in xmb  

```

Open FDSE "textures-common.tex" 1

get FOLDER basename
idstring "BXML"
goto 0xc48 
for i = 1 to 258
	get HASH long
	get FORMAT byte
	get UNK threebyte
	get MIPS long //??
	get WIDTH long 
	get HEIGHT long
	get UNK2 byte 
	get OFFSET long
	get SIZE long
	string NAME p "%s\%03d_%08x_%02d_%04d_%04d_%02x.dxt" FOLDER i HASH MIPS WIDTH HEIGHT FORMAT
	log NAME OFFSET SIZE 1
next i
```

you open the textures-common.xmb file and the script will automatically find the textures-common.tex file if they are next to each other.

i didn't bother with adding headers here because there is a couple of swizzled formats,
i will try make a Noesis python script soon with this info to display the texture sequence.
## Post #5
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-02-05T16:58:30+00:00
- Post Title: Brute Force (XBOX 2003) - .tex files format

Awesome! I got a bunch of .dxt texture files, wonder how to convert them to png..
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-16T13:20:17+00:00
- Post Title: Brute Force (XBOX 2003) - .tex files format

i modified the previous bms script to log consistent header info into the filename so
it works with this Noesis python script, so you'll have to extract the dxt files again  


 tex_BruteForce_Xbox_dxt.zip
(554 Bytes) Downloaded 41 times


supports dxt3 and main mip only 
all but 23 of those extracted textures are dxt3 and the python script only supports dxt3 currently,
most of the unsupported formats are too small or not diverse enough for me to figure out as easily
so i'm not going to struggle decoding them, you have enough to work with for now i think.   
i may come back around to this at a later time unless someone else gets to it first.
## Post #7
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-25T00:33:54+00:00
- Post Title: Brute Force (XBOX 2003) - .tex files format

> Reply from Acewell ↑Fri Feb 16, 2018 9:20 pm at Fri Feb 16, 2018 9:20 pm
>
> 
i modified the previous bms script to log consistent header info into the filename so
it works with this Noesis python script, so you'll have to extract the dxt files again   
tex_BruteForce_Xbox_dxt.zip
supports dxt3 and main mip only 
all but 23 of those extracted textures are dxt3 and the python script only supports dxt3 currently,
most of the unsupported formats are too small or not diverse enough for me to figure out as easily
so i'm not going to struggle decoding them, you have enough to work with for now i think.   
i may come back around to this at a later time unless someone else gets to it first.

Hey would you be able to make this script work for all the textures in the game. please.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-26T15:13:00+00:00
- Post Title: Brute Force (XBOX 2003) - .tex files format

I checked those "dxt" files from the appended zip with a size >= 64 kB, at no avail. Nearest hit was the 24+8 bits option from TextureFinder for the 86 kB ones. (DXTx didn't apply.)
.


 BruteForce unk tex.zip
(155.34 KiB) Downloaded 17 times



Also be informed that there's a strange block of zeros from 0x2c5370 to 0x3c5380 in textures-common.tex, a 1 million byte gap which I found worth to mention, while the filesize is 4,418,645 bytes.
