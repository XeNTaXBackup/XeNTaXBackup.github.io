## Post #1
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-16T06:08:14+00:00
- Post Title: Binary Domain .Par Archive

Hello all,

Can anyone have a look please here on this archive ? It is from X360 version.

```
http://dl.dropbox.com/u/38234344/Pars.rar
```


mirror:

```
https://www.rapidshare.com/files/473367003/Pars.rar
```
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-16T11:06:27+00:00
- Post Title: Binary Domain .Par Archive

This is the same people who made yakuza.
They use an unkown lzss compression.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-16T11:14:27+00:00
- Post Title: Binary Domain .Par Archive

*sorry, my error*
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-16T11:20:26+00:00
- Post Title: Binary Domain .Par Archive

i get this error
invalid command "while" or arguments -1 at line 37
## Post #5
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-16T11:29:07+00:00
- Post Title: Binary Domain .Par Archive

so is there any chance to unpack/repack/reimport ?
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-16T12:17:20+00:00
- Post Title: Binary Domain .Par Archive

don't consider the post I deleted, I made confusion with another topic.

I have seen the files and yes they are the same of yakuza 3 [viewtopic.php?f=21&t=5061](http://forum.xentax.com/viewtopic.php?f=21&t=5061) so there is the problem of the SLLZ compression algorithm.

in the meantime I have created a script based completely on the code made by MrAdults that may help who is working on this format:

```
endian big
idstring "PARC"
   int            hdr_unknownA;
   int            hdr_unknownB;
   int            hdr_unknownC;
   int            hdr_numFolders;
   int            hdr_foldersOfs;
   int            hdr_numFiles;
   int            hdr_filesOfs;

math foldNames = 32
math fileNames = hdr_numFolders
math fileNames *= 64
math fileNames += 32
math foldInfos = hdr_foldersOfs
math fileInfos = hdr_filesOfs

for i = 0 < hdr_numFolders
    goto foldInfos
   int            foi_unknownA;
   int            foi_unknownB;
   int            foi_numFiles;
   int            foi_fileOfs;
   int            foi_unknownE;
   int            foi_unknownF;
   int            foi_unknownG;
   int            foi_unknownH;
    savepos foldInfos

    goto foldNames
    char           foiName[64];
    savepos foldNames

    for j = 0 < foi_numFiles
    math TMP = foi_fileOfs
    math TMP += j
    math TMP *= 32
    math TMP += fileInfos
    goto TMP
   int            fi_comprFlags;
   int            fi_fileSize;
   int            fi_fileSizeComp;
   int            fi_fileOfs;
   int            fi_unknownE;
   int            fi_unknownF;
   int            fi_unknownG;
   DWORD          fi_chkSum; //guessing

    math TMP = foi_fileOfs
    math TMP += j
    math TMP *= 64
    math TMP += fileNames
    goto TMP
   char           fiName[64];

        set fn string foiName
        string fn += /
        string fn += fiName
        if fi_comprFlags & 0x80000000
            goto fi_fileOfs
            getdstring SIGN 4
            if SIGN == "SLLZ"
                math fi_fileOfs += 0x10
                math fi_fileSizeComp -= 0x10
                clog fn fi_fileOfs fi_fileSizeComp fi_fileSize
            else
                log fn fi_fileOfs fi_fileSizeComp   # ???
            endif
        else
            log fn fi_fileOfs fi_fileSize
        endif        
    next j
next i
```
the chosen compression algorithm is NOT the correct one but it's enough close so you can continue your tests.
## Post #7
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-16T13:59:43+00:00
- Post Title: Binary Domain .Par Archive

thx aluigi, but is this can be normally use or we have to wait for some modifications of the script?
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-16T14:11:05+00:00
- Post Title: Binary Domain .Par Archive

it doesn't work with the compressed files, so it's of no use or maybe partial use.

I have posted it only for giving a chance to extract the uncompressed files and studying the compressed ones, so nothing "stable" because the compression algorithm remains the only problem
## Post #9
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-16T16:55:23+00:00
- Post Title: Binary Domain .Par Archive

> Reply from aluigi
>
> it doesn't work with the compressed files, so it's of no use or maybe partial use.

I have posted it only for giving a chance to extract the uncompressed files and studying the compressed ones, so nothing "stable" because the compression algorithm remains the only problem

I tested many archives and non of them work  . Aluigi did u test it on some archive posted by me ?
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-16T17:17:36+00:00
- Post Title: Binary Domain .Par Archive

here it works with all the files you provided.

are you sure you are not using an old (very old in this case) version of quickbms?
## Post #11
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-16T17:40:10+00:00
- Post Title: Binary Domain .Par Archive

> Reply from aluigi
>
> here it works with all the files you provided.

are you sure you are not using an old (very old in this case) version of quickbms?

DUMP  Shame on me mate sorry for that update it and now it is ok:) thx mate again
## Post #12
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-16T17:48:56+00:00
- Post Title: Binary Domain .Par Archive

