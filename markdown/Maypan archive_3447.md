## Post #1
- Username: babebabe
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Jan 07, 2006 12:19 am
- Post datetime: 2009-04-27T16:34:12+00:00
- Post Title: Maypan archive

Maypan archive [http://maypan.co.kr/](http://maypan.co.kr/)
FxAdr containt header and information
FxSpr containt actual data
FxAdr have format like this: {name}{108 byte information} and so on, but that all I figure   , some one help me to unpack these file , thanks all ^_^
[texture.zip](https://xentaxbackup.github.io/file/1989_texture.zip)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-27T20:20:47+00:00
- Post Title: Maypan archive

it's a strange format moreover because the files look strange like "headerless"... if you have other sample files they can be useful.

in the meantime a quick test script can be the following, as you can see the name of the data file to open is fixed because I don't have other examples to guess the difference between the filename of the header and data file:

```
string MYFILENAME -= "Adr.ltf"
string MYFILENAME -= "Spr.ltf"
set NAME_ADR MYFILENAME
set NAME_SPR MYFILENAME
string NAME_ADR += "Adr.ltf"
string NAME_SPR += "Spr.ltf"
open FDSE NAME_ADR 0
open FDSE NAME_SPR 1

get FILESIZE asize

for
    savepos OFFSET
    if OFFSET >= FILESIZE
        cleanexit
    endif

    getdstring NAME 108 # name and other useless stuff
    get OFFSET long
    get DUMMY long
    get SIZE long
    get TYPE long

    log NAME OFFSET SIZE 1
next
```
## Post #3
- Username: babebabe
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Jan 07, 2006 12:19 am
- Post datetime: 2009-04-28T02:39:39+00:00
- Post Title: Maypan archive

Yep I think so too, that is headless, I just need size of texture, start point and size in *Spr file, then I will rebuild DDS file, but there are look like they encoded that information somewhere 
[texture.rar](https://xentaxbackup.github.io/file/1990_texture.rar)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-28T10:35:12+00:00
- Post Title: Maypan archive

ok, from what I have seen these tga images are stored in raw uncompressed format indeed if you try to rename them as .raw and open them with irfanview setting 8 bit and a resolution of about 1024x640 you can see the image.
anyway I have updated the script in the previous post for handling the input filename automatically
