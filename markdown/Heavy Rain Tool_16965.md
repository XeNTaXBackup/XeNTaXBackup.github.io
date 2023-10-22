## Post #1
- Username: MushroomLT
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 02, 2017 8:09 pm
- Post datetime: 2017-09-03T13:42:04+00:00
- Post Title: Heavy Rain Tool

The beginnings of the ultimate Heavy Rain extractor tool, or even PC port in the future - Heavy Rain Tool



After finding @HugoPeters work on Beyond, I became really interested in the concept of reverse-engineering a game engine, so I started working on my favourite game - Heavy Rain.

Currently I managed to:
Read the BigFile index (the sdat encrypted file)
Find and display a list of entries grouped by type
Unpack all of the segs archived entries
Read the inner structure of the entries
Parse some of the blocks of the entries to extract data from them:
    Textures (some of them are misaligned)
    Scripts that are not compiled
    BIK Video files
    Some of the audio files + Multi-Channel audio exporting (Mostly soundtrack)

What I'm working on:
Linking the entries together by parsing the storyboard
Properly aligning textures

(Last updated: 2017-09-12, PreAlpha 3)

Tool usage: 
* Run the tool to generate "engine.json" configuration file.
* Open the configuration file and set "qdGameDirectory" to the game file directory location
* Set vlcExeLocation to the location of your VLC Media Player installation to be able to play sounds directly from the tool
* Set loadBigFile to the BigFile index file you want to load.

The tool can extract any entry into a separate binary file by selecting an entry and clicking the Export button.
To view the inner blocks of the entry double click it in the tree. Selecting a block will automatically adjust the offset in the hex view.
To export video from an entry double click the entry, and double click the VIDEDATA block.
To export sounds from an entry double click the entry, and double click the PARTITIO block.
To play the exported sound using VLC player, double click the entry inside of the PARTITIO block.

To view scripts, double click the SCRIPT block, and select the inner script entry, it will be displayed under the Contents tab.
## Post #2
- Username: MushroomLT
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 02, 2017 8:09 pm
- Post datetime: 2017-09-08T16:17:51+00:00
- Post Title: Heavy Rain Tool

I managed to perform a RAM dump of RPCS3 running the game by modifying it's source, and from the dump I found the LUA initialisation code for probably all of the data types. Now the tool is capable of displaying what data each entry has:

