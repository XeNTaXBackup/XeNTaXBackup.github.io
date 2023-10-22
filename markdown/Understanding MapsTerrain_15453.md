## Post #1
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-11-05T20:42:19+00:00
- Post Title: Understanding Maps/Terrain

I'm trying to understand how this game builds the map and terrain. Specially if it uses a heightmap. So I can write an app that can view the map and move around (camera) freely. But most of the tutorials here are about extracting textures and 3d models, not much about maps/terrains.

First, I'm not entirely sure if the game actually uses height maps. But it was made in 2000/2001, so it makes sense if it did.

The following files are loaded each time a map is loaded. I'll use map 4 as an example from here on:

```
/map/map4.inf
/map/map4.obj
/terrain/addterrain4.ctr
/terrain/addterrain4.obj
/terrain/addterrain4.inf
/terrain/addterrain4.t16
/terrain/terrain4.obj
/terrain/terrain4.t16

```


*.T16
I know these are textures.

Here is terrain4.t16 unpacked (terrain):  


And here is addterrain4.t16 unpacked (building):  


*.SPT
I know this is an encrypted script. It contains things like ambient light color, sky color and other configurations for the map. 

*.CTR
I'm not sure about this yet but I don't think this is the heightmap.

*.INF
I'm not sure about this yet but I don't think this is the heightmap. But it looks like positions for buildings/objects on the map.

*.OBJ
Although this sounds like a 3D object file, it isn't. So far I was able to parse this file with this script:

Checking map4.obj

```
        bin.seek(0, 2)
        file_size = bin.tell()
        
        bin.seek(0)

        unk1 = struct.unpack("<h", bin.read(2))[0]
        
        width  = struct.unpack("<h", bin.read(2))[0]
        height = struct.unpack("<h", bin.read(2))[0]
        
        c_width = struct.unpack("<h", bin.read(2))[0]
        c_heigth = struct.unpack("<h", bin.read(2))[0]
        
        size1 = struct.unpack("<I", bin.read(4))[0]
        size2 = struct.unpack("<I", bin.read(4))[0]

        bin.seek(50)
        
        # (1, 76, 76, 304, 304, 5776, 92416)
        print(unk1, width, height, c_width, c_heigth, size1, size2)

        for x in range(size1):
            unk2 = struct.unpack("<BBBB", bin.read(4))
     
        for y in range(size2):
            unk3 = struct.unpack("<BB", bin.read(2))

```


The script reads the file till the end so I think I got the parsing right. But I still don't understand what those bytes (unk2, unk3) mean.

Here are the first few bytes: (1, 76, 76, 304, 304, 5776, 92416).

76x76 seems to me like an image widthxheight. This is the part where I start to suspect that this must be the heightmaps.

304x304 is the size of the map coordinates, if I go to the bottom right part of the map, the coords show me x304 y304. (0,0) (304,304)

5776 is 76*76.

92416 is 304*304.

I'm guessing the cellspacing is 4, because 304/76 = 4.

Checking terrain4.obj

First few bytes:

```
00000016 00 00 80 C2 08 00 00 00 00 00 80 42 00 00 FF 43 ...........B...C
```

4C 00 00 00 4C 00 00 00 is again: 76 76. The next coming bytes looks like floating points. But I'm still trying to figure out what these floats are.

I wrote a script that can parse the whole file:

```
    bin.seek(0, 2)
    file_size = bin.tell()

    bin.seek(0)

    width  = struct.unpack("<I", bin.read(4))[0]
    height = struct.unpack("<I", bin.read(4))[0]

    print(width, height)

    for x in range(width*height):
        unk1 = struct.unpack("<fffHH", bin.read(16))
        print(unk1)

        for y in range(10):
            unk2 = struct.unpack("<ffffffBBBBff", bin.read(36))
            print(unk2)

        unk3 = struct.unpack("<HH", bin.read(4))
        print(unk3)

    print((bin.tell()-file_size) == 0)
```


Here are the last few lines of the prints of the script:

