## Post #1
- Username: juddo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 10, 2012 10:56 pm
- Post datetime: 2012-11-11T07:28:34+00:00
- Post Title: the warriors ps2

hello all, such a great forum here. i've been visiting regularly this last month and found many posts useful for what i am trying to achieve, thank you for sharing.

i've had some incredible help and success (thanks albinoleopard) extracting files from the warriors ps2 archive, but to my surprise theres no file names (which is making identifying files a painful task)! all i know about the game is it was built on a modified renderware engine (clearly not the same as the gta sa engine, as i originally hoped! - from the same era). i have been staring myself blind looking at files for patterns (i've had no prior experience using a hex editor to look at files, but learning fast) and comparing similar file types.

an observation i've made having played the game many times over is the animations look shared between characters. each character has a "special" set of animations (punches, kicks etc), but animations like walking, running and idle are the same? even the female animations look identicale to the male ones? when playing in battle mode (coop, vs or single player), when playing as another gang, lots of animations are reused! for example, an animation used for the baseball furies is the same from the warriors. so, i believe theres one skeleton for all models, generic animations and character specific animations (with the exception for maybe a hand full). another hint is some animation files i've found are named (at the bottom of the file) "gen_xxx.anm". i know how a typical skeleton is stored in a file and that each vertex needs indexing to a particular bone, but the way ints and floats are stored for the ps2 format (for memory purposes), is all new to me. i cant structurally see a skeleton in each character file, but i wouldnt know any better. i hope there is, because locating the base skeleton will be a mammoth task (10,700 odd files, not labeled!).

albinoleopard originally found the vertex data in files that have id's of "47000000" (71) and "02000000" (2). i've been randomly opening different files and noticed theres other id's (4 & 5) that contain vertex data also, even some that have multiple sets of vertex data (sub models). theres no clues to which file contains what, though (even closely numbered files have random content!).

so far, only the vertex data is confirmed. it's confirmed that floats for the vertex data in these game files are stored in two byte signed integers. theres four floats per set of vertex data. the last float is always 0. ultimately all i need help with is just identifying how the following data is stored (i dont need any scripts or tools)...

normals (i believe theyre stored as 4 floats???) i tried calculating my own normals at runtime, but get bad results.
texture uv's
textures (i believe this is stored in the same file, bellow the vertex data)
skeletons (or how the vertices are linked to a (my suspicion) "base" or "shared" skeleton)
animations

attatched is three example files...

to locate the models vertices count, i search for "140000000A00021C0100000001000000". the four bytes that follow are the total vertices count. to locate the vertex data, i search for "000000170000001100000011". then read vertices count * 8 (four floats, each two byte signed integers). the data is stored as a triangle strip.

at the top of each file you'll find;

