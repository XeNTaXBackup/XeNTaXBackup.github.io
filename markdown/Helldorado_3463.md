## Post #1
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2009-05-04T19:42:04+00:00
- Post Title: Helldorado

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-05T00:14:53+00:00
- Post Title: Helldorado

extracting the files is ok, the only problem is retrieving their names.
I have made only a quick external analysis of the archives but I guess that if the names are really stored in them they are located in the bytes between the offset/size table and the first file in a compressed form.
the following is the quickbms script for extracting the files without names:

```
get DUMMY long  # ever the same
get DUMMY long  # ever the same
filexor 0x08

get DUMMY long
get DUMMY long
get DUMMY long
get FILES long
get DUMMY long
get BASE_OFFSET long
get TOTAL_SIZE long

for i = 0 < FILES
    get SIZE long
    get OFFSET long
    get DUMMY long
    get DUMMY long
    math OFFSET += BASE_OFFSET

    log "" OFFSET SIZE
next i
```
## Post #3
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2009-05-05T17:10:36+00:00
- Post Title: Helldorado

Thx Bugtest
## Post #4
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2009-05-06T21:16:20+00:00
- Post Title: Helldorado

Yes, the only - and biggest - problem is to retrieve the filenames. They seem to be encrypted in a special way.
Also, the whole file seems to be XORed with 0b6h - but according to a flag somewhere. I haven't been able to analyze this further...
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-06T23:08:10+00:00
- Post Title: Helldorado

an idea for catching the right XOR byte can be the reading of the byte at offset 0x18 which is 0xff in clear mode so it's enough to xor it with 0xff to get the right xor value.
the only problem is that now the Filexor command uses a fixed number/string as argument while in the past it used a variable so now I need to re-introduce that old argument type for allowing the usage of dynamic xor values

*edit* I have figured the filenames encryption
## Post #6
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2009-05-08T18:57:21+00:00
- Post Title: Helldorado

Great work as always Bugtest.
Can it be handled with a BMS script?
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-08T19:29:34+00:00
- Post Title: Helldorado

sure and indeed I have already written the script yesterday but the dynamic xor value has been re-introduced in the new version that I will release tomorrow.
so you need only to wait some hours :)
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-09T15:33:20+00:00
- Post Title: Helldorado

