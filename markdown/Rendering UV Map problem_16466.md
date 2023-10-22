## Post #1
- Username: eatrawmeat391
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Dec 06, 2016 5:51 pm
- Post datetime: 2017-06-28T15:11:24+00:00
- Post Title: Rendering UV Map problem

In the SVR Blender yobj script,there is an uvlist which contains groups of 3 uv lines,when I tried to read the data to create an obj from the data (debug_uv.txt) I was able to get meaningful display.But when I grouped 3 uv lines from the OBJ that Blender creates and printed them out,the result looked like a mess.Also when Blender exports the uv,none of the lines has any relation to the uv coords in debug_uv.txt that the SVR script is extracting.

debug_uv.txt = UV that SVR YOBJ Script extracts,grouped by 3 uv
test_uv.txt = UV that Blender extracts
uv3.obj: Obj generated from test_uv.txt
uv2.obj: Obj generated from debug_uv.txt

This code converts debug_uv.txt to uv2.obj.Preview looks right.

```

input = open("debug_uv.txt")
a = open("uv2.obj", 'w')
vertices = []
faces = []
face = 0
for line in input:
    x1, y1, x2, y2, x3, y3 = scanf.sscanf(line, "[%f, %f] [%f, %f] [%f, %f]\n")
    vertices.append([x1, y1, 0])
    vertices.append([x2, y2, 0])
    vertices.append([x3, y3, 0])
    faces.append([face, face+1, face+2])
    face += 3
for x in xrange(len(faces)):
    a.write("v %.6f %.6f %.6f\n" % (vertices[x*3][0], vertices[x*3][1], vertices[x*3][2]))
    a.write("v %.6f %.6f %.6f\n" % (vertices[x*3+1][0], vertices[x*3+1][1], vertices[x*3+1][2]))
    a.write("v %.6f %.6f %.6f\n" % (vertices[x*3+2][0], vertices[x*3+2][1], vertices[x*3+2][2]))
for x in xrange(len(faces)):
    a.write("f %d %d %d\n" % (faces[x][0]+1,faces[x][1]+1, faces[x][2]+1))
a.close()


```


This code converts test_uv.txt to uv3.obj,results look weird.I grouped each 3 uv lines and draw them separately

```
input = open("test_uv.txt")
faces = []
vertices = []
a = open("uv3.obj", 'w')
i = 0
for line in input:
    x1, y1 = scanf.sscanf(line, "%f %f\n")
    vertices.append([x1, y1, 0])
    if (i + 1) % 3 == 0:
        faces.append([i-2, i-1, i])        
    i += 1
for x in xrange(len(faces)):
    a.write("v %.6f %.6f %.6f\n" % (vertices[x*3][0], vertices[x*3][1], vertices[x*3][2]))
    a.write("v %.6f %.6f %.6f\n" % (vertices[x*3+1][0], vertices[x*3+1][1], vertices[x*3+1][2]))
    a.write("v %.6f %.6f %.6f\n" % (vertices[x*3+2][0], vertices[x*3+2][1], vertices[x*3+2][2]))
for x in xrange(len(faces)):
    a.write("f %d %d %d\n" % (faces[x][0]+1,faces[x][1]+1, faces[x][2]+1))

```

uv2.obj looks right while uv3.obj looks weird.
[uv_2.7z](https://xentaxbackup.github.io/file/13040_uv_2.7z)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-06-28T17:24:07+00:00
- Post Title: Rendering UV Map problem

well, see, you're still struggeling with that ugly yobj format  
[viewtopic.php?f=16&t=15579&p=124985&hilit=yobj#p124985](http://forum.xentax.com/viewtopic.php?f=16&t=15579&p=124985&hilit=yobj#p124985)

From your post as of Dec. 12th, 2016 I made this comparison for the mesh 0 (as you called it):



02-yobj-model-0.jpg (201.1 KiB) Viewed 50 times


As you can see there's some ugly swapping for the uv order (bold underlining).

You also might be required to get the (uv) face indices from the yobj file since they are not really regular:
(+: upward count)
+ f 1 2 3 -> a b c
f 3 2 4 -> c b c+1
f 2 5 4
+ f 4 5 6 -> x y z
f 5 7 6 -> y z+1 z

+ f 6 7 8 -> A B C
f 7 9 8 -> B C+1 C
+ f 8 9 10
f 9 11 10
+ f 10 11 12
f 11 13 12
+ f 12 13 14
f 13 15 14

+ f 14 15 16
+ f 17 18 19
f 19 18 20
f 18 21 20

At least I don't see how to recreate them automatically.

(keep in mind that this yobj format doesn't seem to use "render to vertex". Therefore the uv face indices are different from the ones for the vertices.)
