## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-02-02T09:05:08+00:00
- Post Title: Twisted Metal PS3 (2012)

Twisted Metal PS3 (2012) models tool

Usage: drop .NGP file onto the tool. Corresponding .VRAM file must be in the same folder
Tool will output all meshes into single .ASCII file with all UV pairs, and also each mesh into individual .OBJ file with only 1st UV
Skeletal meshes will be output as static. The full data tree will be written to console.






[tm2012.rar](https://xentaxbackup.github.io/file/17454_tm2012.rar)
## Post #2
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-02-02T11:50:06+00:00
- Post Title: Twisted Metal PS3 (2012)

"I've killed tougher than you, a**hole! Don't get cocky, you're just the appetizer...before I find and slaughter the entree!"
—Sweet Tooth


Ohhh man!!! Thank you so much for this tool!!!
Finally i can get my hands on the Brothers Grimm models   

EDIT:
The single .obj files come out very distorted....or faces seem to connect wrong:

This is what seems to be warthogs tank part.
Blender won't even let me import the .objs

Can u help me out here?
Judging from your screenshots, you managed to import the files into blender 

2. EDIT:
I found a quickbms script here on xentax that is able to convert the games .rtt and .vram textures into .dds!
[viewtopic.php?f=10&p=92488#p92488](https://forum.xentax.com/viewtopic.php?f=10&p=92488#p92488)
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-02-02T17:40:31+00:00
- Post Title: Twisted Metal PS3 (2012)

ok OBJ fixed
## Post #4
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-02-04T12:50:59+00:00
- Post Title: Twisted Metal PS3 (2012)

> Reply from daemon1 ↑Mon Feb 03, 2020 1:40 am at Mon Feb 03, 2020 1:40 am
>
> ok OBJ fixed

Thanks man! Looking much better now!!!


Did you allign the wheels to the axels yourself or did you do it via the .ascii file?

EDIT:
There also seems to be no UV-Map for the .OBJ files:


How did you do your blender imports?

PEACE
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-02-04T19:22:54+00:00
- Post Title: Twisted Metal PS3 (2012)

Tool updated. OBJs fixed again.

Also "boss3" level now must work. This level had additional .PGM file with extra geometry. It will not be exported, just skipped. But tool will not crash and export everything else.

I can add PGM export later if there's anything important there.
## Post #6
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-02-05T17:21:18+00:00
- Post Title: Twisted Metal PS3 (2012)

> Reply from daemon1 ↑Wed Feb 05, 2020 3:22 am at Wed Feb 05, 2020 3:22 am
>
> 
Tool updated. OBJs fixed again.

HELL YEAH! UVs now work!!! (but have to be flipped on the y-axis) Thank you for the time you put into this tool man 



Theres still alot to move and tweak by hand....most of the boss1/hammerhead submeshes allign perfectly well and keep their damage versions on the exact same place. However alot of other meshes (wheels, mohawk exhaust, monitors, dashboardparts) are either slightly off on the y-axis or just just simply at 0,0,0 (world origin). Are these position coordinates handled by other files in that case?

Heres a picture of the original hammerhead from artstation:




NOTE: The truck has two phases during the boss fight. One with armor, the other without.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-02-05T17:46:10+00:00
- Post Title: Twisted Metal PS3 (2012)

> Reply from Henchman800 ↑Thu Feb 06, 2020 1:21 am at Thu Feb 06, 2020 1:21 am
>
> 
Are these position coordinates handled by other files in that case?
no, they are in the data tree
i dont have time to analyze and apply them, because there are too many
## Post #8
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-02-06T01:49:47+00:00
- Post Title: Twisted Metal PS3 (2012)

> Reply from daemon1 ↑Thu Feb 06, 2020 1:46 am at Thu Feb 06, 2020 1:46 am
>
> 
no, they are in the data tree
i dont have time to analyze and apply them, because there are too many

I See 
Still big ups for the tool man!
## Post #9
- Username: RockFistLee
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 07, 2023 3:41 pm
- Post datetime: 2023-06-26T11:12:50+00:00
- Post Title: Twisted Metal PS3 (2012)

Bah ive tried this tool on three pc's and it just doesn't wanna work for me.
## Post #10
- Username: ZFPInTheAir
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Feb 24, 2020 2:27 am
- Post datetime: 2023-09-11T03:26:35+00:00
- Post Title: Twisted Metal PS3 (2012)

i noticed that the UI files dont give all textures for the characters, im assuming the rest are in the .LTN that i have no idea how to get into
