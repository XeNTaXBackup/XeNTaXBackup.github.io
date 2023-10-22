## Post #1
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2018-06-20T09:39:56+00:00
- Post Title: FortniteGame-Switch.pak (Fortnite for Nintendo Switch)

Hey Guys,

I just decrypted the Nintendo Switch Game "Fortnite" and wanted to extract and probably rebuild the pak I just extracted from the Game.

I've tried the unreal_tournament_4.bms to extract the pak-file ( [http://zenhax.com/viewtopic.php?f=9&t=1005](http://zenhax.com/viewtopic.php?f=9&t=1005) ) without luck.

I'm getting this error:

> select the BMS script to use. type ? for using the clipboard
>
> - select the input archives/files to extract, type * or "" for whole folder and subfolders
>
> - select the output folder where extracting the files
>
> - open input file I:\Nintendo Switch\Fortnite Update\romfs\FortniteGame\Content\Paks\FortniteGame-Switch.pak
>
> - open script I:\Nintendo Switch\Fortnite Update\romfs\FortniteGame\Content\Paks\unreal_tournament_4 (1).bms
>
> - set output folder I:\Nintendo Switch\Fortnite Update\romfs\FortniteGame\Content\Paks
>
> 
>
>   offset           filesize   filename
>
> --------------------------------------
>
>   0000000000000000 0          FortniteGame/FortniteGame.uproject
>
> + 0000000000000049 7404       FortniteGame/FortniteGame.uproject
>
> Info:  algorithm   250
>
>        offset      0000000000000049
>
>        input size  0x0000000000000586 1414
>
>        output size 0x0000000000001cec 7404
>
>        result      0xffffffffffffffff -1
>
> 
>
> Error: the uncompressed data (-1) is bigger than the allocated buffer (7404)
>
> 
>
> Last script line before the error or that produced the error:
>
>   194 clog NAME CHUNK_OFFSET CHUNK_ZSIZE CHUNK_SIZE

Using u4pak.py gives me this:

> u4pak.py info "I:\Nintendo Switch\Fortnite Update\romfs\FortniteGame\Content\Paks\FortniteGame-Switch.pak"
>
> unsupported version: 6

So it seems the file is somehow compressed and uses UE4 PAK version 6?

Could you help me out with that?

I want to extract the files and, if possible, rebuild it / replace files.


EDIT:
Here's the file:
[https://drive.google.com/open?id=1s8fKs ... cnvkhOqku9](https://drive.google.com/open?id=1s8fKs24vjnt-w63PQh04LPcnvkhOqku9)