all i care about it is archive file call font.par, which can be unpack ok, but its giving some strange DDS files and it cannot be open  Any idea anyone pls ?

```
http://dl.dropbox.com/u/38234344/font.rar
```
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-16T18:05:28+00:00
- Post Title: Binary Domain .Par Archive

the strange dds files are probably those compressed.
as already said it decompresses them using a wrong algorithm ONLY because who wants to work on the real algorithm can have a starting point.
## Post #14
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-17T08:05:19+00:00
- Post Title: Binary Domain .Par Archive

anyone working on it pls ?
## Post #15
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-17T12:12:36+00:00
- Post Title: Binary Domain .Par Archive

the problem is its an unkown compression th eonly way to get the compression is to reverse the game on a devkit xbox 360.
there are several files that include compressed and uncompressed versions of the files in yakuza 3 but i dont hink even that would help to much with reversing the compression.
## Post #16
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-17T15:13:38+00:00
- Post Title: Re: Binary Domain .Par Archive

> Reply from chrrox
>
> the problem is its an unkown compression th eonly way to get the compression is to reverse the game on a devkit xbox 360.
there are several files that include compressed and uncompressed versions of the files in yakuza 3 but i dont hink even that would help to much with reversing the compression.

This is very bad than  Are you sure that it cannot be reversed different way than on the DevKit machine ? That sounds scary
## Post #17
- Username: MeteoraMan
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jul 08, 2010 4:39 am
- Post datetime: 2012-04-27T11:50:22+00:00
- Post Title: Re: Binary Domain .Par Archive

PC version has released.
Any progress in LZSS compression reversing?
## Post #18
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-04-27T13:00:34+00:00
- Post Title: Re: Binary Domain .Par Archive

I'm working on porting the content over to the Source Engine

So far the pc release contains the same .par files 

I wish I could help if you guys need any files I can provide them
## Post #19
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2012-04-27T20:03:42+00:00
- Post Title: Re: Binary Domain .Par Archive

Up.
## Post #20
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-04-29T07:19:50+00:00
- Post Title: Re: Binary Domain .Par Archive

well until someone cracks the files looks like I will be ripping from memory
## Post #21
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-04-30T19:49:48+00:00
- Post Title: Re: Binary Domain .Par Archive

