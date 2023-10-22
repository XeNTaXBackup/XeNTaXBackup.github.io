## Post #1
- Username: mrjohnson86
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 02, 2017 12:53 am
- Post datetime: 2017-09-01T19:04:14+00:00
- Post Title: Game:CodO/ Archives: IFS/ Header nifs..

Hey all,

So I am pretty new to reverse engineering File formats.
I have spent the last few days trying to make sense of theCall Of Duty: Online .IFS files.
I use Hex Workshop and ide.Kaitai for a visual viewport
a screenshot of, offset:


files: [https://drive.google.com/open?id=0Bzp4Q ... G1FUGwtVzA](https://drive.google.com/open?id=0Bzp4QywF5DscOHdUNG1FUGwtVzA)

I can upload more if needed, just request

thanks
## Post #2
- Username: mrjohnson86
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 02, 2017 12:53 am
- Post datetime: 2017-09-03T23:12:21+00:00
- Post Title: Game:CodO/ Archives: IFS/ Header nifs..

The game Call Of Duty: Online is a free to play call of duty based in china. anyone can download for free form the official site, however to register and play you would need assistance.. perhaps a search on your favourite search engine will guide you

So I have 347 .ifs files ranging from 17kb - 350mbs

Now opening one of the 17KB files in Hex Workshop, just after the 
header:
HEX header:

```
6E696673, AC000000, 00000500, 0040000000000000, 3527000000000000, E221000000000000, 0040000000000000, 2040000000000000, 4305000000000000, D900000000000000, 2000000000000000, 0100000000000000, 00400000, 00400000, 33B4, 80B8, 4BAE, 919A, C35C, 1043, BF31, 5343, 6257, 2222, A2D9, E397, 996F, AFD2, DF2D, 57FE, 45D7, 4FD8, AC7B, FEE0, BB87, 7523, 394D, 047E, 5028, 8851, 85D5, ED73, 8987, A6AD, F37C, 8505, 47AA, 17B2, 86D5, 2C6B, 9981, 7C3F, 4995, E2CC
```

ASCII header:

```
nifs.........@......5'.......!.......@...... @......C............... ................@...@..3...K....\.C.1SCbW"".....o...-W.E.O..{....u#9M.~P(.Q...s.....|..G.....,k..|?I...
```


I can see readable strings, it seems that these are File locations, for example:

```
main/models/projectile_cbu97_clusterbomb_lod011..
main/sound/amb_emitters/emt_cave_stress.mp3..
main/sound/amb_emitters/emt_mach_hum_splash2_loop.wav..
main/sound/amb_emitters/emt_rock_debris_verby_loop.wav..
main/sound/amb_emitters/emt_water_drips_loop.wav..
main/sound/amb_emitters/emt_water_rivernobird_dist_loop.wav..
main/sound/amb_emitters/emt_wind_loop_desert2.wav..
main/sound/amb_emitters/emt_wood_rocks_heavy1res.wav..
main/sound/amb_emitters/emt_wood_rocks_heavy2res.wav..
main/sound/explosions/dest_firextngsh01.wav..
main/sound/explosions/dest_firextngsh02.wav..
main/sound/explosions/dest_firextngsh03.wav..
main/sound/music/mp/mp_afghan_spawn_141.mp3..
main/sound/music/mp/mp_afghan_spawn_scar.mp3..[/color]
```


If you were to count, there are 15 files listed above and yet another 174 .iwi files found by a quick search....

Now after each file string shown above, you see .. , the two bytes that represent these are 0D 0A

Now to me this seems very unlikely or even possible to fit 189 files, specially with .wav/mp3, even compressed?

Checking other files:
Doing a search on part of the file name "afghan" shows the following results

```
ff_dlc2_mp_afghan_V42.ifs     - 27.4
ff_dlc19_hp_addon_mp_afghan_V1.ifs - 32kb
lf_dlc19_hp_addon_mp_afghan.ifs    -32kb
lf_dlc2_mp_afghan_V8.1.ifs    - 17kb
lf_dlc2_mp_afghan_V8.2.ifs    - 17kb 
```


The files lf_dlc2_mp_afghan_V8,  lf_dlc2_mp_afghan_V8.1.ifs, lf_dlc2_mp_afghan_V8.2.ifs seem to have the same filenames in all three.

A quick hex search on these files shows the following
lf_dlc2_mp_afghan_V8 has 177 .iwi files
lf_dlc2_mp_afghan_V8.1 has 174 .iwi files
lf_dlc2_mp_afghan_V8.2 has  173 .iwi files

So what can this mean? As you can most probably tell, I am a bit lost.. 

any help will be grateful
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-09-04T01:09:55+00:00
- Post Title: Game:CodO/ Archives: IFS/ Header nifs..

there is some code here for a tool which might work, needs compiling though i guess   
[https://github.com/FreeTheTech101/ifs-tool](https://github.com/FreeTheTech101/ifs-tool)
edit: i think i found compiled tool here, or maybe not   
[http://rgho.st/8T828NYdb&prev=search](http://rgho.st/8T828NYdb&prev=search)

or you could run this by aluigi on Zenhax and see if you can get a bms extraction script.
## Post #4
- Username: mrjohnson86
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 02, 2017 12:53 am
- Post datetime: 2017-09-05T11:12:39+00:00
- Post Title: Game:CodO/ Archives: IFS/ Header nifs..

> Reply from AceWell
>
> there is some code here for a tool which might work, needs compiling though i guess   
https://github.com/FreeTheTech101/ifs-tool
edit: i think i found compiled tool here, or maybe not   
http://rgho.st/8T828NYdb&prev=search

or you could run this by aluigi on Zenhax and see if you can get a bms extraction script.

Thank you, I will give this unpacker ago, I have tried other unpackers for ifs, but no lucky yet.

Well as soon as unzipped this, I got an overwrite message, it is one of the ones I have already tried, but thank you anyways
