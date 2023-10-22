## Post #1
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2009-09-10T00:16:13+00:00
- Post Title: cage & hab files.

well this section said post file archives you dont know about.

iv been playing "darkest of days" good game.

iv decided that the wepons will be nice in fallout3 but iv done some research into the file types & absoulutly nothing has come up. dos anyone know anything thay can share with me 

i can post one some if anyone wants to mess with it.
## Post #2
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2009-09-10T06:37:10+00:00
- Post Title: cage & hab files.

Cage is archive format, zlib compressed blocks, filenames preceding data blocks (null terminated).

zstring file_name
dword file_uncompressed_size
dword file_compressed_size
. dword block_uncompressed_size
. dword block_compressed_size
. byte[block_compressed_size] block_data
. repeat until end of file_compressed_size
repeat until end of cage file.

So simple a caveman could do it.
## Post #3
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2009-09-10T12:58:43+00:00
- Post Title: cage & hab files.

yeh srry, i must be a monkey then haha.


i guess you want me to open the file with notepad & put that stuff in it?.

is there anyware on this site where i could learn somethings?

-

the most iv done is extract hl2 stuff to fallout 3, vie crafty & max.

i think im getting in too deap lol, but im willing to learn
## Post #4
- Username: nikitatp
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 11, 2009 4:34 am
- Post datetime: 2009-09-10T20:57:03+00:00
- Post Title: cage & hab files.

> Reply from Rick
>
> Cage is archive format, zlib compressed blocks, filenames preceding data blocks (null terminated).

zstring filename
dword total_uncompressed_size
dword total_compressed_size
. dword block_uncompressed_size
. dword block_compressed_size
. byte[block_compressed_size] block_data
. repeat until end of total_compressed_size
repeat until end of cage file.

So simple a caveman could do it.

So they repeat the Bigfiles entire size for every file in there? arent that kinda weird 
aww nevermind i misread 
im new at this so just one question..
Do i need to unpack each block seperately then and merge them afterwards?

Again.. found it out myself.. Extracted my first wav
## Post #5
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2009-09-10T22:11:15+00:00
- Post Title: cage & hab files.

> Reply from nikitatp
>
> So they repeat the Bigfiles entire size for every file in there? arent that kinda weird 
aww nevermind i misread 
im new at this so just one question..
Do i need to unpack each block seperately then and merge them afterwards?

Again.. found it out myself.. Extracted my first wavYes I wasn't clear, that was total of the file data, not archive. Good work!
## Post #6
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2009-09-10T22:28:29+00:00
- Post Title: cage & hab files.

nik, are you doing the same game?

any chance one of you guys can walk me thru it a bit,
## Post #7
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-09-11T05:02:49+00:00
- Post Title: cage & hab files.

So if I'm interested in extracting the music, I can simply cut out the compressed parts and run offzip or on it?
## Post #8
- Username: nikitatp
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 11, 2009 4:34 am
- Post datetime: 2009-09-11T05:40:53+00:00
- Post Title: cage & hab files.

well basicly you can just cut out a file and use a zlib decompressor on it
the actually zlib packed file starts with ASCII xæ in a hex editor or HEX 78 9C
End of string filename +18 bytes and then the compressed file runs from the xæ mark
all the way to the next filename string.. If you cut that out and save to a new file
you can use a zlib depacker on that file. and bang your good to go.

Anyone knows if there are some freeware fast loading activex binary editor (non-visual)
the one integrated in my language is slow as hell as long files gets over 50mb

~ Tina
## Post #9
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-09-11T05:46:49+00:00
- Post Title: cage & hab files.

What zlib depacker are you using by the way?
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-09-11T10:40:40+00:00
- Post Title: cage & hab files.

if you posted the files someone could write a decompreessor ibn 2 seconds or if you do not care about file names just use 
offzip.exe -a filename output 0x0
that will extract every zlibed file in the archive for you.
## Post #11
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-09-11T15:01:46+00:00
- Post Title: cage & hab files.

I'll post a few files when I get home.
## Post #12
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2009-09-11T15:47:56+00:00
- Post Title: cage & hab files.

The contents of this post was deleted because of possible forum rules violation.
## Post #13
- Username: nikitatp
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 11, 2009 4:34 am
- Post datetime: 2009-09-11T18:51:30+00:00
- Post Title: cage & hab files.

well heres a small cage file..
6mb so easy to work with.

> http://www.flintbutikken.dk/small.cage.rar
## Post #14
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-09-12T04:28:45+00:00
- Post Title: cage & hab files.

Hey nikita, what archive were the wav's in? Do you know where the music was? The 360 version has a music folder but my copy seems to have been damaged in the music folder. Will take a look at the PC version.
## Post #15
- Username: nikitatp
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 11, 2009 4:34 am
- Post datetime: 2009-09-12T05:45:47+00:00
- Post Title: cage & hab files.

