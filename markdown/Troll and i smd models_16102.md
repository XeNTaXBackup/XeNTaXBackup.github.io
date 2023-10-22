## Post #1
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2017-04-07T14:32:41+00:00
- Post Title: Troll and i smd models

I have Win 7 and game Troll and I not launch on Win 7 !
 

But i found smd models in this game !   

This game for 2017 year.

I try smd importer(2011) for 3d max 2009  , but model was not loaded.


 FOREST_01_DIRT_HILL_01.rar
file (25.63 KiB) Downloaded 21 times
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-04-17T07:17:14+00:00
- Post Title: Troll and i smd models

have a look at the smd in a hexeditor to see that it's binary data



Forest_Dirt_Hill.JPG (123.88 KiB) Viewed 91 times

(no normals)

It starts with this submesh (FVFsize= 60, has normals):
0x12600 1218
Vb1
60 28
0x888 1218
020000
0x0 255
## Post #3
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2017-04-23T06:32:07+00:00
- Post Title: Troll and i smd models

Hm...

shakotay2 do you use PRIMITIVE_TOPOLOGY_TRIANGLELIST ?

My mesh not look like on your picture !

And i find Box.smd mesh.


 BOXORIGIN.rar
(487 Bytes) Downloaded 12 times


I render correct this box.smd (vertices offset 24 decimal value not hex) PRIMITIVE_TOPOLOGY_TRIANGLELIST and 36 indexes and 24 vertices.
Vertex begin at 0x0888 and Index begin at 0x0AC8
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-04-23T07:36:09+00:00
- Post Title: Troll and i smd models

> Reply from Roman
>
> shakotay2 do you use PRIMITIVE_TOPOLOGY_TRIANGLELIST ?guess, no. (There's many other names, for example D3DPT_TRIANGLELIST or GL_TRIANGLES.)

I just use the face indices from the model to create triangles, one after the other.
You could open the test.obj which hex2obj creates with a text editor and compare the faces to the ones your app produces:
f 1/1 2/2 3/3 
f 4/4 5/5 6/6 

For the Forest_Dirt_Hill sample you could even use the face autocreation feature (button noPtC -> Fake).
(Be aware that there's a naming bug, it says "autocreated tristripped", but it's normal triangles only. )
## Post #5
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2017-04-23T10:59:21+00:00
- Post Title: Troll and i smd models

Aha !
I found 'VERT' and i use this data for vertices !

Now i understood  and now work all fine  

Thanks !
## Post #6
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-05-13T10:32:20+00:00
- Post Title: Troll and i smd models

> Reply from Roman
>
> Aha !
I found 'VERT' and i use this data for vertices !

Now i understood  and now work all fine  

Thanks !

Did you find the UV datas for the character model (48 bytes vertex size)?
