## Post #1
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-05-23T21:10:19+00:00
- Post Title: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

I've had a VERY brief look at it (doing exams atm) and besides .pak archives I did not notice anything too enlightening. has someone had better luck?
## Post #2
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2012-03-15T04:29:38+00:00
- Post Title: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

Wish this thread didn't die, it's almost a year and there's no way to extract assets from the game's .pak files (real noob talking here I always assumed .pak was easy to figure out)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-15T04:50:45+00:00
- Post Title: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

Maybe you can post samples?
## Post #4
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2012-03-15T06:24:17+00:00
- Post Title: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

I think I'll be able to get the game before the week ends. 
Yeah this is gonna be a noob questing but is the a particular file I should look for that would help anyone?
## Post #5
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2012-03-15T06:42:12+00:00
- Post Title: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

I'd say in something similar to the "Data" folder there are probably archives.
## Post #6
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2012-03-15T11:16:12+00:00
- Post Title: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

Was lucky enough to get the game earlier than I expected. 

Installed the game had several directories (named as audio, flash, video, levels etc.) so I went with the "Levels". Files were named from the locations (Helm'sDeep.PAK, BlackGates.PAK Shire.BIN etc.) and these are the smallest ones I could find I hope they're the right ones.

shell.PAK and shell.BIN (10mb) [http://www.mediafire.com/?ql91okl36cqwfui](http://www.mediafire.com/?ql91okl36cqwfui)

Training.PAK (7mb) [http://www.mediafire.com/?5s7eac9g6qml70t](http://www.mediafire.com/?5s7eac9g6qml70t) (Training.BIN was 80mb)
## Post #7
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2012-03-15T11:50:29+00:00
- Post Title: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

those PAK and BIN files I guess are the key. archives where everything is located.
## Post #8
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2012-03-16T15:20:40+00:00
- Post Title: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

Tried using chrrox quickbms tutorial from here [viewtopic.php?f=29&t=3525](http://forum.xentax.com/viewtopic.php?f=29&t=3525) guessing the file had 6 extractable files? and was able to extract an 80mb .dat file off Training.BIN but encountered some sort of error before the next file extracted. Pretty much way beyond my current knowledge.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-16T15:31:58+00:00
- Post Title: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

Oh, you managed to unpack one of the bin's.
Did you hardcode anything?

Maybe you can post what you found.
The pak and bin files don't look like they are related to each other since they all have a bunch of strings at the bottom.
## Post #10
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2012-03-16T15:38:36+00:00
- Post Title: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

Just guessing actually. Used the script from the tutorial changing long and short for several tries mostly misses except for one hit on that 80mb file. Do it put it online as is?
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-16T17:18:52+00:00
- Post Title: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

Just copy paste the script you are working on even if it doesn't work.
## Post #12
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2012-03-16T18:23:03+00:00
- Post Title: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

can you get music files out as well?
## Post #13
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2012-03-16T22:59:42+00:00
- Post Title: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

this was the bms I used using quickbms_4gb_files.exe on the Training.BIN file (been trying to upload that file to mediafire but for some reason but I can't)

get FILES long
get HEADERSZ long
for i = 0 < FILES
get NSIZE long
getdstring NAME NSIZE
get OFFSET short
get SIZE long

log NAME OFFSET SIZE
next i
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-17T00:00:46+00:00
- Post Title: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

That's odd, shell.bin looks completely different.
Maybe there's a archive type somewhere at the top that indicates how to parse it.

```

get unk long
get unk long
get NAME_OFS long
get unk long
get FILES long
get FILES2 long
get FILE_OFS long

goto NAME_OFS
for i = 0 < FILES do
	get len long
	getdstring NAME len
	print %NAME%
next i

```


There are two offsets given in the header; one goes to a list of strings, while the other goes to file entry info.

The string table is pretty simple...read a length, get the string.
The other table appears to be 20 bytes per entry (total size / numFiles)

Given only one file to work with, I don't know which one of those values is the actual file count.

Data is also compressed it seems.
## Post #15
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2012-03-17T00:13:07+00:00
- Post Title: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

I hope this helps... I managed to upload Training.BIN but it's a big 80MB file
[http://www.mediafire.com/?e55w5bqi566m4j2](http://www.mediafire.com/?e55w5bqi566m4j2)
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-17T00:46:44+00:00
- Post Title: Re: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

Maybe you can build on this.
The data starts at 0x800, and the first entry points to 0x800. The next one points to 0x9000
So you would think filesize == 0x9000 - 0x800 would be stored somewhere in one of those 4 variables in the file entry, but I don't see it.

```
#Array 0 = Names
#Array 1 = Offsets
#Array 2 = Sizes
#Array 3 = Compressed sizes

get unk1 long
get unk2 long
get NAME_OFS long
get unk3 long
get FILES long
get FILES2 long
get FILE_OFS long
get null long
get unk4 long
get unk5 long
get unk6 long #FILES == unk4 + unk6

#get the entries
goto FILE_OFS
for i = 0 < FILES do
	get unk1 long
	get OFFSET long
	get unk2 long
	get unk3 long
	get unk4 long
	
	#put offset in array 1 at index i
	putarray 1 i OFFSET
next i

#get the names
goto NAME_OFS
for i = 0 < FILES do
	get len long
	getdstring NAME len
	putarray 0 i NAME
next i

#just testing. Grab values from index 0 of arrays
getarray NAME 0 0
getarray OFFSET 1 0
print "%NAME% %OFFSET%"

```
## Post #17
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2012-03-17T03:59:38+00:00
- Post Title: Re: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

> Reply from finale00
>
> Maybe you can build on this.
The data starts at 0x800, and the first entry points to 0x800. The next one points to 0x9000
So you would think filesize == 0x9000 - 0x800 would be stored somewhere in one of those 4 variables in the file entry, but I don't see it.
Code: Select all#Lord of the Rings - Conquest BIN unpacker
#Array 0 = Names
#Array 1 = Offsets
#Array 2 = Sizes
#Array 3 = Compressed sizes

get unk1 long
get unk2 long
get NAME_OFS long
get unk3 long
get FILES long
get FILES2 long
get FILE_OFS long
get null long
get unk4 long
get unk5 long
get unk6 long #FILES == unk4 + unk6

#get the entries
goto FILE_OFS
for i = 0 < FILES do
	get unk1 long
	get OFFSET long
	get unk2 long
	get unk3 long
	get unk4 long
	
	#put offset in array 1 at index i
	putarray 1 i OFFSET
next i

#get the names
goto NAME_OFS
for i = 0 < FILES do
	get len long
	getdstring NAME len
	putarray 0 i NAME
next i

#just testing. Grab values from index 0 of arrays
getarray NAME 0 0
getarray OFFSET 1 0
print "%NAME% %OFFSET%"

Tried it on Training.BIN using quickbms_4gb_files.exe and got this message

IGD_GB_Wood_01_D* 2048

Just guessing but it ooks like a texture filename (diffuse) with a dimension of 2048px
## Post #18
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-17T04:13:45+00:00
- Post Title: Re: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

No that number is just the offset of where the data starts (at least, I think it is).
The names don't have extensions so I don't know how that works.

The test printing there is just to show how to retrieve from arrays.
## Post #19
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2012-03-17T12:57:44+00:00
- Post Title: Re: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

I'm not sure if this would be any help at all but would the game's exe have the answer?
## Post #20
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2012-03-19T00:26:41+00:00
- Post Title: Re: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

scratch that idea... this is beyond my current knowledge level. maybe next year lol
## Post #21
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2012-03-19T06:55:58+00:00
- Post Title: Re: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

thanks anyway
## Post #22
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2012-03-20T08:06:55+00:00
- Post Title: Re: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

> Reply from Devilot
>
> thanks anyway

Hey man cheer up. There are 5 downloads of the Training.BIN file that I uploaded... if it's any consolation (and if we're lucky) that's 5 potential engineers trying to come up with an extractor.
## Post #23
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2012-08-12T14:28:36+00:00
- Post Title: Re: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

I guess they did not
## Post #24
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2012-09-04T15:04:21+00:00
- Post Title: Re: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

would this program help?
[http://soldieroffortune2.filefront.com/ ... ractor;149](http://soldieroffortune2.filefront.com/file/Winpak_pak_extractor;149)
## Post #25
- Username: MacDougal
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Mar 04, 2014 7:20 am
- Post datetime: 2014-03-11T15:30:38+00:00
- Post Title: Re: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

Has anyone had any success with this?

It would be awesome if someone was able to unpack the bin/pak files.
## Post #26
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-03-11T18:35:27+00:00
- Post Title: Re: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

I think that NinjaRipper is the best choice for this game. it should be considered as the "spiritual successor" to 3d ripper dx and, hopefully, it has solved its issues.
## Post #27
- Username: cadu1990
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 16, 2011 11:06 am
- Post datetime: 2014-05-09T05:26:04+00:00
- Post Title: Re: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

So, anyone managed to extract something from the game? This is probably the only game I've found that has a good Sauron model, and I'm very interested in that particular model
## Post #28
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-05-09T06:32:30+00:00
- Post Title: Re: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

> Reply from cadu1990
>
> So, anyone managed to extract something from the game? This is probably the only game I've found that has a good Sauron model, and I'm very interested in that particular model
my same reason exactly..
## Post #29
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2014-09-26T16:45:48+00:00
- Post Title: Re: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

Can't believe I posted here two years ago... and still no closer to getting anything. Oh the memories LOL
## Post #30
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-09-26T16:51:27+00:00
- Post Title: Re: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

that's because ninja ripper is still completely wonky, for me.
## Post #31
- Username: ellegirl01
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 28, 2014 1:08 pm
- Post datetime: 2014-09-28T05:42:52+00:00
- Post Title: Re: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

This thread had me all excited; I thought there had finally been a breakthrough.   I know FinalBig can do some LOTR games but not all.
## Post #32
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-09-28T07:25:45+00:00
- Post Title: Re: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

no BIG files tho in Conquest, right?
## Post #33
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2014-10-05T18:16:21+00:00
- Post Title: Re: [PC/Ps3]Lord of the Rings - Conquest Models/Textures

Aluigi took time to create and graciously provide a quickbms script to extract Conquest files... I hope somebody has the game still installed to check this out.

```
#   this script is incomplete and the extracted data is probably useless
#   because some files are not extracted completely
#   you can use also offzip but it's not much useful too
# script for QuickBMS http://quickbms.aluigi.org

get EXT extension
if EXT == "bin"

    goto 8
    get STRINGS_OFF long    # not related to the files
    goto 0x14
    get FILES long
    get OFFSET long
    goto OFFSET
    for i = 0 < FILES
        get DUMMY long
        get OFFSET long
        get SIZE long
        get ZSIZE long
        get DUMMY long
        if SIZE != 0
            clog "" OFFSET ZSIZE SIZE
        endif
    next i

elif EXT == "pak"

    get DUMMY long
    get SOME_TABLE_OFFSET long
    get DUMMY long  # 0x13
    get DUMMY long  # 0x1
    get STRINGS_OFF long
    get DUMMY long
    get DUMMY long

    for i = 0 < 2   # only two?
        get OFFSET long
        get SIZE long
        get ZSIZE long
        get INFO_OFF long
        clog MEMORY_FILE OFFSET ZSIZE SIZE

        if i == 0   # lame backup for later
            math INFO_OFF0 = INFO_OFF
            log MEMORY_FILE2 0 SIZE MEMORY_FILE
        endif

        goto INFO_OFF MEMORY_FILE
        get ZERO long MEMORY_FILE
        get FILES long MEMORY_FILE
        getdstring ZERO 8 MEMORY_FILE
        for j = 0 < FILES
            get DUMMY long MEMORY_FILE
            get OFFSET long MEMORY_FILE
            get SIZE long MEMORY_FILE
            math OFFSET += INFO_OFF
            log "" OFFSET SIZE MEMORY_FILE
        next j
    next i

    # ???
    goto 0x110
        get OFFSET long
    for i = 1 < 0x18    # till 0x170
        get NEXT_OFFSET long
        if NEXT_OFFSET < OFFSET
            math NEXT_OFFSET = INFO_OFF0
        endif
        xmath SIZE "NEXT_OFFSET - OFFSET"
        if SIZE != 0
            log "" OFFSET SIZE MEMORY_FILE2
        endif
        math OFFSET = NEXT_OFFSET
    next i

    comtype unzip_dynamic
    math SIZE = INFO_OFF0
    math OFFSET = 0x1000
    math SIZE -= OFFSET
    clog "" OFFSET SIZE SIZE

    # other compressed data are not handled!

else
    print "Error: archive %EXT% not supported"
    cleanexit
endif
```
