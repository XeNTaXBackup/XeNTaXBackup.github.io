## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-04-25T00:54:43+00:00
- Post Title: Zone 66 (Classic DOS Arcade Shooter) Modding Update

Thanks to a email message from a Mr. Benjamin (sombody very interested in cracking Zone 66) about this fairly popular underdog he had sent me a cheat program that makes some ships super strong. In the sourcecode I learned somthing new. The actual permenant ship data is stored in:

MAPADAT3.Z66
MAPBDAT3.Z66
MAPCDAT3.Z66
MAPDDAT3.Z66
MAPEDAT3.Z66
MAPFDAT3.Z66
MAPGDAT3.Z66
and
MAPHDAT3.Z66

This is because the ship packages as well as the map packages were put on seperate floppies. So you could play, lets say you install floppy 1&2 package then 5&6 and be able to use all ships from those two. The program made from the source code was just made as a cheating patch program, not an editor, and only recognises MAPADAT3.Z66. And it lacks certain fields I discovered while picking at the SHIPDAT files. This was part of a shovelware CD Benjamin had and included it's source code:

```
#include <stdio.h>
#include <fcntl.h>
#include <dos.h>

#define uchar unsigned char

typedef struct
{
    char    padding[36];
    uchar   payload;
    uchar   fuel;
    uchar   armor;
    uchar   topspeed;
    uchar   accel;
    uchar   turning;

} SHIPDAT0;

void main( void )
{
    int handle;
    SHIPDAT0 sdat;

    /* This is a fake file to screw us over. */
    remove( "SHIPDAT0.Z66" );

    /* Real stats are stored here. */
    handle = open( "MAPADAT3.Z66", O_BINARY | O_RDWR );
    lseek( handle, 1423L, SEEK_SET );
    _read( handle, &sdat, sizeof sdat );
    lseek( handle, 1423L, SEEK_SET );

    sdat.payload = 255;         /* Max, because uchars are used. */
    sdat.fuel = 120;            /* Bleah.  You guess. */
    sdat.accel = 1;             /* 0 = EXCELLENT, 4 = POOR */
    sdat.turning = 1;           /* Ditto */
    sdat.topspeed = 7;          /* DON'T GO OVER 7! */
    sdat.armor = 120;           /* Doesn't really work */

    _write( handle, &sdat, sizeof sdat );
    close( handle );

    puts( "Patch done!" );
```