id [four byte integer]
chunk size [four byte integer]
... then some "clut" style data. (it's similar to gta sa, but not really...) [unknown length]

then i skip to vertices count, then to vertices data...

i've tried reading a set size of data into a tool i wrote for this as (before and after the vertex data starts and ends);

uv's - vertices count * 4 (two floats, two byte signed integers)... not sure if this is correct as i cant convert the image data.
normals - vertices count * 6 (didnt work...) vertices count * 8 (better results, incorrectly displayed)
texture - i believe is rgb,a (w * h * 8?) and using texture finder v21 didnt work... (maybe its swizzled?)

the example files are here;

[https://rapidshare.com/files/2865192716/files.zip](https://rapidshare.com/files/2865192716/files.zip)

5245 [contains two meshes - these two characters are from the same gang...]
3996 [contains only animation data]
3508  from memory, theres not lots of colours in this image.

...

wow thats a long post. didnt mean it to be, i just wanted to clarify what i know and what i am seeking help with   

i look forward to any replys and greatly appreciate any help.

all credit goes to albinoleopard, such a fantastic help.

best regards,


justin
## Post #2
- Username: juddo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 10, 2012 10:56 pm
- Post datetime: 2012-11-11T08:14:23+00:00
- Post Title: the warriors ps2

just re-read that first post and it may appear confusing. i thought maybe i'll use one of the example files above and display hex offsets of what i know... and what i think may be...

i skipped ahead and read to the offset where the vertices count is found. the first mesh has 2103 vertices.

just an observation of below, where i read 4 byte unsigned ints in some areas, may be 2 byte unsigned ints followed by 0000? eg. "20000000" may be seen as "2000" (2) and "0000" (0)? or it could just be the id of the file type? *iunno*

***

another update to this file; i've found a second "clut" just above the second character model...! i was just reading back through the data below and thought why not search for unusual numbers from the clut like (0C000000 - 12) and (0E000000 - 14). i found alot of "0C000000" but one actually landed me around 0x00029A3C (slightly above the second character model...!). i recognised this section was similar to the "clut" at the top of the file... the top clut (as far as i could tell) ended at 0x000000DC (just before 03000000) - and is 0x000000D0 (208 bytes) long. so from 0x00029A3C - 0x00029B0C is 0x000000D0 (208 bytes) long. this lands me just before 03000000! this must be the start of the second character model? 8 bytes before 0x00029A3C is "03000000" & "00000000"...! its late here and im tired... also tired of staring at 0's and 1's... for now! 

***

```

@ 0x00000000
07000000 - (7) id [4 byte unsigned int]
40ED0500 - (388416) chunk size [4 byte 32 int]
00000000 - (zero) unknown, always [4 byte unsigned int]
9567 - (26517) unknown, maybe the size of the first section of data? [2 byte unsigned int]
68DE - (56936) unknown, maybe the size of the second section of data? [2 byte unsigned int]
02000000 - (2) unknown, maybe the file type/id of the first section of data? [4 byte unsigned int]
5094 - (37968) unknown, size for something? [2 byte unsigned int] - [4 byte signed int reads a negative value]
0100 - (1) unknown, appears alot in the following data. maybe its a value to describe how to read the following data? [2 byte unsigned int]
00000000 - (zero) unknown, [4 byte unsigned int]
8508 - (2181) unknown, size for something? [2 byte unsigned int]
0839 - (14600) unknown, size for something? [2 byte unsigned int]
47000000 - (71) id? [4 byte unsigned int] appears alot in the following data. maybe it describes models with bones?
3092 - (37424) unknown, size for something? [2 byte unsigned int]
0100 - (1) unknown, appears alot in the following data. [2 byte unsigned int]
00000000 - (zero) unknown, [4 byte unsigned int]
FA6C - (27898) unknown, size for something? [2 byte unsigned int]
1E4C - (19486) unknown, size for something? [2 byte unsigned int]
10000000 - (1) unknown, maybe its a value to describe how to read the following data? [4 byte unsigned int]
1B92 - (37403) unknown, size for something? [2 byte unsigned int]
0100 - (1) unknown, appears alot in the following data. [2 byte unsigned int]
0A00 - (10) unknown, [2 byte unsigned int]
021C - (7170) unknown, appears alot in the following data. [2 byte unsigned int]
10000000 - (1) unknown, maybe its a value to describe how to read the following data? [4 byte unsigned int]
0C000000 - (12) unknown, id? [4 byte unsigned int]
0A00 - (10) unknown, [2 byte unsigned int]
021C - (7170) unknown, appears alot in the following data. [2 byte unsigned int]
10000000 - (1) unknown, maybe its a value to describe how to read the following data? [4 byte unsigned int]
00000000 - (zero) unknown, [4 byte unsigned int]
00000000 - (zero) unknown, [4 byte unsigned int]
0E000000 - (14) unknown, id? [4 byte unsigned int]
5C0D - (3420) unknown, [2 byte unsigned int]
0000 - (zero) unknown, [2 byte unsigned int]
0A00 - (10) unknown, [2 byte unsigned int]
021C - (7170) unknown, [2 byte unsigned int]
01000000 - (1) unknown, maybe its a value to describe how to read the following data? [4 byte unsigned int]
3C07 - (1852) unknown, [2 byte unsigned int]
0000 - (zero) unknown, [2 byte unsigned int]
0A00 - (10) unknown, [2 byte unsigned int]
021C - (7170) unknown, [2 byte unsigned int]
2100 - (33) unknown, [2 byte unsigned int]
00000000 - (zero) unknown, [4 byte unsigned int]
803F - (16256) unknown, [2 byte unsigned int]
0000 - (0) unknown, [2 byte unsigned int]
00000000 - (zero) unknown, [4 byte unsigned int]
00000000 - (zero) unknown, [4 byte unsigned int]
00000000 - (zero) unknown, [4 byte unsigned int]
803F - (16256) unknown, [2 byte unsigned int]
0000 - (0) unknown, [2 byte unsigned int]
00000000 - (zero) unknown, [4 byte unsigned int]
00000000 - (zero) unknown, [4 byte unsigned int]
00000000 - (zero) unknown, [4 byte unsigned int]
803F - (16256) unknown, [2 byte unsigned int]
0000 - (0) unknown, [2 byte unsigned int]
00000000 - (zero) unknown, [4 byte unsigned int]
00000000 - (zero) unknown, [4 byte unsigned int]
0000 - (0) unknown, [2 byte unsigned int]
0000 - (0) unknown, [2 byte unsigned int]
FFFF - (???) unknown, [4 byte ???]
FFFF - (???) unknown, [4 byte ???]
0300 - (3) unknown, [2 byte unsigned int]
02000000 - (2) unknown, maybe the file type/id of this section of data? [4 byte unsigned int]
803F - (16256) unknown, [2 byte unsigned int]
0000 - (0) unknown, [2 byte unsigned int]
00000000 - (zero) unknown, [4 byte unsigned int]
00000000 - (zero) unknown, [4 byte unsigned int]
00000000 - unknown, [4 byte unsigned int]
803F - (16256) unknown, [2 byte unsigned int]
0000 - (zero) unknown, [2 byte unsigned int]
00000000 - (zero) unknown, [4 byte unsigned int]
00000000 - (zero) unknown, [4 byte unsigned int]
00000000 - unknown, [4 byte unsigned int]
803F - (16256) unknown, [2 byte unsigned int]
0000 - (zero) unknown, [2 byte unsigned int]
00000000 - (zero) unknown, [4 byte unsigned int]
00000000 - (zero) unknown, [4 byte unsigned int]
00000000 - (zero) unknown, [4 byte unsigned int]
0000 - (zero) unknown, [2 byte unsigned int]

```


<end of clut?>

03000000 - unknown, maybe the file type/id of the first section of data? (3) [4 byte unsigned int]

<more data?>

...

i just wanted to run this past you folk. this is how i read the file in my hex editor. am i on the right track? i find it confusing sometimes whether i am meant to read two or four byte unsigned ints?

the wikipedia page for the gta sa clut structure is not the same as this... damn it.

...

onto the juicy stuff. searching for "140000000A00021C0100000001000000" takes me to offset 0x00000ED0 (from the top of the page).

```
37080000 - vertices count (2103) [4 byte unsigned int]
37080000 - vertices count, again? (2103) [4 byte unsigned int]

```


...

the following data i have no idea what it is. i highlight 00000000 in my hex editor and set the background colour for every instance of it to blue and i begin to see a pattern. i dont have the foggiest what this data is. i hope its the skeleton?

...

searching for "000000170000001100000011" takes me to offset 0x00004080 (from the top of the page).

```
read [16824 bytes] (2103 * 8 = 16824). this is the vertices data. x,y,z,w?

@ 0x00008238 - 0x0000C400 (16840 bytes)
at the end of the vertex data, i visually scroll down until i see a change/break in data. i end up with a value of 0x000041C8 (16840). i know theres a break in the data because the next set of data is "000000FF". 16840 - 16824 (vertices count) = 16. whatever the data is, its a division of 4. i would store my model data as vertex, normals, uv, skeleton. however, normals, as far as i am aware, are stored as three floats? unless theres some type of averaging value at the end? can this be the normals data?

@0x0000C400 - 0x0000E4DC (8412 bytes)
at the end of the previous data, i can visually see lots of "000000FF"'s. in fact, theres 2103 (same number as our vertices count!) of them. 2103 * 4 = 8412. is this the uv coords? the model is stored in a triangle strip... would this be correct?

@0x0000E4DC - 0x000194B4 (45016 bytes)
at the end of the previous data, i visually scroll down until i see a change/break in data. i make my way down and bump into some recognisable ascii text! "PS2" (50533200 - finished with a 0 termination) and "orph_bo_v1" (6F7270685F626F5F76310000 - finished with a 00 termination - a fixed 12 bytes long!). this appears at the start of what i suspect is an image file. i have found other image files that are labled loading screens that are 68 bytes from 0x00000000 (start of file) to "PS2". so i am reading from 0x0000E4DC to 0x000194B4 (45016 bytes). it's a large read, and i am convinced theres possibly multiple things between 0x0000E4DC and 0x000194B4 that i visually could not pin point. i may also be off by 36 bytes here (45016 - 36 bytes?)???

@0x000194B4 - 0x0002A1D0 (68892 bytes)
after the last chunk of data, i only sligtly scroll down and can see "PS2" 68 bytes from 0x000194B4. i then scroll down and believe theres a pallette, followed by rgba? this is definately the texture data...

```


***

another update to this texture data; i did a search on "PS2" (50533200) and found five instances! they were called;

```
"orph_bo_v1" (6F7270685F626F5F76310000) // "bo" stands for boss? this is the first result after the first character model...!

@ 0x000416E4
"orph_lt_va" (6F7270685F6C745F76610000) // "lt" stands for leutenant? this is the first result after the second character model...!

@ 0x00051C94
"orph_so_va2" (6F7270685F736F5F76613200) // "so" stands for soldier?

@ 0x00056244
"orph_so_vb1" (6F7270685F736F5F76623100)

@ 0x0005A7F4
"orph_so_vb2" (6F7270685F736F5F76623200)

```


side note; when you beat the snot out of a character, the texture changes to a "bloodied" version! so cool  

***

...

following the above, there appears to be another clut just before the second character model!

...

wheeew!

thanks!
## Post #3
- Username: juddo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 10, 2012 10:56 pm
- Post datetime: 2012-11-11T11:12:05+00:00
- Post Title: the warriors ps2

just thinking more about the lengths the developers went to to reduce wasted memory; if they did share the same animation between each character (the same skeleton) (which i am very confident of), why would they store the skeleton in every character file? that would be a huge waste of memory? oh dear...

on this computer i am running windows seven and only just noticed the search function is nothing like xp! i cant search inside files for a particular word? i was going to search for "pelvis" or other common names used in a skeleton file? but the way everything is concatenated at the end of each other, they probably just indexed the skeleton and didnt include the ascii values? mmm...

just looking at videos and screenshots of the game, theres instances where theres over 18 characters rendered in one scene! it was a great game... *reminisce*    also noted in the videos and screenshots, in the xbox version there was shadow volumes! the ps2 only had a texture "blob" at ground level...! my mate had an xbox with the warriors and when he played it on my ps2 he always swore the graphics were better on the xbox... but i didnt believe him    hope they didnt scale down the textures for the ps2?
## Post #4
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-11-11T13:34:16+00:00
- Post Title: the warriors ps2

Wow, great that someone atleast remembers that game, it will be awesome to see unpacker
## Post #5
- Username: juddo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 10, 2012 10:56 pm
- Post datetime: 2012-11-11T13:52:34+00:00
- Post Title: the warriors ps2

with a little guidance from some talanted people here on nutting out some unknowns, especially the skeleton and animation data, you'll be seeing more than an unpacker 

i'll spill the beans when i get a little further...
## Post #6
- Username: juddo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 10, 2012 10:56 pm
- Post datetime: 2012-11-11T15:47:52+00:00
- Post Title: the warriors ps2

i couldnt walk away from this and got a little further than i ever thought i would on my own. adjusting the columns in the hex editor aligns like data and forms a clearer pattern. i simply highlighted the patterns i saw and with  hex workshop you can set a background colour. worked great. taking screenshots of the patterns is quicker than typing what you see... whew!

i put together this more detailed document on a different character model file i didnt include earlier. i dont have time to upload it, but heres my findings for that file. hopefuly they are the same for [5245]?

```
i think the skeleton structure follows the first clump?

reference #00000001 (clump of data)
[4 bytes unsigned int]		00000000
[2 bytes unsigned int]		0A00 (10)
[2 bytes unsigned int]		021C (7170)
[4 bytes unsigned int]		03000000
[2 bytes unsigned int]		A001 (416)
[2 bytes unsigned int]		0000 (0)
[2 bytes unsigned int]		0A00 (10)
[2 bytes unsigned int]		021C (7170)
[2 bytes unsigned int]		1E01 (286)
[2 bytes unsigned int]		0000 (0)
[2 bytes unsigned int]		9401 (404)
[2 bytes unsigned int]		0000 (0)
[2 bytes unsigned int]		0A00 (10)
[2 bytes unsigned int]		021C (7170)
[2 bytes unsigned int]		0001 (256)
[2 bytes unsigned int]		0000 (0)
[4 bytes unsigned int]		00000000

reference #00000002 (clump of data)
[2 bytes unsigned int]		1800 (24)
[2 bytes unsigned int]		0000 (0)
[2 bytes unsigned int]		0A00 (10)
[2 bytes unsigned int]		021C (7170)
[2 bytes unsigned int]		1E01 (286)
[2 bytes unsigned int]		0000 (0)
[2 bytes unsigned int]		0C00 (12)
[2 bytes unsigned int]		0000 (0)
[2 bytes unsigned int]		0A00 (10)
[2 bytes unsigned int]		021C (7170)
[2 bytes unsigned int]		0001 (256)
[2 bytes unsigned int]		0000 (0)

*****************************************************************************************************************

<start of file>
[4 bytes unsigned int]		id
[4 bytes unsigned int32]	chunk_size
[4 bytes unsigned int]		zero
[208 bytes 0x000000D0]		unknown chunk? has data in it...

<start of skeleton?>

[4 bytes unsigned int]		03000000
[52 bytes 0x00000034]		unknown chunk? has data in it...
x 31 times

<start of more skeleton data? indexing? is this data stored in x, y, z?>
[4 bytes unsigned int]		03000000
[4 bytes unsigned int]		03000000
[40 bytes 0x00000028]		unknown chunk? has data in it... see reference #00000001
... this is where i see some type of indexing to the 31 joints? ... 384 bytes total (32 * 12)
[12 bytes unsigned int]		20000000 00000000 24000000 // 20000000 = 32??? theres only 31 bones?
[12 bytes unsigned int]		00000000 00000000 00000000
[12 bytes unsigned int]		01000000 01000000 02000000
[12 bytes unsigned int]		02000000 02000000 00000000
[12 bytes unsigned int]		03000000 03000000 00000000
[12 bytes unsigned int]		04000000 04000000 02000000
[12 bytes unsigned int]		05000000 05000000 03000000
[12 bytes unsigned int]		06000000 06000000 02000000
[12 bytes unsigned int]		07000000 07000000 01000000
[12 bytes unsigned int]		08000000 08000000 02000000
[12 bytes unsigned int]		09000000 09000000 01000000
[12 bytes unsigned int]		0A000000 0A000000 02000000
[12 bytes unsigned int]		0B000000 0B000000 01000000
[12 bytes unsigned int]		0C000000 0C000000 03000000
[12 bytes unsigned int]		0D000000 0D000000 01000000
[12 bytes unsigned int]		0E000000 0E000000 02000000
[12 bytes unsigned int]		0F000000 0F000000 00000000
[12 bytes unsigned int]		10000000 10000000 00000000
[12 bytes unsigned int]		11000000 11000000 00000000
[12 bytes unsigned int]		12000000 12000000 03000000
[12 bytes unsigned int]		13000000 13000000 01000000
[12 bytes unsigned int]		14000000 14000000 00000000
[12 bytes unsigned int]		15000000 15000000 00000000
[12 bytes unsigned int]		16000000 16000000 00000000
[12 bytes unsigned int]		17000000 17000000 00000000
[12 bytes unsigned int]		18000000 18000000 03000000
[12 bytes unsigned int]		19000000 19000000 01000000
[12 bytes unsigned int]		1A000000 1A000000 02000000
[12 bytes unsigned int]		1B000000 1B000000 01000000
[12 bytes unsigned int]		1D000000 1D000000 00000000
[12 bytes unsigned int]		1E000000 1E000000 00000000
[12 bytes unsigned int]		1F000000 1F000000 01000000

<start of more skeleton data???>
[4 bytes unsigned int]		03000000
[24 bytes 0x00000018]		unknown chunk? has data in it... see reference #00000002
[4 bytes unsigned int]		01000000 // some reference into the skeleton again?
[4 bytes unsigned int]		00000000 // always zero?
x 31 times

<start of new clump?>
[4 bytes unsigned int]		03000000
[208 bytes 0x000000D0]		unknown chunk? has data in it... cbf going through it just now. will update later.
[4 bytes unsigned int]		03000000
[24 bytes 0x00000018]		unknown chunk? has data in it... cbf going through it just now. will update later.
[4 bytes unsigned int]		03000000
[44 bytes 0x00000018]		unknown chunk? has data in it... cbf going through it just now. will update later.
[4 bytes unsigned int]		03000000
[12 bytes 0x00000068]		unknown chunk? has data in it... cbf going through it just now. will update later.
... here is where i land when i search for "140000000A00021C0100000001000000" to find the vertices count.
[16 bytes 0x00000010]		14000000 0A00021C 01000000 01000000
[4 bytes unsigned int]		A3070000 // vertex count (1955)
[4 bytes unsigned int]		A3070000 // vertex count (1955)
[42 bytes 0x0000002A]		unknown chunk? has data in it... cbf going through it just now. will update later.

<start of new clump?>
[32 bytes 0x00000020]		unknown chunk? has data in it... cbf going through it just now. will update later.
x 371 times... wtf?

<start of new clump?>
[2 bytes unsigned int]		0060 (24576)
[2 bytes unsigned int]		0000 (0)
[4 bytes unsigned int]		00000000
[4 bytes unsigned int]		00000000
[2 bytes unsigned int]		0000 (0)
[2 bytes unsigned int]		0300 (3)
[2 bytes unsigned int]		0004 (1024)
... here is where i land when i search for "000000170000001100000011" to find the vertices data.
[12 bytes 0x0000000C]		00000017 00000011 00000011
... then the vertex data starts here...

<start of vertex data>
[8 bytes unsigned int]		3BF9BE052DFE0000 // x, y, z, w (always zero?)
x 1955 * 8 (four floats, each two byte signed integer - 8 bytes)

```


...

the rest i will have to tackle another night as i start work in 3 hours.
## Post #7
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-11-11T16:46:54+00:00
- Post Title: the warriors ps2

That looks great so far! Would love to see more progress, and eventually more projects like this for other PS2 games
## Post #8
- Username: juddo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 10, 2012 10:56 pm
- Post datetime: 2012-11-13T14:32:19+00:00
- Post Title: the warriors ps2

hey all...

i wish i could knock this over. i think i've spotted the skeleton data and have taken a screenshot. i believe theres 31 bones in each character model. i searched through several files (map filesincluded) and could only find this data in files with character models. for the vertex data, one float is a two byte signed integer. x,y,z,w. i treat everything i read the same way hoping to find a single bones bind pose translation x,y,z and rotation x,y,z,a(angle?), but cant.

i was wondering if any could spot the data storage type? am i on the right track? in the picture below i highlighted in red background the increment of each chunk of data. the maximum the increment went to was 27.

anyway... i'd love any feedback.

thanks! (going coocoo...   )
## Post #9
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2012-11-14T10:57:34+00:00
- Post Title: the warriors ps2

Hi Justin, great job so far!

I think the files are structured like this:

```

@ 0x00000000
07000000 - id
40ED0500 - chunk size
00000000 - unknown
956768DE - unknown

 02000000 - id
 50940100 - chunk size
 00000000 - unknown
 85080839 - unknown

  47000000 - id
  30920100 - chunk size
  00000000 - unknown
  FA6C1E4C - unknown

   10000000 - id
   1B920100 - chunk size
   0A00021C - unknown

    01000000 - id
    0C000000 - chunk size
    0A00021C - unknown
     01 00 00 00 - 0xC bytes of unknown data
     00 00 00 00
     00 00 00 00

    0E000000 - id
    5C0D0000 - chunk size
    0A00021C - unknown

     @ 0x00000060
     01000000 - id
     3C070000 - chunk size
     0A00021C - unknown
      21 00 00 00 - number of structs
      for (number of structs)
       0xC IEEE 754 float numbers
       0x4 signed 16bit integers
      end for
...

```

I didn't want to post the complete txt file because it's 500+ lines, but here it is:


 5245.zip
(2.14 KiB) Downloaded 25 times
## Post #10
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2012-11-14T13:35:50+00:00
- Post Title: the warriors ps2

I'm not sure about this, but I think the chunks at 0x00000060 and at 0x0001897F contain some rotation data.

```

# 01000000 - id
# 3C070000 - chunk size
# 0A00021C - unknown

# 21000000 - number of entries

1.0000000000	0.0000000000	0.0000000000
0.0000000000	1.0000000000	0.0000000000
0.0000000000	0.0000000000	1.0000000000
0.0000000000	0.0000000000	0.0000000000
-1	-1	3	2

1.0000000000	0.0000000000	0.0000000000
0.0000000000	1.0000000000	0.0000000000
0.0000000000	0.0000000000	1.0000000000
0.0000000000	0.0000000000	0.0000000000
0	0	3	0

0.9967041612	-0.0811215267	0.0000014947
0.0811215416	0.9967041612	-0.0000040433
-0.0000011618	0.0000041513	1.0000000000
0.1114943847	-0.0395500883	0.0000000000
1	0	3	0

-0.9907113314	-0.0287897065	0.1328993738
0.0025168688	0.9732813835	0.2296020091
-0.1359586418	0.2278038412	-0.9641683698
-0.0000000271	-0.0000000012	0.1058049947
1	0	3	0

-0.9907109737	-0.0287900474	-0.1329020560
0.0025175032	0.9732807279	-0.2296045572
0.1359613240	-0.2278063744	-0.9641674161
0.0000000276	0.0000000017	-0.1058050096
1	0	3	0

0.9976887107	-0.0679503009	0.0000000072
0.0679502934	0.9976887107	-0.0000000042
0.0000000089	-0.0000000046	1.0000000000
0.5184260011	0.0000000035	0.0000000050
4	0	3	0

0.9894416928	0.0391491987	-0.1395437270
-0.0383108556	0.9992281199	0.0086899279
0.1397761554	-0.0032521123	0.9901778102
0.4909829795	0.0000000024	-0.0000000005
5	0	3	0

0.9976887107	-0.0679503158	-0.0000000036
0.0679502785	0.9976886511	0.0000000056
-0.0000000055	0.0000000054	1.0000000000
0.5184259415	-0.0000000037	0.0000000015
3	0	3	0

0.9894416928	0.0391492024	0.1395437270
-0.0383108705	0.9992281199	-0.0086897686
-0.1397761703	0.0032519244	0.9901778102
0.4909829795	0.0000000006	0.0000000023
7	0	3	0

0.9982290864	0.0594870746	0.0000000000
-0.0594870597	0.9982290268	0.0000000000
0.0000000000	0.0000000000	1.0000000000
0.1474858969	-0.0002344798	0.0000000000
2	0	3	0

0.9382691979	0.3459060192	0.0000000000
-0.3459059298	0.9382692575	0.0000000000
0.0000000000	0.0000000000	1.0000000000
0.2947424948	-0.0017436711	0.0000000000
9	0	3	0

0.9725424051	-0.2327257544	0.0000000000
0.2327257395	0.9725424051	0.0000000000
0.0000000000	0.0000000000	1.0000000000
0.1229690164	0.0000000204	0.0000000000
10	0	3	0

-0.2011698633	0.0287676919	0.9791338444
-0.3463229835	-0.9371005893	-0.0436217561
0.9162919521	-0.3478720188	0.1984792948
-0.0268227402	0.0081012938	0.0401640274
10	0	3	0

-0.2011698484	0.0287731197	-0.9791337252
-0.3463229835	-0.9371008277	0.0436165556
-0.9162920117	0.3478709459	0.1984812617
-0.0268227179	0.0081015145	-0.0401639827
10	0	3	0

0.9730110765	0.0770279318	0.2175228447
-0.0566507168	0.9935314655	-0.0984166786
-0.2236965597	0.0834377110	0.9710808992
0.1563880146	0.0000000009	-0.0000000162
13	0	3	0

0.9679101110	-0.2512967885	-0.0000000087
0.2512966692	0.9679100513	0.0000000018
-0.0000000157	0.0000000005	1.0000000000
0.2916149497	0.0000000010	-0.0000000015
14	0	3	0

0.9921864867	0.0448140986	0.1164375171
-0.1177276373	0.0273075607	0.9926703572
0.0413060486	-0.9986220598	0.0323700570
0.2434040606	-0.0000000039	0.0000000151
15	0	3	0

0.8365968466	0.5478188396	0.0004362201
-0.5478188992	0.8365966678	0.0006661601
0.0000000075	-0.0007962816	0.9999997020
0.0970130190	-0.0204563607	0.0442967303
16	0	3	0

0.7921937108	0.6084867120	0.0466145873
-0.6075065732	0.7790414095	0.1550172716
0.0580120236	-0.1511218846	0.9868113995
0.0977870226	-0.0179551765	-0.0085862968
16	0	3	0

0.9730110168	0.0770280734	-0.2175228596
-0.0566508844	0.9935314655	0.0984166414
0.2236965895	-0.0834376365	0.9710808992
0.1563880146	0.0000000018	0.0000000145
12	0	3	0

0.9679101110	-0.2512967587	-0.0000000095
0.2512966990	0.9679100513	0.0000000011
-0.0000000057	-0.0000000004	1.0000000000
0.2916149795	0.0000000034	-0.0000000009
19	0	3	0

0.9921864867	0.0448141210	-0.1164375395
-0.1177276596	0.0273075532	-0.9926703572
-0.0413060375	0.9986220598	0.0323700570
0.2434041053	0.0000000001	-0.0000000103
20	0	3	0

0.8365967870	0.5478188992	-0.0004362113
-0.5478188992	0.8365966678	-0.0006661564
-0.0000000129	0.0007962895	0.9999997020
0.0970129967	-0.0204563085	-0.0442967303
21	0	3	0

0.7921937108	0.6084867716	-0.0466145799
-0.6075065136	0.7790414095	-0.1550172865
-0.0580120161	0.1511218995	0.9868113995
0.0977870151	-0.0179551747	0.0085863061
21	0	3	0

0.1430426240	0.9897165298	0.0000029803
0.0000000000	-0.0000031001	1.0000000000
0.9897165298	-0.1430427134	0.0000000000
0.1010500565	0.0274238680	0.0011627509
11	0	3	0

-0.1686853021	0.9856699705	-0.0000025733
0.9856699705	0.1686852723	-0.0000029155
-0.0000024396	-0.0000030282	-1.0000000000
0.0013896757	0.0134070432	0.0000000000
11	0	3	0

0.0905170962	0.8612840176	0.4999964535
-0.0481668375	-0.4976837933	0.8660200834
0.9947293997	-0.1024729311	-0.0035636397
-0.0047336901	0.0994113237	0.0001571295
11	0	3	0

0.0905176252	0.8612834215	-0.4999973476
0.0522590540	0.4972587824	0.8660269380
0.9945227504	-0.1045201719	0.0000000024
-0.0047254832	0.0991827548	0.0008798408
11	0	3	0

0.1098695621	0.9939460158	0.0000028091
0.9939460158	-0.1098696142	-0.0000012149
0.0000000000	0.0000029129	-1.0000000000
0.0833394229	0.0824132040	0.0000000000
11	0	3	0

0.0764880180	0.9969943166	0.0123244999
-0.0008183419	-0.0122979870	0.9999240637
0.9970701337	-0.0764923766	-0.0001248190
-0.0024852008	0.0385014452	-0.0006614813
11	0	3	0

0.2395512909	0.9707977772	-0.0129195182
-0.9708750248	0.2395843267	0.0010477225
0.0041124364	0.0122922575	0.9999160171
0.0446228385	-0.0000000007	0.0000000780
27	0	3	0

0.1743506640	-0.9846836329	0.0000000015
0.9846836329	0.1743503362	0.0000000014
-0.0000000009	-0.0000000003	1.0000000000
0.0447242446	0.0000000021	-0.0000000484
26	0	3	0

0.7629407644	0.6464684010	0.0000000000
-0.6464682817	0.7629408836	0.0000000000
0.0000000000	0.0000000000	1.0000000000
0.1212383956	-0.0000025422	0.0000000000
25	0	3	0

```


```

# 16010000 - id
# 50080000 - chunk size
# 0A00021C - unknown

# 01000000 - id
# 44080000 - chunk size
# 0A00021C - unknown

# 04 00 00 00 20 20 04 00 - unknown data

21
22
23
24
25
0
1
2
26
20
3
14
15
29
30
31
27
28
16
17
18
19
4
10
13
6
8
7
11
9
5
12

1.0000000000	0.0000000000	0.0000000000	00 00 00 00
0.0000000000	1.0000000000	0.0000000000	00 00 00 00
0.0000000000	0.0000000000	1.0000000000	18 A0 62 1E
0.0000000000	0.0000000000	0.0000000000	82 02 00 00

0.9967042804	0.0811215341	-0.0000011618	00 00 00 00
-0.0811215490	0.9967042804	0.0000041513	00 00 00 00
0.0000014947	-0.0000040433	1.0000000000	18 A0 62 1E
-0.1143352985	0.0303751472	0.0000002937	82 02 00 00

0.9997648597	0.0216868557	-0.0000011618	00 00 00 00
-0.0216868818	0.9997649193	0.0000041513	00 00 00 00
0.0000012516	-0.0000041251	1.0000000000	18 A0 62 1E
-0.2595366538	0.0461304002	0.0000002937	82 02 00 00

0.9455502033	-0.3254765570	-0.0000011618	00 00 00 00
0.3254764378	0.9455502033	0.0000041513	00 00 00 00
-0.0000002526	-0.0000043034	1.0000000000	18 A0 62 1E
-0.5035031438	0.2366472483	0.0000002937	82 02 00 00

0.9953344464	-0.0964858830	-0.0000011618	00 00 00 00
0.0964857787	0.9953343868	0.0000041513	00 00 00 00
0.0000007558	-0.0000042440	1.0000000000	18 A0 62 1E
-0.6643446684	0.0843532607	0.0000002937	82 02 00 00

0.0468816720	-0.0000013015	0.9989005327	00 00 00 00
0.9989004731	0.0000011743	-0.0468816720	00 00 00 00
-0.0000010240	1.0000000000	0.0000009117	18 A0 62 1E
-0.0531401783	-0.0011622988	-0.7656671405	82 02 00 00

-0.2630015016	0.9647955298	-0.0000009743	00 00 00 00
0.9647954702	0.2630014122	-0.0000074007	00 00 00 00
-0.0000068839	-0.0000028864	-1.0000000000	18 A0 62 1E
0.1822291315	-0.6442267299	0.0000011156	82 02 00 00

0.4230551124	0.9061040282	-0.0000009743	00 00 00 00
0.9061039686	-0.4230552912	-0.0000074007	00 00 00 00
-0.0000071180	0.0000022481	-1.0000000000	18 A0 62 1E
-0.3699381649	-0.5309334993	0.0000011156	82 02 00 00

0.0069925454	0.0000763760	0.9999756217	00 00 00 00
0.8660012484	-0.5000055432	-0.0060175508	00 00 00 00
0.4999929368	0.8660221696	-0.0035623778	18 A0 62 1E
-0.0727538094	0.0391296782	-0.6545907855	82 02 00 00

0.0011439463	0.0068987627	0.9999756217	00 00 00 00
0.6433349252	0.7655609846	-0.0060175527	00 00 00 00
-0.7655839324	0.6433264017	-0.0035623773	18 A0 62 1E
-0.0590126887	-0.1088564321	-0.6545907259	82 02 00 00

0.0069938586	0.0040365332	0.9999675155	00 00 00 00
0.8659967184	0.4999847114	-0.0080751460	00 00 00 00
-0.5000009537	0.8660249114	0.0000020227	18 A0 62 1E
-0.0720395669	-0.0426073819	-0.6544563174	82 02 00 00

-0.0073250551	-0.0047753882	0.9999618530	00 00 00 00
0.6929389238	-0.7209944725	0.0016328315	00 00 00 00
0.7209590077	0.6929243207	0.0085911946	18 A0 62 1E
-0.0608545132	0.1023708656	-0.6554049253	82 02 00 00

0.0134552550	0.9999095201	-0.0000000152	00 00 00 00
0.9999094605	-0.0134553006	-0.0000013261	00 00 00 00
-0.0000012400	0.0000008975	-1.0000000000	18 A0 62 1E
-0.0802194476	-0.7433707118	0.0000003841	82 02 00 00

-0.0200646445	0.0003709470	0.9997987747	00 00 00 00
0.9997228384	-0.0123153636	0.0200676788	00 00 00 00
0.0123203788	0.9999240637	-0.0001236882	18 A0 62 1E
-0.0049022185	0.0006394326	-0.6634277105	82 02 00 00

-0.1995805502	-0.0224615280	0.9796240330	00 00 00 00
-0.0382707007	-0.9987958074	-0.0306980871	00 00 00 00
0.9791337848	-0.0436176434	0.1984805763	18 A0 62 1E
0.0631427988	-0.0473331101	-0.5242548585	82 02 00 00

-0.4090147913	0.0854014978	0.9085227251	00 00 00 00
-0.1074955836	-0.9931882620	0.0449657850	00 00 00 00
0.9061741829	-0.0792705193	0.4154089689	18 A0 62 1E
0.0196627732	-0.0933399200	-0.5260031223	82 02 00 00

-0.4173506498	-0.0201231129	0.9085227251	00 00 00 00
0.1455388665	-0.9883302450	0.0449657887	00 00 00 00
0.8970155120	0.1509919018	0.4154089689	18 A0 62 1E
-0.2397692651	-0.1586853713	-0.5260031223	82 02 00 00

-0.5207775831	-0.8532794118	0.0265526380	00 00 00 00
0.0948748440	-0.0887590647	-0.9915244579	00 00 00 00
0.8484040499	-0.5138446093	0.1271785051	18 A0 62 1E
-0.4252629578	0.5746973157	-0.1555354893	82 02 00 00

-0.9031350017	-0.4285764098	0.0258731879	00 00 00 00
0.0311806481	-0.1255692542	-0.9915947914	00 00 00 00
0.4282231331	-0.8947373033	0.1267693192	18 A0 62 1E
-0.1108496785	0.7840903401	-0.1107648313	82 02 00 00

-0.9330039620	-0.3524807096	-0.0725362003	00 00 00 00
0.0673691779	0.0269194525	-0.9973649979	00 00 00 00
0.3535040319	-0.9354318976	-0.0013692230	18 A0 62 1E
-0.0460849516	0.8048987389	-0.0420514010	82 02 00 00

-0.1995800585	-0.0224615578	-0.9796240926	00 00 00 00
-0.0382736921	-0.9987956882	0.0306986943	00 00 00 00
-0.9791337252	0.0436206870	0.1984799504	18 A0 62 1E
0.0631435215	-0.0473331362	0.5242546797	82 02 00 00

-0.4090143144	0.0854014680	-0.9085229039	00 00 00 00
-0.1074981987	-0.9931880832	-0.0449646004	00 00 00 00
-0.9061740637	0.0792734399	0.4154085815	18 A0 62 1E
0.0196634289	-0.0933400169	0.5260027647	82 02 00 00

-0.4173502028	-0.0201230422	-0.9085228443	00 00 00 00
0.1455362737	-0.9883307815	-0.0449645966	00 00 00 00
-0.8970161676	-0.1509890705	0.4154085517	18 A0 62 1E
-0.2397685796	-0.1586852968	0.5260027647	82 02 00 00

-0.5207771063	-0.8532796502	-0.0265526865	00 00 00 00
0.0948723704	-0.0887575820	0.9915248752	00 00 00 00
-0.8484046459	0.5138443112	0.1271756589	18 A0 62 1E
-0.4252622724	0.5746968985	0.1555354297	82 02 00 00

-0.9031347036	-0.4285769165	-0.0258732252	00 00 00 00
0.0311793815	-0.1255666465	0.9915952086	00 00 00 00
-0.4282237291	0.8947373629	0.1267664582	18 A0 62 1E
-0.1108492762	0.7840896249	0.1107647642	82 02 00 00

-0.9330037236	-0.3524811268	0.0725362152	00 00 00 00
0.0673681274	0.0269221719	0.9973649979	00 00 00 00
-0.3535047472	0.9354315400	-0.0013720125	18 A0 62 1E
-0.0460846610	0.8048979640	0.0420514531	82 02 00 00

-0.9907113314	0.0025168634	-0.1359586567	00 00 00 00
-0.0287896916	0.9732813239	0.2278037965	00 00 00 00
0.1328993738	0.2296020538	-0.9641684294	18 A0 62 1E
-0.0140614444	-0.0242930427	0.1020138338	82 02 00 00

-0.9885925055	-0.0648081154	-0.1359586716	00 00 00 00
-0.0948578939	0.9690755606	0.2278037965	00 00 00 00
0.1169906706	0.2381019443	-0.9641683698	18 A0 62 1E
-0.5296059251	-0.0604195893	0.1020138189	82 02 00 00

-0.9996640682	-0.0257027857	0.0033477154	00 00 00 00
-0.0241292510	0.9699820280	0.2419765443	00 00 00 00
-0.0094666649	0.2418144643	-0.9702762961	18 A0 62 1E
-0.9979432821	-0.0221597515	0.2434693873	82 02 00 00

-0.9907109737	0.0025175100	0.1359613389	00 00 00 00
-0.0287900455	0.9732807875	-0.2278063297	00 00 00 00
-0.1329020411	-0.2296046019	-0.9641674161	18 A0 62 1E
-0.0140616745	-0.0242933184	-0.1020137444	82 02 00 00

-0.9885922074	-0.0648074150	0.1359613389	00 00 00 00
-0.0948582143	0.9690749645	-0.2278063446	00 00 00 00
-0.1169931516	-0.2381046563	-0.9641674161	18 A0 62 1E
-0.5296062231	-0.0604198724	-0.1020137444	82 02 00 00

-0.9996640086	-0.0257020798	-0.0033450129	00 00 00 00
-0.0241292287	0.9699813128	-0.2419792414	00 00 00 00
0.0094639445	-0.2418172359	-0.9702755809	18 A0 62 1E
-0.9979435205	-0.0221600700	-0.2434693277	82 02 00 00

```

PS: There are 8431 (0x20EF) IEEE 754 float numbers located at 0x000105C0-0x0001897B (file #[5245]), but I have no clue about their meaning.
## Post #11
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-11-14T13:57:38+00:00
- Post Title: the warriors ps2

Nice progress, that looks like eventually a 3D data?
## Post #12
- Username: juddo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 10, 2012 10:56 pm
- Post datetime: 2012-11-15T06:58:30+00:00
- Post Title: the warriors ps2

hello herbert3000.

wow! thanks for such a great reply.

you've more than clarified the section chunks for me... this is so great. you've also confirmed for me that the bones are stored in a matrix as i eventually suspected. which also explains the unfamiliar pattern i saw in the animation files.

i did a quick manual plot of the joints and placed it over the top of a model and this is what i see...



i just copied the translation data for the plot. true to rockstars other games (gta vc, gta sa), they seem to scale the model and skeleton either by a fixed number or by the map scale? its either that, or i'm converting the model vertex data incorrectly.

i'm back onto my last night shift for the week so unfortunately i have no time to do anything else tonight, but i will tackle it hard tomorrow and the rest of the week!

thank you again so much herbert3000! i really look forward to finishing this and starting my project 

best regards,


justin
## Post #13
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-11-15T07:50:09+00:00
- Post Title: the warriors ps2

Holy snap!! You did it o.o

Can you see if you can load 3D data for cars? I dont have pics, but here are from gamespot:





That will be great!
## Post #14
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2012-11-16T01:56:37+00:00
- Post Title: the warriors ps2

I must have been blind...
Since the game has been built with a modified version of the RenderWare engine, we can use the tool [RW Analyze](http://web.archive.org/web/20100828094109/http://www.steve-m.com/downloads/tools/rwanalyze/) to explore most of the game files (except for some unknown sections).

But first of all we have to get rid of the custom file headers, like this:

The total size of this chunk is 19227 (= 1921B + C), it starts at 0x30.
Just copy the chunk into a new file and then you can open it with the RW Analyze tool.



Here are some example files (I already removed the headers):
[http://www.mediafire.com/?mz1e4c254xzfs5h](http://www.mediafire.com/?mz1e4c254xzfs5h)

RW Analyze can be found here:
[http://web.archive.org/web/201008280941 ... rwanalyze/](http://web.archive.org/web/20100828094109/http://www.steve-m.com/downloads/tools/rwanalyze/)

Maybe we can manage to convert the game files so we can use them in GTA San Andreas
## Post #15
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-11-16T06:37:33+00:00
- Post Title: the warriors ps2

Wait wait, it's .NIF file? But then you can use [NIFTools](http://www.niftools.org/)! What did you use to unpack the files or they were unpacked? I don't remember :/
## Post #16
- Username: juddo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 10, 2012 10:56 pm
- Post datetime: 2012-11-16T07:41:44+00:00
- Post Title: Re: the warriors ps2

wow! great find here. before i signed up here i downloaded rwanalyze and tried to open the files with it, but obviously couldnt. i didnt think about removing the custom header.

i was going to wait until i got a little further with the skeleton and animation format before i announced this... but, i am writing a scratch and purpose built pc semi-port of this game. it will be an opengl program that reads and draws the original content straight from the ps2 disc (no game files will be distributed with the program). i will introduce a new physics engine, custom lua mission scripting and network support and other environment effects not previously seen. i have plans to make it open source after the first release on sourceforge or github. i could convert the files for mta, but it would not do the work justice (just yet, anyway). the warriors never carried guns... and i really want to see a multiplayer game of the warriors on the original maps with the original unmodified content.

racing freak; i've viewed the police car and sullys little bubble car... theyre very low poly. what do you intend to do with them?
## Post #17
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-11-16T08:09:46+00:00
- Post Title: Re: the warriors ps2

> Reply from juddo
>
> 
racing freak; i've viewed the police car and sullys little bubble car... theyre very low poly. what do you intend to do with them?
Awesome!! I did not know there is a police car at all so its surprise. I would need them for a low poly car models project. Are the textures intact? If so it will be awesome to have them zipped 

And that is very very nice project, looking forward updates!
## Post #18
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2012-11-16T10:17:33+00:00
- Post Title: Re: the warriors ps2

Hey Justin, that sounds great!
Can't wait to see some WIP screenshots 

> Reply from RacingFreak
>
> Wait wait, it's .NIF file? But then you can use NIFTools! What did you use to unpack the files or they were unpacked? I don't remember :/No, the Warriors game files are not related to Gamebryo's .NIF file format. I forget why I chose this extension when I extracted the files. Maybe I thought they were NIF files, but I really can't remember.
## Post #19
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-11-16T10:26:16+00:00
- Post Title: Re: the warriors ps2

Oh alright then. Eagerly awaiting for more progress and info on character + background car models
## Post #20
- Username: fixer75
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Mar 22, 2012 10:53 pm
- Post datetime: 2012-11-16T10:37:56+00:00
- Post Title: Re: the warriors ps2

> Reply from RacingFreak
>
> Oh alright then. Eagerly awaiting for more progress and info on character + background car models

If you realy want cars from this game, i have one, this is a Roguer's car. Already ported to GTA SA by Base5.
[(Gamma) RoguesCar.rar](https://xentaxbackup.github.io/file/5998_(Gamma) RoguesCar.rar)
## Post #21
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-11-16T11:17:57+00:00
- Post Title: Re: the warriors ps2

How have you ripped it? Looks pretty messed up tho
## Post #22
- Username: fixer75
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Mar 22, 2012 10:53 pm
- Post datetime: 2012-11-16T11:50:52+00:00
- Post Title: Re: the warriors ps2

> Reply from RacingFreak
>
> How have you ripped it? Looks pretty messed up tho

This model from psp version, ripped by emulator jpcsp and more colorfull textures from ps2 version, very lowpoly, but usable =)
