## Post #1
- Username: rageraz3
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon May 17, 2010 4:30 am
- Post datetime: 2011-12-18T05:04:05+00:00
- Post Title: need help to begin reading game archive file structure

hi there . i was trying to findout on extracting this game package.
but still gettin confused.. 
[sample.zip](https://xentaxbackup.github.io/file/4908_sample.zip)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-18T10:43:44+00:00
- Post Title: need help to begin reading game archive file structure

I have made the script but you must specify the full name of the game first.
## Post #3
- Username: rageraz3
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon May 17, 2010 4:30 am
- Post datetime: 2011-12-19T01:38:02+00:00
- Post Title: need help to begin reading game archive file structure

wow.. cool, the game is [Age Of wushu](http://9yin.woniu.com/index.html).   can you teach me how to read?.. uhm the files is compressed i think?.. i was tries using hex workshop but always fail..
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-19T07:53:19+00:00
- Post Title: need help to begin reading game archive file structure

*EDIT* updated script

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "PCK"
get TMP byte

    savepos MYOFF
    get NAMESZ short
    get ZERO long
    get FILES long
    get HEAD_SIZE long
    savepos TMP
    math TMP -= MYOFF
    math NAMESZ -= TMP
    getdstring NAME NAMESZ

for i = 0 < FILES
    savepos MYOFF
    get NAMESZ short
    get OFFSET long
    get TYPE long
    get SIZE long
    get ZSIZE long
    getdstring DUMMY 5
    get DUMMY long
    savepos TMP
    math TMP -= MYOFF
    math NAMESZ -= TMP
    getdstring NAME NAMESZ
    clog NAME OFFSET ZSIZE SIZE
next i
```

the archive contains compressed files so let me know if you receive a compression error with some archives because it's possible that some files may be not compressed (the provided archive contains only compressed files).

for the rest the format is enough simple with a 16bit value that specifies how much long is the information entry.
## Post #5
- Username: rageraz3
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon May 17, 2010 4:30 am
- Post datetime: 2011-12-19T10:11:09+00:00
- Post Title: need help to begin reading game archive file structure

thank's man. i'll post here for any errors.  can you give me some tips and trick about reading game archive using hex?.. i really want to learn. btw, i already check your blog [aluigi.altervista.org](http://aluigi.altervista.org) and read some information about qbms. i love this one   [q3infoboom](http://aluigi.altervista.org/quickbms/q3infoboom.zip.htm). thank's man
## Post #6
- Username: rageraz3
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon May 17, 2010 4:30 am
- Post datetime: 2011-12-19T16:03:45+00:00
- Post Title: need help to begin reading game archive file structure

hi, i already test it with larger file. it shows "error: the requested amount of bytes to allocate is negative (-2)" what is it means?.. the filesize is about 292,224,623 bytes. it has 5146 files inside.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-19T17:04:47+00:00
- Post Title: need help to begin reading game archive file structure

The contents of this post was deleted because of possible forum rules violation.
[map_ini.7z](https://xentaxbackup.github.io/file/4917_map_ini.7z)
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-19T18:43:11+00:00
- Post Title: need help to begin reading game archive file structure

ok solved, recheck the previous post
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-19T18:57:31+00:00
- Post Title: need help to begin reading game archive file structure

Works fine.
## Post #10
- Username: rageraz3
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon May 17, 2010 4:30 am
- Post datetime: 2011-12-19T21:17:55+00:00
- Post Title: need help to begin reading game archive file structure

yup it works .. it's gonna be the one of my precious collection.  i already collected some bms script with example of each script... now time for me to learn again.  thank you mr. aluigi for helping.
