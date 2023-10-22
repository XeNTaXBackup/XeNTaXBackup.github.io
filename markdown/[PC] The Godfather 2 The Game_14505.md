## Post #1
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2016-06-23T03:34:06+00:00
- Post Title: [PC] The Godfather 2 The Game

Hi everyone,

I'd love to get my hands on the soundtrack from The Godfather 2 The Game, and it seems like it uses a pretty common EA archive format, similar to what The Godfather and The Dead Space games used. This game has massive .VIV files at its root, then some other formats distributed throughout the game. Namely, I think I'm interested in a particular .STR file - one named emx_global_folder_stream.str and placed in a global/audio folder. I believe this may have my music, or at least something to that effect.

For reference, there's a topic [here](http://forum.xentax.com/viewtopic.php?f=10&t=5881) about Dead Space 2 which involved Rick making an entire suite of tools targeting Visceral games, the same company that made The Godfather 2. Unfortunately his tools can't seem to read The Godfather 2's resources - they report incorrect magic/too large headers. I'll try to post some headers/snippets tomorrow, but so far has anyone had any success with this game?

Update: Here's a hex-view of the first VIV file in the game directory, taking note that the first four bytes are 42 49 47 46 or BIGF. Referring to [a post](http://forum.xentax.com/viewtopic.php?p=47899#p47899) in the aforementioned DS2 thread, someone wrote a BMS that apparently expects an ID of "BIGH"? Maybe that's the issue here?



First VIV file hex view. gf2_viv.PNG (34.42 KiB) Viewed 316 times



