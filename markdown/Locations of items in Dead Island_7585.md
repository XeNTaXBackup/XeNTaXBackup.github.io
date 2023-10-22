## Post #1
- Username: anno1403
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 12, 2011 9:46 pm
- Post datetime: 2011-10-28T22:00:49+00:00
- Post Title: Locations of items in Dead Island

Hello all, I have been lurking in this forum for over a year, and finally decided to post here, since there is some really good information on modding Dead Island. I hope I posted in the right place etc.

I just want to know how Dead Island places its items. For example, if I wanted to move a metal chest to another location, which file would I modify? 

I am hoping to be able to add existing  items to areas so I can take screenshots of them, but after a month and half of looking through the files, I am still no closer to figuring out which file to modify.
## Post #2
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-10-29T01:46:40+00:00
- Post Title: Locations of items in Dead Island

That type of information is typically stored together with the rest of the map data - depending on the exact format used, it typically just consists of something like an ID number to identify what object is being placed, and a set of coordinates for its location and orientation (and possibly some flags for the item's state and what-have-you).
## Post #3
- Username: anno1403
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 12, 2011 9:46 pm
- Post datetime: 2011-10-29T05:49:58+00:00
- Post Title: Locations of items in Dead Island

> Reply from Dinoguy1000
>
> That type of information is typically stored together with the rest of the map data - depending on the exact format used, it typically just consists of something like an ID number to identify what object is being placed, and a set of coordinates for its location and orientation (and possibly some flags for the item's state and what-have-you).

thank you dino. I suspected as much, as I have heavily edited Dead Rising 2, but your email was extremely helpful in pointing me in the right direction. 

I will check the Dead Island\DI\data0.pak\data\maps folders, which include the following folders:

```
act2a
act3a
act3b
act3c
act4a
act4b
buildinginterior
cityhalla
cityhallb
common
hotel
market
menuback
parkinglot
policestation
sewers
```


and the following files:

```
WorldMap.scr
```


Inside the act1a folder, for example is the following files:

```
act1a.road
act1a.scr
act1a.sobj
act1a.startprop
act1a.exp
act1a.height
act1a.loot
act1a_ambient.scr
act1a_cave.scr
act1a_foliage.scr
act1a_forbidden_meshes.scr
act1a_harris.scr
act1a_indoor_hdr_a.scr
act1a_lifeguard_top.scr
act1a_map_info.scr
act1a_medium_range.scr
act1a_medium_range_shadows.scr
act1a_nosmokedust.scr
act1a_ovr.scr
act1a_quest_hubs.scr
act1a_short_range_a.scr
act1a_short_range_shadows_a.scr
Movie_01_DoorOpen_SP.scr
Movie_01_RH_Boss_SP.scr
Movie_02_SaveSinamoi_SP.scr
Movie_02_SinamoiHub03_SP.scr
Movie_05_Suicider01_SP.scr
Movie_07_Hotel_SP.scr
Movie_07_KillFather_SP.scr
```


Screenshot: [http://gyazo.com/2fa24fb2416a962ec5e4935e1e6906dc](http://gyazo.com/2fa24fb2416a962ec5e4935e1e6906dc)

It is probably in one of the big files such as the sobj file. I will need to search the internet on how to open such files.
## Post #4
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-10-29T06:18:48+00:00
- Post Title: Locations of items in Dead Island

The .sobj file is definitely where I'd start looking. 

The first thing I'd try is to just open it in Notepad (or your text editor of choice); there's always the chance it's a plain-text file, which would make editing much easier. If that doesn't work, and you can't find any info or tools online, you'll just have to resort to opening the file in a hex editor, such as XVI32 or Hex Workshop.
