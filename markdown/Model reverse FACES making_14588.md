## Post #1
- Username: Racial
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Dec 20, 2015 11:51 pm
- Post datetime: 2016-07-01T14:44:00+00:00
- Post Title: Model reverse FACES making

Hi to all, thanks for reading this lines and please be good with my english isn't my native language.

First of all, im using Wavefront .OBJ format, but i want to change it if it possible (that format doesn't support bones and other things.

For continue, isn't a problem export models with the format that i will attach to a code, i want to know if there is a similar to put import other type of models to that.

Example:

Bones
XX XX XX XX YY YY YY YY ZZ ZZ ZZ ZZ AA AA AA AA
XX XX XX XX YY YY YY YY ZZ ZZ ZZ ZZ AA AA AA AA
XX XX XX XX YY YY YY YY ZZ ZZ ZZ ZZ AA AA AA AA
xx xx xx xx yy yy yy yy zz zz zz zz aa aa aa aa
xx xx xx xx yy yy yy yy zz zz zz zz aa aa aa aa

XX / YY / ZZ = Positions of Bones
AA xx yy zz aa = Other stuff unknown

Submeshes (are various of this in a bone)
XX XX XX XX YY YY YY YY ZZ ZZ ZZ ZZ AA AA AA AA
xx xx xx xx yy yy yy yy zz zz zz zz aa aa aa aa
UU UU UU UU VV VV VV VV 00 00 00 00 00 00 00 00
XX XX XX XX YY YY YY YY ZZ ZZ ZZ ZZ AA AA AA AA
xx xx xx xx yy yy yy yy zz zz zz zz aa aa aa aa
UU UU UU UU VV VV VV VV 00 00 00 00 00 00 00 00
XX XX XX XX YY YY YY YY ZZ ZZ ZZ ZZ AA AA AA AA
xx xx xx xx yy yy yy yy zz zz zz zz aa aa aa aa
UU UU UU UU VV VV VV VV 00 00 00 00 00 00 00 00


XX / YY / ZZ = Vertex axis
AA = How vertex works with animation (if static, if move and how it does with bones modifications.
xx / yy / zz = Shadding position
aa = Shadder functions
UU / VV = UV (Texture vertex)

The face are ordenated so if there are 10 vertex (all with vt and shadding) the faces order will be this
1 - 2 - 3 
2 - 3 - 4 
3 - 4 - 5 
4 - 5 - 6
5 - 6 - 7
6 - 7 - 8
7 - 8 - 9 
8 - 9 - 10


For that reassons there are some groups of vertex on bones to do the complete model.

There is a way to take a format of model 3D that uses THAT type of faces? Its for create Model3D so i can convert if it got that info with a plugin of QuickBMS or something similar, the problem is that face maker that generally models of internet doesn't follow.

If you can submit a little information i will be very gratefull. Thanks for reading me
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-02T19:06:45+00:00
- Post Title: Model reverse FACES making

> Reply from Racial
>
> The face are ordenated so if there are 10 vertex (all with vt and shadding) the faces order will be this
1 - 2 - 3 
2 - 3 - 4 
3 - 4 - 5 
4 - 5 - 6
5 - 6 - 7
6 - 7 - 8
7 - 8 - 9 
8 - 9 - 10


For that reassons there are some groups of vertex on bones to do the complete model.

There is a way to take a format of model 3D that uses THAT type of faces?hi there,
I'm always happy to see guys like you starting with 3D theory. (there's so many leechers here now and research has decreased more and more...)

I think the faces are triangle strips with swapping face orientation.
You may compare here where orientation is counter clockwise always: [viewtopic.php?f=16&t=13494&p=114317&hilit=+line#p114317](http://forum.xentax.com/viewtopic.php?f=16&t=13494&p=114317&hilit=+line#p114317)

Do you have a reference for the 3D format you presented?
If so it would be helpful if you uploaded a model sample to extract an obj from it.

I know you want to do it the reverse way (obj -> 3D format, "composing") but starting with "extraction" is easier, imho.

(Creating the face indices is simple if you have some coding skills.)
## Post #3
- Username: Racial
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Dec 20, 2015 11:51 pm
- Post datetime: 2016-07-03T01:36:30+00:00
- Post Title: Model reverse FACES making

Yes, i used wavefront to export a example, even with reverse enginering i can reimport it (without removing or adding any vertex) and here is the problem, i write a "macro" to make the OBJ model (of course, without bones they are putted as a other group joining points with edges).

I put it like this (example of 10 vertex submesh)

o: MESH
v X Y Z
v X Y Z
v X Y Z 
# 3 vertex
i 1/2

o: Sub
v X Y Z
v X Y Z
v X Y Z
v X Y Z
v X Y Z
v X Y Z
v X Y Z
v X Y Z
v X Y Z
v X Y Z
#10 vertex (same here put VN = x y z and UV = u v)
f 1/2/3
f 2/3/4
f 3/4/5
f 4/5/6
f 5/6/7
f 6/7/8
f 7/8/9
f 8/9/10



Exporting model right that i can get the model outta the game and even edit. My problem it's the limited editions that i can do to a model (only edit the vertex position) because i can't tell to game how read faces (it do it in order using the last 2)
So im trying to find a way to convert a X model (X = one that i NOT export) for use a similar faces order.

I found a model format that export on 1/2/3 4/5/6, and i managed to add 3 vertex por each submesh, but in that way the size of the model its big (imagine that a submesh gets other information like textures and sizes information.

I see it that post, and its the same as i do but i'm doing with a special soft doing specially to read that. This is a OBJ example, if you compare with that you do its very similar
Thanks for answer 
[Esfera.rar](https://xentaxbackup.github.io/file/11229_Esfera.rar)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-03T07:50:44+00:00
- Post Title: Model reverse FACES making

> Reply from Racial
>
> because i can't tell to game how read faces (it do it in order using the last 2)"using the last 2"? I don't get what you mean exactly. Could you rephrase this, please?

> i write a "macro" to make the OBJ modelwhat kind of "macro", python script?
> I found a model format that export on 1/2/3 4/5/6, and i managed to add 3 vertex por each submesh,which model format?

> but i'm doing with a special soft doing specially to read that.I see, a model manager.
What does it do exactly?

Seems, you want to keep things secret.  
That's ok, but it's very unlikely that someone will put effort in helping you then.

(I could write a simple face converter in plain 'C' if you told exactly what to be done.)
## Post #5
- Username: Racial
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Dec 20, 2015 11:51 pm
- Post datetime: 2016-07-03T15:27:50+00:00
- Post Title: Model reverse FACES making

Not all, sorry if this things keep like secret, it's very big community of modders on ps2 and really i'm the only that tries to get adventages. Even it's for personal use so if i share files or examples maybe that will be against the forum rules. Again, apologies if you see such bad attitude.

About the first quote its the face order, isn't specified in the game files, it use the 1/2/3 - 2/3/4

With i friend we start a code on java to find specific values in the structure containing a character (it's one file subfile in a file for model). Even two guys do a similar versión that export each submesh in an OBJ group.

About the format that i use it's OBJ i write a example here and post an example of a converted model of a sphere on the game.

And the problem isn't really export a model (even we write a "anti-dumb people" tutorial) the big problem it's convert a model to a similar face structure.


See this picture of a file example.



RED SQUARS = Size values
DARK RED =  Other values (Bone number etc)
BLUE = Bone axis
GREEN = Submesh parameters
BLACK = Submesh start
YELLOW (in submesh parameters) = Size of Submesh
PURPLE/VIOLET = Mesh vertex/shadders/UV (one per line)

The problem isn't the game file, even isn't the problem adapt models between game and OBJ format, the problem is trying to adapting new models that are writed.

I dont remember exactly the format for 1/2/3 ; 4/5/6 ; 7/8/9 but i think it isn't usefull, if i remember and i can add it i will do it.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-03T16:46:51+00:00
- Post Title: Model reverse FACES making

> Reply from Racial
>
> And the problem isn't really export a model (even we write a "anti-dumb people" tutorial) the big problem it's convert a model to a similar face structure.why do you think it's only the face structure? (If it were it would be rather simple to create new ones, imho).

I'm not sure whether you know about general 3D format structures. Often there's sizes, offsets and pointers contained.
Just as an example (may not fit for your format, though). Say, you've the file size as a DWORD filesize in the file header.
To modify an existing model you add vertices, change the face indices. Thus the file size will increase, you'll have to increase
the value of the filesize in the same manner. Also it's very likely that vertex count and face count values are present.
(As I said, just an example. There might be other caveats; pointers to be changed, for example.) 

So you'll need to have a full understanding of the file format, every byte (sometimes it doesn't matter if some "unknowns" are left.)

> the problem is trying to adapting new models that are writed.I don't have the time to bother with the format, sry.
(I'd need a sample file, not the obj file.)
I've done several dozens of 3D format extractions using hex2obj. That was rather easy in most cases (without weights, no skeleton, of course).

But I can't remember any thread here (maybe there's one or two) which deal with a successful "obj to 3D" conversion.

This could be a thread to change this situation because I think what you want to achieve could be doable.
(in case it's limited to the "face thingie", what I'm not sure of, to be honest)

But I still don't have an idea how your java code is working (and this won't change, I guess   ).

btw: I'm not a native speaker, too. But it's a pain in the ass to read words like "writed"; it's written.
please consider learning irregular english verbs.
## Post #7
- Username: Racial
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Dec 20, 2015 11:51 pm
- Post datetime: 2016-07-03T18:06:38+00:00
- Post Title: Model reverse FACES making

lol, so sorry for that mistake.

Yes i understand, but im not trying to export or import with my files, those are only examples. Because do test it's needed in most cases i do test with excel convertions (really are usefull).
That im trying to find it's a similar Model3D format that uses triangulate faces with the pattern that we know.

I found that .ply format get an option to export triangulated vertex with 123 456 789 pattern (that is the similar that i mentioned in last post and maybe someone wants to use it in a future)

After finding the new Model3D format i can see if i can't convert or not, and even work on it to make it easier than manual convertion, i don't know if I'm being concise.
