## Post #1
- Username: buckybean
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 17, 2011 12:01 pm
- Post datetime: 2012-11-04T15:13:12+00:00
- Post Title: Tales of Xillia 2 TLFILE.TLDAT

Hello,

Tales of Xillia 2 came out and I remembered chrrox created a quickbms script for the original TOX TLDAT (which can be found here [viewtopic.php?f=10&t=7330](http://forum.xentax.com/viewtopic.php?f=10&t=7330)) file so I gave it a shot and it didn't work.   It's off at "goto 0x1248D8" correct?

I'm not sure what I can post without it violating the forum's rules and policy   

Here is the hexdump of the file called "FILEHEADER.TOFHDB" which was alongside the TLDAT (not the original rip). 
[http://www.mediafire.com/view/?qcqoetm5vs3lou7](http://www.mediafire.com/view/?qcqoetm5vs3lou7)
## Post #2
- Username: buckybean
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 17, 2011 12:01 pm
- Post datetime: 2012-11-04T16:13:20+00:00
- Post Title: Tales of Xillia 2 TLFILE.TLDAT

I tried 0x1AC5F0 after comparing what chhrox had did with the TOX TLDAT last year and it ended abruptly only taking out about 400MB worth of files (total TLDAT is 2.9GB ish). 

All the same file types from the previous TOX TLDAT can be found (listed here [viewtopic.php?f=16&t=9163](http://forum.xentax.com/viewtopic.php?f=16&t=9163)) but there's also a new NUSNUB file type. I dunno what it is...
## Post #3
- Username: buckybean
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 17, 2011 12:01 pm
- Post datetime: 2012-11-04T17:07:41+00:00
- Post Title: Tales of Xillia 2 TLFILE.TLDAT

Almost... there...? 
[3903.png](https://xentaxbackup.github.io/file/5959_3903.png)
## Post #4
- Username: yellow
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 19, 2012 9:54 pm
- Post datetime: 2012-11-10T18:05:40+00:00
- Post Title: Tales of Xillia 2 TLFILE.TLDAT

I'm having, I'd imagine, the same problem as you (though my script also has TOSANMB added but is otherwise the same). The extraction abruptly ends with the following message:

> Error: incomplete input file number -4, can't read 65480 bytes.
## Post #5
- Username: oathkeeper9918
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jul 10, 2011 4:16 am
- Post datetime: 2012-11-11T22:15:46+00:00
- Post Title: Tales of Xillia 2 TLFILE.TLDAT

Yeah, I get the same error and my script just has NUSNUB added to it.
## Post #6
- Username: tomatopasta
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Aug 17, 2012 2:49 am
- Post datetime: 2012-11-16T13:36:26+00:00
- Post Title: Tales of Xillia 2 TLFILE.TLDAT

That is fast, I want the models so badly :p Tales always make good models.
## Post #7
- Username: oathkeeper9918
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jul 10, 2011 4:16 am
- Post datetime: 2012-11-16T13:43:56+00:00
- Post Title: Tales of Xillia 2 TLFILE.TLDAT

Xillia 2 uses the same types of files as Xillia 1 did, although last I checked nobody bothered to convert the models into a usable format
## Post #8
- Username: tomatopasta
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Aug 17, 2012 2:49 am
- Post datetime: 2012-11-16T13:52:46+00:00
- Post Title: Tales of Xillia 2 TLFILE.TLDAT

This is a piece of cake to convert them into skinned fbx format and export into whatever your want, use sb3u and autodesk maya and some of the supported game anyone can do it.
## Post #9
- Username: tomatopasta
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Aug 17, 2012 2:49 am
- Post datetime: 2012-11-17T09:55:04+00:00
- Post Title: Tales of Xillia 2 TLFILE.TLDAT

> * [PS3] Tales of Xillia 2 [JPN]
>
>     *
>
>           o BLJS10188
>
>           o
>
>                 + PS3_DISC.SFB 0 MB
>
>                 + PS3_GAME
>
>                 +
>
>                       # ICON0.PNG 0 MB
>
>                       # LICDIR
>
>                       #
>
>                             * LIC.DAT 0 MB 
>
>                       # PS3_GAME
>
>                       # PARAM.SFO 0 MB
>
>                       # PIC1.PNG 3 MB
>
>                       # PS3LOGO.DAT 0 MB
>
>                       # SND0.AT3 2 MB
>
>                       # NPWR03501_00
>
>                       #
>
>                             *
>
>                                   o TROPHY.TRP 3 MB 
>
>                             * USRDIR
>
>                             * EBOOT.BIN 17 MB
>
>                             * FILEHEADER.TOFHDB 10 MB
>
>                             * MOVIE
>
>                             *
>
>                                   o AM_BAD_END.DAT 167 MB
>
>                                   o AM_GOOD_END.DAT 244 MB
>
>                                   o AM_MC00_015_010_00.DAT 482 MB
>
>                                   o AM_MC00_040_010_00.DAT 121 MB
>
>                                   o AM_MC06_180_010_00.DAT 151 MB
>
>                                   o AM_MC12_370_020_00.DAT 136 MB
>
>                                   o AM_MC14_410_060_00.DAT 292 MB
>
>                                   o AM_OPENING.DAT 241 MB
>
>                                   o AM_SEMI_GOOD_END.DAT 159 MB
>
>                                   o AM_SPECIAL_END.DAT 231 MB
>
>                                   o MOV_DIG_TOX_000.DAT 353 MB
>
>                                   o MOV_DIG_TOX_001.DAT 248 MB
>
>                                   o MOV_DIG_TOX_002.DAT 330 MB
>
>                                   o MOV_DIG_TOX_003.DAT 339 MB
>
>                                   o MOV_DIG_TOX_004.DAT 386 MB 
>
>                             * SCREENSHOT
>
>                             *
>
>                                   o SS_OVERLAY.PNG 0 MB 
>
>                             * USRDIR
>
>                             * TLFILE.TLDAT 2,878 MB 
>
>                       # PS3_UPDATE
>
>                       # PS3UPDAT.PUP 256 MB

The TLFILE.TLDAT 2,878 MB , the file size are way too large, it will unpacked into even larger than 4Gbyte, it is the problem.
## Post #10
- Username: oathkeeper9918
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jul 10, 2011 4:16 am
- Post datetime: 2012-11-18T23:51:24+00:00
- Post Title: Tales of Xillia 2 TLFILE.TLDAT

Tales of Xillia's TLFILE.TLDAT file was 2.3 gb, and it unpacked to 4.11 gb just fine though.
## Post #11
- Username: tomatopasta
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Aug 17, 2012 2:49 am
- Post datetime: 2012-11-19T12:13:06+00:00
- Post Title: Tales of Xillia 2 TLFILE.TLDAT

Your got a different copy, does it included extra gameplay or extra characters?
## Post #12
- Username: oathkeeper9918
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jul 10, 2011 4:16 am
- Post datetime: 2012-11-19T21:37:33+00:00
- Post Title: Tales of Xillia 2 TLFILE.TLDAT

Uh, no, considering there's only one version of the game? Tales of Xillia didn't get a director's cut version like Graces or Vesperia. There isn't even a demo available for Xillia.



in which model_folder is the folder where the unpacked files are located
## Post #13
- Username: oathkeeper9918
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jul 10, 2011 4:16 am
- Post datetime: 2012-12-26T20:54:41+00:00
- Post Title: Tales of Xillia 2 TLFILE.TLDAT

I'm almost afraid to bump this, but it'd be really helpful if someone could modify the script for this game
## Post #14
- Username: oathkeeper9918
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jul 10, 2011 4:16 am
- Post datetime: 2013-01-23T02:34:52+00:00
- Post Title: Tales of Xillia 2 TLFILE.TLDAT

bump
## Post #15
- Username: phlyingpig
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Oct 21, 2010 1:51 am
- Post datetime: 2013-03-23T07:56:03+00:00
- Post Title: Tales of Xillia 2 TLFILE.TLDAT

I think i have the same problem in extracting the files with the thread starter.
Is there any solution for this now?
