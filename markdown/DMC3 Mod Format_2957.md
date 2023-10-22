## Post #1
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-03-02T17:04:15+00:00
- Post Title: DMC3 Mod Format

hehe, i know nothing about models yet i'm trying to dump the models from this game to obj XD, lucky me.



as you can see, the red is the name.  That's all i've accumulated on this model.  I know there's bone data, but i plan on having the app repack the models and apply an isp patch.

EDIT: Looked at it some more and the whole first line always stays the same


 0_pl000.rar
Here's Dante's Model (65.53 KiB) Downloaded 138 times
## Post #2
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-05-24T20:33:08+00:00
- Post Title: DMC3 Mod Format

Well I've looked vigorously at this again.
And have many results

```
    char Signature[4];       //"MOD "
    float Test;                 //always 1.01
    char cushion[8];         //Always here
    char amnt_objs;         //A byte storing how many models
    char amnt_bones;       //A byte storing how many bones
    char ukn[10];             //Unknown data
    int   bone_ptr;            //Pointer to bone data
    char cushion2[16];      //more Null cushioning
} Header;

```


After this every object has a header.

```
    short  ukn;              //unknown short, always 0x180 or 0x280, perhaps two seperate bytes
    short  verts;            //Total amounts of vertices
    int     ptr;               //Pointer to the model data
    char cushion[16];     //More cushioning
    char  ukn2[4];         //Inconsistent float,
    float  XYZ[3];          //XYZ coords of parent node?
} OBJ;

```


After this we reach the direct object header.

```
    short  verts;          //same as before, a vert counter
    short  headers;      //odd counter, sometimes there are two headers before data, this counts down how many
    char   cushion[8];  //more 0 cushioning
    int     vert_ptr;     //vertex pointer
    int     tex_ptr;      //2 floats with a 3rd inconsistent float at this index, assumed UV
    int     wght_ptr;    //weights ptr, 2 shorts that usually add up to 65535
    int     nrm_ptr;      //pointer to 3 bytes of data, obvious normals
    int     ukn_ptr;      //pointer to 2 bytes of data
} PTRS;

```


I know how much data each pointer holds because you simply take the array size and divide by the vertex amount.
Now I know what some of you may be thinking,
"where's the face data"
That's what I don't understand, there is none.
No possible place anywhere for face data.
I've found repeated Vertices, so I think perhaps they're storing this the same way as SMD.
Or at least something similar.

This goes on until we hit the bone data
Haven't mapped it out yet, but there are matrices with shorts..?
If anyone else wants to take a look be my guest.
I'll be attaching a beta script shortly, it can dump to OBJ or SMD, just by the switch of a function called.
lol, any help would be GREATLY appreciated.

edit:
Sorry it took me so long to get up
well, here is the script.


 Modx.zip
(21.42 KiB) Downloaded 190 times



Executable and source packaged along side.