as promised:
[http://aluigi.org/papers/bms/helldorado.bms](http://aluigi.org/papers/bms/helldorado.bms)

remember to update QuickBMS!
## Post #9
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2009-05-16T21:06:29+00:00
- Post Title: Helldorado

@bugtest:
I was using your BMS-script and it is able to recover the file structure properly. Evaluating it I found out that lines 7...9 are not necessary, because the XOR-value is 0xB6 in any case (it is EXE-hard-coded).
But that's not the problem.
The actual problem is that not the whole PAK-file is XORed. Certain files are stored in their original form (like BIK-videos, WAV-sounds and maybe other files which format I don't know.)
I tried to analyze the PAK-structure but I am overextended to find a solution.
There must be a XOR-flag somewhere...
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-16T22:45:27+00:00
- Post Title: Helldorado

from what I have understood (I don't have all the files or the full game) and verified with the demo only some types of files are not xored, like BIKs.
so seems extension-based because the other fields (like the 2 DUMMYs in the table) have a content which is not constant also for the bik files.

so, resuming, here after having checked the content of data.pak of the demo I have seen only the bik files which don't use the xor obfuscation while all the other files are correct.
have you verified if there all the wav files don't use xor or only some of them?
## Post #11
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2009-05-19T20:16:31+00:00
- Post Title: Helldorado

After investigating extracted files I can confirm that only BIK-files seem to be stored without XORing (maybe for performance reasons).
Comparing with the extension ".BIK" to make a XOR-decision might be sufficient, I think.
## Post #12
- Username: drevil
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 20, 2009 4:51 am
- Post datetime: 2009-05-20T04:58:51+00:00
- Post Title: Helldorado

I can not use helldorado.bms unpack a locale language file(ZH.PAK ia a chinese)
I put in 
[http://cid-12e5359bddd15270.skydrive.li ... _v1.01.rar](http://cid-12e5359bddd15270.skydrive.live.com/self.aspx/SBPAK-ZH/Helldorado-GB%7C_v1.01.rar)
please help me unpacker it
thanks!
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-20T10:51:03+00:00
- Post Title: Helldorado

well finally we know when it's used the additional xoring I saw in the code :)
redownload my [script](http://aluigi.org/papers/bms/helldorado.bms) and go down until you see the message "# uncomment the following 5 lines if you get wrong filenames!" and remove the # char in the lines which follow it:

```
        math BYTE ^= 0x6e
    else
        math BYTE ^= 0x65
    endif
```

now you can extract the files from zh.pak without problems.
indeed 0x6e and 0x65 are the "en" string so I guess that in other country based paks will be needed to change it.
for example in the german demo that value was set to "de" (0x65 0x64) but as far as I know it wasn't used while in an hypothetic italian version it will be 0x74 0x69

at the moment I have not found a way to implement this check automatically at runtime in the script, so the manual editing of the script is necessary
## Post #14
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-05-21T07:49:05+00:00
- Post Title: Helldorado

Nice going bugtest!
## Post #15
- Username: Alek Sander
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 04, 2010 8:37 pm
- Post datetime: 2011-03-20T12:09:28+00:00
- Post Title: Helldorado

Hey guys! I used the script posted here. In misc.pak file there is a small program packed inside called "sbpacker.exe", which can create, list and unpack pak-files for the game. It extracts all the data including folders.  It's the official tool, I guess...
[sbpacker.rar](https://xentaxbackup.github.io/file/4086_sbpacker.rar)
## Post #16
- Username: zedEXt
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 23, 2010 12:59 am
- Post datetime: 2011-07-03T14:38:11+00:00
- Post Title: Re: Helldorado

> Reply from Alek Sander
>
> Hey guys! I used the script posted here. In misc.pak file there is a small program packed inside called "sbpacker.exe", which can create, list and unpack pak-files for the game. It extracts all the data including folders.  It's the official tool, I guess...
Unpack: SBPacker locale -x packfilename [destdir]        List is sorted by filename hash values
List  : SBPacker locale -L packfilename         List is sorted by file data order
List  : SBPacker locale -l packfilename         Default pakfilename is 'listfilename.pak'
Create: SBPacker locale -a listfilename.txt [pakfilename]        Default pakfilename is 'cmdfilename.pak'
Create: SBPacker locale -c cmdfilename.txt [pakfilename]
## Post #17
- Username: aeon
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 14, 2006 8:20 pm
- Post datetime: 2012-08-31T16:56:44+00:00
- Post Title: Re: Helldorado

does anybody know what's the 'locale' parameter?
## Post #18
- Username: Alek Sander
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 04, 2010 8:37 pm
- Post datetime: 2012-08-31T17:29:33+00:00
- Post Title: Re: Helldorado

> Reply from aeon
>
> what's the 'locale' parameter?
I don't remember clearly and don't have the game installed at the moment, but "locale" is the name of the localisation if you have more than one language in the game, i.e. English and German.
Is it asking for the parameter? If so try "en" or "eng", or "english", or look and the files and directory where pak-files are, they may have some kind of localisation oriented suffix. Sorry, can't help more, need to install the game.
## Post #19
- Username: aeon
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 14, 2006 8:20 pm
- Post datetime: 2012-08-31T18:52:45+00:00
- Post Title: Re: Helldorado

You are right "en" seems to be correct one, ufortunately the unpacker crashes , I've got a different game using same archives but probably modified ones.
## Post #20
- Username: Alek Sander
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 04, 2010 8:37 pm
- Post datetime: 2012-08-31T19:50:39+00:00
- Post Title: Re: Helldorado

What's the game? Maybe they cranked up the version of archives.
## Post #21
- Username: aeon
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 14, 2006 8:20 pm
- Post datetime: 2012-09-01T11:01:02+00:00
- Post Title: Re: Helldorado

> Reply from Alek Sander
>
> What's the game? Maybe they cranked up the version of archives.

[http://project-giana.com/download/](http://project-giana.com/download/)


These archives are xored by 0xb6
## Post #22
- Username: Abyssinian
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 19, 2013 9:10 am
- Post datetime: 2015-10-13T13:59:28+00:00
- Post Title: Re: Helldorado

Hey guys, I still have no idea how to extract the buildings. I tried using the script but it didn't work for me.
## Post #23
- Username: Kspeh
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 29, 2020 2:16 pm
- Post datetime: 2020-08-29T11:05:16+00:00
- Post Title: Re: Helldorado

Can you please tell how to unpack and repack files games. The misc.pak has a file bik, who want to clean or replace. Each time you start the game slowly show people kissing. I think it's disgusting. It's great when people love each other, but disgusting, when they relish the sight of all. And I hate to run the game because of that. I tried to unpack a proprietary utility that is all in the same misc.pak called sbpacker. She unpacks sort correctly - in folders, but for some reason after unpacking it does not play movies. I looked at some other files - like normal - and the sound played and images are displayed, but when you run the video pops up an error. Then it tries to pack, use third-party shell Arc_PakWorker and Demo_PakWorker (because I did not understand, what keys you need to pack), but even if nothing has changed, the game has not started. I also used to decompress quickbms after it also did not play movies. But even she unpacks all the files in one folder, even though I downloaded the script helldorado.bms and used it. Only UniExtract utility unpacks so that videos are played, but again, it all copy into one folder.
Can you please tell how to cut or replace the file of misc.pak: misc\interface\menu\spellbound.bik and still somehow make clear this?
Correction: when unpacking utility quickbms video is playing, I was wrong. But anyway quickbms dumps all the files in one folder.
