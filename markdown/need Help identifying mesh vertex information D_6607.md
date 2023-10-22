## Post #1
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2011-05-12T20:29:15+00:00
- Post Title: need Help identifying mesh vertex information :D

well im  more or less reverse engineering a .msh file (not the orbiter etc one).
one slice of it would look like this:
Besides the spacing etc that group im tryign to identify  currently consists of 3 "groups"(a kind of a dummy object in a weapon model) - separated by 80 3F bytes (more or less a kind of a  coordinate line breaker  or smthing).

The real problem i get is that i get 4 sets of coordinates.
until the  breaker bytes there is 4 sets of coordinates (separated by empty bytes). Each set is 12 bytes - 3x 4 byte floats.

First if there were 3 it could be 3 corners of a triangle, but 4th doesn't make a sense

```
float vertex_01_Y;
float vertex_01_Z;
skip 4;
float vertex_02_X;
float vertex_02_Y;
float vertex_02_Z;
skip 4;
float vertex_03_X;
float vertex_03_Y;
float vertex_03_Z;
skip 4;
float vertex_04_X;
float vertex_04_Y;
float vertex_04_Z;
skip 2;
x16 Group_end;

```


dont mind the naming, its temporary.
Also since it would be  used for a particle emission point or a dummy weapon "hand" etc location fixer... it wouldn't have any textures

also the hex code for this section im editing would be:

```

```
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-05-12T23:44:59+00:00
- Post Title: need Help identifying mesh vertex information :D

usually you get a bunch of floats, for different data. what you have to do is findout the vertex size.. basically thats how many bytes there are that define 1 vertex. but that one line of bytes could include more then xyz position. it could also include normals, texture corrdinates, vertex colours, and of course vertex weighting.

so if you see a pattern that repeats, then you'll be able to break them down. easiest way to figure out whats what is by importing it. basically trial and error. its easy to spot a float, its just I dont think you'll be able to translate them in your head, not without a conversion aid/tool
## Post #3
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2011-05-13T10:57:20+00:00
- Post Title: need Help identifying mesh vertex information :D

Well this one has no tools, no converters or importers.
Game itself is the only thing that can read it currently.

So i have it split up right but i just dont know which one of those 4 is normal, vertex, texture  etc -_-
i can split  it into 4  xyz groups but beside that , there is no pattern to identify which is which.

The only format  i do  know that the game uses somewhere in its process of exporting from 3dsmax is ASCII scene exporter (.ASE). All i can assume is that they use ASE (well they use a customized version of it so it saves .Map extensions) and then split it up and use it to make what ever they needed (skeletons, bones, animations etc).
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-13T11:35:04+00:00
- Post Title: need Help identifying mesh vertex information :D

post a sample file? mabee post the name of the game?
## Post #5
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2011-05-13T13:23:54+00:00
- Post Title: need Help identifying mesh vertex information :D

k, well its RF online - its been around here at the forum, but the work was never done and was quite incomplete and not even accurate (the  info about the structure of the file was completely off). 
[http://dl.dropbox.com/u/19690781/COM_WE ... CE_008.msh](http://dl.dropbox.com/u/19690781/COM_WEAPON_RMACE_008.msh)
Also iv focused on the first dummy/object parts before i even go for the main model part ( first 2 bytes shows the number of the dummy objects, some of them are in the beginning, some at the end, used for hand position etc and particle emissions points).
as for the structure, i did lay out a basic one that looks like this:

```
//v = vertex position, vn= vertex normals, uv = texture coordinates, currently pure guess.

struct MESHFILE
{
u16 Dummy_bone/object_sections;
child MESHLIMBDATA;
}

struct MESHLIMBDATA
{
str[len=100] Object_Section_Call_Name;
str[len=100] Object_Name_In_Skeleton;

float vertex_01_X;
float vertex_01_Y;
float vertex_01_Z;
skip 4;
float v_X;
float v_Y;
float v_Z;
skip 4;
float uv_X;
float uv_Y;
float uv_Z;
skip 4;
float vn_X;
float vn_Y;
float vn_Z;
skip 2;
x16 Group_end;

float vertex_01_X;
float vertex_01_Y;
float vertex_01_Z;
skip 4;
float vertex_02_X;
float vertex_02_Y;
float vertex_02_Z;
skip 4;
float vertex_03_X;
float vertex_03_Y;
float vertex_03_Z;
skip 4;
float vertex_04_X;
float vertex_04_Y;
float vertex_04_Z;
skip 2;
x16 Group_end;

float vertex_01_X;
float vertex_01_Y;
float vertex_01_Z;
skip 4;
float vertex_02_X;
float vertex_02_Y;
float vertex_02_Z;
skip 4;
float vertex_03_X;
float vertex_03_Y;
float vertex_03_Z;
skip 4;
float vertex_04_X;
float vertex_04_Y;
float vertex_04_Z;
skip 2;
x16 Group_end;
skip 305; // empty space at the end of the block(mostly 2 bytes ill leave for later).
}
```


Oh and ps. this code is for sructurian/datedit.
## Post #6
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2011-05-15T17:23:36+00:00
- Post Title: need Help identifying mesh vertex information :D

lol, as soon as i mention rf online reverse engineering anywhere.. .the thread dies lol
