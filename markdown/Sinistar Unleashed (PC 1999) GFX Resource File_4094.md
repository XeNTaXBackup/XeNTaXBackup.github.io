## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-01-28T21:22:58+00:00
- Post Title: Sinistar Unleashed (PC 1999) GFX Resource File

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-01-30T01:54:03+00:00
- Post Title: Sinistar Unleashed (PC 1999) GFX Resource File

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-02-02T07:50:40+00:00
- Post Title: Sinistar Unleashed (PC 1999) GFX Resource File

Each archive seems oddly uncompressed and are just used to store the data. I was able to extract audio from the sounds archive, and see some scripts. EVERYTHING is stored in these "GFX Resource Files V1.0".

Found something that may be useful. It is a DLL called rsrc.dll and is specifically used by the game in handling the "GFX Resource File" format.
[rsrc.rar](https://xentaxbackup.github.io/file/2761_rsrc.rar)
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-02-04T04:33:23+00:00
- Post Title: Sinistar Unleashed (PC 1999) GFX Resource File

The above attachment is a DLL used by the game to read the GFX Resource Files V1.0 files. It should help for those that can read them, I can't. It is all gibberish to me when I try debugging it.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-04T08:17:51+00:00
- Post Title: Sinistar Unleashed (PC 1999) GFX Resource File

uhmm, maybe try the following script:

```

getdstring SIGN 32
string SIGN -= -17
if SIGN != "GFX Resource File"
    cleanexit
endif

get OFFSET1 long
get OFFSET2 long
get OFFSET3 long
get OFFSET4 long
get OFFSET5 long

goto OFFSET5
get NAMES long
for i = 0 < NAMES
    get NAMESZ long
    getdstring NAME NAMESZ
    putarray 0 i NAME
next i

goto OFFSET4
for i = 0
    savepos MYOFF
    if MYOFF >= OFFSET5
        cleanexit
    endif
    get DUMMY long
    get NAME_NUM long
    get DUMMY long
    get OFFSET long
    get SIZE long

    if NAME_NUM >= 0
        getarray NAME 0 NAME_NUM
    else
        set NAME string "data"
    endif
    string NAME += _
    string NAME += i
    string NAME += ".dat"

    log NAME OFFSET SIZE
next i
```
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-02-04T17:58:48+00:00
- Post Title: Sinistar Unleashed (PC 1999) GFX Resource File

Here is what happens when I try dumping the content of sound.rsc. Doesn't quite read the structure correctly. And when I try extracting textures it gives an unreadable format.
[SinistarSounds.png](https://xentaxbackup.github.io/file/2766_SinistarSounds.png)
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-02-07T21:44:41+00:00
- Post Title: Sinistar Unleashed (PC 1999) GFX Resource File

The script doesn't seem to extract the sounds correctly, doesn't keep their directory structure which is seen in the header there. The TGA files also do not seem readable.
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-08T09:17:18+00:00
- Post Title: Sinistar Unleashed (PC 1999) GFX Resource File

only some archives have filenames inside them.
for the content of the files I can't help, what was archived is extracted as is.
if someone is interested in the format of these files and consequently in updating the script he's welcome, I'm not.
## Post #9
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-02-08T18:34:37+00:00
- Post Title: Sinistar Unleashed (PC 1999) GFX Resource File

Ah I see, well thanks anyways, we are somewhere close at least.
