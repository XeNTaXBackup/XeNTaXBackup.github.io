## Post #1
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-01-19T14:04:28+00:00
- Post Title: Asking for Star Wars - Empire At War .meg support

Hello  

I humbly ask if someone among you talented people might be kind enough to look into the possibility of supporting the .meg format of the Star Wars Empire At War game.

The .meg format seems to be the main archive format for all major parts of the game (textures, models, sound etc) and the file attached contains two of the smaller sized .meg files I found in the demo (i.e. they are in their original full size).

The full demo is available for download at [FragZone](http://www.fz.se/filarkiv/download.php?file=spel/sw_empire_at_war/EmpireAtWarDemo.exe),   [FileFront](http://empireatwar.filefront.com/file/Empire_at_War_Demo;55229#Download), [3Dgamers](http://www.3dgamers.com/news/more/1096483786/), [FilePlanet](http://www.fileplanet.com/159774/150000/fileinfo/Star-Wars:-Empire-at-War-Demo) and [GameDaily](http://www.gamedaily.com/download/info/?packageid=0078700883) (beware - 742 Mb size).

Any help on this would be greatly appreciated.

Thank's in advance and thank's for a great program.

Cheers

N
[Cinematics_&_Maps_MEG.rar](https://xentaxbackup.github.io/file/584_Cinematics_&_Maps_MEG.rar)
## Post #2
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-01-19T14:13:49+00:00
- Post Title: Asking for Star Wars - Empire At War .meg support

Hi again

One more of the smallest .meg files from the demo (also in it's original full size).

Cheers

N
[Shaders_MEG.rar](https://xentaxbackup.github.io/file/585_Shaders_MEG.rar)
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-19T14:19:41+00:00
- Post Title: Asking for Star Wars - Empire At War .meg support

Thanks, sorry about the no reply bit, it's not that we don't want to look, we prolly just didn't have time to respond. 

Will take a look at those!
## Post #4
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-01-19T14:30:37+00:00
- Post Title: Asking for Star Wars - Empire At War .meg support

Thank you!

Much appreciated. 

N
## Post #5
- Username: Acewell
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-19T19:18:58+00:00
- Post Title: Asking for Star Wars - Empire At War .meg support

Okay, I created a MexCom script for ya.

Scroll down for the BMS file. You should add this to your MRF file using the Add BMS to MRF option. Then you can also replace files in the .MEG archives. Enjoy!

```
Get FN Long 0
Get FN Long 0
SavePos FNS 0 
For T = 1 to FN
Get NS Int 0
GetDString FName NS 0
Next T
SavePos FIS 0
For T = 1 To FN
GoTo FNS 0 
Get NS Int 0
GetDString FName NS 0
SavePos FNS 0
GoTo FIS 0
Get U1 Long 0
Get U2 Long 0
SavePos FSO 0
Get FS Long 0
SavePos FOO 0
Get FO Long 0
Get U3 Long 0
SavePos FIS 0
Log FName FO FS FOO FSO
Next T

```

[meg.zip](https://xentaxbackup.github.io/file/587_meg.zip)
## Post #6
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-01-19T23:29:28+00:00
- Post Title: Asking for Star Wars - Empire At War .meg support

Holy Underwear Batman! That was fast...thank's a million I really appreciate this a lot.  

Will try it out at once. Thank you!!!

N
## Post #7
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-01-20T00:28:11+00:00
- Post Title: Asking for Star Wars - Empire At War .meg support

Hi again

Extraction works great (thank's again), tried it out on the wav and the mp3 files and they sound great.  

One small detail I noticed though is that the filenames seem to be mixed up (i.e. the wrong names on the wrong files). However, that's only a minor cosmetical issue I guess...otherwise it seems to work just fine.

Thank's again!

Cheers

N
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-20T07:01:12+00:00
- Post Title: Asking for Star Wars - Empire At War .meg support

> Reply from NinjaMuffin
>
> Hi again

Extraction works great (thank's again), tried it out on the wav and the mp3 files and they sound great.  

One small detail I noticed though is that the filenames seem to be mixed up (i.e. the wrong names on the wrong files). However, that's only a minor cosmetical issue I guess...otherwise it seems to work just fine.

Thank's again!

Cheers

N

Okay, well that's one small detail we don't want. I realize the sound file is too big to send, but how about using the Filecutter (Click the link in my signature to the Game Request rules) for the first (and last part) of the sound file? We gotta fix this .
## Post #9
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-01-20T11:53:32+00:00
- Post Title: Asking for Star Wars - Empire At War .meg support

Hello again  

First of all, thank you for your efforts mate!

After I made the above posts I remembered I do actually have access to a small place to put them (sorry bout that). You can find one of the soundeffects .meg's (in it's full original size) EDIT: file removed. The names of the soundfiles within the .meg archive are pretty clear and self-describing.

Thank's again  

Cheers

N
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-20T14:56:37+00:00
- Post Title: Asking for Star Wars - Empire At War .meg support

Okay, this should get the filenames in the correct order. Takes a little longer to process though, as it's a dirty rotten trick.  

```
Get FN Long 0 ;
Get FN Long 0 ;
SavePos FNS 0 ;
For T = 1 To FN ;
Get NS Int 0 ;
GetDString FName NS 0 ;
Next T ;
SavePos FIS 0 ;
For T = 1 To FN ;
GoTo FIS 0 ;
Get U1 Long 0 ;
Get U2 Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
Get ResNum Long 0 ;
SavePos FIS 0 ;
GoTo FNS 0 ;
Set R Long 0 ;
Do ;
Get NS Int 0 ;
GetDString FName NS 0 ;
Math R += 1 ;
While R < ResNum ;
Log FName FO FS FOO FSO ;
Next T ;
```

[meg.zip](https://xentaxbackup.github.io/file/589_meg.zip)
## Post #11
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-01-20T20:41:05+00:00
- Post Title: Asking for Star Wars - Empire At War .meg support

I really appreciate you taking your time to do this mate.

That's why I feel kinda hesitant to say that I think the problem still remains (at least to a certain degree). However, as you said that this needs to be fixed, I feel obligated to report any possible problems...so I'll continue to do that until you say otherwise if it's ok with you.

Using the new bsm you posted and opening the SFX2D_Non_Localized.meg seem to get some names right, however it seems some are still wrong.

It's easier to notice maybe when opening the Music.meg of the game. I managed to catch on the fly from Filecutter (prolly not as intended, but still) what I think are 2 files of the Music.meg (head & tail). 

Here are some of my findings based on what I can see in the Music.meg file depending on what version of your bms I use...

1st bms version (list of content in order as displayed my MexCom browser):

ADVANCE_ON_THE_CITY.MP3
AOTC_AMBUSH_ON_CORUSCANT.MP3
BATTLE_PENDING_1.MP3
BEGINNING_THE_APPROACH.MP3
CREDITS_2A.MP3
CREDITS_EP3.MP3
E_ATTACK_OF_THE_SANDPEOPLE.MP3
E_DEN_OF_THE_RANCOR.MP3
E_THE_GUNGANS_RETREAT.MP3
E_WOOKIEE_PRISONER.MP3
EMPIRE_AT_WAR.MP3
EMPIRE_LOSE_1.MP3
ESB_THE_IMPERIAL_PROBE.MP3
IMPERIAL_ATTACK_1.MP3
IMPERIAL_CRUISER_PURSUIT.MP3
IMPERIAL_MARCH.MP3
IMPERIAL_MARCH_EDIT.MP3
R_FOREST_AMBUSH.MP3
R_SAIL_BARGE_ASSAULT.MP3
R_THE_BATTLE_RAGES_ON.MP3
R_THE_DUNE_SEA_OF_TATOOINE.MP3
REBEL_LOSE_1.MP3
REBEL_VICTORY.MP3
ROTJ_ALLIANCE_ASSEMBLY.MP3
ROTJ_APPROACHING_THE_DEATH_STAR.MP3
TIE_FIGHTER_ATTACK.MP3 <------------------ missing when using 2nd bms (see below)

Note: Names mismatch

2nd bms version (list of content in order as displayed my MexCom browser):

R_THE_DUNE_SEA_OF_TATOOINE.MP3
EMPIRE_LOSE_1.MP3
REBEL_VICTORY.MP3
BATTLE_PENDING_1.MP3
IMPERIAL_CRUISER_PURSUIT.MP3
AOTC_AMBUSH_ON_CORUSCANT.MP3
ESB_THE_IMPERIAL_PROBE.MP3
E_WOOKIEE_PRISONER.MP3
EMPIRE_AT_WAR.MP3
IMPERIAL_MARCH.MP3
R_FOREST_AMBUSH.MP3
E_THE_GUNGANS_RETREAT.MP3
IMPERIAL_MARCH_EDIT.MP3
R_THE_BATTLE_RAGES_ON.MP3
REBEL_LOSE_1.MP3
ADVANCE_ON_THE_CITY.MP3 <--------------- duplicate
BEGINNING_THE_APPROACH.MP3
IMPERIAL_ATTACK_1.MP3
ROTJ_ALLIANCE_ASSEMBLY.MP3
CREDITS_2A.MP3
E_DEN_OF_THE_RANCOR.MP3
E_ATTACK_OF_THE_SANDPEOPLE.MP3
ROTJ_APPROACHING_THE_DEATH_STAR.MP3
CREDITS_EP3.MP3
R_SAIL_BARGE_ASSAULT.MP3
ADVANCE_ON_THE_CITY.MP3 <--------------- duplicate

Note: Names mismatch and "TIE_FIGHTER_ATTACK.MP3" missing due to duplicate of "ADVANCE_ON_THE_CITY.MP3"

Sorry for the long text, but just in case this info is of some help to you I figured I'll just go ahead and post it.

You can download the Filecutter files (hope they work) I got from the Music.meg [here](http://members.chello.se/temporary/Music_MEG_head_&_tail.zip). 

Cheers

N
## Post #12
- Username: Acewell
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-20T22:13:52+00:00
- Post Title: Asking for Star Wars - Empire At War .meg support

Thanks, your help is much appreciated, so we cansolve this problem. You did right to send those files. All that happens after it is that both files are zipped up and the originals deleted.  I will take a look at them soon.

[EDIT]Looked at them. 

```
Get FN Long 0
Get FN Long 0
SavePos FNS 0
For T = 1 To FN
Get NS Int 0
GetDString FName NS 0
Next T
SavePos FIS 0
For T = 1 To FN
GoTo FIS 0
Get U1 Long 0
Get U2 Long 0
SavePos FSO 0
Get FS Long 0
SavePos FOO 0
Get FO Long 0
Get ResNum Long 0
SavePos FIS 0
GoTo FNS 0
Set R Long 0
Math ResNum += 1
Do
Get NS Int 0
GetDString FName NS 0
Math R += 1
While R < ResNum
Log FName FO FS FOO FSO
Next T

```


This is what I get now (you can save the Table of Contents from the File menu):

```
-----------------------------------
D:\Code\Mexres\Star Wars - Empire At War\Music_MEG_head_&_tail\head.bin
Number of resources: 26
TOC Created on: 1/21/2006 at 12:11:01 AM
-----------------------------------
Filename	Type	Size	Offset
DATA\AUDIO\MUSIC\TIE_FIGHTER_ATTACK.MP3	MP3	2325316	1612
DATA\AUDIO\MUSIC\ESB_THE_IMPERIAL_PROBE.MP3	MP3	8451971	2326928
DATA\AUDIO\MUSIC\ROTJ_ALLIANCE_ASSEMBLY.MP3	MP3	4189623	10778899
DATA\AUDIO\MUSIC\BEGINNING_THE_APPROACH.MP3	MP3	3798622	14968522
DATA\AUDIO\MUSIC\IMPERIAL_MARCH.MP3	MP3	4339670	18767144
DATA\AUDIO\MUSIC\BATTLE_PENDING_1.MP3	MP3	605623	23106814
DATA\AUDIO\MUSIC\E_ATTACK_OF_THE_SANDPEOPLE.MP3	MP3	2364813	23712437
DATA\AUDIO\MUSIC\IMPERIAL_ATTACK_1.MP3	MP3	1536627	26077250
DATA\AUDIO\MUSIC\EMPIRE_LOSE_1.MP3	MP3	251238	27613877
DATA\AUDIO\MUSIC\IMPERIAL_MARCH_EDIT.MP3	MP3	1708408	27865115
DATA\AUDIO\MUSIC\R_SAIL_BARGE_ASSAULT.MP3	MP3	6441169	29573523
DATA\AUDIO\MUSIC\E_WOOKIEE_PRISONER.MP3	MP3	2084571	36014692
DATA\AUDIO\MUSIC\REBEL_LOSE_1.MP3	MP3	445127	38099263
DATA\AUDIO\MUSIC\R_THE_DUNE_SEA_OF_TATOOINE.MP3	MP3	1374877	38544390
DATA\AUDIO\MUSIC\REBEL_VICTORY.MP3	MP3	2000562	39919267
DATA\AUDIO\MUSIC\ADVANCE_ON_THE_CITY.MP3	MP3	4996075	41919829
DATA\AUDIO\MUSIC\CREDITS_2A.MP3	MP3	4091402	46915904
DATA\AUDIO\MUSIC\IMPERIAL_CRUISER_PURSUIT.MP3	MP3	2282057	51007306
DATA\AUDIO\MUSIC\ROTJ_APPROACHING_THE_DEATH_STAR.MP3	MP3	8076643	53289363
DATA\AUDIO\MUSIC\CREDITS_EP3.MP3	MP3	9167099	61366006
DATA\AUDIO\MUSIC\E_THE_GUNGANS_RETREAT.MP3	MP3	3319014	70533105
DATA\AUDIO\MUSIC\E_DEN_OF_THE_RANCOR.MP3	MP3	5072562	73852119
DATA\AUDIO\MUSIC\R_FOREST_AMBUSH.MP3	MP3	1614367	78924681
DATA\AUDIO\MUSIC\EMPIRE_AT_WAR.MP3	MP3	3006171	80539048
DATA\AUDIO\MUSIC\R_THE_BATTLE_RAGES_ON.MP3	MP3	2860722	83545219
DATA\AUDIO\MUSIC\AOTC_AMBUSH_ON_CORUSCANT.MP3	MP3	4519811	86405941
-----------------------------------

```

[meg.zip](https://xentaxbackup.github.io/file/590_meg.zip)
## Post #13
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-01-21T04:05:16+00:00
- Post Title: Asking for Star Wars - Empire At War .meg support

Ok here's what I've done...

Music

It occurred to me that most of the mp3's seemed to be named by their original movie soundtrack title, so I auditioned each one and compared them to corresponding soundtrack name, making sure there was a match between name and sound.

There are however a few exceptions:

ADVANCE_ON_THE_CITY.MP3
BEGINNING_THE_APPROACH.MP3
EMPIRE_AT_WAR.MP3
REBEL_VICTORY.MP3

The mp3's above are obviously synth made music by someone other than John Williams.

BATTLE_PENDING_1.MP3
CREDITS_2A.MP3
CREDITS_EP3.MP3
EMPIRE_LOSE_1.MP3
REBEL_LOSE_1.MP3

The mp3's above are clearly original music and although I could not find a corresponding track name, the description and the style of music fit together.

The rest all have matching soundtrack names and sounds:

AOTC_AMBUSH_ON_CORUSCANT.MP3
E_ATTACK_OF_THE_SANDPEOPLE.MP3
E_DEN_OF_THE_RANCOR.MP3
E_THE_GUNGANS_RETREAT.MP3
E_WOOKIEE_PRISONER.MP3
ESB_THE_IMPERIAL_PROBE.MP3
IMPERIAL_ATTACK_1.MP3
IMPERIAL_CRUISER_PURSUIT.MP3
IMPERIAL_MARCH.MP3
IMPERIAL_MARCH_EDIT.MP3
R_FOREST_AMBUSH.MP3
R_SAIL_BARGE_ASSAULT.MP3
R_THE_BATTLE_RAGES_ON.MP3
R_THE_DUNE_SEA_OF_TATOOINE.MP3
ROTJ_ALLIANCE_ASSEMBLY.MP3
ROTJ_APPROACHING_THE_DEATH_STAR.MP3
TIE_FIGHTER_ATTACK.MP3

Soundeffects

I'm not going to list them here as there are a total of 940 soundeffects. What I did however, was audition them one by one and checking whether the description seemed to fit the sound.

From checking all the soundeffects this way I could not find a single one that seemed to be out of place or inconsistent (in terms of name/sound)  in any way.

Voice

There is an archive in the game called SFX2D_English.MEG which most likely contains in-game voice messages. However, the archive (just over 200 MB in size) seems to contain so many files that when trying to open it in MexCon it becomes busy at "MultiEx ActiveX DLL - Retreiving Archive Contents" dialogue for several minutes and eventually this error message pops up:

"Error: Mex Empty list file"

Pressing "OK" at this point seems to freeze up the program with no option but to terminate it completely. 

I'm guessing this is not due to the .meg format itself, but to do with the large amount of files in the archive. Nevertheless, in case you'd want to check it out you can get a Filecutter file of it [here](http://members.chello.se/temporary/SFX2D_English_MEG_head_&_tail.zip).

Conclusion

I think it's pretty safe to say that your third version seems to have eliminated the problems of mismatching names...at least as far as I can tell.

Although one cannot be 100% certain about some of the music, the odds of there being a mismatch among so many verifiable files are slim to say the least...and although the soundeffects have been judged by ear, the consistency of names and categories is IMHO just too accurate to allow for any mismatch as well.

Looks like you did a great job...your perseverance is truly appreciated and can't really think of anything else to say but...

THANK YOU SO MUCH!!! This is friggin excellent!!!  

N
## Post #14
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-21T17:59:48+00:00
- Post Title: Asking for Star Wars - Empire At War .meg support

Hmm, it's because the script uses a lame but necessary trick to get the right filenames why it takes so darn long. There are thousands of filenames in there apparently. I will see if I can find a solution. For now, it works with the other files, I suppose.
## Post #15
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-01-22T14:24:02+00:00
- Post Title: Asking for Star Wars - Empire At War .meg support

> Reply from Mr.Mouse
>
> There are thousands of filenames in there apparently.

4765 of them to be exact. One can still preview/extract them using the first version of your meg script. The names will be scrambled, but you can still do something with them.

Yes, personally I'm as convinced as I can possibly be (within my limited field of knowledge) that your 3rd version has sorted out the name-mismatch problem. Excellent job!

Thank's again for your great work on this...it's greatly appreciated. 

Cheers

N
## Post #16
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-01-23T18:39:07+00:00
- Post Title: 

Some news regarding this game and the .meg format...

I just discovered a newly made extractor for the Empire At War .meg format.

Called the Empire At War Extractor it can be downloaded [here](http://www.renevo.com/downloads/eaw/EAWExtractor.zip) (NOTE: program requires .Net 2.0 to run).

The originators forum can be found [here](http://www.renevo.com/index.php?showtopic=2930).

It doesn't seem to extract the soundeffects archives at all at this point, since the archives are selected from an existing menu on which they soundeffects are missing (i.e. no "manual" means of selecting archives seems to exist).

Don't know if this is of interest, but I figured I'd post it here just in case.

Thank's again for your great work on this.

Cheers  

N
## Post #17
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-01-24T01:00:59+00:00
- Post Title: 

Found yet another tool that can handle the Empire At War .meg format. Apparently it can handle both export and import of .meg archive data.

It's called EAWTools and can be downloaded [here](http://www.technical-difficulties.com/hacks/eaw/EaWtools-1.1.zip).

The homepage of the tool can be found [here](http://www.technical-difficulties.com/hacks/eaw/). It might be of special interest to you as the creator of the tool describes the specifics of his coding on it.

Cheers

N
## Post #18
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-04-12T08:26:25+00:00
- Post Title: 

Sorry for bumping up this old thread, but I recently found some info that might be of interest for support of this game.

There apparently is a guy named Mike from the Netherlands who's posted some detailed info about Empire At War fileformats (so far .meg, .mtd and .alo) on his website:

[http://alpha1.dyndns.info/eaw/Formats](http://alpha1.dyndns.info/eaw/Formats)

I just thought it might be some of interest and perhaps helpful when implementing MexCom support for EAW, especially with regards to the filenames of the .meg format which he seems to have some specific info about ( [http://alpha1.dyndns.info/eaw/MegFileFormat](http://alpha1.dyndns.info/eaw/MegFileFormat) ). 

Cheers

N