```
(9536.0, 0.0, -9664.0, 8, 60)
(9536.0, 367.3583679199219, -9664.0, 0.6106882691383362, 0.7202576398849487, -0.3290725350379944, 125, 125, 125, 255, 0.5, 0.5)
(9472.0, 439.9534912109375, -9664.0, 0.6727219820022583, 0.5930730104446411, -0.4423908591270447, 72, 72, 72, 255, 0.0, 0.5)
(9472.0, 529.98291015625, -9600.0, 0.5103294849395752, 0.5574429631233215, -0.6548444032669067, 91, 91, 91, 255, 0.0, 0.0)
(9536.0, 428.7572021484375, -9600.0, 0.5774530172348022, 0.5274922251701355, -0.6231372356414795, 83, 83, 83, 255, 0.5, 0.0)
(9600.0, 382.6859436035156, -9600.0, 0.32311421632766724, 0.6967470049858093, -0.6404222846031189, 110, 110, 110, 255, 1.0, 0.0)
(9600.0, 331.24566650390625, -9664.0, 0.4635116457939148, 0.8214490413665771, -0.3322325348854065, 149, 149, 149, 255, 1.0, 0.5)
(9600.0, 326.34356689453125, -9728.0, 0.5303630828857422, 0.847672700881958, -0.012873286381363869, 122, 122, 122, 255, 1.0, 1.0)
(9536.0, 370.5403747558594, -9728.0, 0.603411078453064, 0.7964465618133545, 0.039598409086465836, 107, 107, 107, 255, 0.5, 1.0)
(9472.0, 423.61572265625, -9728.0, 0.6945193409919739, 0.7165639996528625, -0.06464438885450363, 97, 97, 97, 255, 0.0, 1.0)
(9472.0, 439.9534912109375, -9664.0, 0.6727219820022583, 0.5930730104446411, -0.4423908591270447, 72, 72, 72, 255, 0.0, 0.5)
(64656, 900)
(9664.0, 0.0, -9664.0, 8, 60)
(9664.0, 323.531005859375, -9664.0, -0.16421209275722504, 0.9194830656051636, -0.3571907877922058, 202, 202, 202, 255, 0.5, 0.5)
(9600.0, 331.24566650390625, -9664.0, 0.11137175559997559, 0.9239282011985779, -0.3659959137439728, 199, 199, 199, 255, 0.0, 0.5)
(9600.0, 382.6859436035156, -9600.0, 0.32311421632766724, 0.6967470049858093, -0.6404222846031189, 110, 110, 110, 255, 0.0, 0.0)
(9664.0, 370.8617248535156, -9600.0, -0.030711062252521515, 0.8036384582519531, -0.5943247675895691, 202, 202, 202, 255, 0.5, 0.0)
(9728.0, 387.73626708984375, -9600.0, -0.3357184827327728, 0.8114649057388306, -0.478348970413208, 202, 202, 202, 255, 1.0, 0.0)
(9728.0, 359.2901306152344, -9664.0, -0.4858676493167877, 0.869583010673523, -0.0880785584449768, 202, 202, 202, 255, 1.0, 0.5)
(9728.0, 373.6744079589844, -9728.0, -0.6241185665130615, 0.7812370657920837, -0.012026631273329258, 202, 202, 202, 255, 1.0, 1.0)
(9664.0, 302.3572998046875, -9728.0, -0.23366673290729523, 0.9231089949607849, -0.3054006099700928, 202, 202, 202, 255, 0.5, 1.0)
(9600.0, 326.34356689453125, -9728.0, 0.23029862344264984, 0.9547197222709656, -0.18834225833415985, 177, 177, 177, 255, 0.0, 1.0)
(9600.0, 331.24566650390625, -9664.0, 0.11137175559997559, 0.9239282011985779, -0.3659959137439728, 199, 199, 199, 255, 0.0, 0.5)
(64656, 900)
True
```

My Questions:

 Any tutorial on this topic?
 Could the .obj file possibly be the heightmap, if not, what is it?
 Any idea what the .CTR and .INF files are? (guesses?)
Additional Information:
The map 4 is called Lava Canyon. It features paths surrounded by canyons of lava.

Minimap Texture


Related files: [Download from Mediafire](http://www.mediafire.com/file/cab16yc1sbr3gpw/map_files.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-11-06T13:29:15+00:00
- Post Title: Understanding Maps/Terrain

> Reply from majidemo
>
> My Questions:

 Could the .obj file possibly be the heightmap, if not, what is it?
The heightmaps I've dealed with so far, were textures.
terrain4.obj doesn't look like a texture file; if you display the contained floats as a point cloud it looks like a sky (but guess, it's no stars):



terrain.JPG (239.9 KiB) Viewed 200 times
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-11-06T16:58:39+00:00
- Post Title: Understanding Maps/Terrain

had a second glance onto the logged data and,  hah, guess what: 



