## Post #1
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2007-07-30T09:20:01+00:00
- Post Title: WWE Smackdown in game models

Breaking news wrestling fans, i've managed to extract the models from the older smackdown games , namely shut your mouth and hctp. Unfortunately svr06 and 07 use bpe on the textures and files so I cant extract these unless someone knows how to uncompress bpe files?

The way in which i've done this is by using rrunpack to unpack the ch.pac and ch2.pac files. I then used RROExporter to convert the yobject files to obj files and opened these with a 3d model viewer. 

My question to the experts is: Is there any way to erplace the yobject files in the original pac files with other yobject files and rebuild the pac file?

Here's a pic of everybody's fave wrestlers from hctp as proof that I've managed to do what I've said:
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-30T10:23:59+00:00
- Post Title: WWE Smackdown in game models

Nice work !
## Post #3
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2007-07-30T10:34:38+00:00
- Post Title: WWE Smackdown in game models

Thanks. but this isn't very useful unless we can find some way to import the models back into the game.
## Post #4
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2007-07-31T03:37:59+00:00
- Post Title: WWE Smackdown in game models

Without knowing the YOBJ format it is impossible to import the modified models back into the game.  Maybe someone here can shed some light on the format.  

I've partially deciphered the format, although some of my information may be incorrect.  Stuck at this point.  Mike has at least the vertex and texture data.  Maybe he will chime in.

YOBJ files

(Magic Header -- 8 bytes)
char magic[4];
int fileSize1; //(less POFO section)

(Data Header -- 72 bytes)
int null1;
int fileSize2; //(same as above)
int null2;
int null3;
int numBlockHeaders;
int numBones;
int numMaterials;
int constant1;  //(always 64)
int boneOffset; //(offset from Data Header start)
int matNamesOffset; //(offset from Data Header start)
int meshNamesOffset; //(offset from Data Header start)
int constant2;  //(always 1)
int null4;
int null5;
int null6;
int null7;

(Block Header -- 64 bytes)
int numHeaders;
int numMeshesInBlock;
int blockStartOffset;  //(offset from Data Header start)
int blockEndOffset;    //(offset from Data Header start)
int null1;
int constant1;   //(always 1)
int vertexStartOffset;  //(offset from Data Header start)
int vertexEndOffset;     //(offset from Data Header start)
int num??;
int num??;
int num??
int null2;
float unknown1;
float unknown2;
float unknown3;
float unknown4;

(MeshBlockHeader -- 32 bytes * numMeshesInBlock)
int numVertices;  //(vertices are 16 bytes each)
int num??;
int verticesOffset;
int ??Offset;
int unknown1;
int unknown2;
int unknown3;
int unknown4;
## Post #5
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2007-07-31T05:13:39+00:00
- Post Title: WWE Smackdown in game models

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: DMiller
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 12, 2007 11:48 pm
- Post datetime: 2008-06-27T13:58:47+00:00
- Post Title: WWE Smackdown in game models

Sorry to reply in an old topic, but I was just wondering if anyone could tell me what he used to view these models, I've managed to view the textureless models in 3Dstudio max but I don't know how to add the textures to them. So is there anything else I can use to view these or an easy way to add the textures?
## Post #7
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2008-07-01T12:26:34+00:00
- Post Title: WWE Smackdown in game models

Use jasmins svr pac extractor to extract the textures from the pac files. Open the mtl file which is extracted with the model. Name your texture files for that model according to the names specified in the mtl file and 3dsm should automatically apply the texture to the model once opened
## Post #8
- Username: Phileepe
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 07, 2008 1:49 am
- Post datetime: 2008-07-26T03:55:08+00:00
- Post Title: WWE Smackdown in game models

I'm REALLY having trouble with this.  How do I use RRunpack to extract these CAD files of the models?  I tried so many times but it just doesn't work.  Can somebody go into greater detail about how exactly to work Rrunpack (&where to download it from).  Thanks!
## Post #9
- Username: Wise
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 07, 2009 1:54 am
- Post datetime: 2009-03-25T07:44:26+00:00
- Post Title: WWE Smackdown in game models

Sorry if this is old but can anybody.give any updates on this thanks.
## Post #10
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-04-03T12:06:08+00:00
- Post Title: WWE Smackdown in game models

still havent found a way to extract bpe files or import yobj files into the game.
## Post #11
- Username: Wise
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 07, 2009 1:54 am
- Post datetime: 2009-04-05T11:36:28+00:00
- Post Title: WWE Smackdown in game models

> Reply from plodtrew
>
> still havent found a way to extract bpe files or import yobj files into the game.
This maybe a life time project.,see THQ as a ps2 Dev kit it may never be possibility to edit any wrestling game buy Thq or any other wrestling game on ps2 for that madder.