```
DCINFO Entries: 
	Entry 0: SOUND_OFFSET; 64112
	Entry 1: SOUND_DATA; 64108
	Entry 2: SCRIPT_SOUND_ENTITY; 15116
	Entry 3: SOUND_OFFSET; 64116
	Entry 4: SOUND_DATA; 64112
	Entry 5: SCRIPT_SOUND_ENTITY; 15118
	Entry 6: SOUND_OFFSET; 66806
	Entry 7: SOUND_DATA; 66803
	Entry 8: SCRIPT_SOUND_ENTITY; 15117
	Entry 9: SOUND_OFFSET; 46980
	Entry 10: SOUND_DATA; 46976
	Entry 11: SCRIPT_SOUND_ENTITY; 10944
	Entry 12: SOUND_OFFSET; 64114
	Entry 13: SOUND_DATA; 64110
	Entry 14: SCRIPT_SOUND_ENTITY; 15120
	Entry 15: SOUND_OFFSET; 62123
	Entry 16: SOUND_DATA; 62119
	Entry 17: SCRIPT_SOUND_ENTITY; 10947
	Entry 18: SCRIPT_SOUND_ENTITY; 10945
	Entry 19: SCRIPT_SOUND_ENTITY; 15119
	Entry 20: LOADING_ZONE; 5681
	Entry 21: LOADING_ZONE; 5756
	Entry 22: LOADING_ZONE; 6602
	Entry 23: LOADING_ZONE; 6630
	Entry 24: LOADING_ZONE; 6676
	Entry 25: LOADING_ZONE; 6718
	Entry 26: LOADING_ZONE; 6767
	Entry 27: LOADING_ZONE; 6779
	Entry 28: LOADING_ZONE; 22721
	Entry 29: LOADING_ZONE; 22724
	Entry 30: LOADING_ZONE; 22727
	Entry 31: LOADING_ZONE; 22729
	Entry 32: LOADING_ZONE; 22754
	Entry 33: LOADING_ZONE; 38606
	Entry 34: STORYBOARD; 46
	Entry 35: LOADING_ZONE; 5674
	Entry 36: LOADING_ZONE; 5675
	Entry 37: LOADING_ZONE; 5677
	Entry 38: LOADING_ZONE; 5678
	Entry 39: LOADING_ZONE; 5679
	Entry 40: LOADING_ZONE; 5689
	Entry 41: LOADING_ZONE; 5690
	Entry 42: LOADING_ZONE; 5691
	Entry 43: LOADING_ZONE; 5704
	Entry 44: LOADING_ZONE; 5739
	Entry 45: LOADING_ZONE; 5740
	Entry 46: LOADING_ZONE; 5741
	Entry 47: LOADING_ZONE; 5754
	Entry 48: LOADING_ZONE; 6498
	Entry 49: LOADING_ZONE; 6569
	Entry 50: LOADING_ZONE; 6659
	Entry 51: LOADING_ZONE; 6662
	Entry 52: LOADING_ZONE; 6669
	Entry 53: LOADING_ZONE; 6670
	Entry 54: LOADING_ZONE; 6679
	Entry 55: LOADING_ZONE; 6686
	Entry 56: LOADING_ZONE; 6689
	Entry 57: LOADING_ZONE; 6696
	Entry 58: LOADING_ZONE; 6697
	Entry 59: LOADING_ZONE; 6698
	Entry 60: LOADING_ZONE; 6701
	Entry 61: LOADING_ZONE; 6703
	Entry 62: LOADING_ZONE; 6705
	Entry 63: LOADING_ZONE; 6706
	Entry 64: LOADING_ZONE; 6707
	Entry 65: LOADING_ZONE; 6709
	Entry 66: LOADING_ZONE; 6711
	Entry 67: LOADING_ZONE; 6714
	Entry 68: LOADING_ZONE; 6716
	Entry 69: LOADING_ZONE; 6719
	Entry 70: LOADING_ZONE; 6720
	Entry 71: LOADING_ZONE; 6723
	Entry 72: LOADING_ZONE; 6724
	Entry 73: LOADING_ZONE; 6725
	Entry 74: LOADING_ZONE; 6728
	Entry 75: LOADING_ZONE; 6730
	Entry 76: LOADING_ZONE; 6732
	Entry 77: LOADING_ZONE; 6733
	Entry 78: LOADING_ZONE; 6734
	Entry 79: LOADING_ZONE; 6738
	Entry 80: LOADING_ZONE; 6740
	Entry 81: LOADING_ZONE; 6742
	Entry 82: LOADING_ZONE; 6745
	Entry 83: LOADING_ZONE; 6748
	Entry 84: LOADING_ZONE; 6753
	Entry 85: LOADING_ZONE; 6755
	Entry 86: LOADING_ZONE; 6758
	Entry 87: LOADING_ZONE; 6760
	Entry 88: LOADING_ZONE; 6771
	Entry 89: LOADING_ZONE; 6773
	Entry 90: LOADING_ZONE; 6774
	Entry 91: LOADING_ZONE; 6776
	Entry 92: LOADING_ZONE; 6777
	Entry 93: LOADING_ZONE; 6785
	Entry 94: LOADING_ZONE; 6788
	Entry 95: LOADING_ZONE; 6789
	Entry 96: LOADING_ZONE; 6792
	Entry 97: LOADING_ZONE; 6795
	Entry 98: LOADING_ZONE; 6797
	Entry 99: LOADING_ZONE; 6798
	Entry 100: LOADING_ZONE; 6799
	Entry 101: LOADING_ZONE; 6800
	Entry 102: LOADING_ZONE; 6801
	Entry 103: LOADING_ZONE; 6805
	Entry 104: LOADING_ZONE; 6807
	Entry 105: LOADING_ZONE; 6808
	Entry 106: LOADING_ZONE; 6810
	Entry 107: LOADING_ZONE; 6811
	Entry 108: LOADING_ZONE; 6814
	Entry 109: LOADING_ZONE; 6816
	Entry 110: LOADING_ZONE; 6817
	Entry 111: LOADING_ZONE; 6818
	Entry 112: LOADING_ZONE; 6825
	Entry 113: LOADING_ZONE; 6828
	Entry 114: LOADING_ZONE; 6830
	Entry 115: LOADING_ZONE; 6832
	Entry 116: LOADING_ZONE; 6834
	Entry 117: LOADING_ZONE; 6835
	Entry 118: LOADING_ZONE; 6837
	Entry 119: LOADING_ZONE; 7700
	Entry 120: LOADING_ZONE; 10309
	Entry 121: LOADING_ZONE; 10419
	Entry 122: LOADING_ZONE; 17933
	Entry 123: LOADING_ZONE; 18595
	Entry 124: LOADING_ZONE; 20832
	Entry 125: LOADING_ZONE; 20834
	Entry 126: LOADING_ZONE; 20836
	Entry 127: LOADING_ZONE; 20850
	Entry 128: LOADING_ZONE; 20852
	Entry 129: LOADING_ZONE; 22359
	Entry 130: LOADING_ZONE; 23752
	Entry 131: LOADING_ZONE; 23756
	Entry 132: LOADING_ZONE; 23761
	Entry 133: LOADING_ZONE; 23763
	Entry 134: LOADING_ZONE; 23969
	Entry 135: LOADING_ZONE; 25561
	Entry 136: LOADING_ZONE; 28431
	Entry 137: LOADING_ZONE; 29901
	Entry 138: LOADING_ZONE; 29907
	Entry 139: LOADING_ZONE; 29909
	Entry 140: LOADING_ZONE; 29911
	Entry 141: LOADING_ZONE; 29913
	Entry 142: LOADING_ZONE; 29915
	Entry 143: LOADING_ZONE; 29917
	Entry 144: LOADING_ZONE; 29920
	Entry 145: LOADING_ZONE; 29924
	Entry 146: LOADING_ZONE; 29928
	Entry 147: LOADING_ZONE; 29932
	Entry 148: LOADING_ZONE; 29937
	Entry 149: LOADING_ZONE; 29953
	Entry 150: LOADING_ZONE; 29956
	Entry 151: LOADING_ZONE; 33069
	Entry 152: LOADING_ZONE; 33215
	Entry 153: LOADING_ZONE; 33239
	Entry 154: LOADING_ZONE; 33241
	Entry 155: LOADING_ZONE; 34655
	Entry 156: LOADING_ZONE; 35557
	Entry 157: LOADING_ZONE; 35863
	Entry 158: LOADING_ZONE; 38507
	Entry 159: LOADING_ZONE; 39037
	Entry 160: LOADING_ZONE; 39041
	Entry 161: LOADING_ZONE; 39269
	Entry 162: LOADING_ZONE; 39448
	Entry 163: LOADING_ZONE; 39519
	Entry 164: LOADING_ZONE; 39521
	Entry 165: LOADING_ZONE; 39523
	Entry 166: LOADING_ZONE; 40373
	Entry 167: STORYBOARD; 35
	Entry 168: ENGINE_TEXTURE_FILE; 49948
	Entry 169: ENGINE_TEXTURE_FILE; 50553
	Entry 170: ENGINE_TEXTURE_FILE; 54206
	Entry 171: ENGINE_TEXTURE_FILE; 54207
	Entry 172: ENGINE_TEXTURE_FILE; 54208
	Entry 173: ENGINE_TEXTURE_FILE; 54209
	Entry 174: ENGINE_TEXTURE_FILE; 54210
	Entry 175: ENGINE_TEXTURE_FILE; 54211
	Entry 176: ENGINE_TEXTURE_FILE; 54212
	Entry 177: ENGINE_TEXTURE_FILE; 54213
	Entry 178: ENGINE_TEXTURE_FILE; 54214
	Entry 179: ENGINE_TEXTURE_FILE; 62181
	Entry 180: ENGINE_TEXTURE_FILE; 62182
	Entry 181: ENGINE_TEXTURE_FILE; 62183
	Entry 182: ENGINE_TEXTURE_FILE; 62184
	Entry 183: ENGINE_TEXTURE_FILE; 62185
	Entry 184: ENGINE_TEXTURE_FILE; 62186
	Entry 185: ENGINE_TEXTURE_FILE; 62187
	Entry 186: ENGINE_TEXTURE_FILE; 62188
	Entry 187: ENGINE_TEXTURE_FILE; 62921
	Entry 188: ENGINE_TEXTURE_FILE; 64307
	Entry 189: ENGINE_TEXTURE_FILE; 64308
	Entry 190: ENGINE_TEXTURE_FILE; 64309
	Entry 191: ENGINE_TEXTURE_FILE; 69866
	Entry 192: ENGINE_TEXTURE_FILE; 75541
	Entry 193: ENGINE_TEXTURE_FILE; 75542
	Entry 194: ENGINE_TEXTURE_FILE; 75771
	Entry 195: ENGINE_TEXTURE_FILE; 76140
	Entry 196: ENGINE_TEXTURE_FILE; 78367
	Entry 197: ENGINE_TEXTURE_FILE; 78368
	Entry 198: ENGINE_TEXTURE_FILE; 78369
	Entry 199: ENGINE_TEXTURE_FILE; 78370
	Entry 200: ENGINE_TEXTURE_FILE; 78371
	Entry 201: ENGINE_TEXTURE_FILE; 78372
	Entry 202: ENGINE_TEXTURE_FILE; 78373
	Entry 203: ENGINE_TEXTURE_FILE; 78374
	Entry 204: ENGINE_TEXTURE_FILE; 78375
	Entry 205: ENGINE_TEXTURE_FILE; 78376
	Entry 206: ENGINE_TEXTURE_FILE; 78377
	Entry 207: ENGINE_TEXTURE_FILE; 78378
	Entry 208: ENGINE_TEXTURE_FILE; 79345
	Entry 209: ENGINE_TEXTURE_FILE; 62189
	Entry 210: ENGINE_TEXTURE_FILE; 69848
	Entry 211: MENUS_MASTER_FONT_DATA; 9
	Entry 212: MENUS_MASTER_DATA; 28
	Entry 213: CHARACTER; 3
	Entry 214: CHARACTER; 345
	Entry 215: CHARACTER; 7
	Entry 216: CHARACTER; 6

DCDATA Size: 5336713; Entries: 7
	Entry 0: 0
	Entry 1: 48
	Entry 2: 0
	Entry 3: 0
	Entry 4: 256
	Entry 5: 0
	Entry 6: 1

```
## Post #3
- Username: MushroomLT
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 02, 2017 8:09 pm
- Post datetime: 2017-09-08T20:28:15+00:00
- Post Title: Heavy Rain Tool

