## Post #1
- Username: atom0s
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Sep 27, 2014 4:19 pm
- Post datetime: 2014-10-03T07:16:18+00:00
- Post Title: Grim Dawn Content Files [.ARC]

Removed. (Find this info on my personal site or on Zenhax.)
## Post #2
- Username: atom0s
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Sep 27, 2014 4:19 pm
- Post datetime: 2014-10-03T19:05:45+00:00
- Post Title: Grim Dawn Content Files [.ARC]

Removed. (Find this info on my personal site or on Zenhax.)
## Post #3
- Username: Argonaut
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Sep 12, 2014 3:19 am
- Post datetime: 2014-10-03T19:27:31+00:00
- Post Title: Grim Dawn Content Files [.ARC]

Or you could use aluigi's QuickBMS script for this..

```
# script for QuickBMS http://quickbms.aluigi.org

quickbmsver "0.5.29"

comtype lzo1x

idstring "ARC"
getdstring TYPE 1
get FILES long

if TYPE == "E"
    # ARCE not tested!
    goto 0x78
    get ZSIZE long
    get SIZE long
    savepos OFFSET
    clog TEMPORARY_FILE OFFSET ZSIZE SIZE
    open "." TEMPORARY_FILE
else
    goto 0x80
endif

math NAMES_OFF = 0
for i = 0 < FILES
    get CRC long
    get OFFSET long
    get NAME_OFF long
    get DIR byte
    get SIZE threebyte
    reverselong SIZE
    math SIZE u>>= 8 # because it's 24bit and not 32

    putarray 0 i OFFSET
    putarray 1 i NAME_OFF
    putarray 2 i DIR
    putarray 3 i SIZE

    if OFFSET > NAMES_OFF
        math NAMES_OFF = OFFSET
    endif
next i

savepos BASE_OFF
math NAMES_OFF += BASE_OFF

set FOLDER string ""
for i = 0 < FILES
    getarray OFFSET   0 i
    getarray NAME_OFF 1 i
    getarray DIR      2 i
    getarray SIZE     3 i
    math OFFSET += BASE_OFF

    math NAME_OFF += NAMES_OFF
    goto NAME_OFF
    get NAME string

    # note that the folders structure is NOT handled correctly!!!
    # this is justa work-around

    if NAME == ""
        string NAME p= "%08x.dat" i
    endif
    if DIR == 0xff
        set FOLDER string NAME
    else
        set FNAME string FOLDER
        string FNAME += /
        string FNAME += NAME
        log FNAME OFFSET SIZE
    endif
next i
```
## Post #4
- Username: atom0s
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Sep 27, 2014 4:19 pm
- Post datetime: 2014-10-03T19:43:20+00:00
- Post Title: Grim Dawn Content Files [.ARC]

Removed. (Find this info on my personal site or on Zenhax.)
## Post #5
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2016-09-07T07:59:46+00:00
- Post Title: Grim Dawn Content Files [.ARC]

atom0s,
that github page is giving me 404.
Is it gone?
Is there a mirror?
Thanks!
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-07T09:27:08+00:00
- Post Title: Grim Dawn Content Files [.ARC]

he moved his stuff over to gitlab   
[https://gitlab.com/u/atom0s](https://gitlab.com/u/atom0s)
[https://gitlab.com/atom0s/grimarc/tree/master](https://gitlab.com/atom0s/grimarc/tree/master)
## Post #7
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2016-09-07T10:36:00+00:00
- Post Title: Grim Dawn Content Files [.ARC]

Indeed, thank you!!

I could not find the windows binaries though.
Are they available somewhere?
Thank you!

Edit
Nevermind. Attached.
[grimarc.rar](https://xentaxbackup.github.io/file/11668_grimarc.rar)
