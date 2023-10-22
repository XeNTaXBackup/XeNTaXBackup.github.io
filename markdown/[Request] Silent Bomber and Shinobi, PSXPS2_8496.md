## Post #1
- Username: Shinobi
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 07, 2012 9:19 pm
- Post datetime: 2012-03-07T13:43:37+00:00
- Post Title: [Request] Silent Bomber and Shinobi, PSX/PS2

hey, I wonder if anyone can rip/extract the models from one of these games, the first one is Silent bomber and it's for PSX, I can provide the files, it's about 300mb and they're all in .BIN
Second one is called Shinobi and is for PS2, the rom is available on the net.
## Post #2
- Username: Shinobi
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 07, 2012 9:19 pm
- Post datetime: 2012-03-08T14:11:31+00:00
- Post Title: [Request] Silent Bomber and Shinobi, PSX/PS2

Managed to extract the files from the ps2 game Shinobi
I got these file extensions
.ADX
.BDA
.ESP
.EST
.EVD
.MLD
.MLT
.MLX
.SFD
.SOT
.VIB

Anyone know what they are for, or how I can view for example the models?
## Post #3
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-08T15:53:47+00:00
- Post Title: [Request] Silent Bomber and Shinobi, PSX/PS2

> Reply from Shinobi
>
> Managed to extract the files from the ps2 game Shinobi
I got these file extensions
.ADX
.BDA
.ESP
.EST
.EVD
.MLD
.MLT
.MLX
.SFD
.SOT
.VIB

Anyone know what they are for, or how I can view for example the models?
MLD,MLX is container files, model[HMDL], texture[HTSF]
It looks like HMDL format is about the same for Valkyria Chronicles.

Here's a quickbms script.
HMDL model extract by chrrox

```
findloc start string "HMDL"
goto start
savepos offset
get HMDL long
get size long
math size + 32
set name string i
set ext string ".HMDL"
string name += ext
log name offset size
math offset + size
goto offset
next i
```

HTSF Texture extract by chrrox
I have altered chrrox's Valkyria Chronicles quickbms script.

```
findloc start string "HTSF"
goto start
savepos offset
get HTSF long
get size long
math size + 32
set name string i
set ext string ".hts"
string name += ext
log name offset size
math offset + size
goto offset
next i
```
## Post #4
- Username: Shinobi
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 07, 2012 9:19 pm
- Post datetime: 2012-03-08T19:46:05+00:00
- Post Title: [Request] Silent Bomber and Shinobi, PSX/PS2

Thanks, I managed to get the HMDL and HTS files, now how do I import them into some 3d model viewing program?
## Post #5
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-08T21:02:31+00:00
- Post Title: [Request] Silent Bomber and Shinobi, PSX/PS2

> Reply from Shinobi
>
> Thanks, I managed to get the HMDL and HTS files, now how do I import them into some 3d model viewing program?
Without sample file, no one can help you
## Post #6
- Username: Shinobi
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 07, 2012 9:19 pm
- Post datetime: 2012-03-08T22:39:22+00:00
- Post Title: [Request] Silent Bomber and Shinobi, PSX/PS2

Here's the HMDL and HTS sample for Shinobi (PS2).

[http://www.datafilehost.com/download-cf640984.html](http://www.datafilehost.com/download-cf640984.html)
