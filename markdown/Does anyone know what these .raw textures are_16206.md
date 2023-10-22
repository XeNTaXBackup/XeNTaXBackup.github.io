## Post #1
- Username: Mikeee
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Apr 27, 2017 8:12 am
- Post datetime: 2017-04-27T00:17:44+00:00
- Post Title: Does anyone know what these .raw textures are?

[https://mega.nz/#!bxMiVRCA!bpq0pMSYQ44w ... 9vFY8cJsPk](https://mega.nz/#!bxMiVRCA!bpq0pMSYQ44wM5lbKSgj9AB97--OeC5uY9vFY8cJsPk)

Photoshop has trouble opening them, and the ones that do open are just a black and white noise pattern.

These are from an android game.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-27T02:40:57+00:00
- Post Title: Does anyone know what these .raw textures are?

what is the game name?

15 byte little-endian header followed by zlib compressed texture data

header
2 bytes - unk (always 0x7bd)
2 bytes - width
2 bytes - height
1 byte - format
4 bytes - uncompressed size of texture data
4 bytes - compressed size of texture data

this bms script will decompress all but one of your *.raw samples  

```
string NAME + "_dec"
get COMPRESSIONTYPE short
get WIDTH short
get HEIGHT short
get FORMAT byte
get SIZE long
get ZSIZE long
savepos OFFSET
set MEMORY_FILE binary "\x00\x00\x00\x00\x00\x00\x00\x00\x00"
putVarChr MEMORY_FILE 0x0 WIDTH short
putVarChr MEMORY_FILE 0x2 HEIGHT short
putVarChr MEMORY_FILE 0x4 FORMAT byte
putVarChr MEMORY_FILE 0x5 SIZE long
log NAME 0 9 MEMORY_FILE
append
if COMPRESSIONTYPE == 0x7bd
    comtype zlib_noerror
    clog NAME OFFSET ZSIZE ZSIZE
elif COMPRESSIONTYPE == 0x8bd
    comtype zstd
    clog NAME OFFSET ZSIZE SIZE
endif
append

```

the script also places a temporary 9 byte header in each file
2 bytes - width
2 bytes - height
1 byte - format
4 bytes - data size

to decompress "champ_result_640_960.raw" and "champ_result_640_960.raw1" you have to
append the data of *.raw1 to the *.raw file, then you can run the result through the bms script.  

there is still the issue of figuring out the various formats, but at least this is a start
## Post #3
- Username: Mikeee
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Apr 27, 2017 8:12 am
- Post datetime: 2017-04-28T02:11:55+00:00
- Post Title: Does anyone know what these .raw textures are?

These are for [https://www.catsthegame.com/](https://www.catsthegame.com/)

I saw another topic of the zeptolab .raw files you posted in and I got them open with offzip and trial and error of guessing the width and height of the image and opening them as .raw with photoshop! Is there an easier way to open them without having to input the width and height manually?
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-28T02:48:57+00:00
- Post Title: Does anyone know what these .raw textures are?

here is Noesis python script to open the textures decompressed by the bms script  


 tex_CrashArenaTurboStars_raw_dec.zip
(725 Bytes) Downloaded 57 times


supports RGBA8888, BGR565, ABGR4444
## Post #5
- Username: Mikeee
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Apr 27, 2017 8:12 am
- Post datetime: 2017-04-28T03:03:56+00:00
- Post Title: Does anyone know what these .raw textures are?

This is some wizardry! I can only assume though the stickers are weird colors due to them doing something with the colors in-game?
[http://i.imgur.com/92NntxJ.png](http://i.imgur.com/92NntxJ.png)

And anyways, thank you so much!
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-28T03:09:35+00:00
- Post Title: Does anyone know what these .raw textures are?

> Reply from Mikeee
>
> This is some wizardry! I can only assume though the stickers are weird colors due to them doing something with the colors in-game?
http://i.imgur.com/92NntxJ.png
what color are they in the game? do you have a reference photo for comparison?
i might need to switch the color channels around in the script.
## Post #7
- Username: Mikeee
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Apr 27, 2017 8:12 am
- Post datetime: 2017-04-28T03:15:07+00:00
- Post Title: Does anyone know what these .raw textures are?

> Reply from AceWell
>
> 
what color are they in the game? do you have a reference photo for comparison?
i might need to switch the color channels around in the script.
[http://i.imgur.com/2jrLlxl.jpg](http://i.imgur.com/2jrLlxl.jpg)
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-28T03:27:09+00:00
- Post Title: Does anyone know what these .raw textures are?

ok i updated the script here   
[viewtopic.php?p=130114#p130114](http://forum.xentax.com/viewtopic.php?p=130114#p130114)
## Post #9
- Username: Mikeee
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Apr 27, 2017 8:12 am
- Post datetime: 2017-04-28T03:31:11+00:00
- Post Title: Does anyone know what these .raw textures are?

> Reply from AceWell
>
> ok i updated the script here   
viewtopic.php?p=130114#p130114

Thank you my wizard friend!
## Post #10
- Username: tontonGrim
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 17, 2019 1:40 am
- Post datetime: 2019-06-16T18:17:58+00:00
- Post Title: Does anyone know what these .raw textures are?

Hello Acewell !,


i'm french, and two years later,  i would like too extract sprite from this game 

I used your bms script and your neosis script, but i have problems.

in zip joined, you have, yout bms script, your neosis script, a exemple of raw file and the bms result and neosis result.

Can you help me !

Thank you very much
[raw.zip](https://xentaxbackup.github.io/file/16361_raw.zip)
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-06-20T23:01:25+00:00
- Post Title: Does anyone know what these .raw textures are?

the compression on your new sample is zstd instead of zlib,
i have modified the bms script here to decompress both types now.   
[https://forum.xentax.com/viewtopic.php? ... 06#p130078](https://forum.xentax.com/viewtopic.php?f=18&t=16206#p130078)
## Post #12
- Username: tontonGrim
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 17, 2019 1:40 am
- Post datetime: 2019-06-21T14:46:27+00:00
- Post Title: Does anyone know what these .raw textures are?

Hello Acewell!

Thank you for your return, I was looking forward to it! 

It works ! thank you very much ! 
Little question, in the APK file, there are .pb files and .zst files (see my zip file)

Do you know what these files correspond to? is it animations, prefab or other? can I integrate them into Unity or extract them with another particular tool?

Thank you again for your help ! 
[zst_pb_files.zip](https://xentaxbackup.github.io/file/16382_zst_pb_files.zip)
## Post #13
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-06-25T07:15:49+00:00
- Post Title: Does anyone know what these .raw textures are?

> Reply from tontonGrim ↑Fri Jun 21, 2019 10:46 pm at Fri Jun 21, 2019 10:46 pm
>
> 
Little question, in the APK file, there are .pb files and .zst files (see my zip file)
Do you know what these files correspond to? is it animations, prefab or other? can I integrate them into Unity or extract them with another particular tool?
i don't see any zst files in the zip, the zps files are 
text files and i don't know what the pb files are for, sorry.