the music and sounds are in the level/map files.. Seems they packed the sounds and music to be used in a map in the actual map.. Allthough this means some of the audio is there like 10 times.. Bad way of doing a game, why spend more space than they actually needs  would be nice with an unpacker to see if the game would run out of the cage, with a simple directory structure, and thereby save alot of space.
## Post #16
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-09-12T15:56:02+00:00
- Post Title: Re: cage & hab files.

Alright, by the way are you using the PC or 360 version?

I'm asking because using offzip on the 360 version on the first antietam map extracts a lot of 100 kb files, and they're all headerless. Do I need to combine some of these files to get a wav?

Edit: Never mind, figured it out.
## Post #17
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2009-09-13T00:17:44+00:00
- Post Title: Re: cage & hab files.

im useing the pc version of "darkest of days"
## Post #18
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-09-13T00:26:51+00:00
- Post Title: Re: cage & hab files.

Seems the PC and 360 versions are the same cage-wise. Not sure though.
## Post #19
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2009-09-13T01:35:31+00:00
- Post Title: Re: cage & hab files.

> Reply from nikitatp
>
> the music and sounds are in the level/map files.. Seems they packed the sounds and music to be used in a map in the actual map.. Allthough this means some of the audio is there like 10 times.. Bad way of doing a game, why spend more space than they actually needs  would be nice with an unpacker to see if the game would run out of the cage, with a simple directory structure, and thereby save alot of space.

haveing a look about the files i think thay done the same thing with the wepons.
## Post #20
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2009-09-13T02:20:17+00:00
- Post Title: Re: cage & hab files.

see reading you guys talking about this stuff & i havent got a clue what yous are on about?.

its demoralizing haha 

iv tryed everything from offzip to zlib & even googled "file types" & cage files are  non existent.

is this a new file type & im wasteing my time????

thanx
## Post #21
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-09-13T04:19:39+00:00
- Post Title: Re: cage & hab files.

calm down offzip works fine on these archives.
you need to be patient people are not just sitting around waiting to extract any file.
## Post #22
- Username: nikitatp
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 11, 2009 4:34 am
- Post datetime: 2009-09-13T09:41:08+00:00
- Post Title: Re: cage & hab files.

yeah offzip works great.. However what im interested in is preserving the directory structure, that way ive counted you might be able to save over 2gig of HD on the pc version, why they didnt make a common.cage to host files used multiple times is a weird factor...
## Post #23
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2009-09-13T13:55:06+00:00
- Post Title: Re: cage & hab files.

ok, whats some command lines for offzip.

i spend a while with it but all came back negative.
## Post #24
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-09-13T14:21:43+00:00
- Post Title: Re: cage & hab files.

QUICKBMS script for cage files.
hit all when it asks to overwrite it will then append the chunks onto the files so the files will be complete.

```
append
for i = 0 < FILES
savepos NSTART
findloc NEND string "\ 00"
math NEND += 1
math NEND -= NSTART
goto NSTART
print "%NEND%"
if NEND >= 5
getdstring NAME NEND
get UNK1 long
get UNK2 long
get SIZE long
get ZSIZE long
else
get SIZE long
get ZSIZE long
endif
savepos OFFSET
clog NAME OFFSET ZSIZE SIZE
math OFFSET += ZSIZE
goto OFFSET
next i


```
## Post #25
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2009-09-13T15:39:57+00:00
- Post Title: Re: cage & hab files.

> Reply from chrrox
>
> QUICKBMS script for cage files.
hit all when it asks to overwrite it will then append the chunks onto the files so the files will be complete.
Code: Select allmath FILES += 0xFFFF
append
for i = 0 < FILES
savepos NSTART
findloc NEND string "\ 00"
math NEND += 1
math NEND -= NSTART
goto NSTART
print "%NEND%"
if NEND >= 5
getdstring NAME NEND
get UNK1 long
get UNK2 long
get SIZE long
get ZSIZE long
else
get SIZE long
get ZSIZE long
endif
savepos OFFSET
clog NAME OFFSET ZSIZE SIZE
math OFFSET += ZSIZE
goto OFFSET
next i

thanx i apretiate the effort chrrox 

but i dont have clue what that means!

i take it i was wrong in opening a cmd, changeing path & trying:
offzip "file.cage" extract or what ever lol....

i feel that im miles out of everyones else haha.
i managed section8 & a host pf others maby even fear2 "if i can figur out what will import the mesh files" but for an old looking & bmmy game like this is annoying :p.
## Post #26
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-09-13T16:09:35+00:00
- Post Title: Re: cage & hab files.

Go to the tutorials section and read my quickbms guides then you will know what to do with the script.
## Post #27
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2009-09-13T19:48:03+00:00
- Post Title: Re: cage & hab files.

