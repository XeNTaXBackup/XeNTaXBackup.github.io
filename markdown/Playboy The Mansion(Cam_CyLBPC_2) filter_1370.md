## Post #1
- Username: DrPepper
- Rank: VIP member
- Number of posts: 9
- Joined date: Sun Jul 03, 2005 9:31 am
- Post datetime: 2005-07-03T15:47:41+00:00
- Post Title: Playboy: The Mansion(Cam_CyLBPC_2) filter

I have been playing a little more with the Game Extractor and what a cool tool.
I took a look at about ever file in the game and I have found a few interesting things.

One interesting cam is called models.cam  it is about 30 meg in size.
when I open it using GE it shows one bmp about 9k in size.
If I hex edit the cam it looks like there are many more bmps.

There are a group of cam's that are empty.  some are rather large.

I am thinking that maybe the Playboy: The Mansion(Cam_CyLBPC_2) needs a tweak.

I will tarball three cams to take a look at,  1) the models.cam 2) textdatu.cam (a empty one)
and 3) FBSP.Cam (the Swim Suite One 
Tarball to big for upload so I put it out on my site
[http://www.udelsrus.com/cams.rar](http://www.udelsrus.com/cams.rar)

If there is anything I can do to help.....
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-07-04T02:57:32+00:00
- Post Title: Playboy: The Mansion(Cam_CyLBPC_2) filter

OK well it sounds to me like that archive wasn't opened correctly, therefore the scanner tried to find things like BMP images in the archive. The cause of this could be that the archive is a different format to the other archives used in the game, or more probably the plugin is not quite correct. I will take a look at the files you attached, and will try to come up with a plugin fix for you.

As for why it only showed 1 small BMP image - it may be that all the larger BMP images are compressed or something, because BMP images compress fairly well. It could also be that the BMP images do not use the standard compression types or color depths?

Anyway, I will see what I can do.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-07-04T13:56:38+00:00
- Post Title: Playboy: The Mansion(Cam_CyLBPC_2) filter

I took a look - yeah the files are a different format so I will make you a new plugin. The plugin should be available by the end of the week - I have a heap of them to write up.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: DrPepper
- Rank: VIP member
- Number of posts: 9
- Joined date: Sun Jul 03, 2005 9:31 am
- Post datetime: 2005-07-04T14:17:06+00:00
- Post Title: Playboy: The Mansion(Cam_CyLBPC_2) filter

To Cool...   You the man.  All of the Xbox mod'ers will thank you  Once I get my new Pic's in
## Post #5
- Username: DrPepper
- Rank: VIP member
- Number of posts: 9
- Joined date: Sun Jul 03, 2005 9:31 am
- Post datetime: 2005-07-11T23:19:01+00:00
- Post Title: Playboy: The Mansion(Cam_CyLBPC_2) filter

Funney Thing.  I tried to replace  a PICT file in the Cam Archive but I get a error that said " The Archive Formate Doesno't allow this action"
Am I doing something wrong?
## Post #6
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-07-12T14:47:59+00:00
- Post Title: Playboy: The Mansion(Cam_CyLBPC_2) filter

Yeah thats because I havn't written a repacking script for the format - I will try to make one for you as soon as possible.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #7
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-07-14T14:05:31+00:00
- Post Title: Playboy: The Mansion(Cam_CyLBPC_2) filter

No Problem.  I wish there was a Way I could help.  I found some Doc that you and Mr Mouse put together.  I have a long flight to Dallas today.  I thought I would read it.  WIll not be back home to pay with the files till friday.
Thanks again for your help
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-14T15:07:52+00:00
- Post Title: Playboy: The Mansion(Cam_CyLBPC_2) filter

Happy reading! Hope it helps you understand a little more ! Thanks! 

Meanwhile, you can still use MexCom to import in certain .CAM files, I guess.
## Post #9
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-07-17T13:52:12+00:00
- Post Title: Playboy: The Mansion(Cam_CyLBPC_2) filter

yeah hey hope you understand it alright - might still be alittle too technical.

Anyway definately check out Mr Mouses MexCom if you want something quick - I will make time this week to write a repacker for you (in amongst returning to uni  )

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #10
- Username: DrPepper
- Rank: VIP member
- Number of posts: 9
- Joined date: Sun Jul 03, 2005 9:31 am
- Post datetime: 2005-07-22T00:38:32+00:00
- Post Title: Playboy: The Mansion(Cam_CyLBPC_2) filter

Hey Guys. I am back   I downloaded MutltiEx Commander today.  I also got all of the update.  But I don;t see the Playboy Cam format.
What did I not do?
## Post #11
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-22T10:42:44+00:00
- Post Title: Playboy: The Mansion(Cam_CyLBPC_2) filter

Hmm, try the Web update again. 

I have included some new formats, perhaps the CAM format slipped. It should be in there now.
## Post #12
- Username: DrPepper
- Rank: VIP member
- Number of posts: 9
- Joined date: Sun Jul 03, 2005 9:31 am
- Post datetime: 2005-07-23T17:25:55+00:00
- Post Title: Playboy: The Mansion(Cam_CyLBPC_2) filter

Thanks For everthing.  I updated and Works great.  I was able to update my cams and  wow.   Still reading.  So far what I have read I understand.  I have 25 years of programs so it should   Mostly the file formats remind me of my old ISAM days using VSAM.  Anyway, Once I bone up on some stuff I would like to help add more file formats and I would love to learn more about the picture formats.
## Post #13
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-23T18:18:42+00:00
- Post Title: Playboy: The Mansion(Cam_CyLBPC_2) filter

And you thanks for your support! Hope to see you again here !
## Post #14
- Username: SirCarcass
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 20, 2005 8:42 am
- Post datetime: 2005-09-20T00:55:17+00:00
- Post Title: Playboy: The Mansion(Cam_CyLBPC_2) filter

I realize this topic is old, but maybe you can help.  I've been messing around with the PC version of Playboy: The Mansion and am wondering if the cam archives differ from the Xbox version.  Using MEXCOM, I keep getting "MEX Empty list file" on every one I try to open.  Game Extractor lets me see the files and extract them, but I can't do anything with them.  Most of the cam files only have one pict file, according to GE, which seems strange and kind of defeats the purpose of archiving, IMO.  A few of the cam files have a lot of files in them, but when I extract some pict files and try the PICTtoBMP convertor, I get an error on all of them, though it'll work for the one the guy uploaded in the thread about the convertor.  It leads me to believe that either the archive is different on the PC, or the pict files are.  I can't find the specific one he uploaded, so I can't say if the PC version of it works.

Anyway, I have MEXCOM version 4.2.0, running on Windows XP.  Let me know which files you need and I'll see what I can do.
## Post #15
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-09-20T05:48:07+00:00
- Post Title: Playboy: The Mansion(Cam_CyLBPC_2) filter

Hi mate,

Yes, I think there were some very slight differences between the PC and the XBox versions - can't really remember what they were though (i think it was just something stupid like padding sizes or something? ). Game Extractor should be able to open them if you need something right now, otherwise you'll have to wait for a new MexCom script to be written.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #16
- Username: SirCarcass
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 20, 2005 8:42 am
- Post datetime: 2005-09-20T06:55:24+00:00
- Post Title: 

Thanks for the reply.  I can extract them with Game Extractor, but I don't know if it's extracting them correctly or if they're different from the extracted Xbox versions (the more likely explanation).  Like I said, I tried the PICTtoBMP convertor and it just gave errors.  Would it be possible to get an updated version of the PICTtoBMP convertor for the PC version, if that's the case?  I can supply some extracted PICT files.  I would try to do it myself, but I know very little about actual file contents, specifically image files.

Edit:  I attached an extracted PICT file.
[JB11.rar](https://xentaxbackup.github.io/file/443_JB11.rar)
## Post #17
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-09-20T22:48:11+00:00
- Post Title: 

Hi again,

I will take a look at the PICT file you attached - I know the archives were different between XBox and PC but I didn't think the images would be. Never mind - I will look at this soon and see whats going on.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #18
- Username: SirCarcass
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 20, 2005 8:42 am
- Post datetime: 2005-09-21T00:58:04+00:00
- Post Title: 

I appreciate your help.
## Post #19
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-09-23T05:59:31+00:00
- Post Title: 

OK well the file you sent was a generic Bitmap image with 4 extra bytes at the beginning. This would fit in with the specifications for the other PICTs, indicating the field is a format identifier.

In the short term, you can use any image ripping program to find all the BMP images in the archive, or just use the ripper on the PICT file individually. If you have the full version of Game Extractor, you should be able to use the "Scan Archive" command, but there are other programs that will do the same thing such as Dragon Unpacker.

In the longer term, I will look into writing a custom exporter and/or viewer for these images in Game Extractor.

Have fun.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #20
- Username: SirCarcass
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 20, 2005 8:42 am
- Post datetime: 2005-09-23T06:46:57+00:00
- Post Title: 

Awesome.  Thanks for your help.  I downloaded a BMP Extractor and was able to get a viewable bitmap from the PICT file.  Any idea how I would go about putting or converting the edited BMP back into the PICT file?  I assume Game Extractor will put the PICT file back in the CAM file, but I'm not sure about the BMP to PICT.  Is there a simple hex edit I can do to it or something?

Edit:  I think if I delete the first four bytes of the PICT file, it becomes identical to the BMP file I extracted, so theoretically I should be able to add those four bytes back in and make it the PICT again.  I'll try this and see what results I get.

Edit 2:  Okay, I did some test skins by extracting, removing the 4 bytes and renaming to BMP, editing, adding the bytes back in and renaming to PICT, and replacing and it seems to have worked.  Excellent.
## Post #21
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-09-24T08:15:35+00:00
- Post Title: 

Hi again,

Yes, it sounds like you have got it ok - just add the 4 bits back to the beginning of the BMP image and it should be right. Good work.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