Textures reversed!
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-09-09T21:18:56+00:00
- Post Title: Heavy Rain Tool

Awesome keep it up!
## Post #5
- Username: MushroomLT
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 02, 2017 8:09 pm
- Post datetime: 2017-09-12T12:54:11+00:00
- Post Title: Heavy Rain Tool

DataContainer structure reversed - working on the storyboard now, which links all the scenes.
## Post #6
- Username: MushroomLT
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2017-09-16T22:25:22+00:00
- Post Title: Heavy Rain Tool

Great to see my stuff inspired a follow-up!
## Post #7
- Username: Hamers
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Jul 22, 2011 11:39 pm
- Post datetime: 2017-09-17T10:55:17+00:00
- Post Title: Heavy Rain Tool

Awesome work dude! Also these are the scenes that were cut from the game in Beta status, fully playable but unpolished:

0501 Sleepless Night Underwater
0701 Going to School Wakeup
1002 Swimming Again

Since they have almost been completed and use mostly existing assets, everything you could find in regards to them would be quite amazing. I doubt you can fully restore them, but maybe they have a lot of traces left
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2017-09-17T19:42:55+00:00
- Post Title: Heavy Rain Tool

well i hope u finnish it since Hugo had to drop it..
## Post #9
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2017-09-24T22:38:33+00:00
- Post Title: Heavy Rain Tool

Any news?
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-01T12:23:27+00:00
- Post Title: Heavy Rain Tool

Quantic Dream game formats were reversed all the way, and tools released to public. But it was forbidden to talk about this engine here on xentax. Any changes?
## Post #11
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2017-10-02T15:06:06+00:00
- Post Title: Heavy Rain Tool

> Reply from daemon1
>
> Quantic Dream game formats were reversed all the way, and tools released to public. But it was forbidden to talk about this engine here on xentax. Any changes?

<snip>
No they were not, there was only a model extractor which just brute-force scans files for model data.
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-02T15:18:25+00:00
- Post Title: Heavy Rain Tool

> Reply from HugoPeters
>
> daemon1 wrote:Quantic Dream game formats were reversed all the way, and tools released to public. But it was forbidden to talk about this engine here on xentax. Any changes?

<snip>
No they were not, there was only a model extractor which just brute-force scans files for model data.

Yes, they were. You probably just don't know about that. And a proper tool was released which is able to extract all models and levels with textures, skeletons and fully weighted including cloth, from both Heavy Rain & Beyond Two Souls. I posted images with models extracted with that tool.

