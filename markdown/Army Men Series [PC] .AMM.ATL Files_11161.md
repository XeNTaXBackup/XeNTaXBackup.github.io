## Post #1
- Username: SRDDonkey
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 22, 2014 1:39 pm
- Post datetime: 2014-01-25T23:16:03+00:00
- Post Title: Army Men Series [PC] .AMM/.ATL Files

I cannot figure out how the AMM/ATL files for the maps in army men are loaded into the game. I assume the tiles and many of the required assets are included within these two files for a map, but cannot figure out how to extract these assets. The maps also include a "objects.dat" file which I assume is where some assets are possibly.

I have been trying my hand specifically at Army Men 2 [PC] by 3DO

Info
[http://www.mobygames.com/game/army-men-ii](http://www.mobygames.com/game/army-men-ii)

Demo
[http://www.fileplanet.com/135544/130000 ... ial-Client](http://www.fileplanet.com/135544/130000/fileinfo/Army-Men-II-Trial-Client)

These two files are present throughout all their games including the original Army Men, Army Men: Air Tactics, etc

Any help is greatly appreciated
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2014-05-25T23:01:12+00:00
- Post Title: Army Men Series [PC] .AMM/.ATL Files

Ok, this is what I figured out so far:



ARMYMEN_ATL_ANM.png (83.28 KiB) Viewed 121 times


OBJECTS.DAT

byte[4]		maybe checksum?
byte[1024]		color palette (256 colors)
uint32		number of objects

// object index table
for each object {
  byte[4]		unknown
  uint32		offset
}

// actual objects
for each object {
  byte[24]	header
  uint32	size of section1
  <section1>
  uint32	size of section2
  <section2>
  uint32	size of section3
  <section3>
}

<section1>
uint16	sprite_width
uint16	sprite_height
for (sprite_height) {
  uint16	line_offset
}
<run-length encoded pixel data>

<num_transparent_pixels><num_opaque_pixels><opaque_pixels[]>
e.g.
55 00 -> 0x55 transparent pixels, no opaque pixels
45 01 20 0F 00 -> 0x45 tr., 1 opaque (index: 0x20), 0xF tr.

<section2>
same structure as section1 (maybe semi-transparent pixels?)

<section3>
looks like a monochrome bitmap (each byte represents 8 pixels)
maybe the shadow of the object?

size of section3:
(sprite_width/8) round up to the next even number
e.g. sprite_width = 85, sprite_height = 80
85 / 8 = 10.625 -> 12 (=line width)
size of section3 = 12*80 = 960
## Post #3
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2014-05-25T23:08:30+00:00
- Post Title: Army Men Series [PC] .AMM/.ATL Files

I also managed to rebuild the map with the tileset (ATL) and the data from the TLAY section (ANM):
[https://www.mediafire.com/?f3dq5d022c6836r](https://www.mediafire.com/?f3dq5d022c6836r) (2.34 MB)
## Post #4
- Username: SRDDonkey
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 22, 2014 1:39 pm
- Post datetime: 2014-05-26T03:22:51+00:00
- Post Title: Army Men Series [PC] .AMM/.ATL Files

Oh nice! I never would have been able to begin trying to comprehend that stuff xD I can't thank you enough for this help so far. Do you know about the .ani files in any way as well?
## Post #5
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2014-05-28T05:17:33+00:00
- Post Title: Army Men Series [PC] .AMM/.ATL Files

Update: File format of "objects.dat" unveiled.


 ArmyMen2_Object.dat_Extractor_1.0.zip
(196.03 KiB) Downloaded 51 times


The *.ani files have a similar format but I haven't had time yet to go in for a closer look.
## Post #6
- Username: tminard
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 15, 2020 1:46 am
- Post datetime: 2020-05-14T17:52:38+00:00
- Post Title: Army Men Series [PC] .AMM/.ATL Files

I'm building an editor for these files. Thank you for documenting the dat format... I had figured out up to the palette, and this saved me tons of time.

I'll incorporate this information here: [https://github.com/tminard/3do-army-men-file-reader](https://github.com/tminard/3do-army-men-file-reader), and I'll be sure to credit you.
