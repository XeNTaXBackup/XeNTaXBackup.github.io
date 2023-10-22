## Post #1
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-04-02T09:16:30+00:00
- Post Title: Okami models...

Has anyone looked into them yet? I know Okami is using TIM3 files with no extension as the texture format, however, I'm uncertain as to what files are models... The ones I see here are:
.dat
.ses


One I'm pretty sure is animation the other I'm pretty sure is model... however I don't know what either of them really are...

So, any clues or previous research been done?
## Post #2
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-04-26T20:14:40+00:00
- Post Title: Okami models...

All models are stored
The tool game extractor, works on at least the demo for Okami (I think just because another game uses the same archive format but the script is not optimized because you can sometimes use the tool again on extracted subfiles. The extracted files have short names such as "hund1" or "ak1" and some Japanese names. You can tell a file is a model because the header is "mdb" in lowercase. I've done some work on the models at
[http://ps23dformat.wikispaces.com/Okami](http://ps23dformat.wikispaces.com/Okami)

The textures are stored in side the model file after the vertex data. The format is simple but they are bizarre things I have not figured out, Like why some textures in the full game DO use the header TIM3 while in the demo they never do.
Also why there are 2 wolf models (In random access memory) right next to each others when I am using the emulator, But I can't find the wolf's head.

Building and Creatures are stored in one format
Terrain in a different and unknown format
Maybe things like character heads are in a third format.

Characters and buildings are stored very simply and I am sure someone on the forum could easily make a Python Script for blender or a maxport script for 3DSM.
I'll go in depth on the format later today some is already on my website, I have a team project in a few minutes
## Post #3
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-04-27T20:00:08+00:00
- Post Title: Okami models...

Everything is in the big AFS. File that Game Extractor can open. The Sub files that are in that are of the following types:

AFD- unknown purpose but are small and contain no multimedia.

AFS-  if an AFS file is a subfile than it only contains audio, usually a few. Game Extractor can extract these but if you have try after you exact the big one (if some one can optimize the script then this should be displayed as a folder)

BIN- These are sub archives that Game Extractor can't really extract properly. The format is easy the first 4bytes are the number of files. then the next 4 bytes are all of the file offsets, then there are text extensions (4bytea for all of the files possible extensions include: 
ANS These are blank 16bytes strange
AKT Contain Collision Maps and Terrain type Maps (ie is is dirt, water mud ect)
BMH Contain mostly floats possibly level terrain related contain the header BMH
CAM Unknown purpose contain the header mtb3 (in lowercase)
CCH Contain mostly floats probably map related no real header
DRH Related or identical to the SCH files, no real header mostly floats
EFF are similar or identical to the BIN archives
FI2 These contain object placement data
ITS Contain no floats possibly map related no real header
LI3 Contain some floats unknown purpose
MEH Are small contain mostly floats have the header MEH
MOT Unknown Contain the header mtb3 (in lowercase)
MSD which is itself a sub-sub file archive. It contains no header and begins with the relative positions of the files it contains. Maybe it is collision map data, but it does not use floats
MSA Contains no header other than the size of the whole file, no floats maybe texture meta data
MST really small no header no file size no floats ect
RNI These are small, Unknown purpose no real header
SCH These contain mostly Floats probably related to map boundary lines-contain no real header
SCR These contain the Header scr (in lowercase) these are model archives for level terrain that use 16bytesigned vertexes similar to MD archives that contain character meshes
SEQ Probably animation data
T32 These are some sort of Tim2 textures but DO NOT contain the text header TIM2
T3L same as BIN archive
TM2 These are regular Tim2 textures that DO contain the standard TIM2 text header
TRE Unknown related to TSC contain no real header
TS Possibly related to camera movement these contain the header TS
TSC Unknown releated to TSC contain no real header
TST Same as the BIN archive 
BMT- These are small files unknown purpose
D- The ones on the demo are archives that only contain 1 of each of the following
MPD contain Meta data for the textures no real header
T32 see above
DAT- similar to BIN archives  contain many files and models:
MD Contain the Header scr (in lowercase) + five 00 bytes+ the number of models (4bytes)+ four 00 bytes + The offsets to the models
mdb These are the models packages and contain the submeshes+yet another type of Tim2 textures
DIR- a small text file with the name of the path to the video files
(no extension)-Coreidtex similar to the bin archives but contain only textures TM2 and T32
(no extension) hundesumi(+number) these are almost certainly texture transformations for Amy
(no extension) mapstage(+number) almost certainly textures for the level, like hills and streams
(no extension) titlecore textures for the title screen
S- some type of audio or video adx format??? this file might be the promational video for the full version of okami
SES- Audio
SFD- Audio
TBL- (map.tbl) This looks like a source code map, or at least ALL of the functions in the ELF file (PS2 Excutable file) this could easily be into hacks, but the file might not be included in the full version of the game
TM2- (moji8.tm2) a Tim2 texture of the letters used in for menus and character speech.
## Post #4
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-04-30T22:30:34+00:00
- Post Title: Okami models...

Heres a picture of a model, and a model, when I have more time I want to document the format so that a model viewer can be made.



[http://ps23dformat.wikispaces.com/file/ ... wolf.blend](http://ps23dformat.wikispaces.com/file/view/okamiwolf.blend)


Ammys model/textures/animations are all stored in the pl00.dat file. The game stores the model in 4 meshes the hair fringes on the legs (which I did not add because they look bad without the shaders) the body, the tail and the head (which is itself composed of 2 submeshes)
## Post #5
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-05-14T17:55:03+00:00
- Post Title: Okami models...

That's good to know, thanks. When I look back into this, hopefully I'll be able to bash something out.

I honestly hadn't expected any interest to arise, but I'm glad to see someone's done something.

Thanks for posting your info.
## Post #6
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-05-18T14:44:41+00:00
- Post Title: Okami models...

> Reply from Satoh
>
> That's good to know, thanks. When I look back into this, hopefully I'll be able to bash something out.

I honestly hadn't expected any interest to arise, but I'm glad to see someone's done something.

Thanks for posting your info.

Okay here is the rough format of md model archives

They begin with the text string 
scr (which is 73 63 72 in hex)
followed by:
00 00 00 00 00
and then the 4byte number of how many submeshes #SUBMESH are in the file starting at 1 for 1 submesh
followed by:
00 00 00 00
Followed by the same amount of offsets of the value of #SUBMESH
Then all of the rest of the bytes on that line are padded to be 00 until the next line that ends in a offset in 00 eg (010a08-010a10)
Then the first submesh begins with the text string mdb (which is 6D 64 62 in hex)
followed by a 4byte integer specifying what the type of mesh #MESHTYPE (maybe 30 is animated and 20 is static)
followed by a 2byte integer maybe an id #MESHID?
followed by a 2byte integer which is the number of mesh divisions, #MESHDIVISIONS
followed by 16 bytes of zero: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
followed by the relative pointers to each mesh division, #DIVISION1, #DIVISION2... calculated from the text string mdb
Followed by padding until the next 16byte line row.
Followed by some type of boneweights? BoneX,BoneY,BoneZ,Boneid
Bones continue until the beginning of the the first Division
Here there are pointers to the various componets, they are relative to the where the first pointer is 
@Vertexes, ???, @ImplicitTextureMapping, @TexturecolorWeight, @TextureUV
Followed by 2byte number of vertexes #Vertexes
Followed by zero padding until the next 16byte row
VERTEXES:
Are 4byte floating point numbers with an additional 4byte connection information to cull faces that should not be connected to each other. Faces are tristripes except when Connection is 00 80 00 00 for two vertexes in a row.
The rest of each Divison is texture information stored in 3 sections each with 4bytes per vertex therefore eliminating the need of pointers to each section:
TextureMapping, TexturecolorWeight, TextureUV.
TexturecolorWeight is usually just 80 80 80 80.
