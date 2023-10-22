## Post #1
- Username: DrAwesomeXD
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 10, 2017 3:38 am
- Post datetime: 2019-02-18T10:23:56+00:00
- Post Title: Noesis API Separate UV Index list?

So I've been trying to create a noesis plugin, but I don't get how to map uv indeces.
The NoeMesh object only has one triList, but let's say I have 20 vertices and 40 uv-coordinates, a face list AND a uv-index list, how do we accomplish that in noesis? For example, in an OBJ-File, we can have

v ...
v ...
v ...
v ...

vt ...
vt ...
vt ...
vt ...

f 1/1 2/2 3/3
f 1/2 3/3 4/4

In this case, two uv-coords map to the same vertex. 
Do we have to use something from the noesis or rapi module? 

I'd be very grateful for any help.
