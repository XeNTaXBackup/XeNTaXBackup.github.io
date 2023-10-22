## Post #1
- Username: aeon
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 14, 2006 8:20 pm
- Post datetime: 2009-01-31T18:15:01+00:00
- Post Title: tracker music

hi

this is a tracker module music I've had on my hdd for a long time but have never figured what format it is and how it can be played, any help here?


[http://www.zippyshare.com/v/36819630/file.html](http://www.zippyshare.com/v/36819630/file.html)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-05-17T20:54:47+00:00
- Post Title: tracker music

Too bad, the file is no longer available.
## Post #3
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-05-21T19:41:39+00:00
- Post Title: tracker music

Here it is: (hopefully this is the right one  )

[http://www.box.net/shared/z69nxqv97o](http://www.box.net/shared/z69nxqv97o)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-05-23T12:11:33+00:00
- Post Title: tracker music

Okay, and this is not a standard .mus format?  Like Doom etc.?
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-23T13:48:35+00:00
- Post Title: tracker music

no, it's an unknown format composed by various SONG and SMPL chunks.
the only known format which uses chunks with these same names is [DBM](http://modplug.svn.sourceforge.net/viewvc/modplug/trunk/OpenMPT/soundlib/LOAD_DBM.CPP?revision=216&view=markup) but the format is totally different
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-24T22:46:28+00:00
- Post Title: tracker music

ih ih ih Psycho Pinball, great game :)
I was playing this game just now and, interested by the music, I found the same mod which was posted.
with a quick search on internet I have found no converters for this strange format (seems used also in MicroMachines 2) but the converted mods are available here:

[http://www.mirsoft.info/gamemods/Psycho%20Pinball.zip](http://www.mirsoft.info/gamemods/Psycho%20Pinball.zip)

except for "Automatic conversion to MOD" there are no other details about the ripping of these mods, anyway they are not in the process's memory and the content differs from those of the mus files
## Post #7
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2009-05-26T15:05:42+00:00
- Post Title: tracker music

I would guess that Codemasters did an own format that was similiar to MOD/XM , (which actually lots of folks did those days)
both to prevent ripping of the tunes and to optimize the size of them. The info on this particular format is VERY limited, but a wild guess is
because it was developed inhouse.

Im also interested in this , but my googling fails me this time. 

Maybe we should write to an old Codemasters employee and ask for infos
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-26T18:04:55+00:00
- Post Title: tracker music

uhmm considering that this format is used only in a very limited number of very old games and the mods have been already converted I don't think it can be defined interesting.
anyway if you are really interested you could try to contact directly who did the conversion job: [http://users.hszk.bme.hu/~pg429/](http://users.hszk.bme.hu/~pg429/)
## Post #9
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2009-05-26T18:06:34+00:00
- Post Title: tracker music

Any knowledge is interesting!
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-05-26T18:30:41+00:00
- Post Title: tracker music

"PC Music/FX System" (c) Karl Morton 1994 

That's the programmer of the tracker format. Karl Morton of Team17 (also of Worms 2 fame). 

This info is in the exe of Psycho Pinball. 

So you could stalk him if you'd like. 

What I've learned from the .mus file is that it is simply an archive containing the songs for the Abyss level. (Starting with SONG indeed). Comparing the xtraball SONG with the converted MOD shows how very, very similar they are. This means that Karl probably build his format on the MOD format. Possibly even just slight changes.
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-05-26T20:05:22+00:00
- Post Title: tracker music

Okay so far this is what I think the SONG format from Karl is: 

```

Magic Word (4)	"SONG"
uint32		Offset of sample data
char {32}	Song name of 32 bytes in length

// Sample information (1-31), sequential, 34 bytes in length

char {32}	Sample name of 32 bytes in length
Byte		finetune value (signed nibble)?
Byte		volume of the sample (max 64)

// Pattern data (1024 bytes)

Bytes {2}	Unknown
Bytes {2}	channels? 
Bytes {6}	Unknown
uint32 		Size of pattern data

// Sample data 

Magic Word {4}	"SMPL"
uint32		Total size of sample file
char {32}	Sample name of max 32 bytes in length
uint32		Size of raw audio data? (sometimes 0!)
uint32		Size of raw audio data

```


I'll see if I can have some more time later to work on it.
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-05-27T19:29:36+00:00
- Post Title: tracker music

Okay , a little update. The pattern information is sometimes similar to .MOD, e.g. 4 channel columns of 64 rows. (each channel is 4 bytes and in sequence). Except when the rows are mostly empty, Karl has build in some kind of compression. The rows are simply saved in a .mod file, but Karl was smart, and made sure these parts were compressed to save diskspace. 

I've attached the pattern info of the getwed.mod and that of the corresponding .song file taken from abyss.mus. The latter is compressed. 

Any thoughts?


 getwet.zip
(1.22 KiB) Downloaded 37 times
## Post #13
- Username: Darkfox
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-05-30T19:14:01+00:00
- Post Title: tracker music

I've contacted Gergely, the man who converted those tunes to MOD  

Turns out he has the converter and source code at his website: 

[http://sgate.iit.bme.hu/patai/programs/](http://sgate.iit.bme.hu/patai/programs/)

I've attached mus2mod at this post as well. 


 mus2mod.zip
(12.97 KiB) Downloaded 45 times



Here is some additional info that he'd like to bring forward: 

> Reply from Gergely
>
> 
The trickiest part was figuring out how the pattern compression works,
the rest is pretty much trivial. The basic idea is that the player has
to maintain a buffer that stores all the data of the current line. The
pattern data contains markers that tell you how many of the following notes in the current
channel are the replica of the current one, hence the subsequent data
treats this channel as nonexistent until the counter gets back to zero. In other words, this
number can be more than the number of channels (in this case we just
start filling the subsequent rows (per channel) note by note), so a single byte can
describe several rows if there's not much going on. It's also possible
to reuse half of the previous data (e.g. only the pitch changes).

This idea is ingenious, because you can play back the song without
having to decompress the pattern data. However, on the other hand, there
are no separate patterns stored in the file (i.e. all the music data is
continuous) and no order list, so the repetitions normally expressed by
patterns are not handled well by this method. I had to work around this
and added some mechanism to reconstruct patterns, but it makes quite a
mess if the non-looping intro part of the song is short (like two
lines), because that shifts every pattern in an unpleasant way.

The details are in the code. Feel free to do whatever you want with it.

I posed the idea that it could be cool if someone could make a genuine .mus player, as to be the most faithful to Karl's player:

> Reply from Gergely
>
> 
The player can be derived from a plain MOD player (and I believe that's
what he did too), because as I noted in the source, the effects seem to
work the same way down to the smallest nuances (e.g. portamentos don't
have any effect in the first tick of the respective row). All you need
to do is modify the front-end to decode his pattern format, but my code
can do that already, so there's just a little plumbing to do.

So, the code is there. Anyone familiar with, say bass.dll from un4seen might be able to do the trick using Gergely's code. 



Thanks, Gergely!
## Post #14
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2009-06-01T22:37:45+00:00
- Post Title: tracker music

This is pleasing to my eyes! Im spoonfed with fileformat fetisch rampage! =O
You deserve a damn cookiejar! =D
## Post #15
- Username: Borg Number One
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jun 06, 2004 10:33 pm
- Post datetime: 2010-02-14T03:31:32+00:00
- Post Title: tracker music

Hi.

While tidying up my old emails, I found some with relations to these themes: Karl Morton, SONG SMPL MUS SFX, Patai Gergely.
There was a time (long time before the current thread was started) when I had the same problem: playing/converting tunes from Micro Machines, Psycho Pinball etc.
So I got in contact with Patai Gergely and later I did help with some small new ideas / improvements for its mus2mod .
Here are the emails which will maybe:
+ contain some important key words (for other user who search in google for a .mus to .mod conversation solution or a Psycho Pinball .mus player solution) 
+ show the relationship/context between a) last modified date (29.07.2008) in mus2mod.zip and in its compressed files (convert.c - 29.07.2008 - 21:43 - 12.454 bytes; convert.exe - 29.07.2008 - 21:55 - 29.607 bytes; Makefile - 29.07.2008 - 21:27 - 84 bytes) and b) the time stamps in the emails
+ show the backgrounds while developing, testing, improving mus2mod

----------
----------
Received: from 84.184.181.132 by www098.gmx.net with HTTP;
 Fri, 25 Jul 2008 13:17:29 +0200 (CEST)
Content-Type: text/plain; charset="us-ascii"
Date: Fri, 25 Jul 2008 13:17:29 +0200
From: "Borg No. One" <[borg_no.one@gmx.net](mailto:borg_no.one@gmx.net)>
Message-ID: <[20080725111729.15610@gmx.net](mailto:20080725111729.15610@gmx.net)>
MIME-Version: 1.0
Subject: Psycho Pinball - Micro Machines v2 - Music Format
To: [patai_gergely@fastmail.fm](mailto:patai_gergely@fastmail.fm)
Hi.

After many years of searching Psycho Pinball related music format documents/specifications, I finally found some links.

[http://www.mirsoft.info/gmb/music_info. ... e=MTQwMDA=](http://www.mirsoft.info/gmb/music_info.php?id_ele=MTQwMDA=)
[http://www.un4seen.com/forum/?topic=5051.0](http://www.un4seen.com/forum/?topic=5051.0)
[http://forum.rscnet.org/showthread.php?t=106688](http://forum.rscnet.org/showthread.php?t=106688)

I would like to know, if you could successfully understand the Karl Morton Sound Format?
How can the .mus/.sfx ("SONG"/"SMPL") tunes be converted to common amiga module formats?

----------
----------
Return-Path: <[patai_gergely@fastmail.fm](mailto:patai_gergely@fastmail.fm)>
X-Flags: 1011
Delivered-To: GMX delivery to [borg_no.one@gmx.net](mailto:borg_no.one@gmx.net)
Received: (qmail invoked by alias); 25 Jul 2008 16:29:32 -0000
Received: from out3.smtp.messagingengine.com (EHLO out3.smtp.messagingengine.com) [66.111.4.27]
  by mx0.gmx.net (mx110) with SMTP; 25 Jul 2008 18:29:32 +0200
Received: from compute1.internal (compute1.internal [10.202.2.41])
	by out1.messagingengine.com (Postfix) with ESMTP id 86ABF141BBF
	for <[borg_no.one@gmx.net](mailto:borg_no.one@gmx.net)>; Fri, 25 Jul 2008 12:29:31 -0400 (EDT)
Received: from web5.messagingengine.com ([10.202.2.214])
  by compute1.internal (MEProxy); Fri, 25 Jul 2008 12:29:31 -0400
Received: by web5.messagingengine.com (Postfix, from userid 99)
	id 6B0AB3006D; Fri, 25 Jul 2008 12:29:31 -0400 (EDT)
Message-Id: <[1217003371.4646.1265352393@webmail.messagingengine.com](mailto:1217003371.4646.1265352393@webmail.messagingengine.com)>
X-Sasl-Enc: LrNGQcQ43oJDWkkDd08gAsRz2b7SXcX18Q2K+QkzgiE3 1217003371
From: "Patai Gergely" <[patai_gergely@fastmail.fm](mailto:patai_gergely@fastmail.fm)>
To: "Borg No. One" <[borg_no.one@gmx.net](mailto:borg_no.one@gmx.net)>
Content-Disposition: inline
Content-Transfer-Encoding: 7bit
Content-Type: text/plain; charset="ISO-8859-2"
MIME-Version: 1.0
X-Mailer: MessagingEngine.com Webmail Interface
References: <[20080725111729.15610@gmx.net](mailto:20080725111729.15610@gmx.net)>
Subject: Re: Psycho Pinball - Micro Machines v2 - Music Format
In-Reply-To: <[20080725111729.15610@gmx.net](mailto:20080725111729.15610@gmx.net)>
Date: Fri, 25 Jul 2008 18:29:31 +0200

Hello,

> I would like to know, if you could successfully understand the Karl
> Morton Sound Format?
> How can the .mus/.sfx ("SONG"/"SMPL") tunes be converted to common amiga
> module formats?
Yes, I managed to reverse-engineer the format for the most part (I can't
handle every effect, but those needed by PP and MM2 are all supported).
The tricky bit is the actual notes, because they are stored in a way
that doesn't resemble any other major module format (for instance, there
are no patterns at all), so it took a while to work out. I wrote a
utility to do the conversion, you can get it here:

[http://users.hszk.bme.hu/~pg429/misc/convert.exe](http://users.hszk.bme.hu/~pg429/misc/convert.exe)

The usage is very simple, just pass the .mus file to it as a parameter,
and the .mod files will be created in the same directory. The results of
the PP and MM2 conversions can be downloaded from Mirsoft (registration
is free, an I can only recommend joining, because they have a lot of
wonderful material to offer!). I was also looking for other games with
music in the same format, but couldn't find anything, so if you happen
to know more than these two, I'd be glad to hear about it.

PG

----------
----------
Received: from 84.184.150.123 by www008.gmx.net with HTTP;
 Sun, 27 Jul 2008 22:57:10 +0200 (CEST)
Content-Type: text/plain; charset="iso-8859-1"
Date: Sun, 27 Jul 2008 22:57:10 +0200
From: "Borg No. One" <[borg_no.one@gmx.net](mailto:borg_no.one@gmx.net)>
In-Reply-To: <[1217003371.4646.1265352393@webmail.messagingengine.com](mailto:1217003371.4646.1265352393@webmail.messagingengine.com)>
Message-ID: <[20080727205710.307120@gmx.net](mailto:20080727205710.307120@gmx.net)>
MIME-Version: 1.0
References: <[20080725111729.15610@gmx.net](mailto:20080725111729.15610@gmx.net)>
 <[1217003371.4646.1265352393@webmail.messagingengine.com](mailto:1217003371.4646.1265352393@webmail.messagingengine.com)>
Subject: Re: Psycho Pinball - Micro Machines v2 - Music Format
To: "Patai Gergely" <[patai_gergely@fastmail.fm](mailto:patai_gergely@fastmail.fm)>

Hi.

1.)
Y O U  A R E  A B S O L U T E L Y  G R E A T  ! ! !

The converter works fine and it is able to even extract/convert the subsongs in .mus files to single .mod files.

Extracted mods will also be played fine in modplug tracker. 

This feature is also great:
The converter is so intelligent to take the subsong names and sample names from the .mus files.

I mostly like the abyss tunes.

2.)
I already know about mirsoft's homepage. 
Check this:
[http://www.mirsoft.info/gmb/user_info.p ... e=MTY0OQ==](http://www.mirsoft.info/gmb/user_info.php?id_ele=MTY0OQ==)
[http://www.mirsoft.info/gamemids-help.php](http://www.mirsoft.info/gamemids-help.php) --> look for "Borg" in the text. 

(But until now, I never had enough time to login / create an mirsoft account.)


3.)
The .mus format seems to have some special commands
(in songs which have one intro pattern and many loop patterns).

For example:
abyss_sunkentreasure.mod will be played in this way: [intro tune][main tune]


But it should be played in this way: [intro tune][main tune][main tune][main tune]...[main tune]


In other words, could you figure out, how loops/loop beginnings are marked/encoded in .mus tunes?
And could you add a feature to the converter where the user can define how often a loop will be played in the finally converted .mod tune?


4.)
If you open "abyss_sunkentreasure.mod" (and other songs) in modplug tracker, then you will see that the [intro tune] and a part from the main tune use the space in .mod-module pattern 0.
In other words, intro tune and the first part of the loop/main tune share pattern 0.

It would be great if your converter could detect and make a difference between intro tunes and loop tunes (endless main tunes) and put only intro tunes to pattern 0 (or 0, 1, 2) and main/loop tunes to the following patterns after the first patterns.


-------- Original-Nachricht --------
> Datum: Fri, 25 Jul 2008 18:29:31 +0200
> Von: "Patai Gergely" <[patai_gergely@fastmail.fm](mailto:patai_gergely@fastmail.fm)>
> An: "Borg No. One" <[borg_no.one@gmx.net](mailto:borg_no.one@gmx.net)>
> Betreff: Re: Psycho Pinball - Micro Machines v2 - Music Format

> Hello,
> 
> > I would like to know, if you could successfully understand the Karl
> > Morton Sound Format?
> > How can the .mus/.sfx ("SONG"/"SMPL") tunes be converted to common amiga
> > module formats?
> Yes, I managed to reverse-engineer the format for the most part (I can't
> handle every effect, but those needed by PP and MM2 are all supported).
> The tricky bit is the actual notes, because they are stored in a way
> that doesn't resemble any other major module format (for instance, there
> are no patterns at all), so it took a while to work out. I wrote a
> utility to do the conversion, you can get it here:
> 
> [http://users.hszk.bme.hu/~pg429/misc/convert.exe](http://users.hszk.bme.hu/~pg429/misc/convert.exe)
> 
> The usage is very simple, just pass the .mus file to it as a parameter,
> and the .mod files will be created in the same directory. The results of
> the PP and MM2 conversions can be downloaded from Mirsoft (registration
> is free, an I can only recommend joining, because they have a lot of
> wonderful material to offer!). I was also looking for other games with
> music in the same format, but couldn't find anything, so if you happen
> to know more than these two, I'd be glad to hear about it.
> 
> PG

----------
----------
Return-Path: <[patai_gergely@fastmail.fm](mailto:patai_gergely@fastmail.fm)>
X-Flags: 1001
Delivered-To: GMX delivery to [borg_no.one@gmx.net](mailto:borg_no.one@gmx.net)
Received: (qmail invoked by alias); 27 Jul 2008 21:59:39 -0000
Received: from out4.smtp.messagingengine.com (EHLO out4.smtp.messagingengine.com) [66.111.4.28]
  by mx0.gmx.net (mx055) with SMTP; 27 Jul 2008 23:59:39 +0200
Received: from compute2.internal (compute2.internal [10.202.2.42])
	by out1.messagingengine.com (Postfix) with ESMTP id 6427214529F
	for <[borg_no.one@gmx.net](mailto:borg_no.one@gmx.net)>; Sun, 27 Jul 2008 17:59:38 -0400 (EDT)
Received: from web5.messagingengine.com ([10.202.2.214])
  by compute2.internal (MEProxy); Sun, 27 Jul 2008 17:59:38 -0400
Received: by web5.messagingengine.com (Postfix, from userid 99)
	id 47EFE348DC; Sun, 27 Jul 2008 17:59:38 -0400 (EDT)
Message-Id: <[1217195978.7577.1265594745@webmail.messagingengine.com](mailto:1217195978.7577.1265594745@webmail.messagingengine.com)>
X-Sasl-Enc: ZId6n4TXABF4ieT3aRRSB542Ah1CYOiRYwZE03pIeBE4 1217195978
From: "Patai Gergely" <[patai_gergely@fastmail.fm](mailto:patai_gergely@fastmail.fm)>
To: "Borg No. One" <[borg_no.one@gmx.net](mailto:borg_no.one@gmx.net)>
Content-Disposition: inline
Content-Transfer-Encoding: 7bit
Content-Type: text/plain; charset="ISO-8859-2"
MIME-Version: 1.0
X-Mailer: MessagingEngine.com Webmail Interface
References: <[20080725111729.15610@gmx.net](mailto:20080725111729.15610@gmx.net)>
 <[1217003371.4646.1265352393@webmail.messagingengine.com](mailto:1217003371.4646.1265352393@webmail.messagingengine.com)>
 <[20080727205710.307120@gmx.net](mailto:20080727205710.307120@gmx.net)>
Subject: Re: Psycho Pinball - Micro Machines v2 - Music Format
In-Reply-To: <[20080727205710.307120@gmx.net](mailto:20080727205710.307120@gmx.net)>
Date: Sun, 27 Jul 2008 23:59:38 +0200

Hello again,

> Y O U  A R E  A B S O L U T E L Y  G R E A T  ! ! !
Oh, come on, that's gratuitous flattering. But I like it. 

> Extracted mods will also be played fine in modplug tracker. 
Actually, I consider it a huge luck that Karl Morton's effects work the
exact same way as standard Protracker mod effects, otherwise the
conversion wouldn't be possible. This is extremely important in the Wild
West songs for instance, because they rely on portamentos a lot.

> [http://www.mirsoft.info/gmb/user_info.p ... e=MTY0OQ==](http://www.mirsoft.info/gmb/user_info.php?id_ele=MTY0OQ==)
> [http://www.mirsoft.info/gamemids-help.php](http://www.mirsoft.info/gamemids-help.php) --> look for "Borg" in the
> text. 
Oh, I found out in the meantime that you are quite an active person. 

> In other words, could you figure out, how loops/loop beginnings are
> marked/encoded in .mus tunes?
I know that already, I just haven't added that feature to the converter.
It's a bit inconvenient, but not too much trouble, and I'll gladly do it
for you.

> And could you add a feature to the converter where the user can define
> how often a loop will be played in the finally converted .mod tune?
I'm not sure how you mean that. MODs don't have a numbered loop command.
If you mean to replicate the patterns in the order list, that's of
course possible, but then you are limited by the length of the order
list.

> In other words, intro tune and the first part of the loop/main tune share
> pattern 0.
Yes, and that's not the only problem. Since the .mus files only contain
the notes played (in a very clever fashion that doesn't require them to
be uncompressed during playback!) without any indication of pattern
boundaries, I'm just making 64-line slices and put them in patterns. The
only intelligent step is the detection of identical patterns. However,
some songs (e.g. the Wild West theme) are apparently composed of 48-line
patterns, and my method doesn't reconstruct them properly either.

> It would be great if your converter could detect and make a difference
> between intro tunes and loop tunes (endless main tunes) and put only
> intro tunes to pattern 0 (or 0, 1, 2) and main/loop tunes to the
> following patterns after the first patterns.
Yes, this is the only way it could be done anyway, since the loop
command takes an order index.

By the way, I plan to release the source of the converter too (it's just
a tiny C program), but I want to document the format first, because I
haven't done that so far. I'm rather busy nowadays, but I'll try to get
all that done by the end of August.

So let me repeat: if you come across this format anywhere else, please
notify me too, because I'm also interested in improving the converter
(note: with some experimentation I have actually managed to decode more
features than those used by PP and MM2, but it's still not complete).
After finishing the current version I have made some searches for Karl
Morton, looked through Mobygames, Mirsoft etc., but couldn't find
anything else, only the fact that this music system was used in numerous
games.

Regards,

PG

----------
----------
Return-Path: <[patai_gergely@fastmail.fm](mailto:patai_gergely@fastmail.fm)>
X-Flags: 1011
Delivered-To: GMX delivery to [borg_no.one@gmx.net](mailto:borg_no.one@gmx.net)
Received: (qmail invoked by alias); 29 Jul 2008 18:03:02 -0000
Received: from out1.smtp.messagingengine.com (EHLO out1.smtp.messagingengine.com) [66.111.4.25]
  by mx0.gmx.net (mx088) with SMTP; 29 Jul 2008 20:03:02 +0200
Received: from compute1.internal (compute1.internal [10.202.2.41])
	by out1.messagingengine.com (Postfix) with ESMTP id CD05814F017
	for <[borg_no.one@gmx.net](mailto:borg_no.one@gmx.net)>; Tue, 29 Jul 2008 14:03:01 -0400 (EDT)
Received: from web6.messagingengine.com ([10.202.2.215])
  by compute1.internal (MEProxy); Tue, 29 Jul 2008 14:03:01 -0400
Received: by web6.messagingengine.com (Postfix, from userid 99)
	id B1CC1378D5; Tue, 29 Jul 2008 14:03:01 -0400 (EDT)
Message-Id: <[1217354581.19864.1265964501@webmail.messagingengine.com](mailto:1217354581.19864.1265964501@webmail.messagingengine.com)>
X-Sasl-Enc: AgJYSRDUaSTFM284z3IckOsPxMHeXsIcu3wLgNybggWS 1217354581
From: "Patai Gergely" <[patai_gergely@fastmail.fm](mailto:patai_gergely@fastmail.fm)>
To: "Borg No. One" <[borg_no.one@gmx.net](mailto:borg_no.one@gmx.net)>
Content-Disposition: inline
Content-Transfer-Encoding: 7bit
Content-Type: text/plain; charset="ISO-8859-2"
MIME-Version: 1.0
X-Mailer: MessagingEngine.com Webmail Interface
References: <[20080725111729.15610@gmx.net](mailto:20080725111729.15610@gmx.net)>
 <[1217003371.4646.1265352393@webmail.messagingengine.com](mailto:1217003371.4646.1265352393@webmail.messagingengine.com)>
 <[20080727205710.307120@gmx.net](mailto:20080727205710.307120@gmx.net)>
Subject: Re: Psycho Pinball - Micro Machines v2 - Music Format
In-Reply-To: <[20080727205710.307120@gmx.net](mailto:20080727205710.307120@gmx.net)>
Date: Tue, 29 Jul 2008 20:03:01 +0200

Hello again,

I added some more intelligent loop handling. Now the converter detects
the intro part and cuts the pattern before the repetition starts. You
can also specify the number of repetitions in an optional second
argument, simply as a decimal. If it is zero, looping is enabled, so
that's the default behaviour. If it is more than zero, looping is
disabled (it wouldn't really make sense to enable, since the result
would be identical to the default, just having a longer order list), but
the repeating part is included n times in the song if the parameter is
n.

E.g. if you execute "convert abyss.mus", you'll get properly looped
songs, and if you say "convert abyss.mus 3", then the looping part will
be played 3 times before you hear the intro again. Note that the song
will be cut after 128 orders if the repetition number is too big to fit.

Please tell me if there is a bug or something unexpected happens.

The download link is the same as before:

[http://users.hszk.bme.hu/~pg429/misc/convert.exe](http://users.hszk.bme.hu/~pg429/misc/convert.exe)

Have fun with it,

PG

----------
----------
Received: from 84.184.173.39 by www067.gmx.net with HTTP;
 Sat, 02 Aug 2008 16:16:09 +0200 (CEST)
Content-Type: text/plain; charset="us-ascii"
Date: Sat, 02 Aug 2008 16:16:09 +0200
From: "Borg No. One" <[borg_no.one@gmx.net](mailto:borg_no.one@gmx.net)>
In-Reply-To: <[1217354581.19864.1265964501@webmail.messagingengine.com](mailto:1217354581.19864.1265964501@webmail.messagingengine.com)>
Message-ID: <[20080802141609.227970@gmx.net](mailto:20080802141609.227970@gmx.net)>
MIME-Version: 1.0
References: <[20080725111729.15610@gmx.net](mailto:20080725111729.15610@gmx.net)>
 <[1217003371.4646.1265352393@webmail.messagingengine.com](mailto:1217003371.4646.1265352393@webmail.messagingengine.com)>
 <[20080727205710.307120@gmx.net](mailto:20080727205710.307120@gmx.net)>
 <[1217354581.19864.1265964501@webmail.messagingengine.com](mailto:1217354581.19864.1265964501@webmail.messagingengine.com)>
Subject: Re: Psycho Pinball - Micro Machines v2 - Music Format
To: "Patai Gergely" <[patai_gergely@fastmail.fm](mailto:patai_gergely@fastmail.fm)>
X-Authenticated: #13423119
X-Flags: 1001
X-GMX-Parent-Flag: answered
X-GMX-Parent-Folder: inbox
X-GMX-Parent-UID: OTbtHDNlbXBte2qg/jQ2CEgqLyUmZQjR
X-Mailer: WWW-Mail 6100 (Global Message Exchange)
X-Priority: 3
X-Provags-ID: V01U2FsdGVkX19n/8YN3LxnR+FY6b75DoHRZWFvYXIIxuPYFpZVk3
 F0DhIVraej24RPS0edrhokbXE28FeOfSqi1g== 
Content-Transfer-Encoding: 7bit
X-GMX-UID: SAD/IPY7TlIvZWe3u2hrxDhGU2poZdkR

Hi Patai,


I did many tests and experiments with the converter and the converted .mod files.
The converter works great, but there are some points I figured out and some questions about the points.
Furthermore I took some time to prepare a few improvements/suggestions.

1.)
In DeliPlayer and some other players the .mod files are identifed as "TakeTracker".
In OpenMPT and newer other players the .mod files are identifed as "ProTracker".

While programming the converter, did you exactly use/follow ProTracker or TakeTracker specification?
[http://protracker.de/pages/index_apps.p ... ule-Format](http://protracker.de/pages/index_apps.php?action=3&system=amiga&dir=formats&name=Protracker+3.61&source=protracker_361_format.txt&addon=Module-Format)"
[http://pouet.net/prod.php?which=33176](http://pouet.net/prod.php?which=33176)

It would be great if we could exactly agree to one format specification(I would prefer ProTracker, because it has subsong capabilities.)

2.)
What do you think about a subsong feature in the converter?
Check:
[http://www.exotica.org.uk/wiki/Cool_Spot](http://www.exotica.org.uk/wiki/Cool_Spot)
[http://www.exotica.org.uk/wiki/Aladdin](http://www.exotica.org.uk/wiki/Aladdin)

In DeliPlayer ([http://www.google.de/search?q=dp250pb1](http://www.google.de/search?q=dp250pb1)) you will see that the .mod file
has subsongs. (Open Window-->Detailed information; "+"/"-" for selecting a subsong.)
Or use following method: Deliplayer --> right mouse click --> Config --> Control Client --> Evaluation --> Creatue Sublists for Sub-songs --> Save.

Even DeliTracker, XMPlay and other players can detect and play ProTracker (.mod) with subsongs.

Well, a ProTracker module with subsongs is still compatible with applications which have no subsong feature. (OpenMPT)

3a.)
Here are some suggestions for convert.exe and history.txt.
(use notepad or DOS-editor or --pre-- --/pre-- HTML tags for correct display.)

```
0123456789
          0123456789
                    0123456789
                              0123456789
                                        0123456789
                                                  0123456789
                                                            0123456789
                                                                      0123456789

Output if no or wrong parameters are used:

c:\>convert.exe

CoBB's [ Patai Gergely ] - Karl Morton to Protracker converter ver. 3
(Or: Karl Morton to Protracker converter by CoBB
...testing/improvements by Borg Number One... or something like this.)

Converts: Karl Morton tracker format / Karl Morton module format (.mus files) /
tunes from Games with "PC Music/FX System" (c) Karl Morton 1994"
to Protracker format (.mod files).
Working/known Games: Psycho Pinball, Micro Machines v2

%Error%

Syntax / How to use the converter.
Convert [input file] [/n=#n] [/s]

  input file    specifies the Karl Morton module (.mus file) for conversion
  #n            specifies how often the main loop in .mus files will be repeated
                in the converted target module (.mod file).(Optional)
                (#n max=???)
  s             Puts all subsongs from a Karl Morton module to a Protracker
                module with subsongs.(Optional)
Example:        convert.exe title.mus 2


Generally Karl Morton .mus files consist of sub songs.

The converter is able to either store each converted sub song into single .mod
files or all subsongs into one .mod file. This would save space.

Furthermore, many subsongs contains an intro part and a main part which will be
repeated while the subsong is playing inside the game. #n defines the number of
repeatings in the converted .mod file.
```




```
%Error%
```
 can be: 
```
"Please specify an input file."
```
/
```
"Input file not found or not accessible."
```
/

```
"Input file is not a Karl Morton module or it is a demaged module."
```
/
```
"Cannot write output file."
```
/

```
"%n is not a number between 0...xxx / 1...xxx"
```


(not accessible means: Specified file is available but already in use or protected via NTFS rulez anyhow.)
("%n is not a number between..." solves two problems: a) User typed a letter b) User typed a too large number.)


Output while converting:

```

CoBB's [ Patai Gergely ] - Karl Morton to Protracker Converter ver. 3

Converts Karl Morton tracker format / Karl Morton module format (.mus files)
to Protracker format (.mod files).
Working/known Games: Psycho Pinball, Micro Machines v2

Input file:   title.mus
Detected Subsongs: choosegame, psychotitle
Loops: 2
Output files: %[input file]-[extension]%_choosegame.mod
              %[input file]-[extension]%_psychotitle.mod
...done

```


3b)
history.txt/readme.txt

version 3 - xx.08.2008
Bug Fix:     Exactly following the Protracker Format Specification.
             Output .mod files were either detected as TakeTracker or ProTracker in different players like
             DeliPlayer, Winamp, OpenMPT(ModPlug Tracker), XMPlay
New Feature: Detailed help screen and example converting instructions.

Version 2 - 28/29.07.2008

New Feature: Repeating/equal patterns in a Karl Morton tun (.mus file)  will be saved with same pattern numbers in .mod file.
             Old behaviour: A Karl Morton tune contains patterns like this: 0,1,2,1,2,3,4,...
             The converted .mod tune looked like this: 0,1,2,3,4,5,6,7. (Equal patterns were not detected.)
New Feature: Loop detection in .mus files. Intro and main part in Karl Morton tunes will be separated in converted .mod tunes,
             which makes it possible to 

version 1 - xx.xx.200?
.... initial release .... for Micro Machines v2 and Psycho Pinball.



Furthermore, I did some research finding more details about Karl Morton (email adress, phone number etc...).
Here are the results:
[http://spong.com/people/751?cb=771](http://spong.com/people/751?cb=771)
[http://www.worms2.com/main.html?page=ab ... &inte=karl](http://www.worms2.com/main.html?page=abou&area=thet&inte=karl)
(--> "about 12 miles") , could it mean that he lives/lived in/around (West) Yorkshire?)
[http://www.google.de/search?q=%22Karl+M ... +yorkshire](http://www.google.de/search?q=%22Karl+Morton%22+yorkshire)

[http://genforum.genealogy.com/morton/all.html](http://genforum.genealogy.com/morton/all.html)
(Wait until the site will be ready with loading then look for: "Karl". You will find some postings by a member called Karl and and an email adress: [majmorton@aol.com](mailto:majmorton@aol.com).
I tried sending him a message some days ago, but until now I did not get any answer.)

[http://www.thephonebook.bt.com/publisha ... =&x=28&y=5](http://www.thephonebook.bt.com/publisha.content/en/search/residential/search.publisha?Surname=morton&Initial=k&Street=&Town=yorkshire&Postcode=&x=28&y=5)
[http://www.thephonebook.bt.com/publisha ... Range=xloc](http://www.thephonebook.bt.com/publisha.content/en/search/residential/search.publisha?Surname=morton&Initial=k&Street=&Town=yorkshire&Postcode=&x=28&y=5&Location=YORKSHIRE&OriginalLocation=yorkshire&Range=xloc)
[http://www.thephonebook.bt.com/publisha ... Range=xloc](http://www.thephonebook.bt.com/publisha.content/en/search/residential/search.publisha?Surname=morton&Initial=k&Street=&Town=yorkshire&Postcode=&x=28&y=5&Location=YORKSHIRE+WEST&OriginalLocation=yorkshire&Range=xloc)
(If you can find the real Karl Morton, then you will be good.)


Well, today I could find another game which uses Karl Morton's PC Music/FX System inside the .exe file: "Back to Baghdad."
[http://www.mobygames.com/developer/shee ... erId,1705/](http://www.mobygames.com/developer/sheet/view/developerId,1705/)
-->
[http://www.google.de/search?q=%22back+to+baghdad%22+dos](http://www.google.de/search?q=%22back+to+baghdad%22+dos)
[http://www.the-underdogs.info/game.php?id=4454](http://www.the-underdogs.info/game.php?id=4454)
[http://doperoms.com/roms/dos/Back](http://doperoms.com/roms/dos/Back) To Baghdad (1996)(Military Sim).zip.html

I had no time to check the game until now.


Here are some further interesting abandonware links / links about new and classic stuff:
[http://hem.passagen.se/abandonware/?k](http://hem.passagen.se/abandonware/?k)

-------- Original-Nachricht --------
> Datum: Tue, 29 Jul 2008 20:03:01 +0200
> Von: "Patai Gergely" <[patai_gergely@fastmail.fm](mailto:patai_gergely@fastmail.fm)>
> An: "Borg No. One" <[borg_no.one@gmx.net](mailto:borg_no.one@gmx.net)>
> Betreff: Re: Psycho Pinball - Micro Machines v2 - Music Format

> Hello again,
> 
> I added some more intelligent loop handling. Now the converter detects
> the intro part and cuts the pattern before the repetition starts. You
> can also specify the number of repetitions in an optional second
> argument, simply as a decimal. If it is zero, looping is enabled, so
> that's the default behaviour. If it is more than zero, looping is
> disabled (it wouldn't really make sense to enable, since the result
> would be identical to the default, just having a longer order list), but
> the repeating part is included n times in the song if the parameter is
> n.
> 
> E.g. if you execute "convert abyss.mus", you'll get properly looped
> songs, and if you say "convert abyss.mus 3", then the looping part will
> be played 3 times before you hear the intro again. Note that the song
> will be cut after 128 orders if the repetition number is too big to fit.
> 
> Please tell me if there is a bug or something unexpected happens.
> 
> The download link is the same as before:
> 
> [http://users.hszk.bme.hu/~pg429/misc/convert.exe](http://users.hszk.bme.hu/~pg429/misc/convert.exe)
> 
> Have fun with it,
> 
> PG
> 

----------
----------
Return-Path: <[patai_gergely@fastmail.fm](mailto:patai_gergely@fastmail.fm)>
X-Flags: 1001
Delivered-To: GMX delivery to [borg_no.one@gmx.net](mailto:borg_no.one@gmx.net)
Received: (qmail invoked by alias); 05 Aug 2008 17:54:02 -0000
Received: from out2.smtp.messagingengine.com (EHLO out2.smtp.messagingengine.com) [66.111.4.26]
  by mx0.gmx.net (mx088) with SMTP; 05 Aug 2008 19:54:02 +0200
Received: from compute2.internal (compute2.internal [10.202.2.42])
	by out1.messagingengine.com (Postfix) with ESMTP id A7A21153D51
	for <[borg_no.one@gmx.net](mailto:borg_no.one@gmx.net)>; Tue,  5 Aug 2008 13:54:01 -0400 (EDT)
Received: from web6.messagingengine.com ([10.202.2.215])
  by compute2.internal (MEProxy); Tue, 05 Aug 2008 13:54:01 -0400
Received: by web6.messagingengine.com (Postfix, from userid 99)
	id 7A39412885; Tue,  5 Aug 2008 13:54:01 -0400 (EDT)
Message-Id: <[1217958841.14684.1267138409@webmail.messagingengine.com](mailto:1217958841.14684.1267138409@webmail.messagingengine.com)>
X-Sasl-Enc: X0nEesHalq3jX1dWeift3eSezLsrhvOuaOVqW2M0NwOj 1217958841
From: "Patai Gergely" <[patai_gergely@fastmail.fm](mailto:patai_gergely@fastmail.fm)>
To: "Borg No. One" <[borg_no.one@gmx.net](mailto:borg_no.one@gmx.net)>
Content-Disposition: inline
Content-Transfer-Encoding: 7bit
Content-Type: text/plain; charset="ISO-8859-2"
MIME-Version: 1.0
X-Mailer: MessagingEngine.com Webmail Interface
Subject: Re: Psycho Pinball - Micro Machines v2 - Music Format
In-Reply-To: <[20080802141609.227970@gmx.net](mailto:20080802141609.227970@gmx.net)>
Date: Tue, 05 Aug 2008 19:54:01 +0200
References: <[20080725111729.15610@gmx.net](mailto:20080725111729.15610@gmx.net)>
 <[1217003371.4646.1265352393@webmail.messagingengine.com](mailto:1217003371.4646.1265352393@webmail.messagingengine.com)>
 <[20080727205710.307120@gmx.net](mailto:20080727205710.307120@gmx.net)>
 <[1217354581.19864.1265964501@webmail.messagingengine.com](mailto:1217354581.19864.1265964501@webmail.messagingengine.com)>
 <[20080802141609.227970@gmx.net](mailto:20080802141609.227970@gmx.net)>

Hello again,

just notifying you that I am on a long trip at the moment, and I can
only deal with the converter at the end of the month.

About Back to Baghdad, I have also found it during my research, but it
only contains sound samples in this format, and no music at all.

PG
----------
----------

misc:
string which could be found in "PP.exe" (Psycho Pinball):

```
Protected Mode PC Music/FX System (c) Karl Morton 1994
```
## Post #16
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-02-14T09:37:00+00:00
- Post Title: Re: tracker music

Excellent background info!