ok once again thanx c 

i dont know if your gona pat be on the back or kick me up the backside lol.

hears what iv done reading thru the tuts.

i copy the code you gave me & make it "Etc.pac"
1 

i open the cage file & save it as "extract.bms"
2 

this is my folder & what i have.
3 

i get this when i do your command instruction & feel theres a kick up the @ss for doing something wrong haha
4
## Post #28
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-09-13T20:05:25+00:00
- Post Title: Re: cage & hab files.

I only tested this on the 1 cage file I was given i do not know if it will work on a dat file or the hab files.
you only need the -l for listing and not extracting the files. 
the only thing you forgot was the output directory after your imput file it has no idea where to extract the files to.
c:\quickbms.exe test.bms c:\file.dat c:\extracted
## Post #29
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2009-09-13T20:51:30+00:00
- Post Title: Re: cage & hab files.

sorry iv went back a step there?

type what i should write in the command line.

ie: quickbms.exe extract.bms Etc.pac done


with me thinking ill use "done" & it will make me the folder i get this....
## Post #30
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-13T21:17:23+00:00
- Post Title: Re: cage & hab files.

remember that quickbms works from both command-line and (moreover) from gui:

double click on quickbms.exe
select the bms script
select the archive to extract
select the destination folder (you must only enter in the folder and then press Save, no matter the filename)
watch the status of the extraction from the quickbms console for success or possible errors

in your previous command you forgot the destination folder, in case of the listing command (-l) you can insert any location because it will be ignored
## Post #31
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2009-09-14T01:45:38+00:00
- Post Title: Re: cage & hab files.

yehhh. nice one.

thanx bugtest & a big thanx to chrrox, got it now 



hears what i done.

open quickbams.
select etc.pac.
select cage file.
select extraction folder.
all 

this is an example of whats in the files. iv also done the fear2 & got a load of MESH FILE's & havent got one of my 3d's to open them

any ideas
## Post #32
- Username: tedparkes
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Sep 20, 2009 7:47 am
- Post datetime: 2009-09-23T02:41:16+00:00
- Post Title: Re: cage & hab files.

the .mesh file is the native file format for the marmoset toolbag.  google that and dl it, and you can open the .mesh.  the .mat files are the materials for Marmoset.
## Post #33
- Username: Enkidu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 12, 2012 8:03 pm
- Post datetime: 2012-02-13T18:02:45+00:00
- Post Title: Re: cage & hab files.

hi,
I'm trying to localize the game. I've manage to extract all files as suggested here, but now I'm totally lost in how to reimport those changes back.

Any help would be greatly appreciated.
En.
## Post #34
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-13T18:42:25+00:00
- Post Title: Re: cage & hab files.

read section 3 of quickbms.txt:
[http://aluigi.org/papers/quickbms.txt](http://aluigi.org/papers/quickbms.txt)

the script seems valid for the reimporting so it should work
## Post #35
- Username: Enkidu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 12, 2012 8:03 pm
- Post datetime: 2012-02-14T06:50:13+00:00
- Post Title: Re: cage & hab files.

> Reply from aluigi
>
> read section 3 of quickbms.txt:
http://aluigi.org/papers/quickbms.txt

the script seems valid for the reimporting so it should work

Ok, thank you. I've probably downloaded older version of QuickBMS (0.3.something), cause I've read quickbms.txt and this section wasn't there.
## Post #36
- Username: Enkidu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 12, 2012 8:03 pm
- Post datetime: 2012-02-14T20:31:16+00:00
- Post Title: Re: cage & hab files.

> QuickBMS generic files extractor and reimporter 0.5.7
>
> by Luigi Auriemma
>
> e-mail: aluigi@autistici.org
>
> web:    aluigi.org
>
> 
>
> - GUI mode activated, remember that the tool works also from command-line
>
>   where are available various options like folder scanning, filters and so on
>
> 
>
> - select the BMS script or plugin to use
>
> - select the input archives/files to extract, type "" for whole folder and subfo
>
> lders
>
> - select the output folder where extracting the files
>
> - open input file D:\DoD\base\level\lbh\bighorn.cage
>
> - open script D:\DoD\base\level\lbh\Extract2.bms
>
> - set output folder D:\DoD\base\level\lbh\Extracted
>
> 
>
>   offset   filesize   filename
>
> ------------------------------
>
> - SCRIPT's MESSAGE:
>
>   5659139
>
> 
>
>   00565a13 3536442133 base/level/lbh/bighorn.hab
>
> 
>
> Error: impossible to write -758525163 bytes (total -758525163), check your disk
>
> space
>
> 
>
> Press RETURN to quit

Ok, so I've just downloaded new version of quickbms (directly from luigi's quickbms page - till yesterday page response was always "not authorized"). Tried again, and again, and again and the above is what I mostly get. This "impossible to write" or "memory allocation error".

