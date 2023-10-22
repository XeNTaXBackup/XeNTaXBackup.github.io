## Post #1
- Username: amdl
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Apr 16, 2012 8:38 pm
- Post datetime: 2012-04-17T07:52:56+00:00
- Post Title: Jewel Legends - Tree of Life  .pak files

Hi all, sorry my English is not very good.
I followed all the steps to pack a. Pak and the process ends well, but does not modify the xml that I changed.

- unpack .pak with bms idstring "gfcpk"
- Modified framework.xml, line 45 and 46 EN by ES
- Deleted all other files
- Pack - 1 files reimported in 1 seconds
- Copy in the game xml.pak

but the game still in english, I unpack the. pak and is EN and not ES

What am I doing wrong? I send the. pak

NO LINKS TO GAME FILES ALLOWED!

Thank you very much for your work.

Regards
## Post #2
- Username: amdl
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Apr 16, 2012 8:38 pm
- Post datetime: 2012-04-18T16:15:05+00:00
- Post Title: Jewel Legends - Tree of Life  .pak files

up
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-04-20T10:51:54+00:00
- Post Title: Jewel Legends - Tree of Life  .pak files

Did you not read the rules? NO GAME FILES !
## Post #4
- Username: amdl
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Apr 16, 2012 8:38 pm
- Post datetime: 2012-04-21T00:24:09+00:00
- Post Title: Jewel Legends - Tree of Life  .pak files

Sorry, I thought it was the full game.
## Post #5
- Username: chenshanhuai
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 01, 2012 12:17 pm
- Post datetime: 2012-12-09T15:01:09+00:00
- Post Title: Jewel Legends - Tree of Life  .pak files

> Reply from amdl
>
> Sorry, I thought it was the full game.

The game name is DarkMysteries TheSoulKeeper 

Follow is the game link:


[http://forums.bigfishgames.com/forums/show/3135.page](http://forums.bigfishgames.com/forums/show/3135.page)
## Post #6
- Username: chenshanhuai
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 01, 2012 12:17 pm
- Post datetime: 2012-12-09T15:16:39+00:00
- Post Title: Jewel Legends - Tree of Life  .pak files

> Reply from amdl
>
> Hi all, sorry my English is not very good.
I followed all the steps to pack a. Pak and the process ends well, but does not modify the xml that I changed.

- unpack .pak with bms idstring "gfcpk"
- Modified framework.xml, line 45 and 46 EN by ES
- Deleted all other files
- Pack - 1 files reimported in 1 seconds
- Copy in the game xml.pak

but the game still in english, I unpack the. pak and is EN and not ES

What am I doing wrong? I send the. pak

NO LINKS TO GAME FILES ALLOWED!

Thank you very much for your work.

Regards


# Mystery Stories: Mountains of Madness
# script for QuickBMS [http://quickbms.aluigi.org](http://quickbms.aluigi.org)

idstring "gfcpk"
get VER byte
getdstring KEY 4
get DUMMY long

get SIZE asize
log MEMORY_FILE 0 SIZE

print "wait some seconds/minutes for the decryption..."
savepos OFFSET
for i = OFFSET < SIZE
    getvarchr T MEMORY_FILE i
    math C = i
    math X = i
    math X &= 3
    getvarchr X KEY X
    math C ^= X
    math T ^= C
    putvarchr MEMORY_FILE i T
next i

print "extraction..."
goto OFFSET MEMORY_FILE
get FILES long MEMORY_FILE
for i = 0 < FILES
    get NAMESZ long MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
    get ZIP long MEMORY_FILE
    get SIZE long MEMORY_FILE
    get OFFSET long MEMORY_FILE
    get ZSIZE long MEMORY_FILE
    if ZIP == 0
        log NAME OFFSET SIZE MEMORY_FILE
    else
        clog NAME OFFSET ZSIZE SIZE MEMORY_FILE
    endif
next i
## Post #7
- Username: amdl
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Apr 16, 2012 8:38 pm
- Post datetime: 2012-12-10T12:02:02+00:00
- Post Title: Jewel Legends - Tree of Life  .pak files

at the time the game was Jewel Legends - Tree of Life, and now the same thing happens with Dark Mysteries: The Soul Keeper.
The bms I had it, I need to repack the file.
I do all the steps to repack, but the file is not modified.

thanks
