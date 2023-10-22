## Post #1
- Username: joqqy
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-10T01:28:41+00:00
- Post Title: Dead Rising 2 (PC)

Dead Rising 2 Model Loader.
Extract the .big file so you get the geo files then run this script on that folder and it will import them all.
thanks to help from reveal8n
no weights yet till i figure out the bone pallet.
[dr2.png](https://xentaxbackup.github.io/file/4608_dr2.png)

[Dead Rising  2.rar](https://xentaxbackup.github.io/file/4607_Dead Rising  2.rar)
## Post #2
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2011-08-10T17:09:34+00:00
- Post Title: Dead Rising 2 (PC)

How to load textures to the model?

Edit:
Fix !
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-08-10T17:59:34+00:00
- Post Title: Dead Rising 2 (PC)

wow nice one chrox thanks a lot for what really grateful.
## Post #4
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2011-08-10T19:33:16+00:00
- Post Title: Dead Rising 2 (PC)

Is there any way to make bones work ?
## Post #5
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-08-10T19:39:42+00:00
- Post Title: Dead Rising 2 (PC)

> Reply from Kamillho
>
> Is there any way to make bones work ?
You could help chrrox or just be patient and wait.

> Reply from chrrox
>
> 
no weights yet till i figure out the bone pallet.
## Post #6
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2011-08-10T19:45:38+00:00
- Post Title: Dead Rising 2 (PC)

Anyway finally I have Rebecca model  
I want her, Stacey and Twins
## Post #7
- Username: anno1403
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 12, 2011 9:46 pm
- Post datetime: 2011-08-22T14:12:20+00:00
- Post Title: Dead Rising 2 (PC)

We have a [discussion about this awesome tool on the dead rising 2 mod forums.](http://deadrising2mods.proboards.com/index.cgi?action=gotopost&board=dr2tools&thread=354&post=6721)

[ryan7259 posted a video on how to do this, I followed the video in the next post with detailed instructions](http://deadrising2mods.proboards.com/index.cgi?action=gotopost&board=dr2tools&thread=354&post=6738).
## Post #8
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-10-24T04:03:02+00:00
- Post Title: Dead Rising 2 (PC)

I did work on "Dead Rising 2: Off The Record"

Just posting the progress I made with the format. I have meshes, materials, and the rig. but am having problems with all mesh files. I'll need to look more into the vb/ib pairing method the game is using

my goal is to write a model exporter to get new models into dead rising 2 for game modding. although I've hit a snag on the MatTextureInfoArray file. the 2nd LONG has some effect on the textures. and I'm unable to writting valid materials without understanding this section. I'm posting this here in hopes someone will help solve this puzzle piece.

> Played DR2 for the first time on the OTR version. LOVED IT!
>
> 
>
> so had a look at the model format
>
> 
>
> The game uses a packaging format called BIG, think if it as a replacement for folders that supports compression
>
> 
>
> BIG FORMAT
>
> --HEADER--
>
> {
>
> LONG : Unknown, Possible File ID / Version ID
>
> LONG : Offset to "RAW Data"
>
> LONG : Total File Size
>
> LONG : File Count
>
> LONG : Offset to "Offset Table"
>
> LONG : Offset to "String Table"
>
> }
>
> 
>
> --OFFSET_TABLE--
>
> {
>
> LONG : Offset to "Filename", From String Table
>
> LONG : Unknown, Possible File Checksum
>
> LONG : File Size (Compressed)
>
> LONG : File Size (Uncompressed)
>
> LONG : File Offset
>
> LONG : File Type
>
> -- 0x0004 = Info (Header Information)
>
> -- 0x0020 = Data (Geometry)
>
> -- 0x0100 = BIG (BIG Package File)
>
> -- 0x0800 = Compressed Data
>
> LONG : File Compression Flag
>
> -- 0x0000 = File is uncompressed
>
> -- 0x0001 = File is compressed
>
> )
>
> 
>
> ok so thats old news, but I needed to know that to read a big file. I treat it as a single mesh, rather then unpacking all the files inside. however I'll review the mesh format as if it was decompiled into all its separate component files
>
> 
>
> TEXTURE FORMAT
>
> --HEADER--
>
> {
>
> BYTE : Unknown, always 0?
>
> BYTE : Unknown, always 1?
>
> BYTE : Unknown, always 1?
>
> BYTE : Unknown
>
> SHORT : Width
>
> SHORT : Height
>
> BYTE : Unknown, compression flag?
>
> BYTE : Unknown, always 0x24?
>
> BYTE : Mip Count
>
> BYTE : Unknown, always 0x04/0x08?
>
> LONG : Unknown, Checksum?
>
> LONG : Mip Table Offset
>
> LONG : Padding
>
> { // LOOP*Mip Count
>
> LONG : Texture Offset
>
> LONG : Texture Size
>
> LONG : Unknown, always 0x80? (a dds header is x80) reserve space?
>
> LONG : Padding
>
> }
>
> LONG : Padding
>
> LONG : Padding
>
> }
>
> 
>
> 
>
> MESH FORMAT
>
> "_ANIMLIB_SKELETON_"
>
> { // Header
>
> LONG : Version
>
> LONG : Bone Count
>
> }
>
> { LOOP*Bone Count
>
> FLOAT32 : Unknown, Possible Quat, X Axis
>
> FLOAT32 : Unknown, Possible Quat, Z Axis
>
> FLOAT32 : Unknown, Possible Quat, Y Axis
>
> FLOAT32 : Unknown, Possible Quat, Vector
>
> FLOAT32 : Unknown, Possible Position, X Axis
>
> FLOAT32 : Unknown, Possible Position, Z Axis
>
> FLOAT32 : Unknown, Possible Position, Y Axis
>
> SHORT : Unknown, Possible Flag
>
> SHORT : Unknown, Possible Offset
>
> }
>
> { LOOP*Bone Count
>
> BYTE : Bone Parenting Index
>
> }
>
> 
>
> "_ATTRIBUTE_"
>
> {
>
> LONG : Unknown, 2,3
>
> }
>
> 
>
> "_ANIMCHANNELINFO_"
>
> {
>
> // NOT DOCUMENTED
>
> }
>
> 
>
> "_BONENAMES_"
>
> { // LOOP*Bone Count
>
> STRING[31] : Bone Name
>
> }
>
> 
>
> "_BOUNDINGBOX_"
>
> {
>
> FLOAT32 : Max, X Position
>
> FLOAT32 : Max, Z Position
>
> FLOAT32 : Max, Y Position
>
> FLOAT32 : Min, X Position
>
> FLOAT32 : Min, Z Position
>
> FLOAT32 : Min, Y Position
>
> }
>
> 
>
> "_COLLPRIMS_"
>
> {
>
> // NOT DOCUMENTED
>
> // 16bytes all 0
>
> }
>
> 
>
> "SceneHeader"
>
> {
>
> LONG : Unknown, File Version (always 1?)
>
> LONG : Unknown, Description File Count (files that start with "_")
>
> LONG : Unknown, File Array Count
>
> LONG : Mesh Count
>
> LONG : Material Count
>
> }
>
> 
>
> "SceneDescription"
>
> { // LOOP*Material Count
>
> STRING[36] : Mesh Name / Scene Object
>
> }
>
> 
>
> "MatArray"
>
> { // LOOP*Material Count
>
> LONG : Unknown, Index?
>
> LONG : Unknown
>
> LONG : Texture Count
>
> LONG : Offset in "MatTextureInfoArray" of the texture info
>
> LONG : Unknown
>
> LONG : Unknown
>
> FLOAT32 : Unknown, usually 0.5
>
> FLOAT32 : Unknown, usually 1.0
>
> LONG : Unknown
>
> }
>
> 
>
> "MatTextureInfoArray"
>
> { // LOOP*Texture Count
>
> LONG : Unknown
>
> STRING[52] : Texture Name
>
> LONG : Unknown
>
> LONG : Unknown
>
> LONG : Unknown
>
> LONG : Unknown
>
> LONG : Unknown
>
> LONG : Unknown
>
> LONG : Unknown
>
> LONG : Unknown
>
> LONG : Unknown
>
> LONG : Unknown
>
> LONG : Unknown
>
> }
>
> 
>
> "UsedShaders.txt"
>
> {
>
> // NOT DOCUMENTED
>
> }
>
> 
>
> "CommandBuffer"
>
> {
>
> // Not Fully Understod, but contains 3 very important pieces of information
>
> // 1. Vertex/Face Counts, 2.DrawMethod
>
> }
>
> 
>
> "desc"
>
> {
>
> // NOT DOCUMENTED
>
> }
>
> 
>
> "RenderStrip"
>
> {
>
> LONG : Material Index (+1, search this index to the "MatArray")
>
> LONG : Unknown, Always 63?
>
> LONG : Unknown, Always 0?
>
> LONG : Bone Index (Starting bone to Include from Skeleton)
>
> LONG : Bone Count (Bones to Include From skeleton)
>
> LONG : Unknown, Always 0?
>
> LONG : Vertex Type
>
> }
>
> 
>
> "D3DVertexDesc"
>
> {
>
> // NOT DOCUMENTED
>
> }
>
> 
>
> "VDHeader"
>
> {
>
> LONG : Unknown, Always 0?
>
> LONG : Unknown, Always -1?
>
> }
>
> 
>
> "VBHeader"
>
> {
>
> STRING[36] : Mesh Name to Include
>
> LONG : Unknown, Always -1
>
> LONG : Vertex Count
>
> LONG : Data Size, commonly 56bytes, 14floats
>
> LONG : Unknown
>
> }
>
> 
>
> "IBHeader"
>
> {
>
> STRING[36] : Mesh Name to Include
>
> LONG : Unknown, Always -1
>
> LONG : Face Count
>
> LONG : Data Size, commonly 2bytes (Short)
>
> LONG : Unknown
>
> }
>
> 
>
> "Vertices"
>
> { // LOOP*Vertex Count
>
> FLOAT32 : Vertex X Position
>
> FLOAT32 : Vertex Z Position
>
> FLOAT32 : Vertex Y Position
>
> FLOAT32 : TextureCoordinate U Position
>
> FLOAT32 : TextureCoordinate V Position
>
> BYTE : Vertex Weight #1
>
> BYTE : Vertex Weight #2
>
> BYTE : Vertex Weight #3
>
> BYTE : Vertex Weight #4
>
> BYTE : Bone Index #1
>
> BYTE : Bone Index #2
>
> BYTE : Bone Index #3
>
> BYTE : Bone Index #4
>
> FLOAT32 : Unknown
>
> FLOAT32 : Unknown
>
> FLOAT32 : Unknown
>
> FLOAT32 : Unknown
>
> FLOAT32 : Vertex Normal X Position
>
> FLOAT32 : Vertex Normal Z Position
>
> FLOAT32 : Vertex Normal Y Position
>
> }
>
> 
>
> "Indices"
>
> { // LOOP*Face Count
>
> SHORT : Face Index
>
> } // CommandBuffer has a flag to tell you when to read the buffer as either a triangle strip or triangle list
>
> 
>
> 
>
> 
>
> 
>
> 
>
> ....Unfortunately I just have too many unknowns, and there are alot of variables that appear to be hash checks... I can't do any testing because I do not have the game for PC. but rather the xbox360.
>
> 
>
> would have been kick ass if the format was a bit more flexible and we could import new models into the game!
>
> 
>
> Anyway this is really as far as I got, hopefully my info can help someone else get a jump start on solving the rest of the format
>
> 
>
> 
>
> [center][/center]
>
> 
>
> -mariokart64n