My question is: can I now talk about this on xentax?
## Post #13
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2017-10-03T05:31:41+00:00
- Post Title: Heavy Rain Tool

I think the tool was on the Cg in Games forum  (QDtools)

but it seems it cannot be downloaded any longer

It's to bad since I sold my copy of Heavy Rain for PS3 a while back because I figured there was never going to be a way to get the models
I would probably go buy another copy if I knew the tools were available
(actually I bet a lot of people might buy a copy)
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-03T15:16:51+00:00
- Post Title: Heavy Rain Tool

> Reply from Modman69
>
> I think the tool was on the Cg in Games forum  (QDtools)

Tools can still be downloaded from CG and also Facepunch, and maybe other sites.
## Post #15
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2017-10-04T09:50:29+00:00
- Post Title: Heavy Rain Tool

> Reply from daemon1
>
> HugoPeters wrote:daemon1 wrote:Quantic Dream game formats were reversed all the way, and tools released to public. But it was forbidden to talk about this engine here on xentax. Any changes?

<snip>
No they were not, there was only a model extractor which just brute-force scans files for model data.

Yes, they were. You probably just don't know about that. And a proper tool was released which is able to extract all models and levels with textures, skeletons and fully weighted including cloth, from both Heavy Rain & Beyond Two Souls. I posted images with models extracted with that tool.