Unfortunatelly the script's message cannot be found on internet or quickbms.txt. I'm at lost here. Please advice. Thank you.

I have Win7 64-bit of 4GB RAM. HDD has 35GB free on C: and 80GB free on partition where I'm trying to extract files. The bighorn.cage file has 126MB.
## Post #37
- Username: Enkidu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 12, 2012 8:03 pm
- Post datetime: 2012-02-17T09:00:46+00:00
- Post Title: Re: cage & hab files.

Maybe I wasn't clear with my previous post. Is my situation solvable by any of these:

Upgrading RAM or HDD space
Using XP mode on win7
Improving the script
Getting other version of quickbms?

Thanks.
## Post #38
- Username: Enkidu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 12, 2012 8:03 pm
- Post datetime: 2012-02-19T11:23:46+00:00
- Post Title: Re: cage & hab files.

Ok, new findings and I hope it's not a monologue I'm having here 

With script provided above, previous version of quickbms(0.3.x) was able to extract files from cage cabinet.

Since that I'm struggling to make this work with quickbms 0.5.7. With the script and file listing option "-l" quickbms appears to see only 1 file in cage cabinet, which is incorrect. I've attached a zip file with screenshots.

I only need to extract, localize content and reimport 1 csv file per cage archive, but I'm not able to do so.

Please advice or help me.

Thank you, En.
[quickbms057.zip](https://xentaxbackup.github.io/file/5089_quickbms057.zip)
## Post #39
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-28T19:54:20+00:00
- Post Title: Re: cage & hab files.

```
# script for QuickBMS http://quickbms.aluigi.org

get FULLSIZE asize
for OFFSET = 0 < FULLSIZE
    get NAME string
    get SIZE long
    get ZSIZE long
    savepos OFFSET
    math LIMIT = OFFSET
    math LIMIT += ZSIZE
    putvarchr MEMORY_FILE SIZE 0
    log MEMORY_FILE 0 0
    append
    for OFFSET = OFFSET < LIMIT
        get CHUNK_SIZE long
        get CHUNK_ZSIZE long
        savepos OFFSET
        clog MEMORY_FILE OFFSET CHUNK_ZSIZE CHUNK_SIZE
        math OFFSET += CHUNK_ZSIZE
        goto OFFSET
    next
    append
    log NAME 0 SIZE MEMORY_FILE
next
```
## Post #40
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2012-03-01T22:32:23+00:00
- Post Title: Re: cage & hab files.

another tool, "cagebreak" with this tool we can extract all content of .cage files.

[http://www.mediafire.com/?w1o65follo2sujh](http://www.mediafire.com/?w1o65follo2sujh)

this tool was made for the developers of this game
## Post #41
- Username: Enkidu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 12, 2012 8:03 pm
- Post datetime: 2012-03-02T07:47:46+00:00
- Post Title: Re: cage & hab files.

> Reply from luxox18
>
> another tool, "cagebreak" with this tool we can extract all content of .cage files.

http://www.mediafire.com/?w1o65follo2sujh

this tool was made for the developers of this game

Yes, thank you. I'm aware of this tool, but unfortunately once you "break" cage archives you cannot put them back together. At least I haven't found any tool for that.

That's why I put all my hope towards the quickbms. Aluigi was so kind and help me several times with this, but so far it looks like quickbms's reimport feature does not work for cage files.

Any other idea would be appreciated.
## Post #42
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-02T08:58:24+00:00
- Post Title: Re: cage & hab files.

have you checked with process monitor ([http://technet.microsoft.com/en-us/sysi ... s/bb896645](http://technet.microsoft.com/en-us/sysinternals/bb896645)) if the files get also loaded separately from the archive?

it's not a so rare possibility, some games have this failsafe feature.
## Post #43
- Username: Enkidu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 12, 2012 8:03 pm
- Post datetime: 2012-03-03T06:30:57+00:00
- Post Title: Re: cage & hab files.

Ok, I've given it a try and according to process monitor game loads entire content of cage files by some chunks.

If this is any help, it's beyond my capabilities. 
[ProcessMonitorLog.jpg](https://xentaxbackup.github.io/file/5137_ProcessMonitorLog.jpg)
## Post #44
- Username: Enkidu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 12, 2012 8:03 pm
- Post datetime: 2012-03-07T07:24:25+00:00
- Post Title: Re: cage & hab files.

Thanks everyone for help - especially to aluigi. It seems I have found another solution how to get game localized completely, although it's not that elegant as it would be with reimporting.

Key is to extract all game files from cage archives (with cagebreak or quickbms - both works) and then rename or remove cage files. Game is capable to use extracted files that can be changed.
