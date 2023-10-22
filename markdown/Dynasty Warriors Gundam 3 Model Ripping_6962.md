## Post #1
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-07-12T22:16:31+00:00
- Post Title: Dynasty Warriors Gundam 3 Model Ripping

I know we've made 2 topics about DWG2 and potentially DWG3 but I wanted to start fresh with a new topic specifically for DWG3 and provide some data to get the ball rolling:

360 version, english, list of files on the iso:


AvatarAssetPack - 13,476 KB
default.xex - 6,828 KB
nxeart - 1,568 KB
Data (FOLDER):
 -LINKDATA.ANS - 1,218,730 KB
 -LINKDATA.BNS - 900,302 KB
 -LINKDATA.CNS - 1,516,242 KB
Res/Movie (FOLDER):
 -wmv movies of the cutscenes

Ok, Looks similar to the older games and still has the Linkdata .ans, bns and cns that we're used to with Koei games.
I recall chroxx saying he creates the .tbl files for extracting out of a file called default.xbe. Here we have defaul.xex, likely the same idea here.

Don't know what AvatarAssetPack is.

nxeart must be an image for the background in the nxe dashboard, makes sense.

...Ok, that's where my usefuless ends. I've opened all these in HxD and well... obviously, there really wasn't much point because I don't know what the hell any of it means.

I can send sample data to anyone who requests it, please do... I'm begging, on hands and knees, you can't see it, but trust me, I am, haha.

This is the first Gundam game to come out in the U.S. with decent quality models of more than 7 or 8 mobile suits. The usefulness of such a collection of models for game mods, art, movies, etc. is killing me, I must have them, at all costs! hahaha, ok, end rant.
## Post #2
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-07-17T02:45:13+00:00
- Post Title: Dynasty Warriors Gundam 3 Model Ripping

Yeah I really agree with this, it's really worth ripping for 3ds max, since the models here are really awesome because of the cell shading graphics..
## Post #3
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-06T04:04:47+00:00
- Post Title: Dynasty Warriors Gundam 3 Model Ripping

This just isn't going to happen, is it... I gotta get these models!
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-06T08:34:53+00:00
- Post Title: Dynasty Warriors Gundam 3 Model Ripping

