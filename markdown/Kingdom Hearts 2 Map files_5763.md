## Post #1
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-13T01:58:03+00:00
- Post Title: Kingdom Hearts 2 Map files

Does anyone know how to export KH2 map files? I have Falo's dumper tools, but I don't know what file-paths the .map files would be in.
## Post #2
- Username: kkdf2
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Oct 24, 2010 4:26 pm
- Post datetime: 2011-01-15T10:56:02+00:00
- Post Title: Kingdom Hearts 2 Map files

Hi.

> Reply from Mirrorman95
>
> Does anyone know how to export KH2 map files? I have Falo's dumper tools, but I don't know what file-paths the .map files would be in.
Falo's dumper already includes file-paths the .map files.
However it'll be support for only kh2 final mix.

In nametbl.txt the following lines are available:

```
map/jp/al00.map
map/jp/al01.map
...

```


If you have non final mix, it'll be good challenge to modify "jp" by the country/language code such as "us" and "en". I don't know exact token because I don't acquire such version. sorry!

I got 273 map files by extraction.

Thanks.
## Post #3
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-20T01:52:27+00:00
- Post Title: Kingdom Hearts 2 Map files

I made a nametable as you described, and tried it with both my Final Mix and USA versions, with jp, en, and us, and still got nothing. What do I do? Is it just that it won't work on a Vista?
Also, is there a way of using your mdlx animator as a viewer if I don't have a mset for it?
## Post #4
- Username: kkdf2
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Oct 24, 2010 4:26 pm
- Post datetime: 2011-01-22T07:20:10+00:00
- Post Title: Kingdom Hearts 2 Map files

Hi Mirrorman95.

> Reply from Mirrorman95
>
> I made a nametable as you described, and tried it with both my Final Mix and USA versions, with jp, en, and us, and still got nothing. What do I do? Is it just that it won't work on a Vista?
Sorry, I recalled the correct way.

Copy KH2.IMG (3GB!) to your dumper folder. Then, launch the modified script:

```
kh2_file_dumper.exe KH2 -dT
```


The dumper's help says why it is needed:

```
The included KH2.IDX is from "Final Mix +".
I modified it to merge ALL 20 IDX files into 1
```

falo includes modified KH2.IDX so that we can extract much files from game archive.

> Also, is there a way of using your mdlx animator as a viewer if I don't have a mset for it?
sorry, there is no way to display standalone mdlx. perhaps it may be possible in the far future... yaz0'rs viewer is so excellent, wouldn't it benefit you?

Thanks.
## Post #5
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-22T08:55:16+00:00
- Post Title: Kingdom Hearts 2 Map files

I already did that. I think something is fundamentally wrong with my Vista computer that isn't wrong with yours. Is there any way you could upload the MAP files? Or tell me your operating system so I could try the extraction on that kind of computer?
## Post #6
- Username: kkdf2
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Oct 24, 2010 4:26 pm
- Post datetime: 2011-01-22T11:21:15+00:00
- Post Title: Kingdom Hearts 2 Map files

Hi Mirrorman95

> I already did that. I think something is fundamentally wrong with my Vista computer that isn't wrong with yours.
hmm it is weird.

by the way, can you successfully grab one or more contents such as mdlx files, with the dumper? or it doesn't extract any files?

> Is there any way you could upload the MAP files? Or tell me your operating system so I could try the extraction on that kind of computer?
sorry i cannot upload the map files. plz forgive me 

I'm using windows 7 64bit build 7600. the dumper stored 4,878 files as contents.