My question is: can I now talk about this on xentax?
Again, no they were not. Apparently you think models are the only thing what makes a game 
The tool you're talking about, like I said, brute-force scans files for model data. I didn't say it doesn't produce proper models.
Give me a tool that can also interpret animation data and all the rest that comes with it and can produce a scene like I showcase on my portfolio ([http://hugo.fyi/projects/reverse-engineering-b2s](http://hugo.fyi/projects/reverse-engineering-b2s)) - then we'll talk
## Post #16
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2017-10-04T12:16:32+00:00
- Post Title: Re: Heavy Rain Tool

HugoPeters

Do you have tools like you created for BTS for Heavy Rain also?
## Post #17
- Username: Modman69
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2017-10-04T12:56:23+00:00
- Post Title: Re: Heavy Rain Tool

> Reply from Modman69
>
> HugoPeters

Do you have tools like you created for BTS for Heavy Rain also?
I took a few stabs at implementing HR and got some stuff running, but never finished it due to lack of time/interest.
It looks like MushroomLT is well on his way though and I hope he continues it
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-04T15:20:54+00:00
- Post Title: Re: Heavy Rain Tool

> Reply from HugoPeters
>
> then we'll talk
I don't want to talk with you.

Let me rephrase my question. People who posted information and tools for Beyond two souls were threatened with bans and their messages were deleted. So my question again:

Is it now allowed to talk about (and post tools for) Quantic Dream engine here on xentax ?
## Post #19
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2017-10-04T17:14:42+00:00
- Post Title: Re: Heavy Rain Tool

> Reply from daemon1
>
> HugoPeters wrote:then we'll talk  
I don't want to talk with you.

Let me rephrase my question. People who posted information and tools for Beyond two souls were threatened with bans and their messages were deleted. So my question again:

Is it now allowed to talk about (and post tools for) Quantic Dream engine here on xentax ?
No need for that saltiness man.
("then we'll talk" is a figurative expression btw)

Regarding your question, consider what QD told me when I was working on my project, and the risks that it will cause for Xentax as a whole when more advanced tools / extractors are posted.
## Post #20
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2017-10-27T20:43:19+00:00
- Post Title: Re: Heavy Rain Tool

> Reply from daemon1
>
> 
My question is: can I now talk about this on xentax?

I see no reason why not at this time.
## Post #21
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2017-12-13T15:38:07+00:00
- Post Title: Re: Heavy Rain Tool

> Reply from MushroomLT
>
> DataContainer structure reversed - working on the storyboard now, which links all the scenes.
.
so glad to see someone actually pick this up again   and actually making progress, unlike my on and off dabbling for over a year getting nowhere slowly 

I managed to successfully index + extract meshes/uv/ from heavy rain ages back, but focus has been on B2S mostly. .

there are some slight differences on things like uvs, but for most part b2s & HR data is nearly identical.


Everything is made easier by parsing the lua file by file and tying it up finding the SEQUENCES, and catalogs.

Models(meshes) can appear multiple times, sometimes just referenced or actual dupe of mesh data. but will usually only have one core file with a skelton, of which would contain textures, weights and so on.

to find models just brute force way, each mesh char or Area / prop file will contain "FX_EVENT_" attribute  can also search for PRIMEDGE  SKELETON  NODE_AR       (Primedges are reference and offsets to vertex/uv/ compressed EDGES) each of which is usually aligned at the start of one of the sub-seg' archives of that file .

usually 3x LODs of each char, multiple meshparts,cloth and hair.

CUSTSHADER  attribute are the materials.  in them linking to FILETEXT ..textures trhemselves are found hiding between segs, size defined in either FILETEXT or custshader, IDK

I think they compressed with some form of lzma or huffman or just standard Ps3 sdk EDGE dxt compression tools, (as are Edges) but not looked into it

NODE_AR attribute contains bone info, and links up skeleton to nodes to custshader top text to meshes to meshdata to primedges  (geom)  or something like that...

something in meanwhile will be dusting off more useful goodies to add to the cause, will revert back soon


check here below  (010 template): struct ENTITY_ABC  (this links all things in a character file)  this was work in progress never finished, and the references outdated will send u those seperate (its huge  )

also commented out is file i was using it on if u want to see it in action. ineed to relook at heavy rain i remember there were some differences



```

```
## Post #22
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-13T15:49:18+00:00
- Post Title: Re: Heavy Rain Tool

> Reply from Loomy
>
> textures trhemselves are found hiding between segs

I think they compressed with some form of lzma or huffman or just standard Ps3 sdk EDGE dxt compression tools

Textures are not "hiding between segs". Each segment actually may include raw data part in the end, which holds textures

Since Mr.Mouse approved that, i can say that my tools for Heavy Rain and Beyond 2 Souls are posted here
[https://facepunch.com/showthread.php?t=1566950](https://facepunch.com/showthread.php?t=1566950)
and here [http://cgig.ru/forum/viewtopic.php?p=9316#p9316](http://cgig.ru/forum/viewtopic.php?p=9316#p9316)

I could probably post it here too, but who needs them now, when we can get PS4 version?
## Post #23
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2017-12-13T15:58:33+00:00
- Post Title: Re: Heavy Rain Tool

some of the HR mesh locations:- (left id = sequential index / right hex = sdat absolute offset in particularbigfile if i recall)

[https://pastebin.com/9xF1Edjm](https://pastebin.com/9xF1Edjm)
## Post #24
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2017-12-13T17:53:23+00:00
- Post Title: Re: Heavy Rain Tool

I say "hiding" as an ignorant person who for longest time has just been concatenating segs together thinking those tails were too small to be anything   meanwhile... that compression is insane.

A huge thanks to you and your brilliant work on ur tools, u smashed it  if only u knew how long i been banging head against wall for clues.

Ur resulting output files helped alot, most notably how huge they were compared my own - and that noesis rapi.edgeDecompress is losing many faces in process, some few k' per mesh.  

I have 10,0001 questions id love to ask :p but hope you would kindly oblige me with just  your advice if you know offhand:-

Im looking to research the animation for b2s, between EDGE libs/psd sdk  and Havok which i should be looking to as reference.  seems like havok is used fror more than just cloth & physics.  and just out of interest were textures using some kind of  combination of bitpacking & lzma, or was something else like EDGE dxt cmprssn.   I just find it crazy how ithey shrunk files like that, but then again alot of them are fairly low rez, and quite a small pallette.


> Reply from daemon1
>
> Loomy wrote:textures trhemselves are found hiding between segs

I think they compressed with some form of lzma or huffman or just standard Ps3 sdk EDGE dxt compression tools

Textures are not "hiding between segs". Each segment actually may include raw data part in the end, which holds textures

Since Mr.Mouse approved that, i can say that my tools for Heavy Rain and Beyond 2 Souls are posted here
https://facepunch.com/showthread.php?t=1566950
and here http://cgig.ru/forum/viewtopic.php?p=9316#p9316

I could probably post it here too, but who needs them now, when we can get PS4 version?
## Post #25
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-13T20:25:06+00:00
- Post Title: Re: Heavy Rain Tool

I didn't look into animations, but as for beyond 2 souls textures, they are compressed with JPEG-like algorythm that was introduced by ID-Software in 2006 with source code published. Except a few little tweaks, its just a standard JPEG. Heavy Rain, on the contrary, used usual DDS.
## Post #26
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2017-12-16T05:53:14+00:00
- Post Title: Re: Heavy Rain Tool

@ MushroomLT

How far are u planning to go with this, and if i contribute code can it be in either c#, python or php which is preferred, while i can read java, its not my first language.

Can i stick to my animation research, ive already mapped out most of system and the MotionGraph rigging + default motions, im now trying 2 map out animation blocks and animation tracks and so on.

Do u have the default data mappings as defined in lua ? i think theyre not quite part of Initialization script, but are in the EBOOT, its quite huge, but will help u to automap most attributes, arguments and datatypes

ie:

```
"QDT.SEQUENCE_CONTROLLER_PLAY._MT.SetbDisableForceLoad = function (self, value) return ( self:GenericSetBool(4290, 2, value) ) end",
			"QDT.SEQUENCE_CONTROLLER_PLAY._MT.SetGameplayEndAutomationAtFailure = function (self, value) return ( self:GenericSetBool(4290, 8, value) ) end",
			"QDT.SEQUENCE_CONTROLLER_PLAY._MT.SetGameplayStartAutomation = function (self, value) return ( self:GenericSetBool(4290, 6, value) ) end",
			"QDT.SCRIPT_SOUND_CONTROLLER_FADE._MT.SetbDisableForceLoad = function (self, value) return ( self:GenericSetBool(4263, 2, value) ) end",
			"QDT.SEQUENCE_CONTROLLER_PLAY._MT.SetGameplayEndAutomationAtSuccess = function (self, value) return ( self:GenericSetBool(4290, 7, value) ) end",
			
```


or shall i send u one ive merged between b2s & HR
## Post #27
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2017-12-25T15:10:16+00:00
- Post Title: Re: Heavy Rain Tool

In an attempt to get things moving, and take advantage of holidays and time off from real work   One of main challenges is linking everything together, after that,everything else falls into place and makes further research a little easier.

here are some of my findings, if it helps.  My main issue is not having a moddable ps3(4k slim P.O.S.), and cant for the life of me get rpcss emuworking,  I can only imagine what i could do with Debug logs/output if someone were to take the trouble to make and share such logs. Of interest would be sequential listing of offsets and files/sizes read as game loads to menu, and as it loads into the game itself, - further to that is hacking the LUA system. IE. like B2s, we could do alot with that - printing variables while game running and so on.


Also id like to add, i think it important to give this project some context - to avoid stepping on anyones toes or threatening IP.  For me at least, this is solely for the fun of it - and researching how PS SDK Toolchain + Havok + Mogre + Lua + Mocap came together to deliver one of the highest quality & visual fidelity titles in recent history (that still comparable to its ps4 version) - and ps3 data formats in general - before moving onto all things ps4.  This is not about making some port, or trying to extract any of the game assets and so on - there already tools for that.. (which for me are useless as none of them took the time to share their findings, i can only be thankful that Hugo like to brag as much as he did (and still does ) ) as this research in general can apply to a multitude of titles now and in future, using similar toolchains and formats..  how many games use havok ?    plus B2s/HR have all debug strings not encrypted or custom formats, any idiot or noob (like me) can use it as a great source of learning.
## Post #28
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2017-12-25T15:31:51+00:00
- Post Title: Re: Heavy Rain Tool

Regarding file linking :- 

Sorry bit much to look at, but see notes below :



--------------------------

1.  (Bottom)  *BigFile.sdat  Container List - Lists all individual Data Containers or segments.  They give offset + BigFile location + a unique FileID (ID).  (some of them Duplicated, as there is identical copy in SetupBigFiles (  BigFiles = Streaming,  SetupBigFiles = installed locally) .  There are cases of some files only appearing in setupFiles.  All Beta content and unused stuff is also mostly found in Setup Files.   For our purposes we just take the first entry we find.

----------------------

2. (Far Right) *BigFile.DEP  Container Header Entries - I have only now discovered this, its unique to HR, the B2s version mostly useless afaik.  This is an actual Listing of each of the Communicator Entries, or actual content of the above Containers (Which are normally indexed in each Data Container headers..)  So dont need to UNSEG every single file and parse all 20gb to generate this list anymore.     There are total of 550k+ entries - which sounds about right - B2s is around the same.  

There are Data COntainer entries in this list. each of them 0xC (217) specifies the number of nested entries, or the next number of entries that are found in that specific data container.   (not sure what this value means for other entries - could be similar - some communicators have multiple sub/nested entries ?)

The DataContainer entry itself 0x8 (296)  specifies the .SDAT id of the file.  so the next 217 entries will all be found in SDAT file/seg with ID 296. 

For other Entries 0x4 = Global Unique ID, or Communicator ID, as per CommHeader. and also the ID that is referenced in LUA scripts.

EXAMPLE: 

SetSequence(NewOS("_0501_SLEEPLESS_NIGHT_UNDERWATER_STurnShaun", 4288, 3140))

4288:  Communicator Type (Sequence)
3140: Communicator GlobalID (will be found in CommHeaders, or look it up in .DEP file list).  (again there could be multiple entries.)

so from DEP list we can find the File or DataContainer(s) where we will find this SEQUENCE

-------------------------------------

3. (center)  The Parsed Content of File 296, communicator headers at center top, and attributes, or actual communicator blocks or content in file itself at center (these i still parse manually, or search for their 0x8 magic )

While this doesnt delve into COM_CONT and other attribute stuff - the main point im making here is the linking between SDAT + DEP files + CommHeaders

** Note that some Communicators can appear multiple times, in multiple DataContainers/Files, linking together with its attached LoadingZone, or other linked elements should usually filter this to correct entry
## Post #29
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2017-12-25T17:35:48+00:00
- Post Title: Re: Heavy Rain Tool

Regarding Storyboard Structure:- 

Storyboard = Play Order of Scenes / Levels, from start to finish.. or at least suppose to be.

I am having issues here, as there is meant to be 2x storyboards: Development + Production, the latter being the actual.  But there are multiple storyboards in multiple files, each one missing parts, or not in sequential order, contains unused stuff, or stuff without names or scenes/areas at all.   There meant to be around 50 something main Scenes of the game (each containing one to three parts ie:  _0101,  _0102, _0103  would be scene 1 + 3 parts.

Also unsure of weather there are the same scenes for different characters, each having their own entries in  storyboard. Need to research further, but for now at least, see structs below :-



Structure = 


struct STORYBOARD
{
	char magic[8];          // STORYBRD
	int unknown;           // 1
	int numElements;
	STORYBOARD_ELEMENT[numElements];
	int numScenes;
	STORYBOARD_SCENE[numScenes];
};

struct STORYBOARD_ELEMENT
{
	byte uk0;                      // 1
	uint Comm_Type;          // 0x0000107F
	int   uk1;                      // 1
	char Comm_Magic[8];    // STBRDELM
	int   uk2;                      // 3 (always)
	int   uk3;                      // 0 (always)
	int   numLinked;           // 1 to n
	int   Scene_Idx[numLinked];   // points to / groups Scenes from SCENES array below (seems groups:  _0401, _0402, _0403) etc
};
struct STORYBOARD_SCENE
{
	byte uk0;                      // 1
	uint Comm_Type;          // 0x00001135
	int   uk1;                      // 1
	char Comm_Magic[8];    // STBRDSCN
	int   uk2;                      // 4
	int   scn_len;                 // 4
	char Scene_Label[scn_len];    // _0201_PROLOGUE_BIRTHDAY
	int   sav_len;                 // 4
	char Trophy_Save_Label[sav_len];    // HR_6000_SAVEDATA_ALLSCENES_AASAVE_S004006C05
	int   var_len;                 // 4
	char Lua_VarName[var_len];            //  QDR.HEAVY_RAIN_Var._B26BD95025A240CF9CF52192243A3737()
	int   uk3;                      // 4
	int   uk4;                      // possibly bigFile id ?
	SCENE_ELEMENT[n];  // variable length - parse all b4 next scene Magic
};

struct SCENE_ELEMENT
{
	byte uk0;                      // 1
	uint Comm_Type;          // 0x00001136
	int   uk1;                      // 1
	char Comm_Magic[8];    // STBSCELM
	int   uk2;                      // 3
	0x8 = CommType + ID (Scene or Area) // afaik
	int   scn_len;                 // 
	char Scene_Label[scn_len];    // Label or Var idk ? usually empty
	int   pre_len;                 // 
	char Preload_Message[pre_len];    // PreloadMessageNotSet
	0x8 = CommType + ID (LoadingZone)
	int   end_len;                 // 
	char StopEnd_Message[end_len];    // StopMessageNotSet
};



Storyboard im parsing can be found in my above post SDAT entry file 196 BigFile_PS3.dat  @ offset 76847104  (segs)

Just search for STORYBRD magic, u will find 2 of them

* I have not yet factored in the Bunch of LoadingZone / LoadingContainer definitions / list that preceed each Storyboard, these no doubt are important piece of puzzle.

Why does HR Storyboard look like such a mess versus  B2s

@ MUSHROOM_LT: iin ur pic ur SceneList looks relatively sorted, can u give some insight, or is it sorted by hand ?

Cheers to all & MERRY XMAS
## Post #30
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2017-12-27T16:32:44+00:00
- Post Title: Re: Heavy Rain Tool

Making Progress !  Can now pick any Scene from Storyboard, and get the initial initialization lua scripts & vars for that Scene as well as the AREA (init + geom) Catalog, so in theory can effectively load a level and its mesh collection (all with properly linked & referenced textures -> unlike dumperTool on facepunch.)  honestly not hard to link correct meshes to textures, as same PRIMEDGE block that defines mesh also links specific texture(s) literally right after.

Still trying to find the linkage to the Characters, Anim & Movie (sequence) catalogs.

Using _1301_Nightmare (Madison Intro) as example:-

1. Storyboard links 2x Scenes:-

   Scene [ 235]  Zone [22729]
   Scene [   80]  Zone [ 5754]

2. From .DEP Lookup, Find DataContainer (SDAT entry) with Scene 80

In this file you will find an AREA id: 29, a Lua Initialization script for this area, and the link to the DataContainer that contains the Scene (CATALOG). Decompiled lua script looks something like the following - basically defines AREA, and nodes,cameras, spawn locations, for everything specific to the scene and its static objects.

```

QDR.MADISONHOUSE_Var.OppositeWay = false
QDR.MADISONHOUSE_Var.VarLightOn = false

QDT.ADDRESS.NewPlaced("MADISONHOUSE_Var", "VarAdCrossDown", 0)
QDT.VECTOR.NewPlaced("MADISONHOUSE_Var", "VarAdPosition", 0)
QDT.QUATERNION.NewPlaced("MADISONHOUSE_Var", "VarAdDirection", 0)

QDR.MADISONHOUSE_Var.VarUp6 = false
QDR.MADISONHOUSE_Var._1301TrophyWC = false
QDR.MADISONHOUSE_Var._1301TrophyShowerCut = false
QDR.MADISONHOUSE_Var.VarFridgeClosedArea = false
QDR.MADISONHOUSE_Var.VarPositionZ = 0

QDT.VECTOR.NewPlaced("MADISONHOUSE_Var", "VarPosition", 0)
QDT.ADDRESS.NewPlaced("MADISONHOUSE_Var", "AdDefaultCam", 0)


```


3. The COM_CONT section preceeding, or wrapping the actual AREA section in this INIT file, will contain some links, bottom of those links,we find the actual AREA CATALOG file (id). Going back to DEP lookup we can find the DataContainer (SDAT entry)



4.  Opening up the linked Catalog DataContainer, in the Comm Headers we find a Catalog entry (id:50).  going to the block of that catalog, or the COM_CONT section links, we find a DATA_CONTAINER reference, which points to the SDAT entry containing the actual MESHES, textures, geom, etc.  for Madison' Apartment  (40mb seg file).


So that all said, now only need to explore other linked stuff, and these loading zones,and also important i think si the script zones, script objects.  try to find all other linked catalogs (characters, movies, anim)
## Post #31
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-27T17:49:22+00:00
- Post Title: Re: Heavy Rain Tool

> Reply from Loomy
>
> all with properly linked & referenced textures -> unlike dumperTool on facepunch.

I always knew that it will be easy to read storyboards and then link everything from it. Actually my goal was to find out, was it possible to dump models and textures without that. Also I've been asked to get character models only, and their textures are always in one package with the model and there's no problem to find them.
## Post #32
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2017-12-28T03:39:59+00:00
- Post Title: Re: Heavy Rain Tool

> Reply from daemon1
>
> Loomy wrote:all with properly linked & referenced textures -> unlike dumperTool on facepunch.

I always knew that it will be easy to read storyboards and then link everything from it. Actually my goal was to find out, was it possible to dump models and textures without that. Also I've been asked to get character models only, and their textures are always in one package with the model and there's no problem to find them.

Are u perhaps planning update anytime in future ?  would be much appreciated and super useful for the bigger mesh collections, with some hundred textures to manually apply   atm, its naming meshparts by the parent/attached Material ID ("SHADERCUST"). and Textures by their sequential ID,  if u check the Shadercust block @ 0x1E u get no. of attached textures, and texture ids thereafter.    btw one hacky method to find every single mesh, area or character is to lookup all FXEVENT entries (0x891), or Skeleton (0x7DD) in (Setup)BigFile.DEP file - though HR areas dont come with skel unlike B2s.  Hopefully ur not totally bored with this  ur input could be invaluable.

im trying to write some fixer script, or material list, issue is multiple textures per meshpart, so cant name them according to that, & detecting type of tex, norm/diff/bmp etc. Im guessing its defined somewhere later in same shader block.  though is not issue or priority for me atm,

right now wracking my brain trying to make sense of animation data ^^. motion kits though seem a bit more straight forward.

BTW on sidenote: Are some of HR mesh vertex info stored as ushort (vsize 9 / 15) ?  just seemed odd, but i might be doing it wrong.

Cheers
## Post #33
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-30T15:04:49+00:00
- Post Title: Re: Heavy Rain Tool

> Reply from Loomy
>
> Are u perhaps planning update anytime in future ?
My time is limited. And I prefer to make basic tools for 10 games, rather than one fully complete and user friendly GUI tool for 1 game in the same period of time. I usually only do tools for games in hard cases, when nobody else can do it. In case of B2S the 2 possible problems were textures and edge-compressed faces. Textures appeared to be just variations of JPG and HR is using DDS. And now when PS4 exploit is public, better quality B2S textures are available, and edge compression is not needed.

So to conclude, if after some months you will still not be able to achieve what you want, I can return to quantic dream stuff and do something with it 

> Reply from Loomy
>
> BTW on sidenote: Are some of HR mesh vertex info stored as ushort (vsize 9 / 15) ?
I have no idea what is vsize 9 / 15, but yes, some mesh vertex coordinates were shorts (not ushorts)
## Post #34
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2018-01-04T16:20:07+00:00
- Post Title: Re: Heavy Rain Tool

small progress (if u can call it that) on anim research,

Im focusing on Motion Kits (Graph animation, default motions -> idle, walk, turn, etc.  controller based motions - a bit different to actual movie or sequence based animation, & streamable keyframe anim blocks - however these gmk motions / anims do each reference an external ANIMDATA, block, of which seem compressed or bitpacked somehow, 

each gmk_anim container is specific to a character (or generic for crowds / standard male female)  and in this example has 42 inner blocks.. idk if each is a different motion / specific to bone(s) or time / references to actual animdata blocks.  But take a look, hoping someone more clued up can share some insights.  could these GMK blocks be some kind of skeletal pose/ Spline IK, or graph (hands , feet, etc).  dont see any kind of rotation info, just position xyz over X keyframes / time. 

Attempted to  mapped one such block to an HR skel, (feet) and much to my surprise, it would appear to be some kind of Walking motion.

Bear in mind, i likely attached it to wrong nodes, and the skel itself is possibly scaled down, and the rotation & offset of parent bones affect the result (ie: feet point outward in standing state, thus by animating toes, path of each foot widens over time.   Using root node for anim, it does indeed go straight, but linking both it seem this might just be offsets for knees or leg bone(s).

What is the data ive marked as weights ? it was best guess, but those values strike me as being weight or constraint the 4xdw that follow, could be locks, or bone hierarchy, matrix,  or very likely BoneID Refs. 
.
The flags data, one byte per vector Position transform (3f) that follows after, always 0 / 3 / 12 / 15.  some blocks are all 15.  wild guess is talking to timescale per frame, or weight strength / vertices affected,  from what ive noticed, with footstep anim, when feet in air, flag is 0 or 3, as it makes contact with ground, or slows down, value goes up to 12.. 

after that, 2 sets of Transform tracks (keyframe'd Pos (3f xyz). seems to be for mirrored / opposing body parts running in parallel


Demo Video of this walk anim :- [https://www.youtube.com/watch?v=F__Z-hU57Y0](https://www.youtube.com/watch?v=F__Z-hU57Y0)

gmk block data :-


.
## Post #35
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2018-01-08T09:53:09+00:00
- Post Title: Re: Heavy Rain Tool

AnimData blocks are truly confusing.  For example the animblocks tied to MoKits above have similar index sizes, but the data itself is majority FFFFFFFF and 7F7FFFFF  sprawled with few floats inbetween,  always starting with 0x1500  or 0x15 BE.  if i had to split block by index it come to around 30 bytes .  im thinking bit compression maybe.

Or something like is shown here:- on compression formats

[https://docs.unrealengine.com/udk/Three ... Guide.html](https://docs.unrealengine.com/udk/Three/AnimationCompressionTechnicalGuide.html)

if anyone keen to know more or look into it i can send some samples with notes.

CHeers
## Post #36
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-08T11:11:29+00:00
- Post Title: Re: Heavy Rain Tool

Animation is usually bit compressed. After all 7 or 8 different animation engines I reversed (and each of them was used in a number of games with different changes) I can say its most useless part of the game data. Its fun to look at the animations extracted, but I hardly remember anyone really used that afterwards.

Its usually possible to understand the data layout. The only problematic thing may be coding of rotations. But as far as i know, PS3 SDK covers that.
## Post #37
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2018-04-01T17:13:40+00:00
- Post Title: Re: Heavy Rain Tool

What about ps4 version? Does it work with it? I was able to extract segm files with daemon tools but when im trying to extract segm files i just get empty smd and ascii models. Also will you add support in future for Fahrenheit:Indigo Prophecy? I also dont understand how do i need to set engine.json file,my generated engine.json file is empty.
## Post #38
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-04-01T18:32:09+00:00
- Post Title: Re: Heavy Rain Tool

> Reply from dropoff
>
> What about ps4 version?
ps4 is very different from ps3. no wonder its not working
## Post #39
- Username: Eredus
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 08, 2015 7:39 pm
- Post datetime: 2018-06-07T04:03:37+00:00
- Post Title: Re: Heavy Rain Tool

Any updates on this tool or animations?

There are indeed people like me out there who would really love to get our hands on some of the great mocap in this game.
## Post #40
- Username: MushroomLT
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 02, 2017 8:09 pm
- Post datetime: 2018-09-20T21:05:02+00:00
- Post Title: Re: Heavy Rain Tool

So, after quite a long while, finally an update! 
[https://youtu.be/CzwgLBceaZk](https://youtu.be/CzwgLBceaZk)

There's been quite a lot of progress, but in a nutshell, here's what's new:

Models
SceneGraph parsing
Lua engine
Sequence/Movie parsing and playback engine
Whole new graphics rendering engine written in Java

The entire scene is being run using only native Lua scripts! All the audio is also played by the engine, still have to fix some volumes and cracking.

Sorry for the lag in the video, it's the OBS encoding not keeping up
## Post #41
- Username: mahbod
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 04, 2019 8:20 pm
- Post datetime: 2020-10-14T01:30:06+00:00
- Post Title: Re: Heavy Rain Tool

Where can I download this tool? 
I need this so much
## Post #42
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-04-15T10:06:12+00:00
- Post Title: Re: Heavy Rain Tool

This guy seems to host his tool then delete the links.. classic
## Post #43
- Username: QuasarNebula
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 04, 2023 5:13 am
- Post datetime: 2023-09-09T18:14:44+00:00
- Post Title: Re: Heavy Rain Tool

Please reupload.