Compared to what I have found here: [Ship Hacking By Darkfox](http://www.geocities.com/shindarkfox/Zone66ShipData.html) (Better quality hex screenshot: [http://www.geocities.com/shindarkfox/ZONE66SHIPDAT0.PNG](http://www.geocities.com/shindarkfox/ZONE66SHIPDAT0.PNG)) you can see that it is very similar but mine involves already running the game and modifying the ships as you play. Landing then takeing off again will show the edited effects in gameplay if editing SHIPDAT0 and SHIPDAT1.

However the MAP(x)DAT3.Z66 files contain the permenant ship data for each ship pack (each included) amd if you look the pattern is exactly the same in each, no deviations exists except possibly in the weapons. Still uncertain if that mass of stuff refers to each gun, seems to be an awful lot for just a gun angle point.

I'm no coder but I do understand how to edit games and so far I've accomplished locateing most of the usage for each byte per ship. The future goals are:

-Adding custom ship packs.
-Map editing.
-Decompressing the graphics and possibly converting from/to common formats that doesn't muck up quality (tga, bmp, png).
-Decompression and maybe recompression of sounds and music.
-A small yet graphical program to simplify all this.

The last 3 would require a program, hence why I'm learning codeing is to extend out to underdogs like this to add them to the moddable titles, however for now codeing is nowhere near being my cup of tea. Hopefully the Z66 compression can be figured out because it would help with sound effects, BGM, and graphics.

In any case this is for those who have been emailing me of their interest in editing Zone 66. I hope they find this information helpful. And thanks to Benjamin for his contribution. 

-Darkfox
[MAPXDAT3.rar](https://xentaxbackup.github.io/file/1136_MAPXDAT3.rar)
## Post #2
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-04-27T01:57:18+00:00
- Post Title: Zone 66 (Classic DOS Arcade Shooter) Modding Update

Cool beans. Could you add this to the WIKI?
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-04-29T23:58:56+00:00
- Post Title: Zone 66 (Classic DOS Arcade Shooter) Modding Update

Plan to when I'm out of college which happens in... 2-3 more days. 

Also I just tested a little hypothesis:

Zone 66 DOES supports custom map packages and ship packages! I personally managed to make duplicate maps and ships from an existing package. The result was duplicate ships and maps at the end of selections.

With this confirmed that Zone 66 supports new custom maps, ships and even graphic packages, the possability to make Zone66 moddable is very possible and replacement of existing files is completely unneccesary. Which to modders is a very good thing. 

I plan to make a WIKI page for this with specific and proven methods and perhaps even a small program built partially from the code of that cheat program and off some old obsolete stat edit programs. Well that is the plan anyways and the easiest option I see so far. The basic functions would be modding of all currently known stats of each ship including the name, and even possibly the graphic once I figure out each graphic code and how they are recognised.

In any case at the end of this semester I'll get to work on that WIKI page. It's not often I add pages to a WIKI though so bear with me. XD

-Darkfox
## Post #4
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-04-30T01:56:27+00:00
- Post Title: Zone 66 (Classic DOS Arcade Shooter) Modding Update

Sounds pretty nice. As for adding to the WIKI, don't worry, I can clean it up for you when you're done, and if it needs it...
## Post #5
- Username: Ardent
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Apr 06, 2007 4:23 am
- Post datetime: 2007-05-01T00:13:28+00:00
- Post Title: Zone 66 (Classic DOS Arcade Shooter) Modding Update

"Mr. Benjamin" here! You can call me _Ardent, if you like.  Knowing that z66 is on the verge of cracking wide open is incredible news.  After searching high and low for Tran, the lead programmer (only to discover that he's "gone abroad"), I almost gave up.  Making a map of my own was always intriguing for me.

If there is anything else I can do, ask. I look forward to seeing the wiki.
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-05-01T01:39:33+00:00
- Post Title: Zone 66 (Classic DOS Arcade Shooter) Modding Update

Well my current theory for Zone 66 map data is assigned values for the placement of the chips, turrets, and building data as well as CPU ship spawn points and landing pad(s). I'll test that theory tomarrow which will be my last class day and it'll be an EASY one. 

I believe also in the map file will be the boundary data. Like where the map ends but hex editing a map is rather tedious so thats why I'm going to see into the makeing of a user-friendly map editor.

And if my other theory is right then it might be possible to assign a new chipset per map as soon as decompression/recompression is made possible. Know that when decompression is done it would be a bit harder to recompress. But me myself... well I am no good with compressions. The main compression schemes I understand is PK and LHA but hopefully sombody can help.

Edit: Btw, I'm learning as I'm going along. So I tinker, test, and revert. 

Additional info:

What files do in a map package I have identified:

MAP(?)DAT3.Z66 - Ship Data accompanying the map package.
MAP(?)PIC.Z66 - The picture of the map that appears in the selection screen.
MAP(?)GRFX.Z66 - Map Tileset

I'm going to test the other files and see what they do.
## Post #7
- Username: Ardent
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Apr 06, 2007 4:23 am
- Post datetime: 2007-06-22T18:24:29+00:00
- Post Title: Zone 66 (Classic DOS Arcade Shooter) Modding Update

[http://www.geocities.com/shindarkfox/Zo ... pData.html](http://www.geocities.com/shindarkfox/Zone66ShipData.html)
Regarding your findings, I have been doing a little investigating of my own.  I believe I've found almost all of the structure behind the code:
using the fauchard ship file as an example, I've color-coded a few key features. the first value (in red) has been determined as the ship size.  experimentation shows that if the first byte goes over FF (this value is unsigned) the second goes up by one, and the pattern starts at zero.  for example, if the ship file size is 283 bytes, it would be represented as "1B01", since 283d = 11Bh.  the byte shown in green indicates the number of engines the ship has. this example shows one engine, and it is highlighted in a different shade of green.  I will go into more detail with that later.  the purple-highlighted values should look familiar, they are weapons stats.  but the mystery bytes in between are really quite simple.  in-game, your ship can point in 16 directions: north, north-northeast, northeast, east-northeast, east, east-southeast, southeast, south-southeast, south, south-southwest, southwest, west-southwest, west, west-northwest, northwest, and north-northwest.  every set of two bytes represents a set of (x,y) coordinates in relation to the center of the ship. there are 16 sets of coordinates per weapon, each relating to a direction on the compass.  the values for these coordinates are signed, which means that low numbers are positive, and high numbers are negative. look at this example
...FC=-4 FD=-3 FE=-2 FF=-1 00=0 01=1 02=2 03=3 04=4... etc
the underlined value for the first weapon means that, when you are flying north, the gun should be placed at (-16,-1) on the ship.  this is also true with the engines. 
the way that the coordinates work are odd, the grid on which they are placed looks like this (see picture 2) 

going back, that big blue block of code seems to be the points of the shape that the ship uses for collision detection. I'm not as sure how it works, but I do know that every set of two bytes is a coordinate. I don't know if it is signed or not, or if it even matters.  the dark blue block appears to give the max dimensions of the coordinates.

[edit] I've done some experimenting and I've found that the blue block of code determines where each image of the ship should be placed in relation to the center of the actual ship itself.  collision detection is determined by using non-null (non-invisible) pixels of the ship image. so if the ship is not placed correctly, the enemy bullets will still strike the ship, but the engines, guns, and landing area will be off. [/edit]

I also have a small theory concerning turrets, I believe turrets are simply ships with a maximum move speed of zero and perfect turning. This would explain the slow version (weapon value 4) of the missile launching weapon.  just a theory...
[fauchard2.PNG](https://xentaxbackup.github.io/file/1226_fauchard2.PNG)
## Post #8
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-06-28T23:51:57+00:00
- Post Title: Zone 66 (Classic DOS Arcade Shooter) Modding Update

Turrets I am not so sure as they are completely absent in the ships section and not in a ship package but it is possible they exist in one of the packages but they may just use the weapon without being a ship itself. Hmmmmm... I have yet to figure out where weapon data is stored, let alone turrets.
