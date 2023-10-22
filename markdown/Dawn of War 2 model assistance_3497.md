## Post #1
- Username: potemkis
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 01, 2009 2:11 pm
- Post datetime: 2009-05-19T18:18:17+00:00
- Post Title: Dawn of War 2 model assistance

I extracted a few of the files from Dawn of War 2. I'm uploading the .model file for your viewing pleasure. Hopefully someone can help with a script or something that can import some of these into 3ds max...  (I have the SDK for Max 6 if it would help).
[space_marine.rar](https://xentaxbackup.github.io/file/2046_space_marine.rar)
## Post #2
- Username: potemkis
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-20T11:29:30+00:00
- Post Title: Dawn of War 2 model assistance

That's what I have so far, don't have the time to continue.

```
uint uk;
uint uk2;
uint uk3;
int uk4;
uint uk5;

struct Markers
{
    char ID[8];
    uint numGroups;
    uint size;
    uint uk;
    int uk4;
    uint uk5;
    uint uk6;
    uint uk7;
    char uk8[uk7];
    uint uk9;
    string uk10;
};

struct MeshGroup
{
    char ID[8];
    uint numGroups;
    uint size;
    uint uk;
    int uk4;
    uint uk5;
    Markers markers;    
};

struct Mesh
{
    char ID[8];
    uint numGroups;
    uint size;
    uint uk;
    int uk4;
    uint uk5;
    MeshGroup groups[numGroups];
};

struct Model
{
    char ID[8];
    uint numMeshes; // ?
    uint size;
    uint uk;
    int uk4;
    uint uk5;
    string name;
    Mesh meshes[numMeshes];
} model;
```
## Post #3
- Username: potemkis
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 01, 2009 2:11 pm
- Post datetime: 2009-05-21T01:10:20+00:00
- Post Title: Dawn of War 2 model assistance

Cool, thanks! If I were to put up the script that was written for the Dawn of War 1 .whm files, do you think a new import tool could be created?
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-22T13:04:18+00:00
- Post Title: Dawn of War 2 model assistance

Well who knows, might help.
## Post #5
- Username: potemkis
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 01, 2009 2:11 pm
- Post datetime: 2009-05-22T16:11:02+00:00
- Post Title: Dawn of War 2 model assistance

I believe the animations are handled by Havok...


I'd have to mail the original dawn of war model to you, it won't let me post it.
[SantosTools_0.4.rar](https://xentaxbackup.github.io/file/2053_SantosTools_0.4.rar)
