## Post #1
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-09-08T13:49:41+00:00
- Post Title: RaiderZ *.elu faces

i'm try to understand elu models from the new elu format (see a bpy script for old elus here: [http://forum.ragezone.com/f245/elu-ani- ... er-488857/](http://forum.ragezone.com/f245/elu-ani-blender-importer-488857/))

there is some variety between versions, so my specific request is for 0x500D - which is used for some animal npcs.

it looks like much of the data is now in a table - vertices, uvs, weights, etc but im unable to find the faces.

```
uint32 Version
uint32 Materials - now 0 (for reading old versions) as materials are in an external xml 
uint32 Objects

for each object:
uint32 lenMeshName
char MeshName[lenMeshName]
uint32 lenParentName
char ParentName[lenParentName]
int32 ParentBoneIndex   -1 when no parent bone
uint32 ??   multiple of 4096 - 4 or 20
uint32 ??   always 0
float WorldMatrix[16]
float ??
uint32 ??

uint32 v_indexes
float vertex[3][v_indexes]

uint32 ??
float ??[3][count value above]  values are small

uint32 ??
float ??[3][count value above]  values are small

uint32 ??
float ??[3][count value above]  values are small

uint32 ??   uvs?
float ??[3][count value above]   last value is either 0 or 1

* no idea from here *

the bones have

2 more uint32 values - so possibily 2 more structures
1 int32 value of -1
24 null bytes
24 other bytes (FF or 7F) 

before the next object


```


attached are 3 examples!
[NPC01.zip](https://xentaxbackup.github.io/file/3415_NPC01.zip)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-09-10T20:00:14+00:00
- Post Title: RaiderZ *.elu faces

clearly theres no interest in this game.. last attempt:

the animation format is similar with a slight change to the way bones are handled. cant be bothered to write it up unless i get some face info
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-10T21:48:15+00:00
- Post Title: RaiderZ *.elu faces

I have looked at this format it appears to be using a kind of face table to know how many faces to read before starting a new set of faces.
I have seen other games do this where they have a table before the faces which says read 6 faces for example then go to this offset and read this number of faces.
for example in cat.elu look at offset 0xCBCD
you read 4 bytes null
then 4 bytes number of faces
then read the faces * face count
I have been working with the file
hf_cloth_hood_01.elu
in this file you can clearly see the relationship between the section at
0x7C69
and the faces at
0xDC57
[hf_cloth_hood_01.rar](https://xentaxbackup.github.io/file/3426_hf_cloth_hood_01.rar)