terrain4-heightmap.JPG (148.15 KiB) Viewed 194 times



I modified your script like this:

```
        for y in range(10):
            unk2a = struct.unpack("<fff", bin.read(12))
            unk2b = struct.unpack("<fff", bin.read(12))
            unk2c = struct.unpack("<BBBBff", bin.read(12))
            #unk2 = struct.unpack("<ffffffBBBBff", bin.read(36))
            #print(unk2)
            print(v, unk2a)
            #print(v, unk2b)
        unk3 = struct.unpack("<HH", bin.read(4))
        #print(unk3)
```
then did some textual replacements in notepad+,
such as "('" against nothing to get an obj file with lines like such: v 64.0 510.0 -64.0

btw: accompanied the with open sequence by

```
import struct
orig_stdout = sys.stdout
f = open('terrain_log.txt','w')
sys.stdout = f
v= 'v'

with open...

sys.stdout = orig_stdout
f.close()
```
for logging into a file; tested with Blender 2.49; (rename .txt to .obj)
## Post #4
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-11-06T21:08:31+00:00
- Post Title: Understanding Maps/Terrain

Knowing which game it is would be useful.
## Post #5
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-11-06T21:19:55+00:00
- Post Title: Understanding Maps/Terrain

Great! thanks again for the help mr Shakotay2, I modified your modification to my script 

```

file = "terrain4.obj"
with open(file, "rb") as bin:
    output = "# heightmap? \n"

    width  = struct.unpack("<I", bin.read(4))[0]
    height = struct.unpack("<I", bin.read(4))[0]

    for x in range(width*height):
        unk1 = struct.unpack("<fffHH", bin.read(16))

        for y in range(10):
            unk2a = struct.unpack("<fff", bin.read(12))
            unk2b = struct.unpack("<fff", bin.read(12))
            unk2c = struct.unpack("<BBBBff", bin.read(12))
            output = output + "v %f %f %f\n" % (unk2a[0], unk2a[1], unk2a[2])

        unk3 = struct.unpack("<HH", bin.read(4))
        output = output + "\n"

    f = open("output_%s" % (file), "w")
    f.write(output)
    f.close()

```

This should create the .obj file that can be imported directly to blender.


One thing though, the resulting map object still needs to be mirrored/flipped on its Z-axis to have the same orientation as in-game.

Anyway, So I guess they don't actually use a height-map... instead its a 3d object of the map terrain, interesting... 

