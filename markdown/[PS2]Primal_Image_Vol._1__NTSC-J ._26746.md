## Post #1
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2023-05-09T11:10:34+00:00
- Post Title: [PS2]Primal_Image_Vol._1__NTSC-J .

Hi.This is an old PS2 game contains pretty nice 3d model at that era.
Due to my limited knowledge of decoding..wasn't able to open it's archieve.
It's a CD game,after ripping the image,have to convert it's .bin/.cue into .iso.
There are 2 possible files may be the main container of 3d model.
1st called VIEWDATA.CIG
2nd called ZERO.NOP
I uploaded both of them into send space if you want to look them.
I remembered i had tried to look it's dumped data via cheat engine before,but unlukyly didn't get too much clue.
Hope you can help to open it.
Sample
VIEWDATA.CIG
[https://www.sendspace.com/file/dczlmd](https://www.sendspace.com/file/dczlmd)
ZERO.NOP
[https://www.sendspace.com/file/3183xo](https://www.sendspace.com/file/3183xo)
[0000995497L.jpg](https://xentaxbackup.github.io/file/23789_0000995497L.jpg)
## Post #2
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2023-05-10T12:20:32+00:00
- Post Title: [PS2]Primal_Image_Vol._1__NTSC-J .

watched VIEWDATA.CIG in hex editor.
Found some visible strings and possible texture,,but can't adjust to correct palette offset yet.
So,I assume this archieve is not compressed,,just a container,may be a good news.
[hex.png](https://xentaxbackup.github.io/file/23792_hex.png)
## Post #3
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2023-05-10T17:59:02+00:00
- Post Title: [PS2]Primal_Image_Vol._1__NTSC-J .

Well, i just did not find any TOC header to give files at all.

but if you want to extract the texture, you can do a workaround with findloc

```
math i = 0
get dummy long
do
    math OFFSET + 4
   
    goto OFFSET
    get NAME string
    findloc NEXT_OFFSET long "0x00564552" "" 0

    if NEXT_OFFSET == ""
        get SIZE asize
    else
        math SIZE = NEXT_OFFSET
    endif

    math SIZE -= OFFSET
    STRING PATH = NAME
    log NAME OFFSET SIZE
    math i += 1
    math OFFSET = NEXT_OFFSET
while NEXT_OFFSET != ""

```


This should extract of all textures.
## Post #4
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2023-05-10T19:52:36+00:00
- Post Title: [PS2]Primal_Image_Vol._1__NTSC-J .

It's compelete file list is as picture.
Maybe it's header is stored in the IOPRP15.IMG,,,or PS2 executable PBPX952.01
Also found some strings related to skeleton names of 3d model in the executable too.
IOPRP15.IMG
[https://www.sendspace.com/file/hha46l](https://www.sendspace.com/file/hha46l)

PBPX_952.01
[https://www.sendspace.com/file/umwhaf](https://www.sendspace.com/file/umwhaf)
[img list.jpg](https://xentaxbackup.github.io/file/23802_img list.jpg)
## Post #5
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2023-05-10T19:56:32+00:00
- Post Title: [PS2]Primal_Image_Vol._1__NTSC-J .

possible skeleton name in ps2's executable..
so there is possibility 3d model is stored here.
[skel_name.jpg](https://xentaxbackup.github.io/file/23803_skel_name.jpg)