Note:
To change to SMD dumping
uncomment line 164 and comment out 163
(it's obvious if you just look)

the source is very messy.
A lot of repetition because of the SMD/OBJ abilities.
Anyway, hope someone can help me out :P.
## Post #3
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2008-05-28T04:29:20+00:00
- Post Title: DMC3 Mod Format

Interesting... but what is SMD?

I looked throught the file a little bit following your data and Im afraid I currently have very little to add.

The first short could be a chunck/vertex/etc type. some sort of identifier to know what sort of data it is.

What in the world is that unkwon data at the end O.o!(ukn_ptr)

Good work figuring all this out
## Post #4
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-05-28T20:39:10+00:00
- Post Title: DMC3 Mod Format

SMD is just a model format that supports bones.
I'm trying to lean towards dumping to it because it'll motivate me to get weights in the App.
I've had some suspicion on the unknown data type being some sort of identifier of what bones to use.
ie; where to put the weights of the vertices.
I'm still doubtful though. :(

Thanks for the luck, hopefully I'll be able to find someone with more experience to help me on the matter ^_^.

edit:
lol, I think the third float in the UV array is just the W value.
Lol, gonna just test it out :P.

edit2:
Well I've been looking at the bone data.
The assumed xyz translations :P.

```
    short x;     //assumed x translation
    short y;     //assumed y translation
    float  z;     //assumed z translation
    short rx;    //assumed x rotation
    short ry;    //assumed y rotation
    float z;      //assumed z rotation... always an inverse of the z translation
    short ukn[6];  //not sure
    char cushion[4];
} Bones;

```

note:
All of the shorts are actually floats.
They're put through a function to get to float status of course.
This goes for other short/char values I've used before (eg; weights, normals...)

Here are some examples I have dumped.

```

parent :: child

-001 :: 000
000 :: 001
001 :: 002
002 :: 003
003 :: 004

@offset  x	y	z  ::  rx	ry	rz
	RAWx   RAWy    RAWy:: RAWrx    RAWry   RAWrz

@ 0x730 0.000000 0.000000 0.000000 :: 0.000000 0.000000 0.000000

	0000     0000     00000000 :: 0000     0000     00000000

	0.000000 0.141174 -0.000015 :: 0.145096 0.000000 -0.356873

	0000     24D4     FFFF     :: 2540     0000     A460

@ 0x750 -0.498047 0.149017 -12.000000 :: -0.247070 0.149017 12.000000

	8000     264D     C1400000 :: C000     26DE     41400000

	0.000000 -0.356873 -0.000015 :: -0.352951 0.000000 0.141174

	0000     A4D4     FFFF     :: A540     0000     2460

@ 0x770 0.184311 0.168625 -18.000000 :: -0.231384 -0.329422 18.000000

	2F80     2B95     C1900000 :: C460     ABDC     41900000

	-0.176483 -0.305893 -0.305893 :: 0.184311 -0.254913 -0.301971

	D206     B11C     B186     :: 2FD4     BEF8     B210

@ 0x790 -0.466675 -0.325500 -30.000000 :: 0.250977 0.168625 30.000000

	8800     AC11     C1F00000 :: 4000     2BE0     41F00000

	0.062744 0.192154 0.082352 :: 0.164703 0.494110 -0.305893

	10F9     31A2     150C     :: 2A7B     7E6B     B158

@ 0x7B0 0.219604 0.172546 -35.000000 :: 0.000000 0.164703 35.000000

	3800     2C55     C20C0000 :: 0000     2AFA     420C0000

	-0.090210 -0.301971 0.419601 :: 0.184311 -0.090210 0.192154

	E8FC     B20B     6B8E     :: 2F6C     E8AD     3157


```


edit3:
I think I figured out where textures are!
they're located after the vertex count.
They index a PTX container located past the model.
## Post #5
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2008-06-03T21:50:49+00:00
- Post Title: DMC3 Mod Format

when you say those shorts are floats do you mean a IEEE-7-Iforgotwhat standard 16 bit float or a fixed point float?

also you said some vertices are repeated.. now I don't know what you mean by that now but if it is the same vertex position twice in a row(one after the other) then perhaps the model is made from triangle strips and the 2nd vertex is used to invert the clock.. if that is the case then you don't need any extra face data.

Sorry I havent looked into it but in term of 3d all I have a console* ATM hehe  can't really display anything now but I'm working on it.

as for the bones... without animation data.. aside from pretty dots on screen I don't see the use for them lol.

*a text interface not a gaming console
## Post #6
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-06-04T00:10:41+00:00
- Post Title: DMC3 Mod Format

I think I mean fixed point.
I wasn't aware of 1EEE bit O_o.
I just mean:

```
return((double)x/65536);   //double for extra precision.

```


Yes I do mean that for the vertices. Perhaps it is triangle strips.  I don't really know much about 3-d either.
But I'll go look up what that is ^_^.
## Post #7
- Username: sidneymadmax
- Rank: beginner
- Number of posts: 35
- Joined date: Fri Sep 17, 2010 11:10 pm
- Post datetime: 2010-09-17T17:01:50+00:00
- Post Title: DMC3 Mod Format

[http://images2.wikia.nocookie.net/__cb2 ... 3Dante.jpg](http://images2.wikia.nocookie.net/__cb20071023040550/devilmaycry/images/2/21/DMC3Dante.jpg)

is to get the model in these scenes dante eye with the cool... at least the textures
## Post #8
- Username: Andersen
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Mar 07, 2010 5:52 am
- Post datetime: 2010-09-24T15:36:54+00:00
- Post Title: DMC3 Mod Format

Thats just a wallpaper mate. 

And that model is just the one you see in the cutscenes. only with shiny eyes.
## Post #9
- Username: sidneymadmax
- Rank: beginner
- Number of posts: 35
- Joined date: Fri Sep 17, 2010 11:10 pm
- Post datetime: 2010-09-24T20:45:40+00:00
- Post Title: DMC3 Mod Format

yes I have guy like you could use the DMC3 has 3dxriper during the scene (upload models)