chrox said all dynasty warrior games are the same. did you try [viewtopic.php?f=16&t=6252&hilit=dynasty+warriors+7](http://forum.xentax.com/viewtopic.php?f=16&t=6252&hilit=dynasty+warriors+7)? download the 7z file, run the G1M_0034.bms and G1TG0060.bms on those files and see what happens. Then run the dds.bms and then finally the dw7-1.ms.
## Post #5
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2011-12-06T10:47:15+00:00
- Post Title: Dynasty Warriors Gundam 3 Model Ripping

> Reply from howfie
>
> chrox said all dynasty warrior games are the same. did you try viewtopic.php?f=16&t=6252&hilit=dynasty+warriors+7? download the 7z file, run the G1M_0034.bms and G1TG0060.bms on those files and see what happens. Then run the dds.bms and then finally the dw7-1.ms.
Although similar in appearance,they are a little different from title to title.
## Post #6
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-06T16:22:50+00:00
- Post Title: Dynasty Warriors Gundam 3 Model Ripping

Yep, I tried the dynasty warriors 7 scripts. those instructions called for offzip to be run on the "linkdata.bin" file, which gundam uses the "linkdata.ans, .bns and .cns, not just one .bin. still, i tried offzipping linkdata.cns under different parameters with no results. then i tried running the g1m and g1t scripts on the cns just to see what happens, no good.

I also tried Fatduck's script located here: [http://gameresearch.5d6d.com/archiver/t ... age-1.html](http://gameresearch.5d6d.com/archiver/tid-209-page-1.html) at post "fatduck 发表于 2010-4-19 03:14" on gundam musou 2 and that didn't work, seems it's missing something.

that post has several files and scripts that were uploaded to temnporary servers and are gone now, one of which is the .tbl files for gundam musou 2.

I also tried to cross reference that bms script with Chrrox's fist of the north star bms script and see where they were different, but the fist of the north star script uses .tbl files he created from the default .xbe (i think it was .xbe) file located on the root of the iso. I have the default.xex file which is similar to the .xbe file but without knowing how he derived the file locations i still can't replicate it for this game.

I also tried learning how to research game file formats and understand hex to do it myself, but it seems the .cns files aren't as straightforward as others and it'll take me a long time to understand it.
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-06T20:47:44+00:00
- Post Title: Dynasty Warriors Gundam 3 Model Ripping

are there any models from gundam 00 in it? if so, i can take a look into it in a few days. chrox's script looks like the file format is easy; it just searches for certain chunk names and loads the data directly. i should be able to write a program to mass convert the models into obj.

edit: speaking about gundam...

i went to an anime expo a few years back and the robotech and gundam panels were back to back ha ha ha. what a difference. in the robotech panel everone was in their 40's and falling asleep. no clapping, no shouting...that dickhead tommy yune who has single-handedly screwed the robotech franchise up the ass just showed a single video that pretty much made everyone fall asleep and then everyone left.

then comes in the people for the gundam panel... people were shouting, laughing, waving all their fucking model boxes in the air. people were dressed in cardboard gundam outfits ha ha ha... talk about a difference. it was like a fucking party.
## Post #8
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-06T21:00:53+00:00
- Post Title: Dynasty Warriors Gundam 3 Model Ripping

Yes, Gundam Musou 3 / Gundam Dynasty Warriors 3 has the Gundam 00 Raiser and Ribbon's Gundam, and the Susanowo, Seravee, Cherudim and Arios were all released as DLC. I have legally purchased the DLC on Xbox Live and If you PM me, we can discuss how to get you researching it.

Edit: Here's a full mobile suit list from the game just so people know how extensive a resource for gundam models this game really is.

Mobile Suit Gundam
    RX-78-2 Gundam
    MS-06S Zaku II Commander Type
    MS-06F Zaku II
    MS-14S Gelgoog Commander Type
    MS-14 Gelgoog
    MSN-02 Zeong
    YMS-15 Gyan
    RX-77-2 Guncannon
    MS-07B Gouf
    MS-09 Dom/MS-09R Rick-Dom
    RB-79 Ball
    MSM-07 Z’Gok
    MSM-07S Z’Gok Commander type
    RGM-79 GM
    MSM-04 Acguy

Mobile Suit Variations
    MS-06V Zaku Tank
    MS-07H Gouf Flight Type

Mobile Suit Gundam 0080: War in the Pocket
    RGM-79G GM Command

Mobile Suit Gundam 0083: Stardust Memory
    RX-78GP01-Fb Gundam Full Vernian Zephyranthes
    RX-78GP02A Gundam Physalis

Mobile Suit Zeta Gundam
    MSZ-006 Zeta Gundam
    MSN-00100 Hyaku Shiki
    RX-178 Gundam Mark II (AEUG Colors)
    RX-178 Gundam Mark II (Titans Colors)
    RX-160 Byalant
    PMX-003 The O
    AMX-004 Qubeley
    RX-139 Hambrabi
    PMX-001 Palace Athene
    NRX-055 Baund Doc
    RMS-099 Rick Dias
    RMS-179/RGM-79R GM II
    MSA-03 Nemo
    RMS-106 Hi-Zack
    RMS-108 Marasai
    RMS-154 Barzam
    AMX-103 Gaza C

Mobile Suit Gundam ZZ
    MSZ-010 ZZ Gundam
    AMX-004-2 Qubeley Mark II (Black)
    AMX-004-3 Qubeley Mark II (Red)
    AMX-107 Bawoo
    AMX-004G Mass Production Qubeley
    AMX-106 Gaza D
    Mobile Suit Gundam: Char’s Counterattack
    RX-93 Nu Gundam
    MSN-04 Sazabi
    RGM-89 Jegan
    AMS-119 Geara Doga

Mobile Suit Gundam Unicorn
    Gundam Unicorn (Unicorn Mode)
    Gundam Unicorn (Destroy Mode)
    Sinanju
    NZ-666 Kshatriya

Mobile Suit Gundam F91
    F91 Gundam Formula 91
    Mobile Suit Victory Gundam
    LM314V21 Victory 2 Gundam
    ZMT-S33S Gottrlatan
    ZM-S24G Gedlav

Mobile Fighter G Gundam
    GF13-017NJII God/Burning Gundam
    GF13-001NHII Master Gundam
    Death Army

Mobile Suit Gundam Wing
    XXXG-00W0 Wing Gundam Zero
    OZ-13MS Gundam Epyon
    XXXG-01D2 Gundam Deathscythe Hell
    XXXG-01H2 Gundam Heavyarms Kai
    OZ-00MS2 Tallgeese II

After War Gundam X
    GX-9901-DX Gundam Double X

Turn A Gundam
    SYSTEM ∀-99 Turn A Gundam
    CONCEPT-X 6-1-2 Turn X
    AMX-109 Kapool

Mobile Suit Gundam SEED
    ZGMF-1017 GINN

Mobile Suit Gundam SEED Destiny
    ZGMF-X42S Destiny Gundam
    ZGMF-X20A Strike Freedom Gundam
    ZGMF-X19A Infinite Justice Gundam

Mobile Suit Gundam 00
    GN-0000+GNR-010 00 Raiser
    CB-0000G/C Reborns Gundam
    GNX-Y901TW Susanowo
    GN-006 Cherudim Gundam
    GN-007 Arios Gundam
    GN-008 Seravee Gundam

SD Sengokuden
    Musha Gundam
    Musha Gundam MK. II
    Knight Gundam

Unpilotable Mobile Armors:
    Psyco Gundam
    Psyco Gundam MK. II
    Devil/Dark Gundam
    Big Zam
    Quin Mantha
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-06T21:06:36+00:00
- Post Title: Dynasty Warriors Gundam 3 Model Ripping

it's ok. i will rent it from gamefly. will take a couple days. i know how to rip xbox360 content already.
## Post #10
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-06T21:14:21+00:00
- Post Title: Dynasty Warriors Gundam 3 Model Ripping

Oh, I'm not worried about the game alone, I meant the DLC specifically.
## Post #11
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-06T21:15:34+00:00
- Post Title: Dynasty Warriors Gundam 3 Model Ripping

oh, i c, cool, thanks.
## Post #12
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-09T13:30:07+00:00
- Post Title: Dynasty Warriors Gundam 3 Model Ripping

Started working on this. There appears to be a couple more texture types than from DW7. I don't have the ps3 version of the game to test if the texture code is right as it appears the xbox360 textures are swizzled? Noncompressed type is fine though... Oh well, one way or another I'll figure it out .
## Post #13
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-09T20:10:52+00:00
- Post Title: Dynasty Warriors Gundam 3 Model Ripping

Ah, awesome, this is the first time I've seen ANYTHING from these file archives. Great work, I'm eternally grateful!

How difficult is the model format, have you run into it yet or are you nailing down the texture format first?
## Post #14
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-09T21:54:44+00:00
- Post Title: Dynasty Warriors Gundam 3 Model Ripping

if it goes as planned, should be no problem. chrrox's script for textures was pretty spot on, minus more texture types. going to have to give up on the textures for now (going to have to rent or trade in for the ps3 version now lol) unless someone posts a sample G1TG0060 section from the BNS file (first one in file would be nice, it has 90 or so small dxt5 textures in it, looks at offset 0x8000). looking into the models today. maxscript sucks. whoever invented it should be slapped and shot in the head like saddam hussein. i can see why chrrox is doing tutorials on noesis and python now.
## Post #15
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-09T22:09:20+00:00
- Post Title: Dynasty Warriors Gundam 3 Model Ripping

I should be able to get that to you later tonight or tomorrow. Could you describe the process to get the data sample you're looking for?
## Post #16
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-09T22:33:00+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

1. Sure, get HxD or some other hex editor and open up linkdata.bns.
2. File -> New to add a new file tab that you are going to paste the section into.
3. Scroll down to offset 0x8300 in linkdata.bns.



4. Select all data from offset 0x8300 to 0x92FF. It should be 4 KB of data (0x1000 in hex).



5. Pasted copied data into new file.
6. Save new file as texture.bin or something.
7. Upload somewhere.

In fact, all you have to do is if you have the PS3 version is to tell me if the data looks the same from my screencaps. If it is, then they either changed the texture format the data is purposely modified. If not, textures are swizzled and I will rent the PS3 version and will work on model format in meantime.
## Post #17
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-09T22:41:03+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Ah, no problem, I'll post back as soon as I can.
## Post #18
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-10T00:50:29+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Almost got models... . It's funny because chrrox's dw7-1.ms script, which doesn't work for me and doesn't work for you, is logically 100% correct even for this game. Based on his script, I have loaded the data into memory and it is, logically correct. It should work. Well, we'll find out once I get the data loaded into Maya. .
## Post #19
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-10T01:12:57+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Wow, that's pretty strange, haha. Anyway, here's the section you requested from the PS3 linkdata.bns:

Data Sample: texture.bin

[https://skydrive.live.com/?cid=E74D852E ... DF762F!108](https://skydrive.live.com/?cid=E74D852ED8DF762F&id=E74D852ED8DF762F!108)

It does appear to be slightly different.
## Post #20
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-10T01:32:51+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Thanks, I'll look at it after I finish up getting the models up.
## Post #21
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-11T12:20:28+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

almost there....
lol the CNS file has about 12,000 models in it... ha ha ha ha.
textures will have to be applied manually since filenames are not stored anywhere (unless I or someone else has a lot of time to figure this out).
## Post #22
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-12-11T12:51:27+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Wow that's awesome howfie, now we have a chance to get some decent gundam models and it's all because of you
## Post #23
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-11T12:55:48+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

actually, it's chrrox's code ported to C++ lol. so many models... most are architecture. many models are repeated in the file multiple times. i haven't even run into a gundam yet lol ha ha ha. どこどこどこどこどこどこどこどこどこどこどこどこどこどこどこどこどこどこ
## Post #24
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-12-11T13:48:00+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

So all the models are stored there?
## Post #25
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-11T14:20:54+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

the ans file contains music and sounds.
the bns stores the gundams (i think... i am still having trouble parsing this file)
the cns stores the architecture (finished - can extract all models)

still have to figure out why some models aren't coming out correctly... but, finally found the gundams he he he. also awaiting the ps3 version to come in the mail so i can get textures.
## Post #26
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-11T16:53:30+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

That is glorious, fantastic work howfie!

What model format are you using to import into lightwave? obj? Just curious if it's going to be possible to import into 3ds max as well.
## Post #27
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-11T22:11:56+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Obj and mtl.
## Post #28
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-11T23:59:08+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

You know that DLC sample... it really helped . Now I don't have to search for chunks as was done in the maxscript. I'll post an extractor as soon as I fix some incorrect vertex formats.
## Post #29
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-12T00:03:01+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Oh, glad to hear it!
## Post #30
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-12T01:08:57+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Just found this thread: [http://www.facepunch.com/threads/1124966](http://www.facepunch.com/threads/1124966)

Looks like a lot of other people are going to be very excited about this.
## Post #31
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-12T01:43:58+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

There are lots of wav files in the ANS file but I can't play them on my computer... does the Xbox360 use some special codec?
## Post #32
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-12T02:01:07+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Hmm no idea, probably. nothing's straightforward these days, haha. i have the ripped ost from the japanese release and it's 75 songs, and there's a ton of dialog. wav wouldn't be a very efficient format for all that anyway. I could see there only being 34 sound effects considering beam sabre effects, thruster effects, and certainly others are the same for every mobile suit.
## Post #33
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-12T21:35:50+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Got textures... environment spheres are weird... one triangle is always skewed.
PS3 version is same format as XBox360 but content is slightly different; will try to make sure it rips everything, and I mean everything he he he, including PNG files, from both.
Also, it's going to take just a little while longer since there are more model sections than just G1M_. KTFK sections also contain models too and I have to figure out this section myself .
## Post #34
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-12T22:00:02+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Hey, take your time. I'm just learning C++ and the source engine sdk right now, haha... oh man this is gonna take a while.
## Post #35
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-14T23:42:52+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Hey, just wanted to touch base with you, find out how the progress on the KTFK sections is going?
## Post #36
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-15T00:45:18+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

I'll work on it more tonight. Out of town at the moment gambling my little heart out he he he.
## Post #37
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-15T00:55:10+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

> Reply from howfie
>
> I'll work on it more tonight. Out of town at the moment gambling my little heart out he he he.

Ohh you lucky bastard, haha.
## Post #38
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-16T01:40:41+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

almost got the KTFK section figured out... it's funky ha ha ha almost... can't wait to see what it's hiding lol.
## Post #39
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-16T18:34:05+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

There wasn't jack shit in the KTFK sections... just some crap non-player hud geometry.

Almost there.... a few more things need to be done.
#1 Figure out how to remove LOD models from mesh.
#2 Figure out how to remove collision models from mesh.
#3 Figure out how to automatically texture.
## Post #40
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-16T18:41:42+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Ohhh wow, that is gorgeous... That sucks about the KTFK sections. I was wondering, are the models going to have bones/skin modifiers and/or animations?
## Post #41
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-16T18:53:05+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

There are no bone names anywhere to be found; no bone hierarchy that I could find either. I don't see an obvious weight map in the model data either. So probably not. But you never know what someone might find. I'll release what I have so far sometime later tonight after a little code cleanup so as to stop teasing you guys ha ha ha.
## Post #42
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-17T12:08:13+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Notes:
* Place EXE in same directory as LINKDATA.BNS.
* Run EXE.
* Got take a dump for 10 minutes or so.
* Come back and look in LINKDATA_BNS directory.
* Some folders contain OBJ models and DDS textures, while some only contain DDS textures.
* Happy texturing and deleting LODs and collision meshes.
* DO NOT USE THE XBOX360 LINKDATA.BNS! THEY USE SOME SCREWED UP TEXTURE FORMATS.

Architecture to come in version 0.2.

Let me know if it doesn't work.
OBJs load fine for me in 3DSMax and Lightwave. For some reason Maya is giving me a hard time today lol.
[ripper.7z](https://xentaxbackup.github.io/file/4906_ripper.7z)
## Post #43
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-12-17T14:12:24+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Thanks howfie, so it means we should use ps3 linkdata bns?
## Post #44
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-17T14:23:06+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

yes. you'll get a bunch of texture errors if you use the xbox360 version.
## Post #45
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-12-18T08:36:29+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Got the models from the XBOX360 version, but not the textures yet.
## Post #46
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-18T20:04:35+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

I got the models and textures from the ps3 version, a couple notes:

1.) the models are great, except most have an extra face in a random area protruding out. deleting the face easily fixes the problem.

2.) the textures for the mobile suits are fine but the textures and images for everything else appear to be garbage data. most are just repeating color tables or solid black. some look like health bars, text character sets, logo's etc. but their colors are off. red parts are blue, etc. could be by design, not sure if you meant to have them implemented or not.

fantastic work, the only thing that would make it more useful is ripping them with names, which as i understand, the names are in the default.xex file for 360, and probably the eboot.bin file on ps3.
## Post #47
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-18T22:49:38+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Corrupt textures? Which ones? Inwhat folder? Most I checked were fine. The ones with color channels mixed up is type 0. They are uncompressed but every dds color mask abgr, bgra, rgba, etc. I tried didn't look right. Do the 90 or so character images in 0001 folder look ok? I'll look at it when I get home.
## Post #48
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-18T23:44:24+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Ah, I see. When I apply the corrupt images in 3ds max or open them in photoshop they show up without issue, but in windows thumbnails everything but the mobile suit textures appear corrupted. of course this means they work but it also makes it a nightmare to sort through them... here's a screenshot of what I see in windows:
## Post #49
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-19T07:25:47+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Oh OK, so it's a problem with your thumbnail viewer then. Gundam ones don't use the alpha channel... the other ones do I believe. NVIDIA thumbnail viewer or that mysticthumbs? And yeah, there's 900 directories ha ha ha what a pain huh ?
## Post #50
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-19T18:48:13+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Ahh, yep, that's probably it. i have mystic thumbs and another one called sage thumbs. if i recall the nvidia dds plugin doesn't work on windows 7, and i only have the photoshop plugin installed.
## Post #51
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-12-22T01:58:57+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Oh by the way, why don't the models look cel-shaded  even though they are cel-shaded in the game?
## Post #52
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-22T02:14:11+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

cel shading is applied via a shader loaded by the running game engine. they aren't part of the actual art resources in a game like this.
## Post #53
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-22T02:18:00+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Anyone know what those red colored textures are for? I'll get the architecture up around Christmas when I also release ripper for sudeki as well.
## Post #54
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-22T02:29:50+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

haha, can you be a little more specific, which red colored ones, where are they located?
## Post #55
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-22T02:38:05+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

All of the gundam models contain at least one texture that is mostly red with some black lines. I was wondering if that texture was some kind of cell-shade map or something. I'm not at my dev computer at the moment, but it's usually the second or third texture in a gundam directory.

BTW, there is a problem with some of the models and I will try to fix it. The faces are divided into surfaces, but each surface can use more than one texture map. I wasn't able to find where they store this information, nor was it part of chrrox's script, so some of the gundam models have to be resurfaced for now.
## Post #56
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-22T03:25:25+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

AH, yes, those textures. I'd seen something similar in other games, usually it's a specular map or something similar, most likely in this case related to cel shading, or maybe reflective surface maps. the blurry fish eye lens pictures of different scenery such as the colony exterior or the desert are definitely environment reflection maps so it would make sense.

as for the models, that makes a lot of sense. I was trying to set up the model of the Gundam Mk II for use in the crysis 2 sdk and it wouldn't export because of hundreds of overlapping face and abandoned vertex errors. sounds like that might be the cause.
## Post #57
- Username: Damocles
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 06, 2012 12:17 pm
- Post datetime: 2012-01-06T04:35:28+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

I don't know if you guys have seen them, but a Chinese guy (Lotsbiss) posted a thread at CGmodels.cn containing
most of the gundam models in the game.

[](http://imageshack.us/photo/my-images/24/capturedsa.png/)
[](http://imageshack.us/photo/my-images/834/capturefhjf.png/)
[](http://imageshack.us/photo/my-images/171/capturesdoh.png/)
He has rips from A.C.E.R and a few others. I just happened across your thread while hunting for a few models from D.W.G.2.
## Post #58
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2012-01-09T02:01:38+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Can anyone tell me what viewer he used ^ there?
## Post #59
- Username: DOTAPRINCE
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-01-09T02:26:33+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

deep exploration
## Post #60
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2012-01-09T02:39:52+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Thanks sir chrrox.
## Post #61
- Username: Damocles
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 06, 2012 12:17 pm
- Post datetime: 2012-01-10T02:46:18+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

Can I use this on DWG2?
## Post #62
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-10T03:32:04+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

I don't have DWG2 yet, so I can't check. But when I do, I'll add support for it. As for this one I still need to rewrite the code a little bit and figure out a few more things. LOL at that one chinese web site... I see a bunch of models on that site that look like they were ripped from here. Seems like you have to pay to be a VIP there and to download stuff too. Sketchy web site for sure. In fact, after I posted my Neptunia MK2 rip on Aug. 31, on Sep. 2 that site posted a bunch of models from MK2. 41 pages of replies for that one too ha ha ha ha. So more than likely, anything you see from there, they got from here LOL! Not that I care lol. Would have been nice to see at least a "thanks to the guys at xentax" type of thing. .

[http://www.cgmodel.cn/thread-240591-1-4.html](http://www.cgmodel.cn/thread-240591-1-4.html)
## Post #63
- Username: Damocles
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 06, 2012 12:17 pm
- Post datetime: 2012-01-11T02:13:34+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

I tried using the ripper on DWG2. I got 1697 .bin files before it crashed. Can anything be extracted from those?
## Post #64
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-12T01:02:04+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

No, my batch ripper processes those bin files only after bin extraction has completed successfully. If you know a little C++ you can modify the Gundam code, which I posted in the Macross thread, to try and process those bin files that did extract. I'll look into fixing this one and the other Gundam games when I get some time. Did any of the Gundam games have any human 3D character models in them?
## Post #65
- Username: Damocles
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 06, 2012 12:17 pm
- Post datetime: 2012-01-24T00:41:34+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

> Reply from Damocles
>
> I tried using the ripper on DWG2. I got 1697 .bin files before it crashed. Can anything be extracted from those?

I think operation troy has human 3d characters.
## Post #66
- Username: alientech
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Apr 03, 2010 8:23 pm
- Post datetime: 2012-03-31T05:04:29+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

How can I get models from the game?
## Post #67
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2012-03-31T06:40:57+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

> Reply from alientech
>
> How can I get models from the game?

the thread already answered your question. try backreading man
## Post #68
- Username: ellegirl01
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 28, 2014 1:08 pm
- Post datetime: 2015-03-22T13:53:54+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

> Reply from howfie
>
> Notes:
* Place EXE in same directory as LINKDATA.BNS.
* Run EXE.
* Got take a dump for 10 minutes or so.
* Come back and look in LINKDATA_BNS directory.
* Some folders contain OBJ models and DDS textures, while some only contain DDS textures.
* Happy texturing and deleting LODs and collision meshes.
* DO NOT USE THE XBOX360 LINKDATA.BNS! THEY USE SOME SCREWED UP TEXTURE FORMATS.

Architecture to come in version 0.2.

Let me know if it doesn't work.
OBJs load fine for me in 3DSMax and Lightwave. For some reason Maya is giving me a hard time today lol.

What does it mean if the Ripper crashes with the error Invalid Header Signature or Could Not Open File, please?
## Post #69
- Username: bluearms
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Oct 13, 2010 4:48 am
- Post datetime: 2015-05-07T12:46:58+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

I made quickbms script for PS3 and xbox360.

At first copy quickbms.exe to the position of batchfile and
run
quickbms gundam3_x360.bms linkdata.[a|b|c]ns  for x360
quickbms gundam3_ps3.bms linkdata.[a|b|c|d] for ps3
then
run Runsplit*.bat to further split generated *.tmp files.
you may requires to run Runsplit*.bat multiple times to split all *.tmp files

linkdata*.* contains continuous chunks.
But each chunk can contain further embedded data which can be also a archive and so on.


 gundam3.rar
(4.88 KiB) Downloaded 100 times



there is a script for g1t format, But I think it need further refinement, so it is not included.

To learn more things, check scripts.

ps3 versions are checked with "gundam reborn" but not with "gundam 3"
## Post #70
- Username: luciferdm
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 20, 2015 10:08 am
- Post datetime: 2015-12-20T04:04:58+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

> Reply from bluearms
>
> I made quickbms script for PS3 and xbox360.

At first copy quickbms.exe to the position of batchfile and
run
quickbms gundam3_x360.bms linkdata.[a|b|c]ns  for x360
quickbms gundam3_ps3.bms linkdata.[a|b|c|d] for ps3
then
run Runsplit*.bat to further split generated *.tmp files.
you may requires to run Runsplit*.bat multiple times to split all *.tmp files

linkdata*.* contains continuous chunks.
But each chunk can contain further embedded data which can be also a archive and so on.
gundam3.rar

there is a script for g1t format, But I think it need further refinement, so it is not included.

To learn more things, check scripts.

ps3 versions are checked with "gundam reborn" but not with "gundam 3"

Hello, I use the script, but it not worked. I only get a error information: invalid operator P
## Post #71
- Username: Moonlight
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 31, 2018 4:04 am
- Post datetime: 2021-03-24T20:49:31+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

So the strange red and orange textures are used for shading. Each channel defines an atribute for the shader, how metallic it is, if its shiny or opaque, ambient oclusion, and maybe even emisive areas. For those of you that were curious.
Also, Howfie, you are a legend, thanks man.
## Post #72
- Username: mdtarmimi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 15, 2014 3:42 pm
- Post datetime: 2021-03-28T00:51:30+00:00
- Post Title: Re: Dynasty Warriors Gundam 3 Model Ripping

yes howfie is a true hero no such a person can make a perfect coding extract for the texture
