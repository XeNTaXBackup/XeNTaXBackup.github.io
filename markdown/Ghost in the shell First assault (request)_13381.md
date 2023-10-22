## Post #1
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-10-03T05:01:55+00:00
- Post Title: Ghost in the shell: First assault (request)

Can anybody help with unpack dat archives?
Game files here:
[https://mega.nz/#F!hos3hbgA!osg5PEdocR4ytQqjcupVhg](https://mega.nz/#F!hos3hbgA!osg5PEdocR4ytQqjcupVhg)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-10-03T11:41:33+00:00
- Post Title: Ghost in the shell: First assault (request)

DAT files is encrypted. Need full game for research.
## Post #3
- Username: atvaark
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Aug 28, 2015 10:19 pm
- Post datetime: 2015-10-03T22:39:33+00:00
- Post Title: Ghost in the shell: First assault (request)

The game is protected with Themida, but I had no luck with unpacking it yet. If someone wants the binaries just send me a PM.
## Post #4
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-10-04T21:30:38+00:00
- Post Title: Ghost in the shell: First assault (request)

binary of game:
[https://www.dropbox.com/s/ta3st9q9ihzig ... ng.7z?dl=0](https://www.dropbox.com/s/ta3st9q9ihzigy1/Shipping.7z?dl=0)
## Post #5
- Username: no9
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 07, 2015 12:13 pm
- Post datetime: 2015-10-07T04:15:36+00:00
- Post Title: Ghost in the shell: First assault (request)

> Reply from Ekey
>
> DAT files is encrypted. Need full game for research.

No it's not. Did you even check the file?



I literally copied it from point to point its all just raw data. I'll have a BMS Script up soon.
## Post #6
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-10-07T11:10:48+00:00
- Post Title: Ghost in the shell: First assault (request)

parser dat files

10 line - path to firectory for unpacked files
11 line - path to parsed file

Thank episoder for hint.
([https://facepunch.com/showthread.php?t= ... st48913579](https://facepunch.com/showthread.php?t=1487987&p=48913579&viewfull=1#post48913579))

upd: Fix skipping last file

How to use:

1. Download and install python's interpreter
([https://www.python.org/downloads/](https://www.python.org/downloads/))

2. Edit script - this is simple text file

10 line - path to firectory for unpacked files
11 line - path to parsed file

path_BaseDirectory = " _ your directory for unpacked files  _ "
unpack_file = " _ your path to *.dat file _"

3. Save it.

4. Drag and drop script file to python.exe

5. Wait, watch and enjoy 
[gits_unpacker1.1.py.7z](https://xentaxbackup.github.io/file/9869_gits_unpacker1.1.py.7z)
## Post #7
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2015-12-27T23:18:17+00:00
- Post Title: Ghost in the shell: First assault (request)

I used the Python 3.4 64bit to test your script.
I only downloaded the model.dat Db.dat and StringTable.dat 3 files.
Here is the result(I've edited path you mentioned in line 10 and line 11.

I've put the StringTable.dat and DB.dat in the same folder.

Here is the error log
 
```
  File "H:\GIS\gits_unpacker1.1.py", line 49, in <module>
    print("File discriptor offset: " + str(back_offset - 8) + " " +file_name)
TypeError: Can't convert 'bytes' object to str implicitly

```





Edit : Using the Python 32 bit version has successfully extracted the file.
Do not use 64 bit Python to run this script:P
## Post #8
- Username: staberind
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 21, 2016 7:20 am
- Post datetime: 2016-04-20T23:29:57+00:00
- Post Title: Ghost in the shell: First assault (request)

This is fantastic, thanks, I bought it and was dismayed when I found it was just a crappy fps, now I can actually use the models and justify blowing £££ on it.

Yay, managed to extract the models, now to find a way to import/export the nif.
## Post #9
- Username: Squirrels
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 30, 2016 2:26 am
- Post datetime: 2016-04-29T18:30:51+00:00
- Post Title: Ghost in the shell: First assault (request)

Anybody have an idea how to read data from the TDB's from the DB.dat?
[DB.zip](https://xentaxbackup.github.io/file/10853_DB.zip)
## Post #10
- Username: Gazyi
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 15, 2014 11:07 pm
- Post datetime: 2016-06-20T16:07:06+00:00
- Post Title: Ghost in the shell: First assault (request)

Extractor script works only on Python 2.x. Just saying, so people don't waste time trying to run it on 3+ versons.
## Post #11
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2016-08-01T05:45:35+00:00
- Post Title: Ghost in the shell: First assault (request)

We hacking the game over at [UnknownCheats](http://www.unknowncheats.me/forum/other-fps-games/164610-ghost-shell-stand-complex-assault-online.html)
if anyone wants a full dump of the game exe with fixed IAT/Imports pm me.
They using themida which is so annoying man
## Post #12
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-04-04T04:38:15+00:00
- Post Title: Ghost in the shell: First assault (request)

Would someone possibly be able to help me out here...? I'm not entirely sure what I need to do to rectify this as it doesn't seem to have been an error anyone else has come up against...
[gits.JPG](https://xentaxbackup.github.io/file/12742_gits.JPG)
## Post #13
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-04T04:54:20+00:00
- Post Title: Ghost in the shell: First assault (request)

looks like the \f in the path is being interpreted as the escape sequence \x0c which is a form feed.

3 ways to fix this posted here   
[viewtopic.php?p=127222#p127222](http://forum.xentax.com/viewtopic.php?p=127222#p127222)

raw string

```
r"D:\Steam\steamapps\common\firstassault\Data"
```

double backslash

```
"D:\\Steam\\steamapps\\common\\firstassault\\Data"
```

forward slash

```
"D:/Steam/steamapps/common/firstassault/Data"
```
## Post #14
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-04-04T05:31:55+00:00
- Post Title: Ghost in the shell: First assault (request)

Thanks Ace! Always there when I need ya! ;D
## Post #15
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-06-07T23:06:58+00:00
- Post Title: Ghost in the shell: First assault (request)

just for completeness and future extraction. the v2 capable script. tested on closed pts files and working in python 2.7 (sfm) and 3.5 (blender) and extracting both the live and upcoming v2 files. and it's alil bit faster. 
[gitsfa_undat_wip.rar](https://xentaxbackup.github.io/file/12973_gitsfa_undat_wip.rar)
## Post #16
- Username: bladerj
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 20, 2017 11:36 pm
- Post datetime: 2017-08-20T17:39:42+00:00
- Post Title: Re: Ghost in the shell: First assault (request)

Thanks for the tool! did anyone manage to extract the audio? i got it with one tool, but the audios are unplayable because they have no headers
i really really need the tachikomas audio.
## Post #17
- Username: Ouren
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 25, 2017 3:35 am
- Post datetime: 2017-08-24T05:12:27+00:00
- Post Title: Re: Ghost in the shell: First assault (request)

> Reply from episoder
>
> just for completeness and future extraction. the v2 capable script. tested on closed pts files and working in python 2.7 (sfm) and 3.5 (blender) and extracting both the live and upcoming v2 files. and it's alil bit faster.

Hey duder! Thanks for writing this script!
I can't seem to get it to work though!


any ideas?
I tried typing the name of the file into that space "model.dat" with no luck at all.
## Post #18
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-25T01:53:29+00:00
- Post Title: Re: Ghost in the shell: First assault (request)

aluigi has a Quickbms script to split those *.dat samples too   
[http://aluigi.altervista.org/bms/ghost_ ... ssault.bms](http://aluigi.altervista.org/bms/ghost_shell_first_assault.bms)
## Post #19
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-08-31T02:43:59+00:00
- Post Title: Re: Ghost in the shell: First assault (request)

> Reply from Ouren
>
> episoder wrote:just for completeness and future extraction. the v2 capable script. tested on closed pts files and working in python 2.7 (sfm) and 3.5 (blender) and extracting both the live and upcoming v2 files. and it's alil bit faster. 

Hey duder! Thanks for writing this script!
I can't seem to get it to work though!


any ideas?
I tried typing the name of the file into that space "model.dat" with no luck at all.

you gotta put the complete data file path into the data_file path at the top. i thought it was obvious how i left the sample file in there.

@acewell that's for the old dat file version before 2.0 - won't work with the current files. and it's still using the slow binary search. that's exactly why i rewrote it and using the file index.
## Post #20
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-31T04:19:34+00:00
- Post Title: Re: Ghost in the shell: First assault (request)

> Reply from episoder
>
> @acewell that's for the old dat file version before 2.0 - won't work with the current files.
"2.0" samples please, i will rewrite the bms script  

> and it's still using the slow binary search. that's exactly why i rewrote it and using the file index.
slow? extracting all dats in a folder at once with Quickbms couldn't possibly be slower than having to enter the file names by
hand in a python script after each dat extraction, oh and making sure you have the correct python dependency installed first.
## Post #21
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-08-31T04:41:54+00:00
- Post Title: Re: Ghost in the shell: First assault (request)

sure... have a sample. 

[http://www.mediafire.com/file/9ltgb7t5gb49x9d/world.dat](http://www.mediafire.com/file/9ltgb7t5gb49x9d/world.dat)

extracts it in less then 5 seconds. and... i already posted that the script is pretty much version independant. both file and python versions.

nvm. me doing it myself.

```
# script for QuickBMS http://quickbms.aluigi.org

get ARCHIVE_SIZE asize
do
    idstring "\xdd\x88\x55\x22"
    get DUMMY short # 0x14
    get ZERO long
    get DUMMY1 long
    get DUMMY2 long
    get DUMMY3 long
    get DUMMY4 long
    get NAMESZ short
    get PAD short
    getdstring NAME NAMESZ
    goto PAD 0 SEEK_CUR

    findloc NEXT_OFF binary "\xdd\x88\x55\x22" 0 ""
    if NEXT_OFF == ""
        math NEXT_OFF == ARCHIVE_SIZE
    endif
    math SIZE = NEXT_OFF
    math SIZE - OFFSET

    savepos OFFSET
    log NAME OFFSET SIZE

    goto NEXT_OFF
while NEXT_OFF != ARCHIVE_SIZE
```


works for both file versions. it's actually as fast as the script. the offset calculation is wrong tho. it adds rubbish (from the next parsed file) at the end of the real files. the extract is twice as large. it may be functional, since the importers and converters don't check file sizes, but that's a bit of clutter that could be avoided perhaps.
## Post #22
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-31T06:19:55+00:00
- Post Title: Re: Ghost in the shell: First assault (request)

rewritten bms script to read the table instead   
*updated September 19, 2017*

```

goto -6
get TABLE_OFFSET long
for i 
    goto TABLE_OFFSET
    get IDX_SIG long
    if IDX_SIG != 0x2a2ceb87
        break		
    endif
    goto 0x10 0 SEEK_CUR
    get SIZE long
    goto 0x4 0 SEEK_CUR
    get NAME_SIZE long
    goto 0xa 0 SEEK_CUR
    get DATA_OFFSET long
    goto NAME_SIZE 0 SEEK_CUR
    savepos TABLE_OFFSET 
    goto DATA_OFFSET 
    get CHUNK_SIG long
    goto 0x16 0 SEEK_CUR
    get NAME_SZ short
    get SKIP short
    getdstring NAME NAME_SZ
    goto SKIP 0 SEEK_CUR
    savepos OFFSET
    log NAME OFFSET SIZE    
next
```

works with your world.dat and the samples linked in the first post.
## Post #23
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-08-31T06:41:46+00:00
- Post Title: Re: Ghost in the shell: First assault (request)

good. nvm my lousy quick edit then.
## Post #24
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-31T07:56:13+00:00
- Post Title: Re: Ghost in the shell: First assault (request)

and just for kicks i converted your python code to a Noesis python extraction script  
*script updated September 19, 2017*


 extract_GhostintheShellFirstAssault_dat.zip
(703 Bytes) Downloaded 151 times
## Post #25
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-08-31T15:41:23+00:00
- Post Title: Re: Ghost in the shell: First assault (request)

yeh. am i stupid? they are both not working with the 2.0, if you don't skip the skip.
## Post #26
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-09-20T02:54:01+00:00
- Post Title: Re: Ghost in the shell: First assault (request)

> Reply from episoder
>
> they are both not working with the 2.0, if you don't skip the skip.
yeah i just updated both the bms script and Noesis python script to "skip the skip" after the string  
i had to see more samples to understand what that short data meant. they should work with all versions now
