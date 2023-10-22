## Post #1
- Username: JeffT
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 16, 2009 4:15 pm
- Post datetime: 2009-11-25T17:15:48+00:00
- Post Title: James Cameron Avatar .pak

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-28T22:42:57+00:00
- Post Title: James Cameron Avatar .pak

sendspace fucks up. Can you upload it somewhere else?
## Post #3
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-11-29T07:02:14+00:00
- Post Title: James Cameron Avatar .pak

From where's the file ? PC Demo or XBOX360 ? Just got the xbox360 version today   . And i unpacked the dvd on my pc, so i would like to see a unpacker for this too
## Post #4
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-11-29T08:53:03+00:00
- Post Title: James Cameron Avatar .pak

sound_english.pak - [http://multi-up.com/177670](http://multi-up.com/177670)
From PC Demo.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-29T10:55:14+00:00
- Post Title: James Cameron Avatar .pak

I worked on this format some days ago (there is a thread here [viewtopic.php?f=21&t=3899](http://forum.xentax.com/viewtopic.php?f=21&t=3899)) but there are some fields missing or that require additional checks/reversing mainly in the part regarding the chunks of compressed data because the rest should be complete.

for reference (it works for the first files till encounters one of the those chunks wrongly compressed, so final users stay far away from this) I post my quickbms script written till now:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

set MAX_CHUNKSZ long 0x10000

idstring "PAK!"
get DUMMY long
get OFFSET long
get ZSIZE asize
math ZSIZE -= OFFSET
log MEMORY_FILE OFFSET ZSIZE

math TMP = ZSIZE
math TMP += MAX_CHUNKSZ
putvarchr MEMORY_FILE TMP 0

get OFFSET long MEMORY_FILE
goto OFFSET MEMORY_FILE
get CHUNKS long MEMORY_FILE
math CHUNKS -= 1
append
for i = 0 < CHUNKS
    get OFFSET1 long MEMORY_FILE
    get OFFSET2 long MEMORY_FILE
    if OFFSET2 & 0x80000000
        set ZIP long 1
    else
        set ZIP long 0
    endif
    math OFFSET1 &= 0x7fffffff
    math OFFSET2 &= 0x7fffffff

    math ZSIZE = MAX_CHUNKSZ

    goto OFFSET1 MEMORY_FILE2
    #goto OFFSET2 MEMORY_FILE
    if ZIP == 0
        log MEMORY_FILE2 OFFSET2 MAX_CHUNKSZ MEMORY_FILE
    else
        clog MEMORY_FILE2 OFFSET2 ZSIZE MAX_CHUNKSZ MEMORY_FILE
    endif
next i
append
goto 0 MEMORY_FILE2

comtype lzo1x
get DUMMY byte MEMORY_FILE2
get FILES long MEMORY_FILE2
savepos INFO_OFF MEMORY_FILE2
for extract = 0 < 2
    for i = 0 < FILES
        get OFFSET long MEMORY_FILE2
        get SIZE long MEMORY_FILE2  # full filesize
        get DUMMY long MEMORY_FILE2
        math CHUNKS = SIZE
        math CHUNKS /= MAX_CHUNKSZ
        math TMP = SIZE
        math TMP %= MAX_CHUNKSZ
        if TMP != 0
            math CHUNKS += 1
        endif

        if extract == 0
            for j = 0 < CHUNKS
                get ZCHUNKSZ short MEMORY_FILE2
                get CHUNKSZ short MEMORY_FILE2
            next j
        else
            savepos TMP MEMORY_FILE2
            goto NAME_OFF MEMORY_FILE2
            get DUMMY longlong MEMORY_FILE2
            get NAMESZ byte MEMORY_FILE2
            getdstring NAME NAMESZ MEMORY_FILE2
            savepos NAME_OFF MEMORY_FILE2
            goto TMP MEMORY_FILE2

            callfunction unpack
        endif
    next i
    if extract == 0
        savepos NAME_OFF MEMORY_FILE2
    endif
    goto INFO_OFF MEMORY_FILE2
next extract

startfunction unpack
    putvarchr MEMORY_FILE SIZE 0
    log MEMORY_FILE 0 0
    append
    for j = 0 < CHUNKS
        get ZCHUNKSZ short MEMORY_FILE2
        get CHUNKSZ short MEMORY_FILE2
        if CHUNKSZ == 0
            set CHUNKSZ long MAX_CHUNKSZ
        endif
        if ZCHUNKSZ == 0
            log MEMORY_FILE OFFSET CHUNKSZ
            math OFFSET += CHUNKSZ
        else
            if CHUNKSZ == 0xffff
                get TMP asize MEMORY_FILE
                log MEMORY_FILE OFFSET ZCHUNKSZ
                math TMP += CHUNKSZ
                putvarchr MEMORY_FILE TMP 0
            else
                clog MEMORY_FILE OFFSET ZCHUNKSZ CHUNKSZ # problem here
            endif
            math OFFSET += ZCHUNKSZ
        endif
    next j
    append
    log NAME 0 SIZE MEMORY_FILE
endfunction
```
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-11-29T12:50:44+00:00
- Post Title: James Cameron Avatar .pak

I have tested this and it works well on the 360 pak version, not on pc.
## Post #7
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-11-29T14:58:54+00:00
- Post Title: James Cameron Avatar .pak

What program are you using to extract the xbox360 iso ? Also the script don't work for the demo files
## Post #8
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-11-29T15:18:14+00:00
- Post Title: James Cameron Avatar .pak

Try WXripper for 360 iso's.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-29T17:03:39+00:00
- Post Title: James Cameron Avatar .pak

does the script really work at 100% with the x360 archives of this game???
cool :)
## Post #10
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-11-29T17:08:44+00:00
- Post Title: James Cameron Avatar .pak

I got no errors with the 360 extraction.
## Post #11
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-11-29T17:14:59+00:00
- Post Title: James Cameron Avatar .pak

Thanks, about the script, Im getting this error ( x360 files)

> Error: invalid datatype longlong at line 68

Edit: Hmm works now, maybe i was using a old vs of quickbms cause i got the one from the script, and works now 

Thanks
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-29T17:19:36+00:00
- Post Title: James Cameron Avatar .pak

update quickbms, you have an old version
## Post #13
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-11-29T17:25:26+00:00
- Post Title: James Cameron Avatar .pak

Im the only one who get just around 3.03 gb of files (from x360 ofc) ?
## Post #14
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-11-29T17:43:52+00:00
- Post Title: James Cameron Avatar .pak

Ive got 1gib on sounds.pak, but i need to update my quicbms too.
## Post #15
- Username: zedEXt
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 23, 2010 12:59 am
- Post datetime: 2010-01-24T11:37:04+00:00
- Post Title: James Cameron Avatar .pak

> Reply from aluigi
>
> I worked on this format some days ago (there is a thread here viewtopic.php?f=21&t=3899) but there are some fields missing or that require additional checks/reversing mainly in the part regarding the chunks of compressed data because the rest should be complete.

for reference (it works for the first files till encounters one of the those chunks wrongly compressed, so final users stay far away from this) I post my quickbms script written till now:
I do not know English. My language is Russian.
Что нужно подправить(дописать) в скрипте, чтобы распаковать файлы *.pak(PC)?(What it is necessary to correct to (add) in a script to unsqueeze files *.pak (PC)?) 100% unpacked, only: "patch.pak"(avatar_1.01_rus.exe -patch Buka russian ), shadersobj.pak, sound_english.pak. Other(data.pak, sound.pak, data_english.pak): "Error: the compressed LZO input is wrong or incomplete (-6)", "Error: there is an error with the decompression the returned output size is negative (-1)"
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-24T15:39:02+00:00
- Post Title: Re: James Cameron Avatar .pak

> "Error: there is an error with the decompression the returned output size is negative (-1)"
that's normal because. as I wrote, that script was only a test (the avatar packages are "stranges")
## Post #17
- Username: zedEXt
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 23, 2010 12:59 am
- Post datetime: 2010-01-25T20:24:42+00:00
- Post Title: Re: James Cameron Avatar .pak

A good test, half games unpacked!
## Post #18
- Username: Danio
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 27, 2010 6:45 am
- Post datetime: 2010-01-27T10:22:09+00:00
- Post Title: Re: James Cameron Avatar .pak

For some time i have been observing discussions in different forums and all the people have the same problem with unpacking .pak files from the game Avatar. It is hard to find the specifications of those files. However, we know that the game works on Dunia engine technology (the same as in Far Cry 2). WinRar can not help, but in the case of Crysis it worked.

Is it possible that the method showed above work on PC?
## Post #19
- Username: zedEXt
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 23, 2010 12:59 am
- Post datetime: 2010-02-07T11:44:38+00:00
- Post Title: Re: James Cameron Avatar .pak

When unpacking the file "data.pak", the script finds the same "*. pak" files in the package and exits, you need to finish that-be "*. pak" unpacked as regular files (ignore unpacking inside the archive data.pak). - Google translate.
## Post #20
- Username: Hawkear
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 06, 2010 10:00 pm
- Post datetime: 2010-04-06T17:01:43+00:00
- Post Title: Re: James Cameron Avatar .pak

> "Error: there is an error with the decompression the returned output size is negative (-1)"

Replace

```
            log MEMORY_FILE OFFSET CHUNKSZ
            math OFFSET += CHUNKSZ
        else

```

with

```
            if CHUNKSZ == 0xffff
                log MEMORY_FILE OFFSET MAX_CHUNKSZ
                math OFFSET += MAX_CHUNKSZ
            else
                log MEMORY_FILE OFFSET CHUNKSZ
                math OFFSET += CHUNKSZ
            endif
        else

```

Works here with the PC-Version of Avatar (sound.pak and data.pak tested).
Strange format, indeed.
## Post #21
- Username: Bioscope
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Mar 26, 2007 9:43 pm
- Post datetime: 2010-04-06T19:37:49+00:00
- Post Title: Re: James Cameron Avatar .pak

hey, luigi. Do you have a final script for the pc version of avatar then? Please direct me to it, as i am only now learning how to use your awesome tool quickbms...
## Post #22
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-06T22:06:16+00:00
- Post Title: Re: James Cameron Avatar .pak

no, I didn't continue with the research on this game.
so the so called "final script" is ever the original one plus the above patch of Hawkear (I have not tested it but I'm sure it works ok):
[http://aluigi.org/papers/bms/avatar.bms](http://aluigi.org/papers/bms/avatar.bms)

as written in the header of the script it's not supported and indeed I have not indexed on my website too.
## Post #23
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-04-08T21:03:45+00:00
- Post Title: Re: James Cameron Avatar .pak

Someone posted on my blog about my FC2 code's XmlResourceFile working with Avatar; does my FC2 archive viewer also work?
## Post #24
- Username: VenomOC
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Mar 21, 2010 9:01 am
- Post datetime: 2010-04-13T12:42:23+00:00
- Post Title: Re: James Cameron Avatar .pak

Hello, I come just say i new script provided by aluigi funcioando this perfectly in the PC version, extract normally Arqiva.

Now I will translate the game for the Portuguese.

Thank you.
## Post #25
- Username: zeeh
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 26, 2009 9:10 am
- Post datetime: 2010-04-13T14:50:53+00:00
- Post Title: Re: James Cameron Avatar .pak

Do the translated files need to be recompiled back to .PAK files to work?
## Post #26
- Username: VenomOC
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Mar 21, 2010 9:01 am
- Post datetime: 2010-04-13T21:24:48+00:00
- Post Title: Re: James Cameron Avatar .pak

He needs to be transformed into one. PAK again yes, but I'm not getting, I do not think any tool for that. anyone have any idea?

Thank you for a while.
## Post #27
- Username: Kryspin
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 10, 2010 5:10 am
- Post datetime: 2010-04-14T20:49:40+00:00
- Post Title: Re: James Cameron Avatar .pak

> Reply from Rick
>
> Someone posted on my blog about my FC2 code's XmlResourceFile working with Avatar; does my FC2 archive viewer also work?

No. I created unpack/pack tools for Avatar PAK file format and it's similar, but header is different (header is at the end of file and compressed by block).

My tools is for my use (we created Czech translation of Avatar game). Maybe I'll can in future release my tools.
## Post #28
- Username: VenomOC
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Mar 21, 2010 9:01 am
- Post datetime: 2010-04-16T00:57:45+00:00
- Post Title: Re: James Cameron Avatar .pak

Hello friend Kryspin, as you conseguil create a tool to package the files of the Avatar, could make HUGE PLEASE send me it? I promise not to make it available here in the forum.
Is it only for my use, to translate this great game for the Portuguese. The same way your right?

Please?

My email if you want me to help:

[joao_pr17@yahoo.com.br](mailto:joao_pr17@yahoo.com.br)

Thank you for your attention.
## Post #29
- Username: McGregor II
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jun 29, 2010 8:21 am
- Post datetime: 2010-07-05T16:07:02+00:00
- Post Title: Re: James Cameron Avatar .pak

> Reply from Kryspin
>
> 

No. I created unpack/pack tools for Avatar PAK file format and it's similar, but header is different (header is at the end of file and compressed by block).

My tools is for my use (we created Czech translation of Avatar game). Maybe I'll can in future release my tools.

Kryspin, you don't have to translate this game, it contains a czech language but if you change value from english to czech and you play the game you will see nothing but graphics, I don't know why but czech and polish (my lang) have another structure than english or russian (which is similar but has another end of the file) and you have just change the structure and if you do this plz send me how you did this cause I want to play in my native language but I have no idea how can i change structure or pack this file again to the pak file.
## Post #30
- Username: Pepino
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 09, 2010 10:12 pm
- Post datetime: 2010-07-10T13:12:01+00:00
- Post Title: Re: James Cameron Avatar .pak

well.. i'm extract the data.pak, but now i have a bunch of files.. i have to pack again.. how i can do this?

please send me a script =D
## Post #31
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2010-11-03T00:13:37+00:00
- Post Title: Re: James Cameron Avatar .pak

Friends, I wanted to make the game for the translation PT-BR, does anyone can create or has a tool for file DATA.PAK the ps3, I get the course file with the bms just do not have a tool to extract and modify texts and is right back on. PAK.

can anyone help?
## Post #32
- Username: Kryspin
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 10, 2010 5:10 am
- Post datetime: 2010-11-03T11:48:19+00:00
- Post Title: Re: James Cameron Avatar .pak

Hi,

there are my tools for Avatar game:

[http://preklady.krystufkovi.cz/avatar/AvatarTools.7z](http://preklady.krystufkovi.cz/avatar/AvatarTools.7z)

Usage in "Readme.txt". You need to have .NET Framework 3.5 installed.

Tested for PC version.
## Post #33
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2010-11-03T11:57:46+00:00
- Post Title: Re: James Cameron Avatar .pak

Thanks guy I'll test it and you notice ....

thanks a lot ..


Edit:
Thank you friend, it worked perfectly on the PS3.
## Post #34
- Username: ashkanhsj
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Mar 17, 2010 5:42 am
- Post datetime: 2010-11-24T14:20:38+00:00
- Post Title: Re: James Cameron Avatar .pak

Has anyone seen the files of the Wii version of Avatar? I have the game, but I have no idea how to open the sound and graphic files.
## Post #35
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2010-11-25T18:57:43+00:00
- Post Title: Re: James Cameron Avatar .pak

You can use dolphin, an wii emulator to view and extract the graphic and sound container files from isoof the game. then you can upload some sample fileson this forum or try to use some extrcactor on these files by yourself.
PS: most of wii graphic files and sounds are in the same format...so maybe you can find the right extractor you need.....bye
## Post #36
- Username: reznov
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Dec 17, 2010 6:24 pm
- Post datetime: 2011-08-28T08:52:05+00:00
- Post Title: Re: James Cameron Avatar .pak

pc
I dont no to repack sound and other file to pak.
i can only extract pak file and make a new languages file
only to make language file to pak,sorry my english is to bad
help me?
## Post #37
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2011-08-28T23:33:44+00:00
- Post Title: Re: James Cameron Avatar .pak

> Reply from reznov
>
> pc
I dont no to repack sound and other file to pak.
i can only extract pak file and make a new languages file
only to make language file to pak,sorry my english is to bad
help me?

With this set of tools (by Krispin):
[http://preklady.krystufkovi.cz/avatar/AvatarTools.7z](http://preklady.krystufkovi.cz/avatar/AvatarTools.7z)

You can extract the .pak files, edit language and repack it again.

I've used it in patch.pak, cause this file are smaller then others .pak files, 
and any version of the game first read the patch.pak before the others .pak.
So, if you translate the game using patch.pak, just put it in the game folder and the translation will work.
## Post #38
- Username: desperado
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 21, 2014 2:54 am
- Post datetime: 2014-08-21T10:38:35+00:00
- Post Title: Re: James Cameron Avatar .pak

> Reply from Herdell
>
> reznov wrote:pc
I dont no to repack sound and other file to pak.
i can only extract pak file and make a new languages file
only to make language file to pak,sorry my english is to bad
help me?

With this set of tools (by Krispin):
http://preklady.krystufkovi.cz/avatar/AvatarTools.7z

You can extract the .pak files, edit language and repack it again.

I've used it in patch.pak, cause this file are smaller then others .pak files, 
and any version of the game first read the patch.pak before the others .pak.
So, if you translate the game using patch.pak, just put it in the game folder and the translation will work.

Herdell if you still have the tool, can you upload again for me because this website is dead (i guess).
## Post #39
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-21T13:32:26+00:00
- Post Title: Re: James Cameron Avatar .pak

Link works.
## Post #40
- Username: desperado
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 21, 2014 2:54 am
- Post datetime: 2014-08-21T15:02:30+00:00
- Post Title: Re: James Cameron Avatar .pak

> Reply from Ekey
>
> Link works.

Interesting, doesn't work for me. 

[http://i62.tinypic.com/2z6zh1y.png](http://i62.tinypic.com/2z6zh1y.png)
## Post #41
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-21T15:16:48+00:00
- Post Title: Re: James Cameron Avatar .pak

Here [https://www.sendspace.com/file/9dguy0](https://www.sendspace.com/file/9dguy0)
## Post #42
- Username: desperado
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 21, 2014 2:54 am
- Post datetime: 2014-08-21T15:29:19+00:00
- Post Title: Re: James Cameron Avatar .pak

> Reply from Ekey
>
> Here https://www.sendspace.com/file/9dguy0

Thanks
## Post #43
- Username: esreveR
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Sep 28, 2016 11:52 pm
- Post datetime: 2019-04-17T20:12:29+00:00
- Post Title: Re: James Cameron Avatar .pak

-snip- I ended up using a quickbms to extract them instead.
## Post #44
- Username: SWatB
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 10, 2022 11:50 am
- Post datetime: 2022-12-10T04:19:11+00:00
- Post Title: Re: James Cameron Avatar .pak

Can someone please unpack the texts of the game?
## Post #45
- Username: odocha0986
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Mar 21, 2023 12:13 am
- Post datetime: 2023-03-20T16:14:49+00:00
- Post Title: Re: James Cameron Avatar .pak

> Reply from Kryspin ↑Wed Nov 03, 2010 7:48 pm at Wed Nov 03, 2010 7:48 pm
>
> 
Hi,

there are my tools for Avatar game:

http://preklady.krystufkovi.cz/avatar/AvatarTools.7z

Usage in "Readme.txt". You need to have .NET Framework 3.5 installed.

Tested for PC version.

I try to reimport (recompile) but the file doesn't change size or info and nothing happen with pak file
