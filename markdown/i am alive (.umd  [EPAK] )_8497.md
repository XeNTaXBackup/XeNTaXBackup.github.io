## Post #1
- Username: nickx
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 25, 2011 7:08 am
- Post datetime: 2012-03-07T14:40:56+00:00
- Post Title: i am alive (.umd  [EPAK] )

this game is very strange its unreal engine but is stuctured compleatly different compared to a normal UE3 game

if someone would kindly write a bms script or a unpacker/repacker for this .umd/.ass [EPAK] (they both the same type of file just different extension by the look of it) i would be very thankfull

[http://www.mediafire.com/?mjc3gwi84xzzb4r](http://www.mediafire.com/?mjc3gwi84xzzb4r)

i belive the file im looking for will be in here if not i may be back requesting for a different file type to have scripts written for.

many thanks
## Post #2
- Username: nickx
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 25, 2011 7:08 am
- Post datetime: 2012-03-08T15:07:25+00:00
- Post Title: i am alive (.umd  [EPAK] )

bump
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-03-08T15:28:30+00:00
- Post Title: i am alive (.umd  [EPAK] )

I'm interested too. I tried to make a quickbms script but i'm not good at it.

I assume EPCK means Encrypted Pack

Anyway:

Endian: Big

0x8 4 bytes; Represents size of uncompressed/encrypted data?
0xC 4 bytes; Represents header size 

That's all i know really.
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-08T15:29:38+00:00
- Post Title: i am alive (.umd  [EPAK] )

Just Zlibed. Use offzip 

```
; Automatically generated by Martin's awesome oasis exporter 
; Edit at your own risks ( David will molest you if you do~ ) 


[Barks]
AI_ELEMV2_VIC_SEE_FAR_01_01ELEMV2_DRY=Oh no!
AI_LOWFL_VIC_SEE_FAR_01_01LOWFL_DRY=Good morning.
AI_STMCV1_VIC_FAREWELL_01_01STMCV1_DRY=See you later.
AI_DISPM_VIC_INFO_01_01DISPM_DRY=<run d="8"/>The biggest emergency shelter was set up inside the mall. It was abandoned pretty quick. <br/>There's probably other shelters around that still have people.<run d="6"/>You'd have to leave the city to find them. But you'd never catch me wandering out that far.
AI_TOMWV2_VIC_SEE_FAR_01_01TOMWV2_DRY=You again?
AI_TOMAV2_VIC_SEE_FAR_01_01TOMAV2_DRY=He's back. That killer came back. Nooo…
AI_GIRL20_VIC_LOOP_01_01GIRL20_DRY=What's wrong?
AI_TOMAV3_VIC_SEE_FAR_01_01TOMAV3_DRY=He's back!
AI_GMMT_ITM_CMD_STBACK_01_01GMMT_DRY=All right.
AI_SCARM_VIC_SEE_FAR_01_01SCARM_DRY=Where did all the bullets come from? I'm not part of this.
AI_HENR2_VIC_SEE_FAR_01_01HENR2_DRY=Who knows what Linda's going through right now. Hurry Up.
AI_HENR1B_VIC_SEE_FAR_01_01HENR1B_DRY=That transmitter is our only hope to communicate over long distances. We've heard several messages, but have never been able to respond.
AI_LINV3_VIC_SEE_FAR_01_01LINV3_DRY=The boat will come when they see the signal, so light those fireworks and get back here as fast as you can.
AI_HENR3_VIC_SEE_FAR_01_01HENR3_DRY=<run d="8"/>We can't miss this chance, help me put the girls on this boat, then I swear I'll explain you how to find the hidden survivor camps in Haventon.<run d="8"/>These camps are really hidden, they're trying to stay under the radar with all these new gangs coming in.
AI_HENR1A_VIC_SEE_FAR_01_01HENR1A_DRY=There's a bow on the table. Take it. It's yours. I used to kill time shooting at those targets. Figure practice never hurts.

```
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-03-08T15:47:22+00:00
- Post Title: i am alive (.umd  [EPAK] )

what about pack back ?
## Post #6
- Username: nickx
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 25, 2011 7:08 am
- Post datetime: 2012-03-08T16:02:08+00:00
- Post Title: i am alive (.umd  [EPAK] )

> Reply from michalss
>
> what about pack back ?
yeah we need to be able to repack or is useless
## Post #7
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-03-08T16:45:15+00:00
- Post Title: i am alive (.umd  [EPAK] )

> Reply from Ekey
>
> Just Zlibed. Use offzip 
Code: Select all; Barks - English
; Automatically generated by Martin's awesome oasis exporter 
; Edit at your own risks ( David will molest you if you do~ ) 


[Barks]
AI_ELEMV2_VIC_SEE_FAR_01_01ELEMV2_DRY=Oh no!
AI_LOWFL_VIC_SEE_FAR_01_01LOWFL_DRY=Good morning.
AI_STMCV1_VIC_FAREWELL_01_01STMCV1_DRY=See you later.
AI_DISPM_VIC_INFO_01_01DISPM_DRY=<run d="8"/>The biggest emergency shelter was set up inside the mall. It was abandoned pretty quick. <br/>There's probably other shelters around that still have people.<run d="6"/>You'd have to leave the city to find them. But you'd never catch me wandering out that far.
AI_TOMWV2_VIC_SEE_FAR_01_01TOMWV2_DRY=You again?
AI_TOMAV2_VIC_SEE_FAR_01_01TOMAV2_DRY=He's back. That killer came back. Nooo…
AI_GIRL20_VIC_LOOP_01_01GIRL20_DRY=What's wrong?
AI_TOMAV3_VIC_SEE_FAR_01_01TOMAV3_DRY=He's back!
AI_GMMT_ITM_CMD_STBACK_01_01GMMT_DRY=All right.
AI_SCARM_VIC_SEE_FAR_01_01SCARM_DRY=Where did all the bullets come from? I'm not part of this.
AI_HENR2_VIC_SEE_FAR_01_01HENR2_DRY=Who knows what Linda's going through right now. Hurry Up.
AI_HENR1B_VIC_SEE_FAR_01_01HENR1B_DRY=That transmitter is our only hope to communicate over long distances. We've heard several messages, but have never been able to respond.
AI_LINV3_VIC_SEE_FAR_01_01LINV3_DRY=The boat will come when they see the signal, so light those fireworks and get back here as fast as you can.
AI_HENR3_VIC_SEE_FAR_01_01HENR3_DRY=<run d="8"/>We can't miss this chance, help me put the girls on this boat, then I swear I'll explain you how to find the hidden survivor camps in Haventon.<run d="8"/>These camps are really hidden, they're trying to stay under the radar with all these new gangs coming in.
AI_HENR1A_VIC_SEE_FAR_01_01HENR1A_DRY=There's a bow on the table. Take it. It's yours. I used to kill time shooting at those targets. Figure practice never hurts.

pls post repacker for 0000f997.dat file? It can be pack back.
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-03-08T16:47:04+00:00
- Post Title: i am alive (.umd  [EPAK] )

How do i unpack it?
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-03-08T17:51:47+00:00
- Post Title: i am alive (.umd  [EPAK] )

OK i done my researech 

Fonts are in file call UI.umd. Can anyone please have a look? I think bms script would do it with reimport support  In that file are normal DDS textures...

```
http://dl.dropbox.com/u/38234344/UI.umd
```
 

Texts are in umd file as well and can be repacked with offzip pakzip.
how ever ther is 1 file which we need to make a repacker for..
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-03-09T07:13:45+00:00
- Post Title: i am alive (.umd  [EPAK] )

anyone?
## Post #11
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-03-09T10:10:06+00:00
- Post Title: i am alive (.umd  [EPAK] )

How do i unpack them
## Post #12
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-03-18T19:47:45+00:00
- Post Title: i am alive (.umd  [EPAK] )

please anyone can help us out ?
## Post #13
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-03-25T08:32:10+00:00
- Post Title: i am alive (.umd  [EPAK] )

Here are all texts uncomressed also added header separate. It is unicode. Not sure if text have to be same lenght as original, but i guess not . There is not editor yet but might someone will do repacker, it should not be that hard from this files i'm posting  It would be great if anyone could make it. Game is running fine with uncomress texts as well.

```
http://dl.dropbox.com/u/38234344/Imalive_Uncompress_Text%2BFonts.rar
```
## Post #14
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2012-07-20T22:33:20+00:00
- Post Title: i am alive (.umd  [EPAK] )

> Reply from Ekey
>
> Just Zlibed. Use offzip 
Code: Select all; Barks - English
; Automatically generated by Martin's awesome oasis exporter 
; Edit at your own risks ( David will molest you if you do~ ) 


[Barks]
AI_ELEMV2_VIC_SEE_FAR_01_01ELEMV2_DRY=Oh no!
AI_LOWFL_VIC_SEE_FAR_01_01LOWFL_DRY=Good morning.
AI_STMCV1_VIC_FAREWELL_01_01STMCV1_DRY=See you later.
AI_DISPM_VIC_INFO_01_01DISPM_DRY=<run d="8"/>The biggest emergency shelter was set up inside the mall. It was abandoned pretty quick. <br/>There's probably other shelters around that still have people.<run d="6"/>You'd have to leave the city to find them. But you'd never catch me wandering out that far.
AI_TOMWV2_VIC_SEE_FAR_01_01TOMWV2_DRY=You again?
AI_TOMAV2_VIC_SEE_FAR_01_01TOMAV2_DRY=He's back. That killer came back. Nooo…
AI_GIRL20_VIC_LOOP_01_01GIRL20_DRY=What's wrong?
AI_TOMAV3_VIC_SEE_FAR_01_01TOMAV3_DRY=He's back!
AI_GMMT_ITM_CMD_STBACK_01_01GMMT_DRY=All right.
AI_SCARM_VIC_SEE_FAR_01_01SCARM_DRY=Where did all the bullets come from? I'm not part of this.
AI_HENR2_VIC_SEE_FAR_01_01HENR2_DRY=Who knows what Linda's going through right now. Hurry Up.
AI_HENR1B_VIC_SEE_FAR_01_01HENR1B_DRY=That transmitter is our only hope to communicate over long distances. We've heard several messages, but have never been able to respond.
AI_LINV3_VIC_SEE_FAR_01_01LINV3_DRY=The boat will come when they see the signal, so light those fireworks and get back here as fast as you can.
AI_HENR3_VIC_SEE_FAR_01_01HENR3_DRY=<run d="8"/>We can't miss this chance, help me put the girls on this boat, then I swear I'll explain you how to find the hidden survivor camps in Haventon.<run d="8"/>These camps are really hidden, they're trying to stay under the radar with all these new gangs coming in.
AI_HENR1A_VIC_SEE_FAR_01_01HENR1A_DRY=There's a bow on the table. Take it. It's yours. I used to kill time shooting at those targets. Figure practice never hurts.

Well the offset would be interesting 
I don't get anything with offzip
## Post #15
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2012-09-03T21:16:50+00:00
- Post Title: i am alive (.umd  [EPAK] )

Hello!
Is there anybody who can help me, how can i run the game with extracted texts? What file name needed for texts?
How can i extract the fonts? Offzip only gives me some neo and dat files if i extract ui.umd.
## Post #16
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-04T08:31:41+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

repost some file, links are all dead
## Post #17
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2012-09-04T08:40:15+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

I sent a pm.
## Post #18
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-04T09:14:07+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

UI.umd seem easy to unpack...as soon as I can I'll try and write some stuff. Can you provide some other examples please?
## Post #19
- Username: mono24
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-09-04T11:57:59+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

Texts in 33 files (UTF-16)
Fonts - 3 DDS-textures.
[](http://savepic.net/3365144.jpg)
## Post #20
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2012-09-04T13:03:17+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

And can you help me, how can i run the game, with exported texts?
And how to extract and repack the fonts?
## Post #21
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2012-09-04T14:18:52+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

> Reply from nickx
>
> this game is very strange its unreal engine but is stuctured compleatly different compared to a normal UE3 game

if someone would kindly write a bms script or a unpacker/repacker for this .umd/.ass [EPAK] (they both the same type of file just different extension by the look of it) i would be very thankfull

http://www.mediafire.com/?mjc3gwi84xzzb4r

i belive the file im looking for will be in here if not i may be back requesting for a different file type to have scripts written for.

many thanks

Little bit late but actually this is a variation of Unreal Engine 2 or 2.5 which seems to be called LEAD so it's not UE3, just a little fun fact although it matters little. 
[http://en.wikipedia.org/wiki/I_Am_Alive](http://en.wikipedia.org/wiki/I_Am_Alive)
[http://www.gamasutra.com/view/news/2684 ... EYNt4ad9pw](http://www.gamasutra.com/view/news/26843/Guillemot_I_Am_Alive_Rebooted_Delayed.php#.UEYNt4ad9pw)
## Post #22
- Username: oveja
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Feb 24, 2011 4:35 am
- Post datetime: 2012-09-05T12:35:11+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

> Reply from Haoose
>
> Texts in 33 files (UTF-16)
Fonts - 3 DDS-textures.

how can unpack and repack?
## Post #23
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-05T13:24:23+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

be patient, I'm coding
## Post #24
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2012-09-05T13:47:30+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

> Reply from Vash
>
> be patient, I'm coding

Are you coding .bms script ?
## Post #25
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-05T13:49:31+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

No, a tool written in C
## Post #26
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2012-09-05T14:06:07+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

> Reply from Vash
>
> No, a tool written in C

What time finishes ?
## Post #27
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-05T14:08:46+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

when it's finished...don't rush it. I'm at work now
## Post #28
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2012-09-05T14:10:09+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

> Reply from Vash
>
> when it's finished...don't rush it. I'm at work now

ok. is tool can pack/repack ?
## Post #29
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-05T14:12:16+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

I'm just unpacking atm, I have a suspect that I might be able to make it read the files from the outside. Need some testing
## Post #30
- Username: mono24
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-09-05T15:31:28+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

The game can read the extracted files.
Fonts in the file UI.umd and should not be a problem to extract, repaint and reinsert.
## Post #31
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-05T15:47:53+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

THe only problem I'm having atm are the header of the EPAK files, the first file is (compressed or not) the list of the zlib chunks with, I guess, the dimensions of the compressed chunks.... but I can't decode that line    I think I'll have to go with asm on that
## Post #32
- Username: JonhOliver
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Mar 12, 2011 12:10 am
- Post datetime: 2012-09-05T23:59:17+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

How to extract the files? Can not understand...
## Post #33
- Username: oveja
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-09-06T06:18:53+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

1. Rename or Delete file src/system/loc_int.umd
2. Download: [http://www.mediafire.com/?r9p5ooc0ben238o](http://www.mediafire.com/?r9p5ooc0ben238o) (English texts - 33 files)
3. Extract to Data/Localization
4. Play game
## Post #34
- Username: oveja
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Feb 24, 2011 4:35 am
- Post datetime: 2012-09-06T08:26:15+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

> Reply from Haoose
>
> 1. Rename or Delete file src/system/loc_int.umd
2. Download: http://www.mediafire.com/?r9p5ooc0ben238o (English texts - 33 files)
3. Extract to Data/Localization
4. Play game

thank you.
so, how can change the font?
## Post #35
- Username: JonhOliver
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Mar 12, 2011 12:10 am
- Post datetime: 2012-09-06T15:19:20+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

It worked perfectly. You could also do this with Spanish? Or explain how to do...
## Post #36
- Username: JonhOliver
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-09-06T15:29:48+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

JonhOliver
Spanish (*.esp) - [http://www.mediafire.com/?j8y6o029mw9a5pl](http://www.mediafire.com/?j8y6o029mw9a5pl)
German (*.deu) - [http://www.mediafire.com/?6tu2d2665ea26k8](http://www.mediafire.com/?6tu2d2665ea26k8)
French (*.fra) - [http://www.mediafire.com/?hwlqt7k68mrg69f](http://www.mediafire.com/?hwlqt7k68mrg69f)
Italian (*.ita) - [http://www.mediafire.com/?rsnpo4bmq7q1jpt](http://www.mediafire.com/?rsnpo4bmq7q1jpt)
Then one text file. Divide itself to 33 files.
File names:

```
Localization\Barks.esp
Localization\Controls.esp
Localization\Credits.esp
Localization\Episodes.esp
Localization\Equipments.esp
Localization\HUD.esp
Localization\Loadings.esp
Localization\Menus.esp
Localization\System.esp
Localization\SystemValidation.esp
Localization\Tutorials.esp
Localization\Maps\_Alive_Single\M01_Bridge.esp
Localization\Maps\_Alive_Single\M02_Mall.esp
Localization\Maps\_Alive_Single\M03_Skyscraper.esp
Localization\Maps\_Alive_Single\M04_Subway.esp
Localization\Maps\_Alive_Single\M05_WreckedBoat.esp
Localization\Maps\_Alive_Single\M06_Hotel.esp
Localization\Maps\_Alive_Single\M07_Highrise.esp
Localization\Maps\_Alive_Single\M08_PierPark.esp
Localization\Maps\_Alive_Single\S01_ResidentialStreet.esp
Localization\Maps\_Alive_Single\S02_DownTownStreets.esp
Localization\Maps\_Alive_Single\S03_HenrysPlace.esp
Localization\Minimaps\_Alive_Single\City.esp
Localization\Minimaps\_Alive_Single\Hotel.esp
Localization\Minimaps\_Alive_Single\Mall.esp
Localization\Minimaps\_Alive_Single\PierPark.esp
Localization\Minimaps\_Alive_Single\WreckedBoat.esp
Localization\Test1\Test2\Test3.esp
Localization\Trailer\Encounters.esp
Localization\Trailer\Lines.esp
Localization\Trailer\Survival.esp
Localization\Trailer\The_Only_One.esp
Localization\Trailer\World.esp
```

Example: [](http://savepic.net/3382500.jpg)
## Post #37
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-06T15:34:56+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

In the meantime I cracked the fuckin' table encryption...almost done, just unpacking is missing
## Post #38
- Username: JonhOliver
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Mar 12, 2011 12:10 am
- Post datetime: 2012-09-06T15:43:06+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

Thank you again.
## Post #39
- Username: GARID
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-09-06T16:28:24+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

Fonts and Injector:
[http://www.mediafire.com/?a6gyvcmcohdpqrc](http://www.mediafire.com/?a6gyvcmcohdpqrc)
FIXED!
## Post #40
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-06T17:04:21+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

For fuck sake...this game uses 2 different kinds of archiviation  

[edit]
In the meantime, here the first version: [http://www.mediafire.com/download.php?jddv71t8h4mdraw](http://www.mediafire.com/download.php?jddv71t8h4mdraw)

syntax: iaa_unpacker file.umd

it decompresses and extracts half of the umds in the game, the other half uses a completely different kind of archiviation, I'm still looking into it. If it detects the other fileformat it will warn you so you can even make a for cycle in a batch
## Post #41
- Username: mono24
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-09-06T18:47:20+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

Vash, for loc-*.umd use OffZip + HexEditor + Hands =)
## Post #42
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-09-06T18:51:40+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

> Reply from Haoose
>
> Vash, for loc-*.umd use OffZip + HexEditor + Hands =)
Yeah.
## Post #43
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-06T18:56:21+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

And why should I do that since my tool can handle those archives? Plus, I'm not interested in this game, I was just curious about tha format. The second archive type files are just maps assets and other useless stuff (useless to a translation)
## Post #44
- Username: hunpatrik
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-09-07T17:36:39+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

Fonts and Injector (Fixed! and add Extractor)
[http://games-gen.com/soft/IamAlive_FontsInjector.rar](http://games-gen.com/soft/IamAlive_FontsInjector.rar)
## Post #45
- Username: mono24
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-09-07T18:01:23+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

List of Textures
[http://pastebin.com/8RZw1XQx](http://pastebin.com/8RZw1XQx)
## Post #46
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2012-09-08T17:03:20+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

Thank you Haoose!
My last problem: I use photoshop 6 and nvidia's dds plugin. 
If i load a font file then save as with dds dx5 format, the filesize gets bigger (for example two_font +21kb). How should i save it for the same file size?
## Post #47
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-09-08T17:11:29+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

Turn off mipmap generating
## Post #48
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2012-09-08T17:43:11+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

Thanks!!
## Post #49
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2012-09-09T08:44:20+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

Hunpatrik, edit fonts in GIMP and save file as original with DXT5 compresion. Works well.

And Haose, can you make a little unpacker/packer for textures? THX for your hard works.
## Post #50
- Username: mono24
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-09-09T12:52:29+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

GRiNDERKILLER, Use 3D Ripper DX for "unpack" textures )
## Post #51
- Username: maggot666x
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Dec 13, 2010 3:51 am
- Post datetime: 2012-09-10T18:04:46+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

ps3 version dosn't work with unpack files. Somebody know how can pack loc-int.umd ?
Change size of file in header, and replacement zlib dosn't work
## Post #52
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2012-09-14T06:57:54+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

No Unpacker for other .umd files yet?
Vash's tool can decompress them but no extraction.
## Post #53
- Username: GARID
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Apr 06, 2011 8:29 pm
- Post datetime: 2012-09-14T10:55:35+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

> Reply from Haoose
>
> Fonts and Injector (Fixed! and add Extractor)
http://www.mediafire.com/?a6gyvcmcohdpqrc

Awesome!
## Post #54
- Username: ZezoConquer2023
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 13, 2023 5:08 am
- Post datetime: 2023-06-12T21:37:04+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

> Reply from Haoose ↑Thu Sep 06, 2012 2:18 pm at Thu Sep 06, 2012 2:18 pm
>
> 
1. Rename or Delete file src/system/loc_int.umd
2. Download: http://www.mediafire.com/?r9p5ooc0ben238o (English texts - 33 files)
3. Extract to Data/Localization
4. Play game

Please Please, upload the files again
## Post #55
- Username: ZezoConquer2023
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 13, 2023 5:08 am
- Post datetime: 2023-06-12T21:38:54+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

> Reply from Haoose ↑Thu Sep 06, 2012 11:29 pm at Thu Sep 06, 2012 11:29 pm
>
> 
JonhOliver
Spanish (*.esp) - http://www.mediafire.com/?j8y6o029mw9a5pl
German (*.deu) - http://www.mediafire.com/?6tu2d2665ea26k8
French (*.fra) - http://www.mediafire.com/?hwlqt7k68mrg69f
Italian (*.ita) - http://www.mediafire.com/?rsnpo4bmq7q1jpt
Then one text file. Divide itself to 33 files.
File names:
Code: Select allLocalization\Achievements.esp
Localization\Barks.esp
Localization\Controls.esp
Localization\Credits.esp
Localization\Episodes.esp
Localization\Equipments.esp
Localization\HUD.esp
Localization\Loadings.esp
Localization\Menus.esp
Localization\System.esp
Localization\SystemValidation.esp
Localization\Tutorials.esp
Localization\Maps\_Alive_Single\M01_Bridge.esp
Localization\Maps\_Alive_Single\M02_Mall.esp
Localization\Maps\_Alive_Single\M03_Skyscraper.esp
Localization\Maps\_Alive_Single\M04_Subway.esp
Localization\Maps\_Alive_Single\M05_WreckedBoat.esp
Localization\Maps\_Alive_Single\M06_Hotel.esp
Localization\Maps\_Alive_Single\M07_Highrise.esp
Localization\Maps\_Alive_Single\M08_PierPark.esp
Localization\Maps\_Alive_Single\S01_ResidentialStreet.esp
Localization\Maps\_Alive_Single\S02_DownTownStreets.esp
Localization\Maps\_Alive_Single\S03_HenrysPlace.esp
Localization\Minimaps\_Alive_Single\City.esp
Localization\Minimaps\_Alive_Single\Hotel.esp
Localization\Minimaps\_Alive_Single\Mall.esp
Localization\Minimaps\_Alive_Single\PierPark.esp
Localization\Minimaps\_Alive_Single\WreckedBoat.esp
Localization\Test1\Test2\Test3.esp
Localization\Trailer\Encounters.esp
Localization\Trailer\Lines.esp
Localization\Trailer\Survival.esp
Localization\Trailer\The_Only_One.esp
Localization\Trailer\World.esp
Example:

And i Want change font to Arabic Please man Help me
## Post #56
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2023-06-14T14:24:18+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

* I Am Alive original (English) localization files
* I Am Alive - Fonts Injector
## Post #57
- Username: ZezoConquer2023
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 13, 2023 5:08 am
- Post datetime: 2023-06-19T00:39:46+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

> Reply from terminator ↑Wed Jun 14, 2023 10:24 pm at Wed Jun 14, 2023 10:24 pm
>
> 
* I Am Alive original (English) localization files
* I Am Alive - Fonts Injector

Thx Man
i Exctract all file to _ Data/Localization
but the Font How can I install and activate the Arabic font in the game so that the game can accept the Arabic language
and the  (FontsInjector.exe) How do I use it, because I use it and I choose
Inject one_font.dds & Inject two_font.dds & Inject three_font.dds 
Nothing happened and the Arabic language did not appear
## Post #58
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2023-06-19T08:00:27+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

You have to EDIT the DDS files with your native language's fonts - GIMP, Photoshop -, then you can inject back them into the gam (or place them into the game's folder structure, 'cause the game can read them from there too).
So, you have to work about it.
## Post #59
- Username: ZezoConquer2023
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 13, 2023 5:08 am
- Post datetime: 2023-06-21T15:56:21+00:00
- Post Title: Re: i am alive (.umd  [EPAK] )

> Reply from terminator ↑Mon Jun 19, 2023 4:00 pm at Mon Jun 19, 2023 4:00 pm
>
> 
You have to EDIT the DDS files with your native language's fonts - GIMP, Photoshop -, then you can inject back them into the gam (or place them into the game's folder structure, 'cause the game can read them from there too).
So, you have to work about it.

Can you do this for me, because I have no one with me and no one to help me