Referring to the wiki, there is a page called [EA BIG BIGF Archive](http://wiki.xentax.com/index.php?title=EA BIG BIGF Archive) with a header that matches my file. Checking the file though, the archive size doesn't seem to match up according to the spec. In my file, the archive size is supposedly defined as bytes D0 5E F4 6B or dec 3,495,883,883. However, the file size reported by Windows is 1,811,177,168 bytes. Maybe there's a compressed/uncompressed difference going on here?
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-24T15:57:47+00:00
- Post Title: [PC] The Godfather 2 The Game

There was never a case when visceral music was located in .str files.
Do you have a list of files you get after extracting VIV archives?
## Post #3
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2016-06-24T20:43:02+00:00
- Post Title: [PC] The Godfather 2 The Game

The problem is that I can't even open the VIV files, Rick's tools report that the magic is incorrect.

Edit: I've been updating the OP with some information I'm currently gathering.

Edit2: I've downloaded Visceral's sourcecode so I can start taking a look at it. He is expecting a magic number 0x42494748 (BIGH) which the Dead Space games use for some reason, while GF2 uses BIGF as stated before. Interestingly, there's no wiki page on the BIGH file 

Also interesting is a comment where rick scans in the file size int:

```
input.ReadValueU32(true); // :wtc:
```


That function indicates that the value read in is little endian, while apparently everything else is big endian. A little curve ball there which explains why I was getting a strange number in my BIGF header before. When I flip the bytes to account for endianness now:



Little endian! gf2_viv2.PNG (12.37 KiB) Viewed 316 times



Hey, it matches up! So far it looks like the file archives are identical, but I haven't even tested my modifications to rick's tool yet.

Update: After some googling, it looks like watto's Game Extractor could handle the [VIV/BIGF](http://www.watto.org/game_extractor.html) format. I've downloaded it and so far it's able to read the archive just fine, I think I may have my work cut out for me.
## Post #4
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2016-06-25T00:20:59+00:00
- Post Title: [PC] The Godfather 2 The Game

Ok, I've gotten much farther than I though! I'm currently trying to tackle one of the sound files, which has an extension exa.snu.

The four byte file header is 03 08 00 04 which doesn't seem to convert to any ASCII very nicely. Just looking at the hex in general, it appears that there isn't much data until offset 28-ish. Here's a screenshot:



gf2_exasnu.PNG (27.14 KiB) Viewed 316 times



Initial googling has only directed me to discussions on other variations of the SNU format, so maybe this one is a little special...

Updates: I've been playing with the ealayer3 tool and I think it might be a possibility. Running it without any parameters fails immediately. Some people suggested (again in Dead Space 2) to use offset 32, which doesn't work here. Looking at the hex though, it seems like actual data is at offset 40. This is what appears to be the "header":

```

```


```

```


When I tell ealayer3 to start at offset 40, here's what it outputs:

```
L: header B loader incorrect because of block type
L: headerless loader correct
P: EAL3 ver. 6 and 7 incorrect with exception: Ver. 6 and 7 header: granule size set incorrectly.
P: EAL3 ver. 5 incorrect with exception: Sample rate index field invalid.

```


Right now, I wonder if I'm just fumbling around for the right offset or if this is actually an incompatible format...?
## Post #5
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2016-06-25T02:10:11+00:00
- Post Title: [PC] The Godfather 2 The Game

Finally, I've got it! The last program I needed was [ToWav](http://www.ctpax-x.org/?goto=files&show=24) (site in Russian, just find the download button near the bottom). I did come across this program on Xentax before, but the version linked there was a packed executable that was likely a trojan. This one doesn't set off my virus scanner, although I wish the author would post the source code.
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-25T05:22:45+00:00
- Post Title: [PC] The Godfather 2 The Game

Yes, VIV archives are really simple structured, so no wonder there are many programs that can handle it.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-25T05:32:06+00:00
- Post Title: [PC] The Godfather 2 The Game

> Reply from tgp1994
>
> the version linked there was a packed executable that was likely a trojan.

It was never a trojan, just antiviruses false-detected it. You know, I once made a simple program with only a couple lines of code to split an archive similar to this VIV and a big icon of the game it was for. And it was detected as a trojan by 20 of 50 antiviruses on virustotal.
## Post #8
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2016-06-25T12:54:47+00:00
- Post Title: [PC] The Godfather 2 The Game

> Reply from daemon1
>
> tgp1994 wrote:the version linked there was a packed executable that was likely a trojan.

It was never a trojan, just antiviruses false-detected it. You know, I once made a simple program with only a couple lines of code to split an archive similar to this VIV and a big icon of the game it was for. And it was detected as a trojan by 20 of 50 antiviruses on virustotal.

Yet somehow the version I've downloaded from that website has a way lower detection rate? I mean, I dunno. If you write a program that simple and it gets picked up by nearly half of the major AV programs, you must be doing something wrong
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-25T13:00:16+00:00
- Post Title: [PC] The Godfather 2 The Game

> Reply from tgp1994
>
> Yet somehow the version I've downloaded from that website has a way lower detection rate?

That's just because its much older version, having much more formats to handle.

> Reply from tgp1994
>
> If you write a program that simple and it gets picked up by nearly half of the major AV programs, you must be doing something wrong

No. Because I know it had ABSOLUTELY NO VIRUSES. So this is because AV programs can't detect anything correctly. People are actually forced to make efforts to have AV programs don't false-detect their clean code.
## Post #10
- Username: SURly
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 13, 2014 7:35 am
- Post datetime: 2018-04-25T12:47:01+00:00
- Post Title: [PC] The Godfather 2 The Game

Just confirming that Game Extractor and ToWav work perfectly; thx to anyone involved.
## Post #11
- Username: pablo67340
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 31, 2017 1:57 am
- Post datetime: 2018-10-12T22:31:15+00:00
- Post Title: [PC] The Godfather 2 The Game

I don't mean to necro or anything, however this topic grabbed my attention. The Godfather is my ALL time favorite nostalgic Xbox 360 Game. I have beaten the game close to about 6 times in my lifetime, and I've enjoyed it every time. 

Just out of curiosity, I was wondering if anyone could continue helping me tackle this "reverse-ish" engineering. 

After looking through all the posts, I was able to use Game Extractor to successfully extract .str files and a "localetable".

Now, I am left with STR files that appear to be archives as well. I'd like to be able to get into the game and make some tweaks, mess around with things. I have my fair share of programming knowledge with just under 7 years of experience, however, when it comes to reverse engineering, memory editing, etc, I get lost. What I am getting at here is, or what I'd like to know rather, is, would it be possible to break this game down into editable source? I notice missions are inside of a missions folder which also contains a ton of .str files. Theoretically, could it be possible to make my own missions? Bug Fixes? Additions? How far can we break this game down before its un-editable? And what IS possible here? 

I know this looks very confusing, and my typing isnt the best, but I would love if an expert in this area could give input! I'd absolutely love to be able to make some changes my all time favorite game! I was able to achieve something similar by extracting FF files from COD Black Ops 1, which I had to decrypt & extract .gsc files from. Those gsc files also had to be "decrypted" so it was in proper code format. Lastly, I was able to get RawFileManager (loaded via dashlaunch), and have it inject my decompiled, edited GSC's back into blackops during map load on Zombies. The reason I did this was to address many things:

Bugs:
Mule Kick does not spawn on Der Riese while in Splitscreen, but OFFLINE. If online, it spawns?
Max ammo doesn't replenish magazine already inside weapons
If player 1 removes battery pack, causing the game to freeze, when the game resumes, It will no longer be splitscreen and player 1 will take the entire screen until 
player 1 pauses again. This also locks player 2's controls. 
If player 1 sets the screen brightness/audio settings, and player 2 opens the options, all brightness and audio settings reset to default
until player 1 pauses and enters options again.

Tweaks:
No more dog & zombie mix rounds. Just zombie, or dog rounds.
Reduced price of betties
Reduced price of Gewher (speed up start rounds)
Zombies no longer keep attacking when their heads are blown off... this was always ridiculous, and messed up trains while aiming for headshots. Often led to deaths.

Added:
All Revive powerup to teleporters
Free perk powerup to teleporters
Firesale powerup to teleporters


All of these bugs, I have fixed for the pure enjoyment of the game, as Black ops 1 zombies is also one of my favorite game modes when friends are over. I guess, all in all, I'd like to have The Godfather at a stage where I can make edits like this too. 

Thanks for the time, and sorry for the long read.
## Post #12
- Username: ManFat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 27, 2019 4:31 am
- Post datetime: 2019-01-26T22:25:19+00:00
- Post Title: [PC] The Godfather 2 The Game

sorry if anyone gets offended by me bringing an old post back from the dead.

anyhow, im trying to extract my godfather 2 xbox 360 files(BIGFILE1.VIV). i have the visceral gibbed from github. ive read a bunch of threads and seems that is the thing to use. ive used other versions of gibbed for other games no problem. i dont understand how to use the files i downloaded. usually there ia a .bat or .exe to drag the target file on to . on what i have here, the extensions are all .cs and .csproj. maybe i downloaded the wrong package or im just not familiar with this format.

im trying to get to the key/button bindings to see if i can alter them a bit. the files are named 'BIGFILE1.VIV'.. etc. 
i did get some result from dragging on to 'Frostbyte_chunk.exe'. it took a 100mb file and turned it into a 1gb .chunk file. no idea what to do with that.

i ask here before i would create my own post cuz maybe someone involved with this post has experience with this extraction and will be alerted.

thank you anyone
Fat

edit:trying to figure out visual studio atm
