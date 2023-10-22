## Post #1
- Username: ItsEasyActually
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Dec 17, 2010 7:49 am
- Post datetime: 2011-05-23T05:30:44+00:00
- Post Title: Sonic's .GNO model format

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: ItsEasyActually
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Dec 17, 2010 7:49 am
- Post datetime: 2011-05-25T12:01:22+00:00
- Post Title: Sonic's .GNO model format

I worked on more of it last night, but I still need help.

```
//The model appears to have about seven different main structs for data. 
//NGIF, NGTL, NGNN, NGOB, NOF0, NFN0, NEND
*DENOTE OF EACH SECTION*

[NGIF]Header of file
textHeader; NGIF
unknown uint32; 18000000 //Appears to be always the same
unknown uint32; //Seen both 00000002 and 00000003
unknown uint32; 00000020 //This might be the size of the header within the file because the header is also 32 bytes long
unknown uint32; //This seems to be a location 32 bytes before the next location, I do not know what for yet
Address uint32; //Leads to the NOF0 data area
unknown uint32; //Seems to be different between files unlike the first two above
unknown uint32; //Appears to be always the same
[End NGIF Header]

[NGTL]Texture List
textHeader; NGTL 
unknown[4] uint32; 
fileSize; //Number of bytes before texture name data
//It appears that 00050001 denotes the start of little structs that equal the number of texture names, each one being 20 bytes in length
*MINI-STRUCTS*
unknown[2] uint16; 0005 0001 //These appear to denote the start of these mini structs.
unknown[3] uint32; //Appears to always be null\padding, but in the last struct, data appears in the third uint32 piece
unknown uint32; //Seems to be the end of the struct, no other info yet. On the final struct right before textures names, it seems to always be 00000010
*END MINI-STRUCT NOTES*
//The rest of the data is a 'commenting' system that holds the names of all of the textures used for the model in question
[End NGTL Data]

[NGNN]Rig Data (Sonic 4 models do not have this)
textHeader; NGNN
unknown uint32[2];
bytesNull[4];
*MINI-STRUCT*
boneID uint32;
unknown uint32; //I have no idea
*END MINI-STRUCT*
//Just like above, the rest is a 'commenting' system on the bone names

[NGOB]Mesh Data
textHeader; NGOB
unknown uint32; 
unknown uint32;
bytesNull[4];
	\Lasts for 16 bytes ALWAYS\
*Data Chunk 1*
\128 bytes CONSTANT chunks listed until next Data Chunk\
unknown uint32; //Last byte is an ID
bytesNull[4]; //Uses FFFFFFFF
unknown uint16; //Sometimes an ID like object, sometimes starts off with FFFF
unknown uint16; //Somtimes FFFF, sometimes ID like object
unknownSet1; //24 bytes used for something. They are sometimes null, and the sometimes have data in them
unknownSet2; //16 bytes, four floats that equal 1
unknownSet3; //16 bytes, Same as unknownSet1
unknownFloat1; //Single float equaling 1
unknownSet4; //16 bytes, Same as unknownSet1
unknownFloat2; //Single float equaling 1
unknownFloat3(?); //Possible float that's sometimes null, sometimes not.
Null[32]; //Padding inbetween each section of 128 byte chunks
	\Unknown\

*Data Chunk 2*
	\Unknown\

*Data Chunk 3*
vertexFloat; XYZ Buffer for model's vertex
normalsFloat; XYZ Buffer for model's vertex
//Unknown if normals follow the vertex or if it's one mass after the vertex buffer is complete
	\Vertex/Normals buffers?\

*Data Chunk 4*
X-Pos uint16; 
Y-Pos uint16;
	\UV Data?\

*Data Chunk 5*
	\Unknown\




[NOF0]Fourth Data Sector
textHeader; NOF0
unknown uint32; //Same strange data as with every other data section
Count uint32; //Total number of data addresses listed after Null data
Null uint32;
Addresses uint32; //Points to areas throughout the file for specific data
[End NOF0 Data]

[NFN0]
textHeader; NFN0
unknown uint32;
Null uint32[2];
textFilename; 
//Continues with null bytes until NEND

[NEND]
textHeader; NEND
unknown uint32;
Null; 24 bytes to total to 32 bytes.
```
## Post #3
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-06-04T14:02:02+00:00
- Post Title: Sonic's .GNO model format

i think its gonna be really hard to figure out this format
I bet chrrox can crack this one easily
