## Post #1
- Username: Ikeness
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jan 10, 2007 2:09 am
- Post datetime: 2007-01-09T18:56:34+00:00
- Post Title: Identify and Interpret 3d models, help in Megaman Legends

I want to extract the 3d models from the PC game Megaman Legends.  This game has a directory of .bin files.  Mirex's Unmass can break the archives into seperate files.  Both Mirex's Biturn and the Yu_Ri program can extract the TM texture files.

But what I would like to know is: what I should be looking for if I want to find and interpret the 3d models in this game.  How long should I expect the file to be?  Are their any patterns that I should look for.

Like, should I expect to find a list of groups of 3 Unsigned Short Bits that represent the x,y,z coordinates of a vertex?  Or can I expect edges, faces, and references to textures to be thrown inbetween vertex coordinates?

Thanks,

Joel
## Post #2
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-01-09T19:18:24+00:00
- Post Title: Identify and Interpret 3d models, help in Megaman Legends

Try running the content of few randomly extracted files through TrID (online) : 
[http://mark0.net/soft-trid-e.html](http://mark0.net/soft-trid-e.html)
Maybe you will be lucky and ID tool will recognise 3D format. 
Looking into file with HexEditor could give some hints too. 
No guarantees though, but as above - pure luck.
## Post #3
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-01-10T05:21:33+00:00
- Post Title: Identify and Interpret 3d models, help in Megaman Legends

here are some random tips :)

I don't know what type of game megaman legends is but finding vertices made from 16 bit integers is very far fetched

vertices are usually made from floats(32bit)

the typical vertex in games is (position) X Y Z, (Normal) nX nY nZ and (texture coordinates) U and V and perhaps some extra data like skinning, vertex color or texture assignments (as numeric Ids)

faces are usually stored as an index made from integers eg: Face 1 = A B C, Face 2 = B C A etc

file size depends on the model complexity, a model with 3000 triangles can weight around 400 kilobytes including textures

because normals and texture coordinates is normalized, data gets very repetitive and will look like this " ?   > " :)
like in the eg below
0x7F3FA25B
0x433FA036
0xD03E0C77
0x8C3EE236
where 3F and 3E are ? and > respectfully

vertices will look like very random data but be on the look out for "A", "B", "SB" and "@"

well that is all I can think of right now
## Post #4
- Username: Ikeness
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jan 10, 2007 2:09 am
- Post datetime: 2007-01-10T05:40:27+00:00
- Post Title: Identify and Interpret 3d models, help in Megaman Legends

Thanks man.  You are right: It is all luck.. good and bad.

But anyway, like I said, Megaman Legends has a bunch of .bin archive files.  In many of them are "BD" files.  Some BD files hold 3d model information.  Another BD holds the Font.  There's a bunch of BDs that I have no idea what they might be for.

At the end of the 3d model files are all the vertex coordinates are listed one after the other with 16 bit null spaces between them.
And each X, Y and Z value is stored as a 16 bit signed short.
They were pretty easy to spot because of the 16 bit spaces inbetween them.  

But the verticies are only a small part of the model file.  The rest I do not understand, although I've color mapped the heck out of the HEAD00.BIN file.  There's a lot of repitition, and the colors spiral up the hex, but I have no idea what to do with it.  I figure it has information on the models edges and texture mapping, but I cannot even guess what to look for at this point.  I know X,Y,Z intergers translate to vertex points, but I have not modeling or texturing expierence.  How are edges represented?  How are texture mappings represented?

Imediate, though, I just want a quick way to change the vertexes into something I can put into my Maya Personal Learning Edition.  If someone could get me one of those, it'd be awsome.  Right now I am just going to try to manualy insert Teisel's vertecies into Maya and then figure out the edges and faces on my own.. and then try to apply the textures or something; because Teisel is the king.

Thanks,

Joel

Edit:

I am sorry alera, I hadn't read you post before writing this message.
In this game it seems that the verticies are stored at the end of the model data.  And, like I said, most of the model information file has a lot of regularly repeating values that I have color mapped.  I will look back over them to see if they appear to be in groups of 3 or 4 or whatever indicating polygon face defintions.  I can post the file that I have color mapped (one of Megaman's arms) along with the color mapping file if I need to.

By the way, Megaman's head (without his helmet) has about 102 verticies.
Also, what's with Hex Workshop's Color Mapping.  It changes the some values that I set to color map.  It changes a bunch of them to "FFFF" sometimes.  Is it just me?

Thanks again,

Joel
## Post #5
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-01-10T17:16:53+00:00
- Post Title: Identify and Interpret 3d models, help in Megaman Legends

I could take a quick peek at the file if you post it :)

games don't store edge visibility flags, they use the vertex normal for lighting(what they call smooth groups in 3dsmax)

edge data is redundant since the face index tells you what vertices makes what face in a specific order.


---
if Im not mistaken hexworkshops color definition is a text file that you can edit, try changing ff to what ever you wanted it to be to see if you can force it to work
## Post #6
- Username: Ikeness
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jan 10, 2007 2:09 am
- Post datetime: 2007-01-12T02:39:49+00:00
- Post Title: Identify and Interpret 3d models, help in Megaman Legends

Note to alera after writing this post:
You do not really need to read all of this.  I am just trying to write down what I know. The most important stuff is in bold

Ok, here is what I got

First, lemme spell out the simple indexing of these archives.  I can be useful for navigating them, but you can proabably just use the bookmarks that I set up.
Basically, the first 32 bits give the offset for the beginning first file,
the second 32 bits give the offset for the beginning second file.. ect for however many files you have.
Then, after listing these offsets, a 32 bit unsigned long gives the size of the archive.  This is the end of the archive header and where the first file begins.