if you are interested in trying to extract map files with [another dumper](http://kkdf2.sakura.ne.jp/pcsx2lair/expack1e.7z), here it is.
pass ][

Thanks
## Post #7
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-22T15:53:10+00:00
- Post Title: Kingdom Hearts 2 Map files

> Reply from kkdf2
>
> Hi Mirrorman95
I already did that. I think something is fundamentally wrong with my Vista computer that isn't wrong with yours.
hmm it is weird.

by the way, can you successfully grab one or more contents such as mdlx files, with the dumper? or it doesn't extract any files?
Is there any way you could upload the MAP files? Or tell me your operating system so I could try the extraction on that kind of computer?
sorry i cannot upload the map files. plz forgive me 

I'm using windows 7 64bit build 7600. the dumper stored 4,878 files as contents.

if you are interested in trying to extract map files with another dumper, here it is.
pass ][

Thanks

Thank you! I can extract many more files then I could before!
But I still can't extract the MAPs.

I can extract most files like MDLXs, but specific files in the nametable I cannot obtain for some reason. Like any libretto file, world symbol, or MAP file.
The MAP viewer, by the way, is awesome at reading wave files within MDLX files. Much appreciated!

And I'm using Windows Vista 32bit with an ATI Radeon Xpress 1250 graphics card and an AMD Turion 64 X2 Mobile Technology TL-58 dual processor. My laptop's at least 3 years old.
## Post #8
- Username: denetsu
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 05, 2010 2:03 pm
- Post datetime: 2011-01-24T13:34:38+00:00
- Post Title: Kingdom Hearts 2 Map files

Where i can find a map viewer?
## Post #9
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-24T15:31:14+00:00
- Post Title: Kingdom Hearts 2 Map files

> Reply from denetsu
>
> Where i can find a map viewer?

The sixth post of this topic.
## Post #10
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-01-24T22:11:38+00:00
- Post Title: Kingdom Hearts 2 Map files


## Post #11
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-24T23:58:31+00:00
- Post Title: Kingdom Hearts 2 Map files

Please for the love of god tell me how you did that.
## Post #12
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-01-25T01:16:43+00:00
- Post Title: Kingdom Hearts 2 Map files

> Reply from Mirrorman95
>
> Please for the love of god tell me how you did that.
I sent you a PM. Maybe it'll help you out.
## Post #13
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-25T01:28:28+00:00
- Post Title: Kingdom Hearts 2 Map files

Thank you.
## Post #14
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2011-01-25T01:36:29+00:00
- Post Title: Kingdom Hearts 2 Map files

I too would like to know that if it's possible, thanks in advance.
## Post #15
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-01-25T01:42:06+00:00
- Post Title: Kingdom Hearts 2 Map files

> Reply from Mirrorman95
>
> Thank you.
You are most welcome!

> Reply from Panzah
>
> I too would like to know that if it's possible, thanks in advance.
Sent you a PM as well then.
## Post #16
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-01-25T01:46:26+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

So I ran the .bat extractors included on my KH2 (not Final Mix) disc and got several files but I didn't get any .map files which is one of the file types the viewer mentions supporting. It appears that the "Explode maps" .bat is supposed to exctract them but I only get other files.

Also for some reason no matter what file I drop on the window I get a D3D Error and then an empty viewer window.

Am I doing something wrong?
## Post #17
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-01-25T01:57:49+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Zerox
>
> So I ran the .bat extractors included on my KH2 (not Final Mix) disc and got several files but I didn't get any .map files which is one of the file types the viewer mentions supporting. It appears that the "Explode maps" .bat is supposed to exctract them but I only get other files.

Also for some reason no matter what file I drop on the window I get a D3D Error and then an empty viewer window.

Am I doing something wrong?
The viewer window only works for MAP files, not MDLX files or otherwise. I've sent you a PM as well, although I have no idea why none of you can extract the *.map files.. I followed kkdf2's instructions and they extracted fine for me.. I didn't do anything special or different from what was already mentioned in this thread.
## Post #18
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-25T03:37:37+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Krisan Thyme
>
> Zerox wrote:So I ran the .bat extractors included on my KH2 (not Final Mix) disc and got several files but I didn't get any .map files which is one of the file types the viewer mentions supporting. It appears that the "Explode maps" .bat is supposed to exctract them but I only get other files.

Also for some reason no matter what file I drop on the window I get a D3D Error and then an empty viewer window.

Am I doing something wrong?
The viewer window only works for MAP files, not MDLX files or otherwise. I've sent you a PM as well, although I have no idea why none of you can extract the *.map files.. I followed kkdf2's instructions and they extracted fine for me.. I didn't do anything special or different from what was already mentioned in this thread.

I have a Vista. Is that why I couldn't extract the files?
## Post #19
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-01-25T04:52:58+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

It's possible. I'm on Windows 7 myself though, which isn't too fundamentally different from Vista.. Who knows really.
## Post #20
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-01-25T07:17:38+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Be sure that you are doing this with KH2 Final Mix. It doesn't work on the normal Kingdom Hearts 2 as it doesn't use the combined .IDX file.

There's so many maps in this! And some are hard to find as their categorized with an odd world such as the Keyblade Graveyard where you fight the lingering sentiment.

Here's some maps of interest I've found so far.

```
dc01 Mickey's Library
dc07 Keyblade Graveyard
he00 Olympus Coliseum Arena
he01 Olympus Coliseum Entrance Gate
he03 Underworld Trophy Room
he04 Coliseum Entrance Room with Trophies
eh03 Complete Memory Skyscraper
eh04 Castle of Nothingness
eh05 Kairi's Cell
eh18 Altar of Naught Door to Nothingness
eh19 Memory Skyscraper Incomplete
eh29 Altar of Naught
tt08 Clock Tower
tt14 Mansion Gate
tt18 Namine's Room
tt21 Underground Lab Sora's Monitoring Room Broken Screens
tt22 Other Memory Pods
tt23 Sora's Memory Pod
tt25 Outside Yen Sid's Tower
tt27 Yen Sid's Office
tt33 Station of Awakening connected by Stain Glass stairs
tt34 Sora Station of Awakening
tt35 Yensid Train
```


Edit: So I converted the Coliseum Entrance but it appears the legs of the statues are still not there, there's geometry for them at all. i didn't see the legs of the statues in the viewer but I had hoped it was just a rendering error. I could always rebuild the legs that's not too big of an issue, just curious to know if anyone else is having the problem of their leg's not showing up.
## Post #21
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-25T08:06:03+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

My favorite is eh03, Memory's Skyscraper.
## Post #22
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-01-25T09:28:33+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Zerox
>
> Edit: So I converted the Coliseum Entrance but it appears the legs of the statues are still not there, there's geometry for them at all. i didn't see the legs of the statues in the viewer but I had hoped it was just a rendering error. I could always rebuild the legs that's not too big of an issue, just curious to know if anyone else is having the problem of their leg's not showing up.
The legs are indeed missing, but I believe that may be because (for whatever reason) that they are a prop\actor in the level, and not part of the actual static map. I couldn't venture to guess why that would be the case, but it's the only explanation I can ascertain at the moment. It seems far too isolated and clean to be a dumping error of some kind..

Although it could possibly be a problem with the viewer itself, being unable to read\render the legs.. very odd if it is, to be so isolated as that. But yeah.

> Reply from Mirrorman95
>
> My favorite is eh03, Memory's Skyscraper.
Yeah, I agree. That's just an awesome map.
## Post #23
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-01-25T13:56:29+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

HB14 is Castle Oblivion.
## Post #24
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-25T15:34:40+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

These files all correspond to the world digits of the room mod. I modified this list from a Room Mod chart. Unfortunately, the Twilight Town index is not complete. Also, some of the Tron maps don't load correctly. And I figured out how to extract the maps on my own.

es00 - The Dark Margin
es01 - Empty

tt00 - The Empty Realm
tt01 - Roxas's Room
tt02 - The Usual Spot
tt03 - Back Alley
tt24 - On The Train
tt34 - Station of Awakening

di00 - Beach
di01 - The Main Road
di02 - Main Island: Shore

hb00 - Villain's Vale
hb01 - The Dark Depths (With Heartless Army below)
hb02 - The Great Maw
hb03 - Villain's Vale
hb04 - Villain's Vale 
hb05 - Ansem's Study
hb06 - Villain's Vale
hb07 - Restoration Site (Before Destruction)
hb08 - Bailey (Before Destruction)
hb09 - Borough
hb10 - Marketplace
hb11 - Castle Corridors
hb12 - Heartless Manufactory
hb13 - Merlin's House
hb14 - Castle Oblivion
hb15 - Ansem's Study before Ansem's exile
hb16 - Ravine Trail
hb17 - The Great Maw (1000 Heartless Conditions)
hb18 - Restoration Site (After Destruction)
hb19 - Bailey (After Destruction)
hb20 - Castle Corridors during Nobody and Heartless fight (Sealed)
hb21 - Cavern of Remembrance: Depths
hb22 - Cavern of Remembrance: Mining Area
hb23 - Cavern of Remembrance: Engine Chamber
hb24 - Cavern of Remembrance: Mineshaft
hb25 - Transport to Remembrance
hb26 - Garden of Assemblage
hb27 - Room of Sleep and Stairwell
hb32 - The Old Mansion (Vexen's Area)
hb33 - Station of Remembrance (Larxene's Area)
hb34 - Ravaged Destiny Islands (Zexion's Area)
hb36 - Villain's Vale
hb38 - Station of Oblivion (Marluxia's Area)

bb00 - Entrance Hall
bb01 - Parlour
bb02 - Belle's Room
bb03 - Beast's Room
bb04 - Ballroom
bb05 - Ballroom
bb06 - Courtyard
bb07 - The East Wing
bb08 - The West Hall
bb09 - The West Wing
bb10 - Dungeon
bb11 - Undercroft
bb12 - Secret Passage
bb13 - Bridge
bb14 - Ballroom
bb15 - Bridge

he00 - Colosseum Arena
he01 - Colosseum Gates 
he02 - Colosseum Gates (destroyed)
he03 - Underworld Entrance
he04 - Colosseum Foyer
he05 - Valley of the Dead
he06 - Hades's chamber
he07 - Cave of the Dead: Entrance
he08 - Pete Battle
he09 - The Underdrome
he10 - Cave of the Dead: Inner chamber
he11 - Underworld Cavern: Entrance
he12 - The Lock
he13 - The Underdrome
he14 - Colosseum Gates (destroyed, night)
he15 - Cave of the Dead: Passage
he16 - Underworld Caverns: The lost road
he17 - Underworld Caverns: Atrium
he18 - Colosseum Gates (Hydra battle)
he19 - Underdrome

al
00 - Agrabah
01 - Bazaar
02 - The Peddler's Shop
03 - The Palace
04 - Vault
05 - Above Agrabah
06 - Palace Walls
07 - The Cave of Wonders Entrance
09 - The Cave of Wonders Stone
10 - The Cave of Wonders Treasure Room
11 - Ruined Chamber
12 - The Cave of Wonders Valley of Stone
13 - The Cave of Wonders Chasm of Challenges
14 - Agrabah Dunes (Jafar chase)
15 - The Peddler's Shop

po
00 - 100 Acre Wood World Selection
01 - The Big Tree
02 - Pooh Bear's House
03 - Rabbit's House
04 - Piglet's House
05 - Kanga's House
06 - The Day of a Wind
07 - Eye the collection of Honey
08 - Flower Fence Valley
09 - The Spooky Cave 

lk
00 - Pride Rock
02 - King's den
03 - Long gourge place
04 - The Savanna
05 - Elephant graveyard
06 - Gorge
07 - Wastelands
08 - Jungle
09 - Oasis
10 - Pride rock (restored)
11 - Oasis (Night)
12 - Overlook
13 - Peak
14 - Scar's darkness
15 - (Looks like Savana, cept it didn't have a proper title and I couldent leave the area)
16 - (Where Mufasa died)

lm01 - Treasure Room
lm02 - Undersea Courtyard
lm03 - Submarine Open Space (02 Recolored)
lm04 - Music Stage
lm05 - Sunken Ship 
lm06 - Wrath of the Sea (Daytime)
lm07 - Seashore (Nighttime)
lm08 - Seashore (Evening)
lm09 - Wrath of the Sea 
lm10 - Wedding Ship

dc00 - Audience chamber
dc01 - Library
dc02 - Colonnade
dc03 - Courtyard
dc04 - The Hall of the Cornerstone (With Thorns)
dc05 - The Hall of the Cornerstone
dc06 - Gummi Hanger
dc07 - Gathering Place

ti00 - Cornerstone Hill
ti01 - Pier
ti02 - Waterway
ti03 - Wharf
ti04 - Lilliput
ti05 - Building Site
ti06 - Scene of the Fire
ti07 - Mickey's House
ti08 - Villain's Vale

tr
00 - Pit Cell
01 - The Canyon
02 - Game Grid (Crash)
03 - Data Space (Crash)
04 - I/O Tower (Crash)
05 - I/O Tower: Communications Tower (Crash)
06 - Simulation Hanger
07 - Solar Sailor Simulation (Crash)
08 - Central Computer
09 - Central Computer Core
10 - Solar Sailor Simulation
11 - Repeat of 08

eh
00 - Where Nothing Gathers
02 - Fragment's Crossing
03 - Memory's Skyscraper
04 - The Brink of Despair
05 - The Soundless Prision
06 - Nothing's Call
07 - Crooked Ascension (Going up)
08 - Crooked Ascension (Going down)
09 - Twilight's View
10 - Hall of Empty Melodies
11 - Something of Empty Melodies (Where you meet up with Kairi and Riku)
12 - Naught's Skyway
13 - Proof of Existence
14 - Havoc's Divide
15 - Saix Boss Area
16 - Naught's Approach
17 - Something something passage (Where Maleficent and Pete fight the heartless swarm. )
18 - The Altar of Naught (Oddly the Kingdom Hearts moon is still full and there is no door.)
19 - Memory's Contortion (where you fight Xemnas 1)
20 - The world of nothing (the final fight area, with exit)
21 - The world of nothing (where you fight Roxas)
22 - Station of Awakening (where you fly around in the litte thing with Riku and Sora)
23 - Armor 2 fight (Dragon)
24 - Armor 1 fight
25 - Core (with attackable core! (Crashes if you attack it enough) )
26 - Twin cannons (With working reaction commands)
27 - First area of final battle
28 - Second area of final battle
29 - Altar of Naught (no kingdom hearts moon)

wm00 - World Map
## Post #25
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2011-01-26T10:24:54+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Krisan Thyme
>
> Mirrorman95 wrote:Thank you.
You are most welcome!
Panzah wrote:I too would like to know that if it's possible, thanks in advance.
Sent you a PM as well then.
pm me too
## Post #26
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-01-26T16:05:44+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Wow Castle Oblivion's Map! That's awesome. Thanks for the list Mirrorman seems to match ours quite well.

You said you've made it work now so I'm curious have you or anyone else been successful in dumping Destiny Islands maps?
They're in the .bat file but don't appear to be dumped.
## Post #27
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-01-26T19:41:40+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Zerox
>
> Wow Castle Oblivion's Map! That's awesome. Thanks for the list Mirrorman seems to match ours quite well.

You said you've made it work now so I'm curious have you or anyone else been successful in dumping Destiny Islands maps?
They're in the .bat file but don't appear to be dumped.
He contacted me here recently and asked me to look into it, I was able to dump them successfully.
## Post #28
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-01-26T19:45:19+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Yeah I dumped them. Nothing special though. You can see the Island but it's in very low quality.
## Post #29
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-01-26T23:17:55+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Krisan Thyme
>
> Mirrorman95 wrote:Thank you.
You are most welcome!
Panzah wrote:I too would like to know that if it's possible, thanks in advance.
Sent you a PM as well then.

I hate to bug you, but would you mind sending me a PM as well? When it's convenient for you, of course. Thanks!   

> Reply from Krisan Thyme
>
> Yeah I dumped them. Nothing special though. You can see the Island but it's in very low quality.
Oh, I still think that's pretty awesome. I don't have a codebreaker or any other ps2 add on like that, but I was able to emulate KH2 with pcsx2 and run the code that lets you run around on destiny island's mainland. That was pretty fun.
## Post #30
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-26T23:50:53+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Krisan Thyme
>
> Zerox wrote:Wow Castle Oblivion's Map! That's awesome. Thanks for the list Mirrorman seems to match ours quite well.

You said you've made it work now so I'm curious have you or anyone else been successful in dumping Destiny Islands maps?
They're in the .bat file but don't appear to be dumped.
He contacted me here recently and asked me to look into it, I was able to dump them successfully.

I eventually found out how to dump them myself. It turns out, I didn't modify the bat file correctly to map to the F drive instead of the E drive.
## Post #31
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-01-27T00:06:19+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Mirrorman95
>
> I eventually found out how to dump them myself. It turns out, I didn't modify the bat file correctly to map to the F drive instead of the E drive.
Ahhh~
Figures it'd be something like that. Oh well, glad it works for you now!
## Post #32
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-27T04:47:44+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

This program can extract any file, including the Tron and Nightmare keyblades. Falo's extractor couldn't even do that. If you can find the pathname, you have the file. I'm currently extracting the soundclips from Space Paranoids. Thank kkdf for epack1e!
## Post #33
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-01-28T06:45:52+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

i managed to extract some of the audio files from kh1 with Sora, Donald, and goofy, like Sora saying deep freeze! the things he says while hes in battle.. theres also a Japanese Sora too.... now only if i figured out how to rip the sounds from cut-scenes.... i cant get the map files cause my CD drive is screwed up  Wish i could... seriously... that one pic in twilight town looks amazing...
## Post #34
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-01-28T19:21:51+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

I ripped sound files from KH2FM with, er... can't remember. One of those dumpers that dumps nearly anything. It was like 3 years ago though, I burned them onto a CD for safe keeping. The format was new to me, but I found a program that could open and convert them. I noticed that a lot of the files that were huge in size also had a negative bitrate (I think), or something, I'm going on a memory of three years ago. I think they were placed there to take up space, because I could never convert them. 

I managed find all the clips of Sora's reunion speech with Riku, except for one stupid line. How annoying.   There's also a few of sora grunting or huffing. Out of context and without the game showing what's going on, those sound so horribly horribly wrong.  

Oh, I also wanted to say thanks to kkdf2 for the map viewer and to Krisan!   

I also found something I thought was interesting. Maybe it's no big deal, but i found it cool. The collision for first destiny island map (the secret place) seems to show the entire destiny island base map or mesh.. whatever you call it, minus the foliage layers and some objects. 




I thought this was weird because that map was only used during the short clip at the very end, where Sora walks into the secret place. Yet, they used a collision base that was basically the entire island, and not just the part for the secret place. 

At first I thought it was the mesh they used for Kairi's cutscene where we see the little island in the distance, but I noticed at least one difference. The collision has the mesh part for the vine that goes up between the two stairs/ramps/whatever on the giant tree, Kairi's cutscene island doesn't.


So... kinda interesting IMO.
## Post #35
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-01-28T23:54:07+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from SoftIce
>
> I ripped sound files from KH2FM with, er... can't remember. One of those dumpers that dumps nearly anything. It was like 3 years ago though, I burned them onto a CD for safe keeping. The format was new to me, but I found a program that could open and convert them. I noticed that a lot of the files that were huge in size also had a negative bitrate (I think), or something, I'm going on a memory of three years ago. I think they were placed there to take up space, because I could never convert them. 

I managed find all the clips of Sora's reunion speech with Riku, except for one stupid line. How annoying.   There's also a few of sora grunting or huffing. Out of context and without the game showing what's going on, those sound so horribly horribly wrong.  

Oh, I also wanted to say thanks to kkdf2 for the map viewer and to Krisan!   

I also found something I thought was interesting. Maybe it's no big deal, but i found it cool. The collision for first destiny island map (the secret place) seems to show the entire destiny island base map or mesh.. whatever you call it, minus the foliage layers and some objects. 




I thought this was weird because that map was only used during the short clip at the very end, where Sora walks into the secret place. Yet, they used a collision base that was basically the entire island, and not just the part for the secret place. 

At first I thought it was the mesh they used for Kairi's cutscene where we see the little island in the distance, but I noticed at least one difference. The collision has the mesh part for the vine that goes up between the two stairs/ramps/whatever on the giant tree, Kairi's cutscene island doesn't.


So... kinda interesting IMO.

0_o holy crap... thats amazing... for the love of god i would love to rip saixs voice saying "If I had a heart, this would be where I die of laughter." im trying to rip some of the models from the cgi fmv sequence's XD hopefully it works XD lol...
## Post #36
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-01-29T23:51:51+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Murodragon
>
> 0_o holy crap... thats amazing... for the love of god i would love to rip saixs voice saying "If I had a heart, this would be where I die of laughter." im trying to rip some of the models from the cgi fmv sequence's XD hopefully it works XD lol...

I know isn't it? It's all thanks to other people's hard work though. All I did was run their programs to find the files. So props to whoever created whatever dumper it was that I used to get those files.   

I'll go through the sound files I have on my CD and see if I can find the one of Saix that you wanted. Hm, I'm pretty sure I saved all of them, but the ones that really interest me are Kairi's, Sora's, Riku's, Roxas's, Namine's and Axel's... but I think I saved everything that was convertible just because.

Does 'fmv' mean 'full motion video'? I'm so behind on the lingo these days. If you're talking about the cgi animated opening and ending sequences, you won't be able to rip any models from those, because they're pre-rendered and all there is is a video clip. if you mean just the video frames as jpg or bmp, I have copies of the opening and endings and I can send you a clip of the part that you want if you'd like.

I would love love LOVE to get my hands on the cgi models used in the opening and ending sequences though, as I'm sure every single fan in existence would as well. Delicious super extreme high poly-ness... I want.
## Post #37
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-30T01:34:57+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

If you use PSound on KH2.IMG, provided you hit the stop button after the percentage goes from 76% back to 42%, which if left unchecked will copy the same files indefinitely, you can select, convert, and extract all the cutscene sounds and other sounds from the game as wav files. Same with Kingdom Hearts 1, only it does not repeat.
## Post #38
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2011-01-30T13:14:11+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

how can i convert a py file to obj ?
## Post #39
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-01-30T16:59:14+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

yeah i would love to get my hands on those cgi models too they look amazing D:.. i could recall seeing a program to extract ff13 cgi models but i forgot what it was called... but anyways back on kh2, extracting the cutscene sounds and hearing Sora grunting without seeing what hes doing sounds wrong XDD lol i actually laughed.
## Post #40
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-01-30T17:04:49+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

What do you mean by CGI? You mean like the ending movie and that?
## Post #41
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-01-30T18:14:47+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

yeah like the little movies that square puts like in the intro and the end
## Post #42
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-01-30T18:52:32+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Oh my...You know they are recorded right? You can't capture from a recording.
## Post #43
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-01-30T19:44:37+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Dx crap... oh well xDDDD
## Post #44
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-01-31T01:21:41+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

now if there was a map viewer for ard files which were kh1 map files D: that would be something... :3 i ripped some the cutscene audio from both games but they didnt get everything  sadly..
## Post #45
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-01-31T05:54:11+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Murodragon
>
> now if there was a map viewer for ard files which were kh1 map files D: that would be something... :3 i ripped some the cutscene audio from both games but they didnt get everything  sadly..

Oh man, I want a KH map viewer too. The closest we can get is the giant destiny islands glitch where you can hop around in the air and run on the water. Best game glitch ever!
## Post #46
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-01-31T21:12:28+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from SoftIce
>
> Murodragon wrote:now if there was a map viewer for ard files which were kh1 map files D: that would be something... :3 i ripped some the cutscene audio from both games but they didnt get everything  sadly..

Oh man, I want a KH map viewer too. The closest we can get is the giant destiny islands glitch where you can hop around in the air and run on the water. Best game glitch ever!

haha that glitch is amazing   XDDDDDDD LOL how did you get your kairi model to pose like that in your icon??? anyway.. im putting OBJ Kingdom Hearts files in Photoshop cs5 seriously they look amazing ...
## Post #47
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-02-01T17:06:28+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

So I've been trying to convert the Destroyed Coliseum map to .obj or anything really. But whenever I run the .py script in Blender I get the following error:

"Memory Error

get traceback failed"

Every time I do it I get that. The normal Coliseum worked just fine though. Has anyone else been able to convert it or does anyone know how to fix the error?
## Post #48
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-02-01T17:07:58+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

It does that if your computer runs out of memory. Try it on another computer. Trust me, I'm used to that...
## Post #49
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-02-01T19:07:05+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from ultimaespio
>
> It does that if your computer runs out of memory. Try it on another computer. Trust me, I'm used to that...
Ah I see. Well I commandeered a friends computer that has something like 2GB ram and it worked much better than me and my 768MB.

Now I finally can finish my restoration of those gold statues and their missing legs. Thanks.
## Post #50
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-02-02T07:10:51+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

ps sound is driving me nuts.... seriously it rips everything but the first few cutscenes on destiny islands from kh1.. idk whats up with that...
## Post #51
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2011-02-02T14:20:49+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Can somebody post an image of the world map? How does it look? I've been searching for a good KH2 map for ages.
## Post #52
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-02-02T16:04:33+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Murodragon
>
> ps sound is driving me nuts.... seriously it rips everything but the first few cutscenes on destiny islands from kh1.. idk whats up with that...

Sometimes the VAG sounds are compressed, which can't be found by manual extraction and require you to know the filepaths of the files and have a KH1 manual extractor like Falo's, if it will extract it for you. Also, the first scene of every Kingdom Hearts game is pre-rendered, and I haven't been able to extract a KH1 movie file without it being so large that my computer crashes. Seriously, the largest file I can extract with any KH extractor is kingdom.img, which 1.## GB.

Seriously though, I have no idea how to extract the files from Re:Chain of Memories. I tried Falo's extractor and a hex editor on both the Japanese and English versions of the game, but had no luck. I have no idea how Zerox managed to find Halloween Town Riku.
## Post #53
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2011-02-02T16:44:41+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Maybe he just used a halloween texture which can be got without extracting the files.
But your're right, there a definitely some Re:CoM exclusive models I would like to get my hands on like Marluxia's 2nd and 3rd form or the young Namine etc.
## Post #54
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-02-02T18:31:06+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

well.. some com files are in kh2 final mix.. if you rip them  and they contain most of the organization 13 members like Marluxia.. D: i haven't been able to find Zexion though XD...
## Post #55
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-02-02T18:46:21+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Mirrorman95
>
> Murodragon wrote:ps sound is driving me nuts.... seriously it rips everything but the first few cutscenes on destiny islands from kh1.. idk whats up with that...

Sometimes the VAG sounds are compressed, which can't be found by manual extraction and require you to know the filepaths of the files and have a KH1 manual extractor like Falo's, if it will extract it for you. Also, the first scene of every Kingdom Hearts game is pre-rendered, and I haven't been able to extract a KH1 movie file without it being so large that my computer crashes. Seriously, the largest file I can extract with any KH extractor is kingdom.img, which 1.## GB.

Seriously though, I have no idea how to extract the files from Re:Chain of Memories. I tried Falo's extractor and a hex editor on both the Japanese and English versions of the game, but had no luck. I have no idea how Zerox managed to find Halloween Town Riku.

He got it from me. I ripped it with Texmod from PCSX2.
## Post #56
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-02-02T19:01:11+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

now... D: if only i knew the filenames for the compressed VAG files i will be able to extract them with falos amazing dumper tool XDDDD
## Post #57
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-02-03T00:10:19+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from ultimaespio
>
> Mirrorman95 wrote:Murodragon wrote:ps sound is driving me nuts.... seriously it rips everything but the first few cutscenes on destiny islands from kh1.. idk whats up with that...

Sometimes the VAG sounds are compressed, which can't be found by manual extraction and require you to know the filepaths of the files and have a KH1 manual extractor like Falo's, if it will extract it for you. Also, the first scene of every Kingdom Hearts game is pre-rendered, and I haven't been able to extract a KH1 movie file without it being so large that my computer crashes. Seriously, the largest file I can extract with any KH extractor is kingdom.img, which 1.## GB.

Seriously though, I have no idea how to extract the files from Re:Chain of Memories. I tried Falo's extractor and a hex editor on both the Japanese and English versions of the game, but had no luck. I have no idea how Zerox managed to find Halloween Town Riku.

He got it from me. I ripped it with Texmod from PCSX2.

What is Texmod?
## Post #58
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2011-02-03T01:11:30+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Mirrorman95
>
> 
What is Texmod?
[Texmod](http://wiki.guildwars.com/wiki/Guide_to_modifying_in-game_graphics) is a tool for filtering, saving and even replacing textures in nearly all DirectX applications. It works quite well with PCSX2 emulator but requieres a lot of patience and of course in most cases playtime to get what you want.
## Post #59
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-04T01:45:27+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Murodragon
>
> 
haha that glitch is amazing   XDDDDDDD LOL how did you get your kairi model to pose like that in your icon??? anyway.. im putting OBJ Kingdom Hearts files in Photoshop cs5 seriously they look amazing ...

I love that glitch.  I was bored once and just ran and ran in one direction trying to see how far out I could get from the island and the 'sky'.   

I aquired a posable rigged kairi thanks to the wonderful ChrisSquareFan, and his mdls exporter program.    

> Reply from ChrisSquareFan
>
> The test version:
http://filebeam.com/6df0f73f4ba448b49280f7e54f0f220e
Launch UI.exe. Only fbx works now, do not use paths with spaces.
Also, you must turn backface culling on in your 3d software.
Enjoy!

just so you know, the requirments are:
.NET framework 4, VC++ 2010 redist:
http://www.microsoft.com/downloads/en/d ... bf0912db84

You also need these two dlls. If you google them you should find them. If you can't I can always send you a PM with a link to them or something.

msvcp100d.dll
msvcr100d.dll

Also, only FBX 6.0 binary or ascii work for me. fbx is supported by both maya and max, and I'm not sure about other 3d programs. You can get an educational free version of maya (that I use) and I think you can get one for max as well.
## Post #60
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-02-04T03:02:56+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

The contents of this post was deleted because of possible forum rules violation.
## Post #61
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-02-04T03:15:13+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

The contents of this post was deleted because of possible forum rules violation.
## Post #62
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-02-04T04:39:35+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

The contents of this post was deleted because of possible forum rules violation.
## Post #63
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-02-04T05:02:01+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Mm, the viewer should work.
Anyone having the same issue?
## Post #64
- Username: denetsu
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 05, 2010 2:03 pm
- Post datetime: 2011-02-04T06:01:53+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from kkdf2
>
> Hi Mirrorman95
I already did that. I think something is fundamentally wrong with my Vista computer that isn't wrong with yours.
hmm it is weird.

by the way, can you successfully grab one or more contents such as mdlx files, with the dumper? or it doesn't extract any files?
Is there any way you could upload the MAP files? Or tell me your operating system so I could try the extraction on that kind of computer?
sorry i cannot upload the map files. plz forgive me 

I'm using windows 7 64bit build 7600. the dumper stored 4,878 files as contents.

if you are interested in trying to extract map files with another dumper, here it is.
pass ][

Thanks

Wow thanks! your job are amazing!

But i have one problem when i try to execute the .py script in Blender 2.4.8a

In this line (not matter what map) say: Syntaxis error: Invalid Token :S

coords = [[-36,53,120,053,11,46185],[-32,752,120,053,20,58285],[-39,955,106,596,24,70786],[-44,564,106,596,13,58086],[-36,53,120,053,11,46185],[-39,955,106,596,24,70786],[-45,35,106,596,7,610865],[-36,53,120,053,11,46185],[-44,564,106,596,13,58086],[-36,53,120,053,11,46185],[-45,35,106,596,7,610865],[-37,175,120,053,6,567848]]

Blender 2.4.8a has Python 2.5.2 not 2.5.4 like you say in the code  

Why all you files has password?   

Oh! one last question, your model viewer can export animations?
Works on Win 7?
## Post #65
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2011-02-04T12:32:40+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from yaz0r
>
> Mm, the viewer should work.
Anyone having the same issue?

It doesn't seem to work with the KH mdls files anymore, but the mdlx files of KHII look much better and the compatibility has also improved.

Thank you very much yaz0r.
## Post #66
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-04T22:47:06+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

The contents of this post was deleted because of possible forum rules violation.
## Post #67
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-02-04T23:54:43+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

@Azurfan: so the KH2 models/map are working for you? I will look at the KH models.

@SoftIce: I always drop models on the viewer, but open menu should work too (I occasionaly use it). Can you make a screenshot of those "black box" thingy?
## Post #68
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-05T00:45:44+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

can we extract kh2 model yet
## Post #69
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-05T01:29:01+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from yaz0r
>
> @Azurfan: so the KH2 models/map are working for you? I will look at the KH models.

@SoftIce: I always drop models on the viewer, but open menu should work too (I occasionaly use it). Can you make a screenshot of those "black box" thingy?

Sure thing. Holy crud, I'm happy you're still around.   


The highlighted model was the one that I dropped onto it. I found that it works best for me if I drop the model onto the exe icon and let the model viewer open that way.

The box will hover up and down. If there's no matching mset, the viewing window is blank, usually. 



Although I get this when I drop most sora mdlx models onto it, without the msets (I don't have those on me). 
Map files do not show up in the viewer, but I can see their components listed on the sidebar, by the way. 

I know if you're trying to debug something with your program, you might need to know some of the information about the computer I'm running it on. Here's the basics. Let me know if you wanted to know something else about what computer I'm using. (it's an old Dell Dimension)

XP, home edition, service pack 3. 
pentium 4 @ 2.40GHz, and 1GB of ram. 
DirectX version is 9.0c (4.09.0000.0904)
these things are also enabled for directx: directdraw acceleration, direct3d acceleration, agp texture acceleration
Video card is Radeon 9500 pro 

When I checked the directx files with the directx dialog, I also got this fun message:
The file amstream.dll is missing!n The file d3d9d.dll is a debug version, which will run slower than the retail version., You should reinstall DirectX to get the latest version.

So... it might just be that my directx installation is bad, and I need to reinstall the entire thing. I'll try that, and let you know if it changes anything to do with the viewer.

Yay, I'm so happy to see you're still interested in KH.
## Post #70
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-02-05T18:37:14+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

So, SoftIce, why do you have two models for highpoly Sora? Is he different in Final Mix?

Also, whenever I try to drag a model into the new viewer, it shows me all the instances and whatnot on the left sidebar, but not the actual model, or even a black bar, no matter which model it is, whether or not I has a corresponding MSET.
## Post #71
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-02-05T19:09:28+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Seems to be working fine here. (although, none of the buttons seem to do anything)


> Reply from Mirrorman95
>
> So, SoftIce, why do you have two models for highpoly Sora? Is he different in Final Mix?
I'm actually not sure. At first I thought the cutscene model (much like the player model of the Final Mix) had a crown. But I just checked, and.. apparently not. So I'm not sure, I've never compared them side-by-side before.
## Post #72
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-02-05T19:10:30+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

^ Mine does that too. Can you not cycle through the animations? :/
## Post #73
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-02-05T19:15:09+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from ultimaespio
>
> ^ Mine does that too. Can you not cycle through the animations? :/
Near as I can tell, you cannot.
## Post #74
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-05T23:54:28+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Some of the main characters in final mix get new textures, but as far as I can tell the meshes and bones stay the same. Here's a gif that compares regular sora with FM sora. (Cause it's kinda hard to see the more subtle differences otherwise - for me anyways)
## Post #75
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-06T00:06:08+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

final mix model look more hd
## Post #76
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-02-07T02:14:31+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Are there any kinds of files that can be extracted from Re:Chain of Memories? Or is it just a lost cause at this point, because it didn't have many new 3D models, and there aren't any internal nametables to point one in the right direction.
## Post #77
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-02-07T18:10:48+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

No way to cycle the animations yet.

At last the Sora models (both low and hi poly) were tweaked for final mix. Not exactly sure why, but I suppose it has to do with optimizing the game slightly.
## Post #78
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-08T14:26:51+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

thanks for the info yaz0r
## Post #79
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-10T00:06:45+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Mirrorman95
>
> Are there any kinds of files that can be extracted from Re:Chain of Memories? Or is it just a lost cause at this point, because it didn't have many new 3D models, and there aren't any internal nametables to point one in the right direction.

Hey Mirror, I'm curious how you, uh... "got" tron sora. He always crashes yaz0r's viewer for me.   Oh, and I think the models from chain of memories are mdlx format. hmmmm I dumped kh2 FM a looooong time ago, but for some reason I think that the models with the prefix 'CM' have something to do with reCOM... could be wrong though. I'm going on memories from like 4 years ago or something.

And on a more general note, seeing yaz0r's still active in KH stuff is so great. Even if his newest version of his model viewer doesn't work on my PC for some reason, still so happy he's still interested in it.
## Post #80
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-02-10T01:57:46+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

You'll have got the models from KH2FM. I've checked RAM dumps of RECOM, and they say that it's .MDL not MDLX.
## Post #81
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-10T02:16:37+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

So is it possible to extract from RECOM ultimaespio ?
## Post #82
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-02-10T04:47:21+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from SoftIce
>
> Mirrorman95 wrote:Are there any kinds of files that can be extracted from Re:Chain of Memories? Or is it just a lost cause at this point, because it didn't have many new 3D models, and there aren't any internal nametables to point one in the right direction.

Hey Mirror, I'm curious how you, uh... "got" tron sora. He always crashes yaz0r's viewer for me.   Oh, and I think the models from chain of memories are mdlx format. hmmmm I dumped kh2 FM a looooong time ago, but for some reason I think that the models with the prefix 'CM' have something to do with reCOM... could be wrong though. I'm going on memories from like 4 years ago or something.

And on a more general note, seeing yaz0r's still active in KH stuff is so great. Even if his newest version of his model viewer doesn't work on my PC for some reason, still so happy he's still interested in it.

I used the khddf viewer to make that screenshot. I hope Revelation can come up with a Noesis plugin within the next several months, or yaz0r updates his viewer, because then we could just export KH2 models. CM does stand for Chain of Memories, and I think they're recycled from Re:COM, but Chain of Memories is encrypted more, because it uses a later version of the PS2 disc software. You can still, apparently, rip the textures with PCSX2 and TexMod. By the way, Castle Oblivion uses the abbreviation zz. I have made a list of world abbreviations and am inclined to type it up here.
## Post #83
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-02-10T07:53:42+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from SoftIce
>
> 
Hey Mirror, I'm curious how you, uh... "got" tron sora. He always crashes yaz0r's viewer for me.

What model would that be exactly?
I know there is a few issues due to animation that could crash the viewer.
There is two format of animations in KH2, the compressed one that the viewer support, and a RAW (that is basically uncompressed stuff) that it doesn't support yet. Loading a model with a RAW animation will crash. The walkaround for now is to move the mdlx file to a different folder so that the animation will not get automatically loaded.
## Post #84
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-10T20:33:56+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from yaz0r
>
> SoftIce wrote:
Hey Mirror, I'm curious how you, uh... "got" tron sora. He always crashes yaz0r's viewer for me.  

What model would that be exactly?
I know there is a few issues due to animation that could crash the viewer.
There is two format of animations in KH2, the compressed one that the viewer support, and a RAW (that is basically uncompressed stuff) that it doesn't support yet. Loading a model with a RAW animation will crash. The walkaround for now is to move the mdlx file to a different folder so that the animation will not get automatically loaded.

Thanks for the reply!   Right now none of my tron models have the mset animations with them, but I copied the one I was trying to load into the model viewer's folder just to be sure. It still crashes it for some reason, but since it works on other people's PC's, the problem is probably something at my end. I've tried dropping the mdlx file onto the viewer to start it, dropping the mdlx file onto the viewer's view window when the viewer was already loaded, and opening the model from the viewer's file menu. My computer, the model viewer, and that mdlx file just don't mix for some reason.  

The model I was trying to load was the low poly player tron one. P_EX100_TR.mdlx 

I don't know if this is anything of value, but the error signature was this:
AppName: modelviewerwxd3d9.exe	 AppVer: 0.0.0.0	 ModName: modelviewerwxd3d9.exe
ModVer: 0.0.0.0	 Offset: 000bda71

I thought the offset might mean something to you. I have no idea if that means anything of value though.  

> Reply from ultimaespio
>
> 
You'll have got the models from KH2FM. I've checked RAM dumps of RECOM, and they say that it's .MDL not MDLX.

> Reply from Mirrorman95
>
> 
I used the khddf viewer to make that screenshot. I hope Revelation can come up with a Noesis plugin within the next several months, or yaz0r updates his viewer, because then we could just export KH2 models. CM does stand for Chain of Memories, and I think they're recycled from Re:COM, but Chain of Memories is encrypted more, because it uses a later version of the PS2 disc software. You can still, apparently, rip the textures with PCSX2 and TexMod. By the way, Castle Oblivion uses the abbreviation zz. I have made a list of world abbreviations and am inclined to type it up here.

It would be typical that I would spend while trying to figure out the joints and bones and trying to rig someone's high poly face from KH, or rig a KH2 model with chrissquarefan's mdlx bone extractor skeleton (instead of creating the bones myself or using a biped in max), only to have yaz0r come out with an exporter. Still, I'd be ecstatic, since my rigging would probably be pretty off...   

Ahh, okay at first I was confused because those mdlx models with the CM prefix look like they came from reCOM, and ultimaespio said they were mdl format. So thanks for explaining that they were probably recycled from reCOM. I have no knowledge of the programming or encryption side of things, so unless it's stated outright I'm oblivious.   

All I know how to do is run the dumpers and view models with the right model viewers. And screw things up in 3dmax and maya... that too.   

But, if the reCOM model format is mdl, does that mean it's probably an encrypted version of either the mdls or mdlx model format? Because to my knowledge, I did not know any KH model formats that had that extension. The only ones I've ever dumped were mdls and mdlx ones, with the mset animations. Oh, and the .map KH2 map files, but that's another story. Then again, since I was using a dumper it was looking for predefined things. I have two  KH .ard files that someone posted in another thread, and I can see what looks like other formats in a hex editor (someone also pointed out something that ended in .moa, I think.). I tried extracting a mdls model wi from the di.ard one with a hex editor, and even when someone explained how many spaces you need to highlight before it and all that, I still failed. Typical.
## Post #85
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-02-15T02:26:26+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

I have found that all forms of Roxas and Sora (except most world forms), and also all models of Riku (including Riku-Ansem), several recolored heartless, and any model involving the Oathkeeper and/or Oblivion, plus any other models I haven't completely checked, all have different textures in Final Mix than they do in the English KH2 Disc.
## Post #86
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-02-15T09:59:18+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Most of them are retextured. It's a lot easier searching for ones that aren't. Kairi is the only one i've noticed.
## Post #87
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-15T10:04:13+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

I found aqua armor model in KH2 Final mix
## Post #88
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-02-15T21:39:07+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

I wonder how many more files I will need to extract from KH2 USA to have a complete set. What are some major FM-specific models I missed?

And yes, Aqua's armor is in Final Mix+.

EDIT: I did some more digging, and it turns out that most of the Organization cloaks were retextured for FM+ as well.

Also, kkdf2 also has some kind of anb to mset converter, which really works, except on faces.
## Post #89
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-17T20:50:44+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Mirrorman95
>
> I wonder how many more files I will need to extract from KH2 USA to have a complete set. What are some major FM-specific models I missed?

And yes, Aqua's armor is in Final Mix+.

EDIT: I did some more digging, and it turns out that most of the Organization cloaks were retextured for FM+ as well.

Also, kkdf2 also has some kind of anb to mset converter, which really works, except on faces.

ergh wait, anb.. anb, what is that again? Time to go hunting to see if I saw that post of kkdf2's where he mentioned that. G'Lord, I really need to get all the stuff I download related to this forum organized.
## Post #90
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-02-17T21:02:43+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

ANB is cutscene animations.
## Post #91
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-17T21:07:41+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from ultimaespio
>
> ANB is cutscene animations.

Aaaaaah, thank you very much!
## Post #92
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-02-19T06:05:13+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

yes i finally got the model viewer working on my computer!!!!!!! now im trying to find new animations, like the one where riku is holding his hand out to sora when the heartless attack destiny islands  that would be sweeeeet
## Post #93
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-02-19T19:54:48+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

^^ some new animations.. i replaced it with a different mset on the original mset file in a hex editor, it was a very complicated process.. but, it was worth it ^^ im trying to find different animations like when rikus telling sora to close the door and when kairi gets blown away on the island and sora reaches for her ^^
[newanimations.jpg](https://xentaxbackup.github.io/file/3943_newanimations.jpg)
## Post #94
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-20T00:34:22+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Murodragon
>
> ^^ some new animations.. i replaced it with a different mset on the original mset file in a hex editor, it was a very complicated process.. but, it was worth it ^^ im trying to find different animations like when rikus telling sora to close the door and when kairi gets blown away on the island and sora reaches for her ^^

No fair. I want! Did you find any new mset animations that falo's dumper and yaz0r's dumper missed? I want the missing cutscene animations for Kairi, too. (Esp the ones of her chatting on destiny island in the evening or the first cutscene that has her giggling at something riku said.) 

I wish I knew now to hex edit. There's a giant fail for me. I dumped the di.ard files with falo's duper and looked through them in a hex editor for fun though. Falo's dumper includes an option to dump text though I believe, but I haven't tried that yet.

this is in di03.ard, I think it might be dialogue, and what's interesting is the only model of kairi that shows up is xa_ex_7140.mdls. The mset that goes with that mdls is her standard non animated pose, but I have a feeling that xa_ex_7140.mdls is the model used for one of the DI cutscene animations...but it only mentions the standard xa_ex_7140.mset, which is just her pose. Argh, so confusing... (and then there's the thing where there's a xa_ex_7140_pp.mset animation - for the peter pan cutscene, yet there's no xa_ex_7140_pp.mdls to accompany it.)

Here you can see the mdls, and RIGHT AFTER that, what I think is the dialogue:



Interesting that you see 'RIKU'  'RIKU2', 'KAIRI2' and then 'SORAH' 'KAIRI H' and 'RIKUH'. 

Why is Kairi's 'H' a space apart, I wonder. I wonder if the 'H' stands for a high poly model, or something else. 

Falo's dumper is nice, because if you know the filename, it will dump it for you. But I tried dumping a .MOA file (di_d000.moa) and the dumper said it doesn't exist, even though I see it in the .ard file. Confusing....

I know Yaz0r found the animation of Kairi where she's giggling, because I remember him showing a screenshot of the model posing from that scene in his model viewer (a long time ago...). I wish I could find it somehow.

Oh, and just for fun...

For some weird inexplicable reason, her pose makes me think 'it's Godzilla Kairi!'
## Post #95
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-02-20T01:26:04+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from SoftIce
>
> Murodragon wrote:^^ some new animations.. i replaced it with a different mset on the original mset file in a hex editor, it was a very complicated process.. but, it was worth it ^^ im trying to find different animations like when rikus telling sora to close the door and when kairi gets blown away on the island and sora reaches for her ^^

No fair. I want! Did you find any new mset animations that falo's dumper and yaz0r's dumper missed? I want the missing cutscene animations for Kairi, too. (Esp the ones of her chatting on destiny island in the evening or the first cutscene that has her giggling at something riku said.) 

I wish I knew now to hex edit. There's a giant fail for me. I dumped the di.ard files with falo's duper and looked through them in a hex editor for fun though. Falo's dumper includes an option to dump text though I believe, but I haven't tried that yet.

this is in di03.ard, I think it might be dialogue, and what's interesting is the only model of kairi that shows up is xa_ex_7140.mdls. The mset that goes with that mdls is her standard non animated pose, but I have a feeling that xa_ex_7140.mdls is the model used for one of the DI cutscene animations...but it only mentions the standard xa_ex_7140.mset, which is just her pose. Argh, so confusing... (and then there's the thing where there's a xa_ex_7140_pp.mset animation - for the peter pan cutscene, yet there's no xa_ex_7140_pp.mdls to accompany it.)

Here you can see the mdls, and RIGHT AFTER that, what I think is the dialogue:



Interesting that you see 'RIKU'  'RIKU2', 'KAIRI2' and then 'SORAH' 'KAIRI H' and 'RIKUH'. 

Why is Kairi's 'H' a space apart, I wonder. I wonder if the 'H' stands for a high poly model, or something else. 

Falo's dumper is nice, because if you know the filename, it will dump it for you. But I tried dumping a .MOA file (di_d000.moa) and the dumper said it doesn't exist, even though I see it in the .ard file. Confusing....

I know Yaz0r found the animation of Kairi where she's giggling, because I remember him showing a screenshot of the model posing from that scene in his model viewer (a long time ago...). I wish I could find it somehow.

Oh, and just for fun...

For some weird inexplicable reason, her pose makes me think 'it's Godzilla Kairi!'


^^ yep i did cause i know some of the file names, some of msets are inside the evm files. for example dc08_a011.evm, dc stands for disney castle, and this might be one of the cutscene animations from the disney castle , i tried dumping a .MOA file too and the dumper said it didnt exist.. hmmm .. lol godizilla kairi XD
## Post #96
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-02-20T01:27:02+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

There are things called moa files and they have msets as well but no current dumper can find them. I suspect the mset for Ansem's final speeches are part of that, but as they are unavailable I can't get Ansem to repeat any of his dialogue except his pre-installed mset for Hollow Bastion. Can anyone find those?
## Post #97
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2011-02-20T02:44:56+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

help i can't get the extracter in the map viewer to work
## Post #98
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-20T04:27:34+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Murodragon
>
> ^^ yep i did cause i know some of the file names, some of msets are inside the evm files. for example dc08_a011.evm, dc stands for disney castle, and this might be one of the cutscene animations from the disney castle , i tried dumping a .MOA file too and the dumper said it didnt exist.. hmmm .. lol godizilla kairi XD

Thanks! I'm off to fail at trying to extract some msets from the evm files I dumped.
## Post #99
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-02-20T04:41:37+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

i didnt get all the destiny islands evm files, cause some of the file names i dont know D:.... but i remember keyword searching through this file and seeing evm files not sure if they were all of them.
## Post #100
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-20T05:04:09+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Well I managed to figure out the header thanks to other msets I have. Now I have the problem of figuring out what model it goes with.


horrors! that one leg wiggles around too, like some morbid zombie leg.
## Post #101
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-02-20T05:17:16+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

holy cras
> Reply from SoftIce
>
> Well I managed to figure out the header thanks to other msets I have. Now I have the problem of figuring out what model it goes with.


horrors! that one leg wiggles around too, like some morbid zombie leg.

O.O OMG!!! well i managed to match one model however and thats sora sitting down while talking to kairi during the evening D: i cant get it now however, its on my other computer .... but holy crap D:
## Post #102
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-20T07:51:24+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

lol things went so much easier once I looked at msets I knew belonged to kairi. I found the identifier string, or whatever the heck you call that. 

in hex numbers it's:

22000002 00002002 00408000 00000002 00000002 
00000002 00000000 00000002 00000002 00000000 
00000002 25000002 00006002 00000002 00488002 

but searching for '25000002 00006002 00000002 0048' is the best way to find likely kairi msets, but then you have to search again for '22000002 00002002 00408000 00000002 00000002' to see if it matches. (My hex editor wouldn't let me search for that entire chunk.) 

In ascii it's these four symbols: " @ % H 
But spaced out over two lines inbetween padding, or whatever you'd call the ...'s. 

Then for anyone that doesn't know, the header starts as '03000000 80000000', and 'MMTN' (or 4D 4D 54 4E) should show up on line 0078h.  The mset ends at the ascii code _KN5, but I usually leave the padding in place that comes after that. Or whatever the heck it's technically called. 

I was able to find all her DI cutscenes that were missing (I think), although for two of them, the viewer crashes on one of the animations. For the horrid leg of doom, turns out I didn't trim the mset file well enough, so it screwed up the bone placement.   

Kairi's msets show up in these di.evm files:
di01a_a001.evm		
di01_n011.evm	
di01_n012.evm
di01_n041.evm								
di03_n011.evm			
di03_n012.evm			
di04_n031.evm		
di04_n041.evm			
di04_n043.evm			
di08_n011.evm	

Looking at Riku's msets, I think I see a similar 'identifier' tag or whatever it's called. If they all have those identifier tags, they can easily be matched up with the appropriate model. 

she laughs at my struggles. lol
## Post #103
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-02-20T09:07:12+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

hehehe so you noticed XD
[soyounoticed.jpg](https://xentaxbackup.github.io/file/3947_soyounoticed.jpg)
## Post #104
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-02-20T16:03:48+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

i would love to have riku and soras evm files including when they were little kids.. god that zombie leg scares me XDDD
## Post #105
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-02-20T18:22:34+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

And what of Ansem, Seeker of Darkness? How do I find his msets?

Also, has anyone scene THIS glitched-up scene? [http://www.youtube.com/watch?v=Qn_Ui6hVChY](http://www.youtube.com/watch?v=Qn_Ui6hVChY)
## Post #106
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-02-20T22:49:16+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

im curious how softice got some of the mset files... cause i had some of them, and some of them were missing... and that glitch is weird o.O ive seen this like.. Two years ago i think? holy crap   


ansems msets might start with the abbreviation ew which stands for end of the world....
## Post #107
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-02-21T03:02:44+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

I found an Ansem animation at ew34_a031.evm.
## Post #108
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-02-21T04:09:11+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

sweet some of the evm files are hidden the SCES_509.67 file.. it dosent list all of them though..
## Post #109
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-02-22T03:43:09+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Sora can be put into any of his Original, Valor, Wisdom, Master, Final, World-Specific, and Limit Forms during cutscenes, but tell me this: can Anti-Sora be seen in cutscenes in KH2?
## Post #110
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-02-22T20:59:27+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

I should really make it easier to browse animations...

Anyway, fixed a few things on my end, mainly issues with map files. Will see to make a new release with hopefully a way to select animations from a separate file.
## Post #111
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-22T21:35:45+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Murodragon
>
>  im curious how softice got some of the mset files... cause i had some of them, and some of them were missing... and that glitch is weird o.O ive seen this like.. Two years ago i think? holy crap

Which ones are you looking for? This is how I found them:

I've only tried this with the US version of Kingdom Hearts, not with KH2 yet. I'm running out of room to burn iso's. Must find crap to delete...

I discovered that the msets have an  identifier for the model it's for. Kairi's is this hex byte (uh, sequence?):

22000002 00002002 00408000 00000002 00000002 
00000000 00000000 00000002 00000002 00000000 
00000002 25000002 00006002 00000002 0048

In ASCII, it looks like this:

" . . . . .  . . @. . . . . .
. . . . . . . . . . . . . . . . . . . . 
. . . . . . . . %. . . . . . ` . . . . . 
. H

or the four symbols used are these:
" @ % ` H

I might have messed up the number of dots or spacing though. But, there's always a blank line and the four symbols should always fall over four lines, and the dots should always be the same hex data. I have seen some where the blank line is missing, and those msets don't work for Kairi (the bones are totally messed up.).  

Now, I have gone further with this, and have found that often you can tell what mset is for a model, and if it is a high poly model, by looking at what comes after the 'pB' letters, which usually occurs 5 or 6 lines after the letters MMTN.

For Kairi, her high poly model uses this hex byte (er, sequence)
70420100 000041
in ASCII, it looks like this:
pB. . . . A

Her low poly hex byte (uh sequence) looks like this:
70420000 0000DD00 000050
or in ASCII, looks like this:
pB. . . . . . . . P

So, if you use Kairi's high poly hex byte identifier thing (70420100 000041), and if you have a hex editor that lets you search multiple files for a hex byte sequence, you can quickly find what emv files contain msets for high poly Kairi. 

It works the same way with other characters, but only if you have at least 1 mset for them (for me at least, I need one). 

High poly riku's hex byte sequence is this:
70420100 00004701 000050

I was able to find some more msets that the dumpers missed, including the one where Riku holds his hand out to Sora at the start of the game, I think. 

If anyone's curious, Kairi's child low poly model's hex sequence is this:
70420000 00001C01 000050

I found three more msets, along with the basic pose dumped from falo and yaz0r's dumpers. 
They can be found in di11_n011.evm, ex25_h046.evm and pc06_o011.evm (although two appear to be the same animation sets, the other one shows child kairi kneeling and scribbling (on the rock, which is not there obviously lol), and the animation under that one crashes. Merp. 

Oh, here's high poly ariel, if anyone wanted to search for her msets missed by the dumpers:
70420100 00000801 000050

I found four animations for her in lm06_n012.evm, lm14_n021.evm, lm16_n012.evm and lm16_n031.evm by searching for that hex byte sequence. 

If anyone's interested, I uploaded the msets that I found so far.  Uh, that's okay to do here, right? Riku's isn't complete, because he has a bunch and I'm lazy, but I included the few I extracted from some evm files, one which has him reaching his hand out.

I named the mset after whatever evm I found it in, and I also included a mdls with the same name for convenience (otherwise you have to copy and paste and rename one mdls a bunch of times, like I did). 

Sometimes the msets appear to be duplicates of each other, but at times the file size will differ. There are also instances where the same animation is shown in different animation sets. Some of the specific animations in some msets also crash yaz0r's viewer, sorry about that. I found it interesting that there are some low poly mset animations of kairi that are the same as her high poly cutscene ones. These were never used in the game to my knowledge. An example is kairi's low poly po96_r094.mset (there are 9 animations in this one, the last one crashes the viewer.   ) and kairi's low poly ex26_h016.mset. you can get the ones I've gotten so far here: [http://www.mediafire.com/?4kzrk0376b6b6ds](http://www.mediafire.com/?4kzrk0376b6b6ds)

> Reply from yaz0r
>
> I should really make it easier to browse animations...

Anyway, fixed a few things on my end, mainly issues with map files. Will see to make a new release with hopefully a way to select animations from a separate file.

Yay Yaz0r's around!  Just making that dumper way back when helped people out a whole lot. If not I couldn't have dumped any files, I'd never be able to look at the hex info (well, and without the viewer, it would have been useless anyway lol)
## Post #112
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-02-23T03:48:25+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

oh im trying to find high poly Sora and low poly Sora XDDD i want the animation where hes lost in darkness and when he gets saved by Kairi and he hugs her,that would be sweet
## Post #113
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-02-23T04:27:31+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

I think Ansem's identifier is 70420100 00008801 000050 , or pB☺...ê☺..P in DOS/IBM-ASCII. ew34_a031.evm, ew33_a011.evm, ew31_a011.evm, and ew31_a012.evm all contain Highpoly Ansem animations. A few of the animations crash the viewer. Also, Ansem w/ Guardian's identifier is 70420000 0000F801 000050.
## Post #114
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-24T20:23:03+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Murodragon
>
> oh im trying to find high poly Sora and low poly Sora XDDD i want the animation where hes lost in darkness and when he gets saved by Kairi and he hugs her,that would be sweet

merp, I'm really new at hex editing. So don't be surprised if I get crap wrong.   I think I'm right on the stuff below though.

I think it's okay for me to post this link, if not I'll remove it. But, here's the mset that has sora hugging kairi, and a high poly sora mdls with the same name (although since the model viewer only shows one model, he's hugging the air  ) 

[http://www.mediafire.com/?sy2gwbcbfio6bwv](http://www.mediafire.com/?sy2gwbcbfio6bwv)
I also included two other msets that were from the same category (ex) cause I think they're related. And because first animation in the ex52a_a094.mset is funny as heck, and the second reminds us all why drugs are bad, mkay. 



Sora's high poly identifier is this hex byte sequence:
70420100 00009801 000050

Sora's low poly identifiyer is this:
70420000 00002501 000050

If you don't have a hex editor that lets you search multiple files for hex bytes, here is a list of the evms that have high poly sora'si dentifier (beware the long list ahead):

As for low poly sora, well, I'm pretty sure he'll appear in every evm file since he's the main character and the player character.   

High poly evm list:
al01_a041.evm			
aw03_r011.evm			
dc08_a011.evm			
dc08_a012.evm			
dh05_a011.evm			
dh03_i011.evm			
dh03_n011.evm			
dh27_n004.evm			
dh01_t011.evm			
dh02_t011.evm			
dh05_t011.evm			
dh46_t087.evm			
di01_n011.evm			
di01_n012.evm			
di01_n013.evm			
di03_n012.evm			
di04_n031.evm			
di04_n041.evm			
di04_n042.evm			
di04_n043.evm			
di06_n011.evm			
di06_n021.evm			
di06_n022.evm			
di08_n011.evm			
di09_n011.evm			
di09_n021.evm			
di10_n011.evm			
di11_n011.evm			
ew31_a011.evm			
ew33_a011.evm			
ew33_a021.evm			
ew33_a022.evm			
ew33_a023.evm			
he02_i021.evm			
he02_i031.evm			
pc20_a094.evm			
pc26_a094.evm			
pc05_o041.evm			
pc06_o011.evm			
pc20_t094.evm			
pi32_h011.evm			
pi01_o011.evm			
pi02_o011.evm			
pi06_o012.evm			
pi07_t063.evm			
po07_h011.evm			
po37_o011.evm			
po32_t063.evm			
pp10_o031.evm			
pp05_y021.evm			
pp08_y011.evm			
pp09_y012.evm			
pp09_y032.evm			
tw01_t011.evm			
tw03_t011.evm			
tw03_t022.evm			
tw23_t022.evm			
tw26_t021.evm			
tz12_r078.evm			
tz20_r086.evm			
tz01_y011.evm			
tz01_y012.evm			
ex52a_a094.evm			
ex25_h046.evm			
ex26_h016.evm			

Stupid Sora, and his ten thousand high poly msets... Will take forever to extract manually the msets from all of those.
## Post #115
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-02-25T22:11:27+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

omg Soras face.. XD.. Im trying to rip kh2 cutscene animations.. kffd2s anb to mset converter wont work for me so.. idk what  to do XDDD Thats hilarious haahaha XD
## Post #116
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-02-26T00:40:15+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Murodragon
>
> omg Soras face.. XD.. Im trying to rip kh2 cutscene animations.. kffd2s anb to mset converter wont work for me so.. idk what  to do XDDD Thats hilarious haahaha XD

What's the problem? I just associate the anb filetype with anb2mset, then double-click the file and the mset appears in the folder where a2m is located. Then I take the name of the folder the anb was in, find the corresponding mdlx, and temporarily rename the current mset and rename the new mset and put it there. If that doesn't help, I don't know what to do. And some mset don't work at all, like n_zz160, while others move some of the facial vertexes to the bottom of the model. If kkdf2 is still working on that project, there are still a few bugs in the program that need to be fixed in the next version. But it's really good that we at least have a way of using the anb files instead of just having them sit there, thanks to kkdf2. I think he used pcsx2 as a basis for his programs, which is why his 3D rips are as flattened as rips from the emulator. I hope he's okay with us using these programs.
## Post #117
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-02-26T01:57:22+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

For the record, I'm in the middle of adding support for selecting a specific animation to play in the viewer (this is pretty much done) and an option to load animation from a separate file.
This is mostly for KH2 for now, but I will probably backport that in kh1.
## Post #118
- Username: Kharaxel
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Apr 29, 2008 8:56 pm
- Post datetime: 2011-02-26T10:55:04+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Mirrorman95
>
> Murodragon wrote:omg Soras face.. XD.. Im trying to rip kh2 cutscene animations.. kffd2s anb to mset converter wont work for me so.. idk what  to do XDDD Thats hilarious haahaha XD   

What's the problem? I just associate the anb filetype with anb2mset, then double-click the file and the mset appears in the folder where a2m is located. Then I take the name of the folder the anb was in, find the corresponding mdlx, and temporarily rename the current mset and rename the new mset and put it there. If that doesn't help, I don't know what to do. And some mset don't work at all, like n_zz160, while others move some of the facial vertexes to the bottom of the model. If kkdf2 is still working on that project, there are still a few bugs in the program that need to be fixed in the next version. But it's really goo that we at least have a way of using the anb files instead of just having them sit there, thanks to kkdf2. I think he used pcsx2 as a basis for his programs, which is why his 3D rips are as flattened as rips from the emulator. I hope he's okay with us using these programs.
Hey, if I might ask, what's the password for that anb2mset. It's protected by one, and I can't find it.
Sorry if it's a stupid question, but I'm dying to try some cutscene msets. D :

Thank you.

Oh, and great job to everyone who figured out the formats, and some such. It made me and my friend very happy... since we love dem models and all.
## Post #119
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-02-27T02:11:34+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

I hope this isn't too revealing for him, but usually I can view all his 7z files with the passwords 2, ][, 22, or 1.
## Post #120
- Username: Kharaxel
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Apr 29, 2008 8:56 pm
- Post datetime: 2011-02-27T04:57:38+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

FFFFFFUUuuUuuu-

Thanks, man. To think the passwords were so obvious, yet I didn't figure it out. Seriously, thanks. : D
## Post #121
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2011-03-03T10:53:57+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from yaz0r
>
> For the record, I'm in the middle of adding support for selecting a specific animation to play in the viewer (this is pretty much done) and an option to load animation from a separate file.
This is mostly for KH2 for now, but I will probably backport that in kh1.

Wow, thank you yazo0r.
## Post #122
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-03-03T21:40:21+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

This week is very busy for me. Hope I can finish it up next week.
## Post #123
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-03-05T21:14:18+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

bad news my computer crashed on me and lost everything i had all the character evm animations with the models o-o i am so pissed off right now, now i have to download the whole kh iso again -__- damnnnn.
## Post #124
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-05T22:01:17+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Murodragon
>
> bad news my computer crashed on me and lost everything i had all the character evm animations with the models o-o i am so pissed off right now, now i have to download the whole kh iso again -__- damnnnn.

Or you could just copy the information from your copy of the disk.
## Post #125
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-06T02:47:16+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

I hope you're gonna finish it in next week yaz0r
## Post #126
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-07T04:11:55+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Wellp, I convinced the xnview guy to update his tm2 viewer.
Behold
[http://www.xnview.com/beta/XnView-beta1.zip](http://www.xnview.com/beta/XnView-beta1.zip)
## Post #127
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-03-09T09:02:36+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

The contents of this post was deleted because of possible forum rules violation.
## Post #128
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-09T16:58:32+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

I think all these new features are great, but I still can't see any of the models I drop into it. I was able to get a horizontal black bar from Actor_Sora, but I can't view models or maps. There's got to be a way to keep all these features while still keeping the compatibility it had back in v0.3.
## Post #129
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-03-09T17:59:56+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

One of the reasons I stopped releasing versions after 0.3 was that I didn't want to handle compatibility with every gfx card out there.
If there was a way for me to reproduce this issue, maybe I would fix it. But as long as I can't reproduce it on my end, I won't deal with it.
It's either it works, or don't use it... My days are only 24hours long, and I prefer to spend my free time on things that are of interest than supporting every gfx board out there.
## Post #130
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-09T18:54:09+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from yaz0r
>
> One of the reasons I stopped releasing versions after 0.3 was that I didn't want to handle compatibility with every gfx card out there.
If there was a way for me to reproduce this issue, maybe I would fix it. But as long as I can't reproduce it on my end, I won't deal with it.
It's either it works, or don't use it... My days are only 24hours long, and I prefer to spend my free time on things that are of interest than supporting every gfx board out there.

Alright then, can you tell me what your graphics card is so I know what will work? I have an ATI Radeon Xpress 1250.
## Post #131
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-03-09T19:16:59+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Heh,
I'm running a gtx 580 on a win7 x64.
I'm also running this build on a 8800 GT without issues (also a win7 x64).
I don't have access to ATI cards to test.

Does anyone else than you have this issue?
## Post #132
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-09T19:24:00+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Well, I got it to work on my brother's computer, and he has a Windows 7 Desktop with an ATI Radeon HD 4250 graphics card. 0.4 couldn't load KH1 models but could load maps. 0.5 doesn't have the option of viewing KH1 models, and crashed when I fed it maps. Both can view and animate KH2 models that used to crash the viewer before successfully now. The controls are AWSD Spacebar+Mouse now for navigation, not ALT+Mouse and CTRL+Mouse. I can't input anb files directly, but after using anb2mset, it views the animations flawlessly, whereas kkdf2's mdlx animator makes the faces fall all over the place.
## Post #133
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-09T19:34:54+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Thanks for the new release Yaz0r! 

Merp. I have the same issue. My computer would be considered a fossil in computer years though, so I'm pretty sure it's the video card. My graphics card is an ati raedon 9500 pro (lol told you I'm running a fossil.) 

But, I'm going to stick Yaz0r's latest release, plus a bunch of kh2 models on my flash stick and go take over my friend's computer (that is not in the stone age) later this week, so I'll see what happens then.

Heh, on an unrelated note, on my quest to get a textured version of destiny islands, I ended up using texmod with pcsx2 and kh (the kh textures are a higher resolution.). Texmod loaded like 2,000 of them. Egads! Good thing for the filtering option. 

I also plan on using it on KH2 during the cutscene where kairi gets her keyblade, so I can grab the higher res texture of that as well.
## Post #134
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-03-09T20:11:21+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

I will modify next build to have more debug information and try to see where the issue comes from.
## Post #135
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-09T20:44:53+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Someone PMed me a little while back asking if it was possible to convert Kingdom Hearts animations to another, more usable format. Is that possible?
## Post #136
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-03-09T21:03:45+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Not in current states of things.
## Post #137
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-09T23:00:32+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from yaz0r
>
> I will modify next build to have more debug information and try to see where the issue comes from.
Oh, thank you very much! That's very nice of you!
## Post #138
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-03-10T07:02:43+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

The contents of this post was deleted because of possible forum rules violation.
## Post #139
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-03-10T08:15:32+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

The contents of this post was deleted because of possible forum rules violation.
## Post #140
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-10T09:12:25+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

I can load maps with animations now! And I figured out the right-click animation controller, so everything works now.
## Post #141
- Username: Kharaxel
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Apr 29, 2008 8:56 pm
- Post datetime: 2011-03-10T10:42:23+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Holy hell! This is awesome! Thanks for everything! : D

One question though... is possible to move the model itself, so that I can, for example put it anywhere on the loaded map?
I mean, I know I can move the camera, but not the model... I think.
Either way, awesome work Yaz0r. : D

Oh and one more question... do any of you know where are the animations for Xemnas when he's sitting on dat throne of his? And where to find the map of the Orgy XIII throne room? I kinda looked, but had no luck so far. : <

Thanks. : >
## Post #142
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-10T18:53:43+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Wow! Thanks so much Yaz0r! Version .52 still doesn't show the models for me, but I'm so happy that you're continuing with developing modelviewerwx! I tried version .51 that had added debug info, but I can't figure out how to access the debug options or dump the info. lol. Sorry about that. 

I'm going to try your model viewer on my friend's computer, and also on a relative's laptop that's newer than the desktop I have here, so I'll report back on what happens with those as well. 

Thanks again for all your hard work!!
## Post #143
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-03-10T20:36:19+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

0.52 also have the debug stuff in it. And I will probably leave them in from now on.
There is no debug option to enable, it will just show a message box with the info I need if something bad happens.
I will try to add more debug stuff to try to locate the issue.
## Post #144
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-03-10T23:17:35+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Noesis plugin has been updated with map support.
Check display all models in the Data Viewer if you want them all to render at once.  Cycling through the models can allow you to fame the scene closer, or simply zoom completely in to fly around the scene.
## Post #145
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-10T23:59:07+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from revelation
>
> Noesis plugin has been updated with map support.
Check display all models in the Data Viewer if you want them all to render at once.  Cycling through the models can allow you to fame the scene closer, or simply zoom completely in to fly around the scene.

Thank you so much! We can now view KH2 models and Maps in Noesis, and export them! This is amazing!

Although, strangely, the textures don't show any transparency.
## Post #146
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-03-11T00:11:18+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from revelation
>
> Noesis plugin has been updated with map support.

Haven't checked your plugin yet, but let me know if you have any questions about the format. KH2 uses some very nasty GS tricks for some textures.
I have found some of the scrolling uv parameters and some of the camera/fog/clear color parameters that I'm going to implement soon.
I'm hunting for the informations that groups the model data together in the map, especially on the po08 map (I suppose there is a kind of layer information somewhere that allow scripts to toggle parts of the map on and off).
## Post #147
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-11T00:27:53+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from yaz0r
>
> revelation wrote:Noesis plugin has been updated with map support.

Haven't checked your plugin yet, but let me know if you have any questions about the format. KH2 uses some very nasty GS tricks for some textures.
I have found some of the scrolling uv parameters and some of the camera/fog/clear color parameters that I'm going to implement soon.
I'm hunting for the informations that groups the model data together in the map, especially on the po08 map (I suppose there is a kind of layer information somewhere that allow scripts to toggle parts of the map on and off).

I think kkdf2 would be a good person to talk to about that, because his map viewer can toggle the fog and general shadows.
## Post #148
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-03-11T00:39:26+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Mirrorman95
>
> 
I think kkdf2 would be a good person to talk to about that, because his map viewer can toggle the fog and general shadows.

Question is, is that actual fog parameters from the maps or just generic parameters.
What do you mean by "general shadows"?
## Post #149
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-11T00:49:20+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from yaz0r
>
> Mirrorman95 wrote:
I think kkdf2 would be a good person to talk to about that, because his map viewer can toggle the fog and general shadows.

Question is, is that actual fog parameters from the maps or just generic parameters.
What do you mean by "general shadows"?

"Vertex clr". It's like having shaders for each element so that it looks realistic instead of colorful and bright. Your MAP viewer might have it, but I don't have time to double-check right now. But I know that kkdf2's map viewer does have it.

I checked your viewer, and yours in fact do have generic shadows, as does kkdf2's with vertex clr enabled, while Revelation's plugin does not.
## Post #150
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-11T17:55:07+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Quite interesting. In the cutscene animations for Destiny islands, there is a folder for a model called h_ex860. Tried dumping with kkdf2's stuff, file does not exist.

There's a few animations for this model too.
## Post #151
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-12T01:08:31+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from ultimaespio
>
> Quite interesting. In the cutscene animations for Destiny islands, there is a folder for a model called h_ex860. Tried dumping with kkdf2's stuff, file does not exist.

There's a few animations for this model too.

I only see one animation, in the di folder.

Also, N_ZZ160 can be viewed in 0.4, but not in 0.52 of yaz0r's model viewer.
## Post #152
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-03-14T17:08:44+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Mirrorman95
>
> 
Also, N_ZZ160 can be viewed in 0.4, but not in 0.52 of yaz0r's model viewer.

Will look into that. But I think I already know the issue.
There is in fact two animation formats in KH2, the usual IK based animation system, and a secondary "raw" animation system. While the raw is probably simpler than the first one, my code doesn't support it (yet?). Since the viewer will try to display the first animation it finds, it will usually crash when that first animation is in raw format.
There is a flag in the animation header to tell if it is raw or not, and the plan right now is to just ignore animations with this flag set, probably in next version...
## Post #153
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-14T20:15:58+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from yaz0r
>
> Mirrorman95 wrote:
Also, N_ZZ160 can be viewed in 0.4, but not in 0.52 of yaz0r's model viewer.

Will look into that. But I think I already know the issue.
There is in fact two animation formats in KH2, the usual IK based animation system, and a secondary "raw" animation system. While the raw is probably simpler than the first one, my code doesn't support it (yet?). Since the viewer will try to display the first animation it finds, it will usually crash when that first animation is in raw format.
There is a flag in the animation header to tell if it is raw or not, and the plan right now is to just ignore animations with this flag set, probably in next version...

Just wanted to say that was pretty interesting to read. I don't know anything about file formats, but I know a bit about animation. Thanks for sharing and all your hard work with your viewer and whatnot!
## Post #154
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-03-14T21:52:04+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from SoftIce
>
> 
Just wanted to say that was pretty interesting to read. I don't know anything about file formats, but I know a bit about animation. Thanks for sharing and all your hard work with your viewer and whatnot!

I would add that contrary to popular belief, I don't exactly know all the details of the kh2 animation engine. The animations in the viewer works with a mixture of reverse engineered code, statically recompiled code from the original exe, and completely emulated code from the original exe. This is the same approach that I used on kh1 animations and that kkdf2 used too (I used some of the notes kkdf2 made on kh2 to implement my version).
## Post #155
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-14T23:30:53+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from yaz0r
>
> SoftIce wrote:
Just wanted to say that was pretty interesting to read. I don't know anything about file formats, but I know a bit about animation. Thanks for sharing and all your hard work with your viewer and whatnot!

I would add that contrary to popular belief, I don't exactly know all the details of the kh2 animation engine. The animations in the viewer works with a mixture of reverse engineered code, statically recompiled code from the original exe, and completely emulated code from the original exe. This is the same approach that I used on kh1 animations and that kkdf2 used too (I used some of the notes kkdf2 made on kh2 to implement my version).

Wow, that's kind of more impressive that you and kkf2 were able to make viewers for an animation format that you didn't have all the components to though.
## Post #156
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-15T00:07:52+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from SoftIce
>
> yaz0r wrote:SoftIce wrote:
Just wanted to say that was pretty interesting to read. I don't know anything about file formats, but I know a bit about animation. Thanks for sharing and all your hard work with your viewer and whatnot!

I would add that contrary to popular belief, I don't exactly know all the details of the kh2 animation engine. The animations in the viewer works with a mixture of reverse engineered code, statically recompiled code from the original exe, and completely emulated code from the original exe. This is the same approach that I used on kh1 animations and that kkdf2 used too (I used some of the notes kkdf2 made on kh2 to implement my version).

Wow, that's kind of more impressive that you and kkdf2 were able to make viewers for an animation format that you didn't have all the components to though.
But that also means they don't fully understand the format. They just understand it much better than anyone else, except Square Enix, meaning it would be that much harder to make a mset plugin/converter.
## Post #157
- Username: BakameExcalibur
- Rank: advanced
- Number of posts: 68
- Joined date: Wed Feb 02, 2011 8:02 am
- Post datetime: 2011-03-15T18:18:09+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Probably a noob question, but is there a map dumper for a regular version of KHII? The only one I found is for FM+...
## Post #158
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-16T20:29:39+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from BakameExcalibur
>
> Probably a noob question, but is there a map dumper for a regular version of KHII? The only one I found is for FM+...

This is probably an equally noobish response, but you could try copying your .idx file from the KH2 dvd, and replacing that with the .idx file Falo provides (I'd back up his .idx though). Falo's is a combined .idx file. Then, you can experiment with the nametablebl.txt and see if you can find the file path for the maps from the english version (map/jp/po05.map). I don't know if that would work though, I'm not sure how falo's exe works to dump the files even with the nametable. kkdf2 also wrote a program that lets you dump a file if you know the filename, so even if you don't have the filepath, if the filenames are the same, that could work.

This is all speculation on my part. No clue if anything I suggested actually works. lol
## Post #159
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-04-01T02:28:41+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

The contents of this post was deleted because of possible forum rules violation.
## Post #160
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2011-06-02T19:16:52+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

how do i export the 3d models of the worlds
## Post #161
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-06-02T21:00:36+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Since this topic is still up now, I'd like to point out that I have a much more comprehensive list of undiscovered animations, and if anyone's interested I'll release the latest list. Although, with Xeeynamo's new KH2 extractor coming out soon, I may not be able to find anything his won't, so look out for that.
## Post #162
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2011-06-02T21:32:17+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Mirrorman95
>
> Since this topic is still up now, I'd like to point out that I have a much more comprehensive list of undiscovered animations, and if anyone's interested I'll release the latest list. Although, with Xeeynamo's new KH2 extractor coming out soon, I may not be able to find anything his won't, so look out for that.

how do i export models from the map viewer?
## Post #163
- Username: BakameExcalibur
- Rank: advanced
- Number of posts: 68
- Joined date: Wed Feb 02, 2011 8:02 am
- Post datetime: 2011-08-15T20:18:12+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

I dunno if this is the appropriate topic, but I think I've figured out how to get transparency working with the KH2 plugin for Noesis. Seems to be something to do with the "default blend" setting; for reference, I've used Selphie (pay attention to her hair).

Without default blend: [](http://imageshack.us/photo/my-images/15/selphiewithoutdefaultbl.png/)

Now, with default blend turned on: [](http://imageshack.us/photo/my-images/84/selphiewithdefaultblend.png/)


See the difference? Now if only I could write code (I barely know HTML >_>; ), I'd try to figure out how to enable blending by default for the plugin.
## Post #164
- Username: Xemnass
- Rank: advanced
- Number of posts: 74
- Joined date: Wed Jun 01, 2011 9:07 pm
- Post datetime: 2011-08-15T20:35:42+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

God job  , I tried it whit Sephiroth and it works fine, thanks to verybody =D
If you want to know a lots of thing we are curetly working on let the plugin reading the MSET.

Follow us here:[ :wink:  :)  :mrgreen:  :P 
http://foru ... =16&t=7069](:wink:%20%20:%29%20%20:mrgreen:%20%20:P%20%0Ahttp%3A//forum.xentax.com/viewtopic.php?f=16&t=7069)

However i will speak about thins things to revelations(Plugin autor) and i will ask if can add this to default =D

Thankyou very much for the sharing =D

However, I re-say:

Follow Us:
[viewtopic.php?f=16&t=7069](http://forum.xentax.com/viewtopic.php?f=16&t=7069)    

By:

Xemny
## Post #165
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2011-09-07T15:35:44+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

The KH2DumperX didn't extract any map files for me, so I guess it's still Falo's or yaz0r's dumper for them. Also, does anybody know which image format the .imd files in the itempic folder are?
## Post #166
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-09-08T02:39:42+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

If you hex edit the exe, and replace all instances of map/jp/ with map/us/ , you will be able to export the maps from KH2 ULUS.
## Post #167
- Username: iwantedtoexplode
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 15, 2012 6:07 am
- Post datetime: 2012-01-14T23:15:35+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

The contents of this post was deleted because of possible forum rules violation.
## Post #168
- Username: dragicorn
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Sep 18, 2011 3:21 am
- Post datetime: 2012-01-25T04:19:56+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Anyone have ModelViewerWX3D9 anymore? The MOST updated version? The 0.4 version?
## Post #169
- Username: KiSteem64
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 01, 2010 9:40 am
- Post datetime: 2012-01-28T04:14:03+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Can someone tell me how extract Kingdom Hearts 2 .2ld images ?
## Post #170
- Username: GameAreAwesome
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 07, 2010 1:49 pm
- Post datetime: 2012-01-29T15:47:57+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

The contents of this post was deleted because of possible forum rules violation.
## Post #171
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2012-01-30T06:27:36+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

The contents of this post was deleted because of possible forum rules violation.
## Post #172
- Username: iwantedtoexplode
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 15, 2012 6:07 am
- Post datetime: 2012-02-06T03:52:06+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

The contents of this post was deleted because of possible forum rules violation.
## Post #173
- Username: kkdf2
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Oct 24, 2010 4:26 pm
- Post datetime: 2012-02-08T13:32:38+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Hi.

Sorry. recently I'm very lazy.

> Reply from iwantedtoexplode
>
> It seems that the vertex color information transfers over into Maya, since when I open the Component Editor, the vertices have various RGBA values assigned to them under the Advanced Polygons tab (don't really expect anyone to understand that, since this isn't a Maya forum, but I figured I'd say it anyway ). Hopefully it's only a matter of getting them to render.

If anyone has any other suggestions, I'm open to hearing them  I will keep you up to date as I make progress.
Sorry again, I don't have Autodesk Maya. (i have only Blender or such free softwares)

What I can do is to just ask google for any clue.

Make vertex colors visible
[http://download.autodesk.com/us/maya/20 ... isible.htm](http://download.autodesk.com/us/maya/2009help/files/Coloring_polygons_Make_vertex_colors_visible.htm)

This manual topic benefits you?

Thanks.
## Post #174
- Username: kkdf2
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Oct 24, 2010 4:26 pm
- Post datetime: 2012-02-08T13:48:18+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Hi.

> Reply from KiSteem64
>
> Can someone tell me how extract Kingdom Hearts 2 .2ld images ?
Both of yaz0r's and Falo's extractor can extract some of .2ld files.

files from yaz0'r:

```
menu\fm\camp.2ld
menu\fm\itemshop.2ld
menu\fm\jmemo.2ld
menu\fm\pause.2ld
menu\fm\save.2ld
menu\fm\title.2ld
```

files from Falo's:

```
file\jp\ca_na.2ld
file\jp\gm_ps.2ld
file\jp\he_co.2ld
file\jp\he_co2.2ld
file\jp\he_ft.2ld
file\jp\lm_al.2ld
file\jp\mg_lm_mu.2ld
file\jp\mu_mi.2ld
file\jp\tr_cy.2ld
file\jp\tr_tm.2ld
file\jp\tt_my.2ld
file\jp\wm_ws.2ld
menu\fm\camp.2ld
menu\fm\itemshop.2ld
menu\fm\jmemo.2ld
menu\fm\jm_world.2ld
menu\fm\pause.2ld
menu\fm\save.2ld
```

However I don't know how many files are there.

Falo's dumper usage:

```
kh2_file_dumper.exe P:\KH2 -dT
```
* P: is KH2fm media source.

Thanks.
## Post #175
- Username: iwantedtoexplode
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 15, 2012 6:07 am
- Post datetime: 2012-02-10T22:35:48+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from kkdf2
>
> Hi.

Sorry. recently I'm very lazy.
iwantedtoexplode wrote:It seems that the vertex color information transfers over into Maya, since when I open the Component Editor, the vertices have various RGBA values assigned to them under the Advanced Polygons tab (don't really expect anyone to understand that, since this isn't a Maya forum, but I figured I'd say it anyway ). Hopefully it's only a matter of getting them to render.

If anyone has any other suggestions, I'm open to hearing them  I will keep you up to date as I make progress.
Sorry again, I don't have Autodesk Maya. (i have only Blender or such free softwares)

What I can do is to just ask google for any clue.

Make vertex colors visible
http://download.autodesk.com/us/maya/20 ... isible.htm

This manual topic benefits you?

Thanks.

Thanks for your reply, and the link. I looked at that a few weeks back, but didn't have any success with it. I'll spend some more time now though.

However, I did use Blender to export the meshes into an .fbx file that Maya can use. Maybe if I'm able to get things working well in Blender, it will transfer over. Do you know a way of making vertex colors renderable in Blender? It displays pretty well in the viewport, but when rendered, no vertex colors. I think I was able to get some of it working, but I had to manually go to each part of the mesh and adjust the render settings, and as there are over 2000 draw cells, this isn't very plausible. Know of a faster way? Anything else you can think of that I might be able to do in Blender? Like if I can bake them to textures or lights, that's a more concrete process. As I said before, I'm willing to work with any program, so long as I can ultimately get it into Maya.

Thanks!
## Post #176
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2012-06-05T19:45:50+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Sorry to bump an old thread, but i remember that somewhere the was a mention of how to get one of the dumpers to extract 1 specific file that it hadnt dumped first time through typing a specific command in that program and it would dump that file, but does anyone know which program can do this and how i would go about it?
## Post #177
- Username: jadentheman
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Oct 24, 2014 7:21 am
- Post datetime: 2014-12-24T02:05:58+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Has anyone ever attempted to extract map models from original PS2 KH1FM game or 1.5 game?
## Post #178
- Username: ichibankameha
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Sep 20, 2016 11:33 am
- Post datetime: 2016-09-20T04:10:14+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

I am a pretty new to this but has any body explored the .map animations, like the cloud and water textures moving? 
each mesh seems to have a section of texture it controls for possible animation. are there bones you can control in the .map files?

I have been working on this for a while and thought someone else might be interested too. I am using noesis among others to view the map files, I don't know who made it but I also use the classic KH2FM map viewer that has the hex viewer too, thanks guys!
## Post #179
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2016-09-21T03:06:34+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

I believe those animations were available to view in yaz0r's ModelViewerWX v0.5, but all links to it were removed from this thread. I may have a copy on an old hard drive, so I'll see if I can dig it up.
## Post #180
- Username: ichibankameha
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Sep 20, 2016 11:33 am
- Post datetime: 2016-09-21T05:26:04+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

That would be awesome! I have most of the assets ripped from the original disk, will the .map animation files be .mset?
in the noesis viewer I couldn't find bones to move the map textures, like the water or the clouds. all i found where dozens of independent meshes that I assume control the texture animation.

also, are the effects like the lens flare and water sparkling in the sun (from the destiny islands map,) within the .map file, or are they separate, perhaps in a .2ld file?

This thread has taught me how to rip view the .map files. I have one of yaz0rs first model viewers from years ago but I haven't been able to find it again.

Thank you so much!

I checked and I have the .3 version of Yaz0rs model viewer, did he add .map support? that would be awesome.
## Post #181
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2016-09-21T10:39:53+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

I'm pretty sure Yaz0r didn't add map support until at least v0.4, so I'll have to check my old files. It could take a while, no promises I'll even find it, and if I do the Moderators could very well remove the links again. I'm not exactly sure how the animations worked, but I believe that many of the maps are pre-packed with animation files.
## Post #182
- Username: ichibankameha
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Sep 20, 2016 11:33 am
- Post datetime: 2016-09-21T23:34:35+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

I sure do appreciate it!
Alternatively I used pcsx2 and emu haste to explore the maps, however the dark margin freezes and I have not found a way to implement a free camera within pcsx2/kh2fm(JP).

Thanks again.
## Post #183
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2016-09-22T02:15:52+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

In the meantime, you can free-roam the KH2 map files in their entirety with [http://kkdf2.sakura.ne.jp/pcsx2lair/expack1h.7z](http://kkdf2.sakura.ne.jp/pcsx2lair/expack1h.7z) . The password is ][
## Post #184
- Username: ichibankameha
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Sep 20, 2016 11:33 am
- Post datetime: 2016-09-22T03:29:31+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Thanks so much, that is the one I have been using along with noesis.

I know nothing of the python language or blender, but could the export option provide the map animations in the .py script? I will have to check it out.
Thanks again, I sure do appreciate it!
## Post #185
- Username: ichibankameha
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Sep 20, 2016 11:33 am
- Post datetime: 2016-10-05T04:36:23+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Hey guys, I have been doing a lot of research and it is my goal to make a better map viewer. I am absolutely new to 3d rendering and programing(much less ps2 reverse engineering and emulation), but this is something I want to look into. It will take a while with my studying CNC machining, luckily CNC drafting software and 3D rendering are kinda similar.
Is any how is anybody  interested in this project?

And how about the HD remix's, are the meshes and textures upgraded, or did they just increase the resolution for the PS3?

If I need to I will make a standalone model to run in a generic/free game engine for the models I want.

What are your favorite models for those interested. I personally want Destiny Islands and the Dark Margin. I would like to look into the Twilight Town tower and Memories Skyscraper.
## Post #186
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2016-10-05T15:49:35+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

In the HD remixes, usually what happened is that the map models and textures were generally left as-is, but the character and enemy models all got retextured in HD. Some of the main characters and some of the Princesses of Heart got remodeled too, because a lot of those models were remade in HD for Birth by Sleep and KH3D.
Birth by Sleep HD is a different story. Not only were the textures upgraded, and all of the main character models, but the keyblade models were as well. They barely had any depth on the PSP version, so to look good in HD, all the keyblades had to be remodeled.
KH1, KH1HD, KH2, and BBS all have Noesis plugins or viewers for their models. There currently are no plugins or viewers for re:CoM, BBSHD, KH2HD, or KH3DHD. mysis made a Noesis plugin for BBSHD, but never released it, and Revelation was working on updating and releasing the source to many of his KH plugins, but last I heard from either of them was over a year ago.
In terms of map viewers, several have been released, but all only for KH2.
## Post #187
- Username: ichibankameha
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Sep 20, 2016 11:33 am
- Post datetime: 2016-10-05T17:32:19+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

That is a lot of help, I am Looking at the source code provided by kkdf2's map viewer and slowly learning. I am thankful much of this work has already been done.
I may either make a plugin for Noesis, or I will more likely make a stand alone viewer using slimdx and visual studio, I think that is what kkdf2 did.

I have only looked at PS2 era square game disks, I have not checked out the PS3 disk data of 1.5 or 2.5.
This is an ambitious project and I know I am in over my head, I thank you for the tips and encouragement. 

After 2.8 comes out I would like to see if I can find the way finder model and machine a realistic replica out of metal. Would that pertain to this community?
## Post #188
- Username: zimfan508
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 02, 2017 2:21 pm
- Post datetime: 2017-06-02T06:26:30+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Hey guys, I figured you MIGHT have an answer to this, but for some reason on Windows 10 the map viewer bugs out hardcore. When I go to rotate the camera within the map it freaks out and it only goes up and down super fast. I used it for when I build the maps within MC, but it has become hard to use.

Any way I can stop it from doing so?
## Post #189
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2017-06-13T21:29:34+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

That depends which map viewer you're using. I assume you mean the one in kkdf2's expack1h, but I've run it on my Windows 10 and it handles just fine. But if that doesn't work for you, it has a function to export the maps into .blend files for viewing in Blender. If that still doesn't work, Revelation's latest KH2 plugin for Noesis also can view KH2 map files, and Noesis can export any model you can view in it to a variety of other formats.
## Post #190
- Username: zimfan508
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 02, 2017 2:21 pm
- Post datetime: 2017-06-29T06:08:07+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Mirrorman95
>
> That depends which map viewer you're using. I assume you mean the one in kkdf2's expack1h, but I've run it on my Windows 10 and it handles just fine. But if that doesn't work for you, it has a function to export the maps into .blend files for viewing in Blender. If that still doesn't work, Revelation's latest KH2 plugin for Noesis also can view KH2 map files, and Noesis can export any model you can view in it to a variety of other formats.

Awesome! I'll check this Noesis thing out. Where could I get the plugin?
## Post #191
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2017-07-11T07:05:44+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from zimfan508
>
> Mirrorman95 wrote:That depends which map viewer you're using. I assume you mean the one in kkdf2's expack1h, but I've run it on my Windows 10 and it handles just fine. But if that doesn't work for you, it has a function to export the maps into .blend files for viewing in Blender. If that still doesn't work, Revelation's latest KH2 plugin for Noesis also can view KH2 map files, and Noesis can export any model you can view in it to a variety of other formats.
Awesome! I'll check this Noesis thing out. Where could I get the plugin?
I maintain a dropbox folder of the latest release of Noesis with the latest versions of all the plugins I could find. The Kingdom Hearts-related plugins are all here:
[https://www.dropbox.com/sh/8d4ydoefxp41 ... fMzra?dl=0](https://www.dropbox.com/sh/8d4ydoefxp41v6s/AAA84k0rP5WpSnwkFN0EfMzra?dl=0)
## Post #192
- Username: zimfan508
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 02, 2017 2:21 pm
- Post datetime: 2018-02-04T07:02:05+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Your suggestion definitely worked!
Also, is there map files available for kh2fm like how kh2 were?

I'd love to explore the fm rooms using the map viewer.
## Post #193
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2018-07-02T00:59:48+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from zimfan508
>
> Your suggestion definitely worked!
Also, is there map files available for kh2fm like how kh2 were?

I'd love to explore the fm rooms using the map viewer.
Yes, kh2fm's map files are just as explorable with the viewer as the base game's.
## Post #194
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2018-07-02T04:37:04+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Wow, this thread still lives?
## Post #195
- Username: Larxian
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 09, 2018 1:47 am
- Post datetime: 2018-07-08T18:05:48+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Hello, I just found out about this forum / thread and registered, and I wanted to ask, did anyone here manage to open the maps in Blender?
expack1h gives me a bunch of .py scripts when I export for blender, but it always ends up giving me coords errors like this:

Any idea about how to solve that issue?

Thank you!
## Post #196
- Username: Theo1910
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 29, 2018 6:52 am
- Post datetime: 2018-07-28T22:55:53+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Heyy, If You're Still Looking for the Map Files from 2FM, Tell Me; i Got Them All Dumped Out :D
## Post #197
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2018-08-15T23:09:20+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from ichibankameha
>
> That would be awesome! I have most of the assets ripped from the original disk, will the .map animation files be .mset?
in the noesis viewer I couldn't find bones to move the map textures, like the water or the clouds. all i found where dozens of independent meshes that I assume control the texture animation.

also, are the effects like the lens flare and water sparkling in the sun (from the destiny islands map,) within the .map file, or are they separate, perhaps in a .2ld file?

This thread has taught me how to rip view the .map files. I have one of yaz0rs first model viewers from years ago but I haven't been able to find it again.

Thank you so much!

I checked and I have the .3 version of Yaz0rs model viewer, did he add .map support? that would be awesome.
So, I was finally able to dig out my old hard drive, and I found my copies of all of yaz0r's old KH model viewers, including ModelViewerWXD3D9 versions 0.3, 0.4, and 0.52! I posted them here for those who are still interested in them:
[http://www.mediafire.com/file/ic295q4u8 ... 9.zip/file](http://www.mediafire.com/file/ic295q4u8hx0gq6/ModelViewerWXD3D9.zip/file)
## Post #198
- Username: Larxian
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 09, 2018 1:47 am
- Post datetime: 2018-09-02T18:01:54+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Is the export option supposed to work with this tool you just posted? Nothing happens when I click on it.
I tried using noesis to export as obj but the texture won't show up in blender.
I'd like to get import the maps in blender but didn't really have any luck with that.
## Post #199
- Username: peterpan03
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 06, 2018 5:39 pm
- Post datetime: 2018-09-06T09:42:05+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

I like this game too


[เว็บแทงบอล](http://www.ufa007.com) : po
## Post #200
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2018-09-21T01:00:03+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Larxian
>
> Is the export option supposed to work with this tool you just posted? Nothing happens when I click on it.
I tried using noesis to export as obj but the texture won't show up in blender.
I'd like to get import the maps in blender but didn't really have any luck with that.
I have no idea. I haven't used these in ages, and I didn't write them in the first place. Revelation's KH1 & KH2 Noesis Plugins can export models from the games as OBJs with textures. You might need to write a corresponding MTL file so that the materials are mapped to the associated textures in the OBJ, but once you do, it will work fine. It's possible that making such an an mtl file would fix the problem you're having with yaz0r's tools, but again, I don't know for sure.
## Post #201
- Username: PeacetimeMandylorian
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 01, 2019 10:46 am
- Post datetime: 2019-01-01T02:56:03+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Hello! I'm trying to make a Halloween display for the side of my house using projection mapping. We have a KH family, so I found the models that have been ripped from the game. I know they're rigged, but I'd really like the animations so that I'm not trying to attempt them from scratch. I've animated one thing in my life and it was... tedious and janky.

Do I need to rip the models and animations from the game? I was hoping for a shortcut, because the models are available as downloads. Does anyone have the animations (.mset files) available?

(I'm learning as I go, please forgive me for sounding like it!)
## Post #202
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2019-01-11T17:33:27+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from PeacetimeMandylorian
>
> Hello! I'm trying to make a Halloween display for the side of my house using projection mapping. We have a KH family, so I found the models that have been ripped from the game. I know they're rigged, but I'd really like the animations so that I'm not trying to attempt them from scratch. I've animated one thing in my life and it was... tedious and janky.

Do I need to rip the models and animations from the game? I was hoping for a shortcut, because the models are available as downloads. Does anyone have the animations (.mset files) available?

(I'm learning as I go, please forgive me for sounding like it!)
For KH-specific animations, you need to rip them from the game, but there are several pre-ripped models from the KH games on Models-Resource and DeviantArt. If you get DeviantArt's MMD or XPS KH models, there should also be universal animations also available on DeviantArt for MMD characters, though they are not KH-specific.
## Post #203
- Username: PeacetimeMandylorian
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 01, 2019 10:46 am
- Post datetime: 2019-01-13T03:25:20+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

> Reply from Mirrorman95
>
> PeacetimeMandylorian wrote:Hello! I'm trying to make a Halloween display for the side of my house using projection mapping. We have a KH family, so I found the models that have been ripped from the game. I know they're rigged, but I'd really like the animations so that I'm not trying to attempt them from scratch. I've animated one thing in my life and it was... tedious and janky.

Do I need to rip the models and animations from the game? I was hoping for a shortcut, because the models are available as downloads. Does anyone have the animations (.mset files) available?

(I'm learning as I go, please forgive me for sounding like it!)
For KH-specific animations, you need to rip them from the game, but there are several pre-ripped models from the KH games on Models-Resource and DeviantArt. If you get DeviantArt's MMD or XPS KH models, there should also be universal animations also available on DeviantArt for MMD characters, though they are not KH-specific.

Thank you! I've gotten animations and models- now i'm trying to get them to render correctly in Blender.  Do you know of anyway I can have Noesis export an fbx file that will show up in Blender already textured?  I can drag the textures, but I'm struggling with the alpha layers, immensely.  

Here is:

How it looked in the viewer: [https://pasteboard.co/HW9mQ1k.png](https://pasteboard.co/HW9mQ1k.png)

How it looks in blender: [https://pasteboard.co/HW9es6x.jpg](https://pasteboard.co/HW9es6x.jpg)

The files I'm working with: [https://pasteboard.co/HW9eZSV.jpg](https://pasteboard.co/HW9eZSV.jpg)

The Blender Node view: [https://pasteboard.co/HW9nhOY.png](https://pasteboard.co/HW9nhOY.png)
## Post #204
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2019-03-11T16:37:36+00:00
- Post Title: Re: Kingdom Hearts 2 Map files

Noesis isn't good with textures. It assigns them in the model file in a weird way. You'll likely have to reassign all the textures manually.