I will release the new version of quickbms and the script tomorrow.
the link for the script will be: [http://aluigi.org/papers/bms/parc.bms](http://aluigi.org/papers/bms/parc.bms)
## Post #22
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-04-30T20:56:52+00:00
- Post Title: Re: Binary Domain .Par Archive

> Reply from aluigi
>
> I will release the new version of quickbms and the script tomorrow.
the link for the script will be: http://aluigi.org/papers/bms/parc.bms
Awesome man! Looking forward to it
## Post #23
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-30T21:10:35+00:00
- Post Title: Re: Binary Domain .Par Archive

Oooo will this mean games like Yakuza: Dead Souls will be extractable too ? You really need to write a tutorial on how to reverse this stuff luigi... I tore my head apart trying to figure out what kind of LZSS algorithm these games use!
## Post #24
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-05-01T17:08:27+00:00
- Post Title: Re: Binary Domain .Par Archive

new quickbms and script released.
and yes, the script should work with yakuza 3 too
## Post #25
- Username: oveja
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Feb 24, 2011 4:35 am
- Post datetime: 2012-05-01T17:46:30+00:00
- Post Title: Re: Binary Domain .Par Archive

> Reply from aluigi
>
> new quickbms and script released.
and yes, the script should work with yakuza 3 too

new script not working.
some error.
## Post #26
- Username: MeteoraMan
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jul 08, 2010 4:39 am
- Post datetime: 2012-05-01T18:12:21+00:00
- Post Title: Re: Binary Domain .Par Archive

Not working with binary Domain PC files.
Error on third file.

```
------------------------------
  00003010 728        font/font.fpf
  00300000 186368     gothic/ont.fpf
  00380000 33587200   gothic/othic_8182.dds

Error: incomplete input file number 0, can't read 806912 bytes.
       anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted


Press RETURN to quit
```
## Post #27
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-05-01T20:16:46+00:00
- Post Title: Re: Binary Domain .Par Archive

sorry a lot, the problem has been caused by a stupid change I did to the script before the release (one of my stupid pseudo-optimizations).
now solved simply restoring it to the original script:

[http://aluigi.org/papers/bms/parc.bms](http://aluigi.org/papers/bms/parc.bms)

sorry again.
## Post #28
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-05-02T06:56:31+00:00
- Post Title: Re: Binary Domain .Par Archive

> Reply from aluigi
>
> sorry a lot, the problem has been caused by a stupid change I did to the script before the release (one of my stupid pseudo-optimizations).
now solved simply restoring it to the original script:

http://aluigi.org/papers/bms/parc.bms

sorry again.
Can you point me in the right direction because I really have no idea what to do with the script and quickbms

**Edit**

Yeahhh!! it works



Ok so the Model files are .gmd and the textures are .dds

dds Can be opened in photoshop 
.gmd not sure :S

##update##
looks like Noesis doesn't open the .gmd files
## Post #29
- Username: vitoci
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Nov 11, 2011 2:24 am
- Post datetime: 2012-05-08T18:27:01+00:00
- Post Title: Re: Binary Domain .Par Archive

Thanks to master Aluigi  and achieved great tool QuickBms unpack the files. Along with this excellent game.
But I can not find the form of repackaging them as to put in the game directory, the folder extracted by the tool, this does not start and hangs.
Greetings to all Members.
## Post #30
- Username: prudislav
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 13, 2010 6:48 am
- Post datetime: 2013-03-30T21:55:47+00:00
- Post Title: Re: Binary Domain .Par Archive

is there any way to repack it back?
## Post #31
- Username: prudislav
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 13, 2010 6:48 am
- Post datetime: 2013-04-04T09:50:22+00:00
- Post Title: Re: Binary Domain .Par Archive

> Reply from prudislav
>
> is there any way to repack it back?
anyone?
## Post #32
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-04-04T10:40:41+00:00
- Post Title: Re: Binary Domain .Par Archive

> Reply from prudislav
>
> prudislav wrote:is there any way to repack it back?
anyone?
There is a way, send a PM to Haoose ([memberlist.php?mode=viewprofile&u=33729](http://forum.xentax.com/memberlist.php?mode=viewprofile&u=33729)), they can repack your texts back.
## Post #33
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-04-04T11:27:24+00:00
- Post Title: Re: Binary Domain .Par Archive

> Reply from lostprophet
>
> prudislav wrote:prudislav wrote:is there any way to repack it back?
anyone?
There is a way, send a PM to Haoose (memberlist.php?mode=viewprofile&u=33729), they can repack your texts back.
NO!

> Our team does not paste text in the game.
>
> Did other guys.
>
> Look there: http://enpy.net/forum/files/file/79-binary-domain/
>
> Quote:
>
> Alexander Blade – программирование
>
> ENPY – тестирование, корректура, программирование, сборка
>
> 
>
> Russian fonts inserted into the game pirates. I do not know how to contact them.
>
> 
>
> As a packaged fonts pirates - do not know. And the text are not converted to the stb. There's another technique used (injection of text in memory of the process)
## Post #34
- Username: prudislav
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 13, 2010 6:48 am
- Post datetime: 2013-04-09T22:39:23+00:00
- Post Title: Re: Binary Domain .Par Archive

so no way to import/export files from those *.par archives?
## Post #35
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-04-09T22:41:05+00:00
- Post Title: Re: Binary Domain .Par Archive

games do not re-compress files when they are run so the compression code was not in the exe.
this is a one way only process of extracting files from the archives like the game does.
your best bet is to try to get the game to load uncompressed files outside of the .par archives.
## Post #36
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-04-17T03:45:21+00:00
- Post Title: Re: Binary Domain .Par Archive

> Reply from chrrox
>
> games do not re-compress files when they are run so the compression code was not in the exe.
this is a one way only process of extracting files from the archives like the game does.
your best bet is to try to get the game to load uncompressed files outside of the .par archives.

Will you ever reconsider updating the Noesis script for props with proper uvmaps? BD has some really neat assets
## Post #37
- Username: AdamSaeed
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 25, 2017 3:13 am
- Post datetime: 2018-10-11T12:49:06+00:00
- Post Title: Re: Binary Domain .Par Archive

It's now 2018, I know.
but I thought someone will need it so much

I was searching around and I found this
[https://github.com/SlowpokeVG/PARC-Archive-Importer](https://github.com/SlowpokeVG/PARC-Archive-Importer)

I tested it my self and it's working,
I wish if there's a way to modify the font width table too.