The first 16 bytes of each file appears to be some kind of file type extension for the files in these archives.  In ASCII they translate to extentions such as BD, TM and CT.  I am very sure that the TM files are always texture files.  I know that some of the BD files hold model information.  There is another BD file that defines the Font appearance.  There are other BD files that I can only guess define skeleton animations, but they could be anything.  I dunno what the CT files do.

About the BD model files:
Like I said, some BD files have 3d model information.  After their file extentions and would could possibly be a file name, there is a lot of hex that is probably referencing the INIT_DAT.BIN file.

The INIT_DAT.BIN file has BD files for megaman's torso and legs, megaman's regular arms and megaman's buster gun arm.  It also has a TM texture file for Megaman's face, hair and helmet as well as a TM texture file for megaman's body, arms, shoes and weapons.  INIT_DAT also has the BD Font file and some other files that I don't understand.

Evidence for file names:
Common to many of the INIT_DAT BD files, as well as the Head and Feet BD files is this hex arround where the filename might appear, after the BD extension:
180000001C000000
That is barely 2 unicode chars but there are other longer strings of hex common to a couple of these BD file names as well.

But I do know that all of megaman's BD Model files have many instances of BOTH of these hex values:
00000009808080AD
00000007808080A5
which is why I believe that they are (part of) some way of referencing the INIT_DAT or megaman's skeleton or texture or object data.  The are probably other hex values that are repeated throughout all of Megaman's model files, but these are the most obvious and they occure regularily.

Like I said before, the BD files end with vertex coordinates.  I know that they are 16 bit signed shorts because I changed them and reran the game a number of times to see what would happen.

About the TM texture files:
When running the Yu_Ri texture extractor on these files, the textures that you get are pretty recognizable.  But the one problem with them is that it appears that every other pixel needs to be swaped with the one next to it.  If you run the program you will see.  (This is not really a problem, just noting it.

Attached is a zip of INIT_DAT.BIN, HEAD00.BIN and HEAD01.BIN as well as their bookmark files.  I made the color map file mainly for HEAD00.BIN, but please select it for the other files as well.

By The Way, the Head00.bin is for megaman's head with a helmet, and head01.bin is for megaman's head without his helmet (he has spikey brown hair).  The head00.bin is the only file that you really need to look at.  The others are there incase you think compairing them will help.

Thanks,

Joel

Edit:
I replaced these hex values
00000009808080AD
00000007808080A5
with zeroes in the head bins and the game ran the same.  No changes to his head, anyway.  Maybe they aren't references, but they are common to the Megaman player model files anyway.  Sorry
[megman legends DAT.zip](https://xentaxbackup.github.io/file/1026_megman legends DAT.zip)
## Post #7
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-01-13T08:15:43+00:00
- Post Title: Identify and Interpret 3d models, help in Megaman Legends

> Reply from Ikeness
>
> Note to alera after writing this post:
You do not really need to read all of this.  I am just trying to write down what I know. The most important stuff is in bold

I like to read :) specially information like this one :P
## Post #8
- Username: Ikeness
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jan 10, 2007 2:09 am
- Post datetime: 2007-01-15T21:57:58+00:00
- Post Title: Identify and Interpret 3d models, help in Megaman Legends

I don't really know how to put this in words, so I got some pictures.
Megaman's helmet has both 3 AND 4 vertex faces.  They refer to the array of vertexes at the end of the file, with the vertex being indexed by number 0, the second index by number 1, the third by number 2, ect.
The vertex indicies that form a face are refered to by 3 or 4 8bit unsigned bytes.  Here are example of both 3 and 4 vertex faces.

3 Vertex Faces


4 Vertex Faces


As you can see, the 3 vertex faces begin with 00000007808080A5 and then some texture mapping infromation.  This portion beginning with 00000007808080A5 repeats itself before giving the 3 vertex indicies for the face.

The 4 vertex faces are nearly the same, except they begin with 00000009808080AD.

Replacing faces verticies with 00000000 one at time generally let me see what faces represented which in game.  Some faces will use the same texture.  There are also 2 faces arround megaman's mouth which show up twice in the same file.  Only one appears to actually matter.  The other might be used for some cut-scene or something, I don't know.

Anyway, I updated the head00 bookmarks a bit.  I was just labeling some of the faces and what they are in game.  Download it if you want to look at some faces that I cannot seem to identify (marked by "?") or if you just need see some labeled faces.
## Post #9
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-01-16T00:50:20+00:00
- Post Title: Identify and Interpret 3d models, help in Megaman Legends

[](http://img294.imageshack.us/img294/4812/mm64st9.jpg)


you know models can already be extracted from the n64 ROM eh. I used it to pop megaman in Halflife2
## Post #10
- Username: Ikeness
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jan 10, 2007 2:09 am
- Post datetime: 2007-01-16T06:02:59+00:00
- Post Title: Identify and Interpret 3d models, help in Megaman Legends

cool.  please tell me how you do that
## Post #11
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-01-16T11:25:54+00:00
- Post Title: Identify and Interpret 3d models, help in Megaman Legends

um, well actually its a plugin for an n64 emulator, which does the geo ripping.

and I used nemu and some plugin called lemings?

the plugin has a dump geometry option in its debug mode, which dumps everything playing in the emu. any rom, textures models.. but there not going to be dumpped in there default pose. or in other words the dumper doesn't dump the raw original model, just what it intercepts the time of the dump.

but the models are so low poly, its not hard to setup a new bone chain in 3dmax.