I'll try to figure out what the rest of the data on this file is about. 

 Shouldn't there be faces? or could it be internally calculated? (I can't find obvious face indices on the file)
 Some of this should possibly be UV data for texture right, to apply the different tile textures? (I'm guessing unk2c?)
 <strike>unk2b seems to add-up to 1.0, normals?</strike> (update: I tried plotting this and it was the dome structure you first talked about)

Here are the related textures for terrain4.obj. Extracted from terrain4.t16:


Preview of Map (in-game)


__________________________________________________
Additional Findings

I noticed that:

 texture_index are numbers that are equal or less than 63, where 64 is the total number of textures from terrain4.t16 or 0 to 63 indices. Which gives me an idea that this must be the corresponding texture for the cell. 
Code: Select all    for x in range(width*height):
        unk1 = struct.unpack("<fffH", bin.read(14))
        texture_index = struct.unpack("<H", bin.read(2))[0]
        print(unk1)

        for y in range(10):
            unk2a = struct.unpack("<fff", bin.read(12))
            unk2b = struct.unpack("<fff", bin.read(12))
            unk2c = struct.unpack("<BBBB", bin.read(4))
            tex_uv = struct.unpack("<ff", bin.read(8))
            
            output = output + "v %f %f %f\n" % (unk2a[0], unk2a[1], unk2a[2])
            output = output + "vt %f %f\n" % (tex_uv[0], tex_uv[1])
            
        unk3 = struct.unpack("<BBBB", bin.read(4))
        output = output + "\n"

 tex_uv seems to me are UV values. I'm not totally sure though because I don't know where the face indices are yet. So I can't actually check.
 There is some kind of pattern if you print unk1, looks like cell positions, divisible by 8.
 Also, if you check the vertices, you'll notice a repeated vertex for every loop range(10).
Code: Select all# heightmap? 
v 64.000000 510.000000 -64.000000
v 0.000000 510.000000 -64.000000 // repeated
v 0.000000 510.000000 -0.000000
v 64.000000 510.000000 -0.000000
v 128.000000 510.000000 -0.000000
v 128.000000 510.000000 -64.000000
v 128.000000 510.000000 -128.000000
v 64.000000 510.000000 -128.000000
v 0.000000 510.000000 -128.000000
v 0.000000 510.000000 -64.000000 // repeated

v 192.000000 510.000000 -64.000000
v 128.000000 510.000000 -64.000000 // repeated
v 128.000000 510.000000 -0.000000
v 192.000000 510.000000 -0.000000
v 256.000000 510.000000 -0.000000
v 256.000000 510.000000 -64.000000
v 256.000000 507.343750 -128.000000
v 192.000000 508.984375 -128.000000
v 128.000000 510.000000 -128.000000
v 128.000000 510.000000 -64.000000 // repeated
This is the result if you only plot the first loop range(10), 9 vertices only because 2 are on top of each other:


__________________________________________________
Faces

So I tried to logically create the faces (because I couldn't really find the face indices on the files) and got this:


My code now looks like this:

```
        unk1 = struct.unpack("<fffH", bin.read(14))
        texture_index = struct.unpack("<H", bin.read(2))[0]

        for y in range(8):
            output = output + "f %d %d %d\n" % ((x*10)+1, (x*10)+y+2, (x*10)+y+3)        

        for y in range(10):
            unk2a = struct.unpack("<fff", bin.read(12))
            unk2b = struct.unpack("<fff", bin.read(12))
            unk2c = struct.unpack("<BBBB", bin.read(4))
            tex_uv = struct.unpack("<ff", bin.read(8))

            output = output + "v %f %f %f\n" % (unk2a[0], unk2a[1], unk2a[2])
            output = output + "vn %f %f %f\n" % (unk2b[0], unk2b[1], unk2b[2])
            output = output + "vt %f %f\n" % (tex_uv[0], tex_uv[1])
  
        unk3 = struct.unpack("<BBBB", bin.read(4))

        output = output + "\n"
```

Now, applying multiple textures... Hmmm...

You can find the code that generates the map and adds the textures [here](http://pastebin.com/P5D6hsG6). 
But the approach seems too hackish or somewhat bit forced, is there a more elegant way of doing this?

This looks right though, thoughts?:


__________________________________________________
Now looking for the buildings(fixtures,bridges) and position it on the terrain...
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-11-07T17:21:41+00:00
- Post Title: Understanding Maps/Terrain

great progress you've made! Well done.  

I was a little bit unsure about the way you're creating the faces:
f 1 2 3
f 1 3 4
f 1 4 5
f 1 5 6
f 1 6 7
f 1 7 8
f 1 8 9
f 1 9 10

Then I realized that vertex 1 is the middle point of a square that is built of 8 triangles
so it's part of every triangle.
Great!

btw: where did you get the idea for this "formulae"? From yourself or somewhere else?  
for y in range(8):
 output = output + "f %d %d %d\n" % ((x*10)+1, (x*10)+y+2, (x*10)+y+3)

And: what's the name of the game?
First thing I'd urgently mod would be the camera zoom (in case you can't zoom in).
## Post #7
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-11-07T17:35:21+00:00
- Post Title: Understanding Maps/Terrain

Thanks 

As for the faces, I just displayed the first 10 vertices on blender and counted/plotted which one should be a triangle/face. So I drew a line from vertex 1 to vertex 2 to vertex 3 forming a triangle and repeated until I had all the right faces. Then tried to create a formula out of it that can be applied to all the remaining vertices. That's how I got the calculation.

This game is called Khan, from 2001. I'm actually writing a browser version of the client that's why I'm unpacking the files. 

This is what I have so far, in relation to parsing the map data:


I have a question though, how do I flip/mirror the map? On blender I just change the Z scale to -1.0, but what if I want it to be mirrored already? How should I change my python script?
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-11-07T20:04:22+00:00
- Post Title: Understanding Maps/Terrain

mirroring at axis is done by multiplying with -1.0
If you want to flip it for example in y-direction then y' = -y.

But it you want to flip without moving/offset then the formulae is
y' = deltaY - y, where deltaY = ymax + ymin

example flipping uvs (where tymax= 1.0, tymin=0.0 -> deltaY= 1.0)
ty' = 1.0 - ty

Hopefully ymin, ymax are constant for all maps else you will have to do a min/max calculation
([http://stackoverflow.com/questions/8525 ... ax-and-min](http://stackoverflow.com/questions/8525447/python-max-and-min)) but it's about int.
