## Post #1
- Username: Nukem
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Sep 28, 2006 9:00 pm
- Post datetime: 2006-09-28T15:37:29+00:00
- Post Title: Loco Mania / Locomania

Hi there!

Does anybody know something about the level file format for the game "Loco Mania" / "Locomania"?

The official website http://www.loco-mania.com seems to be dead right now... (although the address responds to pings) 

But you can get a demo version via [wazap.de](http://www.wazap.de):http://de.wazap.com/loco-mania-pc,infor ... 52,22.html
http://de.wazap.com/locomania-pc,inform ... 66,22.html

or the official publisher forums:http://www.lighthouse-interactive.com/f ... 87d53a767d

Developer:7FX (website also dead!?   )

Publisher / Distributor:Lighthouse Interactive
Eclypse
Frogster Interactive

The subdirectory ".\lm\data" contains the levels, 3 files for each - for example Level 2:level002.dat - ASCII file, contains a hash/checksum (?) for the data file and some parameters regarding gameplay (maximum count of trains etc.)
level002.pkg - binary file, big (10 - 25 MB), seems to contain the mesh data for the landscape of the level, the magic word at the beginning is "#LF2PKG:"
level002.sc - ASCII file, contains parameters for the graphical representation (like fog density etc.)

Unfortunately, the change of even a single value (like 12 instead of 10 maximum train count) in the ASCII files causes the game to not even start (jumps back to the desktop immediately), so I pretend that the hash in the DAT-file is taken as a checksum.

Also, I would want to know how the mesh data of the landscape is stored in the PKG file.

Does anybody has a clue, is already on it, or in need of a challenge?!   

The level002.* files are identical for the demo and the retail version, so there is just ONE checksum for demo/retail for each level.
## Post #2
- Username: Nukem
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Sep 28, 2006 9:00 pm
- Post datetime: 2006-09-28T15:42:33+00:00
- Post Title: Loco Mania / Locomania

Here are the level 2 ASCII files:

level002.dat:

```

[params]
concurrent_trains 5
hour_train_freq 90
delayed_spawn_sec 3
passmark 18
target_done_sec 30

[io_defs]
rail_018_pth io 2515FF
rail_019_pth io FF0505
rail_020_pth io FFEC4D
rail_021_pth i  05C8FF
rail_022_pth o  008000
rail_025_pth io FF05F1
rail_027_pth io 000000

[target_defs]
tg0 rail_036_pth|rail_038_pth 2515FF
tg1 rail_042_pth|rail_040_pth 008000

[io_pairs]
rail_021_pth rail_019_pth
rail_025_pth rail_019_pth
rail_018_pth rail_025_pth
rail_020_pth rail_022_pth
rail_027_pth rail_018_pth
rail_021_pth rail_025_pth
rail_025_pth rail_027_pth
rail_018_pth rail_022_pth tg1
rail_019_pth rail_018_pth tg0
rail_019_pth rail_020_pth
rail_021_pth rail_027_pth tg1
rail_021_pth rail_020_pth tg1
rail_018_pth rail_022_pth tg0|tg1

[predef_trains]
LD08 VC12 VC12
LD03 VC13 VC13 VC17 VC16 VC03 VP01
LD07 VC14 VC14 VC02 VC03 VC19
LD05 VC19 VC19 VC19 VP01
LD07 VC02 VC02 VC03 VC18
LS02 VC17 VC02
LD03 VC02 VC19 VC18
LD01 VC10 VC10 VC11 VC11 LD01
```


level002.sc:

```
set sv_ambient_color 128 128 133 255

set sv_fog_start 1000
set sv_fog_end 700000
set sv_fog_color 200 202 207 255

set sv_shadow_bound -1500

set gv_day_duration 600

set gv_sun_rot_azimuth  45
set gv_sun_elevation -20
set gv_sun_horizon_angle 15

set gv_sun_perc 100
set gv_fog_perc 0
set gv_rain_perc 0
set gv_rain_fog_perc 15
set gv_snow_perc 0
set gv_snow_fog_perc 0

set gv_fog_start_sunny 1000
set gv_fog_end_sunny 700000
set gv_fog_color_sunny_90 200 202 207 255
set gv_fog_color_sunny_30 185 168 138 255
set gv_fog_color_sunny_15 115 65 65 255

set gv_fog_start_foggy 300
set gv_fog_end_foggy 85000
set gv_fog_color_foggy 140 145 148 255

set gv_sun_diffuse_90 225 225 220 255
set gv_sun_diffuse_30 235 230 222 255
set gv_sun_diffuse_15 215 170 145 255

set gv_ambient_90 128 128 133 255
set gv_ambient_30 115 115 100 255
set gv_ambient_15 100 85 85 255

```
