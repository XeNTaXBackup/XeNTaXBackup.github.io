## Post #1
- Username: St3ve
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 21, 2016 7:07 am
- Post datetime: 2017-01-22T00:08:26+00:00
- Post Title: Part way to finding a vertex header, need some pointers

I'm trying to extract some of the wanzer models from Front Mission 4 but I'm having trouble locating their vertex header either through savestates or individual files. Originally, I couldn't grasp the details of model extraction and tried to leave the effort to the guy from PS23DFormat who did meet with some success- he identified the terrain vertex header and managed to create an unpacker for the games archive. After months of silence, though, it became clear that I couldn't simply sit back and would have to continue on my own. Thus far, I have gone through the xentax guides and cobbled together a basic python script that creates vertices from three consecutive values read in from a file but haven't managed to locate the vertex header for the mechs which I want to extract. I'm at a loss for what my next step should be- I tried to swap parts of the mechs around and then use a file comparison program but so many values changed it wasn't possible for me to locate a header, I tried poking around vertex clouds made form every variant of longs, shorts, and floats in hopes of working backwards but haven't seen anything recognizable. Should I go back to sifting through cheat engine for floats? Alter the range of my python script? Keep looking through the vertex clouds? Any ideas would be appreciated.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-22T09:34:05+00:00
- Post Title: Part way to finding a vertex header, need some pointers

welcome to the forum  

1) could you show a picture of the terrain vertex header?
2) sample of a mech would be nice
## Post #3
- Username: St3ve
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 21, 2016 7:07 am
- Post datetime: 2017-01-23T00:39:42+00:00
- Post Title: Part way to finding a vertex header, need some pointers

The terrain vertex header is 0480*68 with * being the number of byte long floats that follow. The PS3D guy managed to find the face index as well but he didn't explain that part to me.
[http://i.imgur.com/spyPAXG.jpg](http://i.imgur.com/spyPAXG.jpg)
[http://i.imgur.com/rayVATj.jpg](http://i.imgur.com/rayVATj.jpg)

Here's a snapshot of a mech from the savestate I've been working on, there are two more off screen. If you mean't an actual sample of code that's kind of a chicken and egg situation. 
[http://i.imgur.com/2TSKKp3.png](http://i.imgur.com/2TSKKp3.png)

Here is the savestate itself if anyone wants to take a look.
[https://drive.google.com/file/d/0B04lzj ... sp=sharing](https://drive.google.com/file/d/0B04lzjiwkqoESHFXeURoWGxVb3c/view?usp=sharing)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-23T18:20:48+00:00
- Post Title: Part way to finding a vertex header, need some pointers

reminds my of WildArms3 ([http://ps23dformat.wikispaces.com/Wild+Arms+3](http://ps23dformat.wikispaces.com/Wild+Arms+3))
I've tried the WildArms3eememoryto3ds.BMS with a modified search pattern (findloc OFFSET string "\x80\x00\x00\x00\xC0\x2E\x30\x12\x04\x00\x00\x00\x00\x00" 0 0 ; ) at no avail.

Produces 1 or two senseles 60 bytes files and I don't have the time to review that horrible script.
## Post #5
- Username: St3ve
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 21, 2016 7:07 am
- Post datetime: 2017-01-24T01:55:53+00:00
- Post Title: Part way to finding a vertex header, need some pointers

Right now, I' mulling over how to modify my vertex script- I wouldn't be surprised if the mech models used byte long floats like the terrain meshes but are obscured by all the non mesh vertices the script generates.
## Post #6
- Username: St3ve
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 21, 2016 7:07 am
- Post datetime: 2017-01-28T17:40:16+00:00
- Post Title: Part way to finding a vertex header, need some pointers

```
import struct

coordinates = [0.0, 0.0, 0.0]
vertices = []

f = open(r"C:\Users\Greg\Documents\Front Mission savestates\eeMemory.bin", 'rb')

data = f.read(4)

while data != b'':
    value = struct.unpack('<f', data)
    value = value[0]

    if value <= 50 and value >= -50:
        coordinates[0] = value
        data = f.read(4)
        value = struct.unpack('<f', data)
        value = value[0]

        if value <= 50 and value >= -50:
            coordinates[1] = value
            data = f.read(4)
            value = struct.unpack('<f', data)
            value = value[0]

            if value <= 50 and value >= -50:
                coordinates[2] = value
                vertex = (coordinates[0], coordinates[1], coordinates[2])
                vertices.append(vertex)

    data = f.read(4)

mymesh = bpy.data.meshes.new("vertices")
myobject = bpy.data.objects.new("vertices", mymesh)
bpy.context.scene.objects.link(myobject)
mymesh.from_pydata(vertices,[],[])

```


Here's my script. It works but I just can't figure out how to filter code that isn't vertex data but still is a float, I tried having the program separate each "group" of vertices into an object but that slowed blender to a crawl. As It stands, I can't see past all these false positives but the only other option is to randomly test hundreds of individual files. Maybe opening a few of the files at a time rather than an entire savestate would provide better results.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-29T05:48:06+00:00
- Post Title: Part way to finding a vertex header, need some pointers

thx, but I don't have that bin file.

(used with eeMemory.bin the script fails:
"struct.error: unpack requires a bytes object of length 4")
## Post #8
- Username: St3ve
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 21, 2016 7:07 am
- Post datetime: 2017-01-29T14:48:23+00:00
- Post Title: Part way to finding a vertex header, need some pointers

Sorry about that, I forgot to change the or operators to ands and repath it to the savestate I posted. It should "work" now.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-29T17:04:28+00:00
- Post Title: Part way to finding a vertex header, need some pointers

thx; so your'e at the very beginning.  
Why not split the eeMemory.bin into smaller parts and treating them seperately?

There's blocks of zeroes  at 0x990BB0 to 0xE78360 (5 MB), another at 0x016E1280 to 0x01DC1300 (7 MB).

There's 70(?) TIM2 textures contained. Maybe identify/cut them first?
## Post #10
- Username: St3ve
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 21, 2016 7:07 am
- Post datetime: 2017-01-29T17:22:10+00:00
- Post Title: Part way to finding a vertex header, need some pointers

I didn't know that was an option. Would there be a difference between this and testing the files I've extracted from the archive?
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-29T17:37:25+00:00
- Post Title: Part way to finding a vertex header, need some pointers

depends on what your extractor extracted. Did it create 70 TIM2 files?
If the extracted files in sum + 5 MB + 7 MB = 32 MB (=size of eeMemory.bin) I'd say: no.

(but that formulae is only applicable for uncompressed data)

Did you read here, for example? [viewtopic.php?f=10&t=13680&p=113434&hilit=tim2#p113434](http://forum.xentax.com/viewtopic.php?f=10&t=13680&p=113434&hilit=tim2#p113434)

TextER.exe extracts 70 TIM2 files. (Pay attention that the parameter -tm to follow after the archivename (weird),
-e before.)



0028-TM2.JPG (50.29 KiB) Viewed 117 times

This matches part of the point cloud your script is showing.
## Post #12
- Username: St3ve
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 21, 2016 7:07 am
- Post datetime: 2017-01-29T18:13:36+00:00
- Post Title: Part way to finding a vertex header, need some pointers

The file extractor the PS23D guy made extracted about 3000 game files ranging from 0 to 300MB. While that sounds like a lot, the script generated quite a few duplicates I've been deleting on and off again. In any case, I poked around them in the beginning and found some level mesh data around the 1000kb mark- given how low poly the mesh data is, I would assume the mechs would be less than half that with weapons and backpacks being smaller still, which does narrow things down and cuts down on the false floats. I think I'll try taking a look at them again.  

I actually tried munge explorer and timtool but they weren't as helpful as I thought. It's pretty hard to tell what textures go where without using texmod. If I ever manage to extract models out of Front Mission Online, it's not going to be fun using old screenshots from 2005 as a guide...
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-29T21:04:19+00:00
- Post Title: Part way to finding a vertex header, need some pointers

for the vertices shown by your script there's a more selective way to find them:
search for 0480xx68 (xx being a wildcard) in eeMemory.bin, there's 1523 finds.
After find address +4 log 11*3 floats each (11 vertices).



eeMemory-bin-Arena.JPG (29.87 KiB) Viewed 109 times
## Post #14
- Username: St3ve
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 21, 2016 7:07 am
- Post datetime: 2017-01-29T21:26:27+00:00
- Post Title: Part way to finding a vertex header, need some pointers

Performing a wildcard search for the terrain header was actually the first script I made but I don't understand what "+4 log 11*3 floats each (11 vertices)" means or does. Are you trying to exclude the terrain vertices?
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-29T23:17:04+00:00
- Post Title: Part way to finding a vertex header, need some pointers

it just means that I logged 33 floats (11 vertices) starting 4 bytes after each pattern find address (1523 vertices)

ah, ok, re-read your posts, seems I misunderstood your problem.

Why exactly did you stick to a general search again after having performed a more specific one.
Wouldn't it make more sense to search the face indices instead?

Maybe they have to be autogenerated (guess tri strips).
## Post #16
- Username: St3ve
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 21, 2016 7:07 am
- Post datetime: 2017-01-29T23:32:18+00:00
- Post Title: Re: Part way to finding a vertex header, need some pointers

Oh, I see. My original script just read in the terrain vertices until it reached what might be the vertex color header.
## Post #17
- Username: St3ve
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 21, 2016 7:07 am
- Post datetime: 2017-01-30T00:41:28+00:00
- Post Title: Re: Part way to finding a vertex header, need some pointers

I took a look at the vertex clouds again, I'm starting to wonder if the reason I can't see the mechs is because the their vertex data is "off" and forming a different shape- if the header itself is read in as a float wouldn't that cause the resulting vertex coordinates to be one off, thus altering the entire pattern as the script reads in the first coordinate as the second coordinate and so on? I altered the the script to read in everything and I couldn't recognize even the level data.
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-30T01:02:51+00:00
- Post Title: Re: Part way to finding a vertex header, need some pointers

> Reply from St3ve
>
> if the header itself is read in as a float wouldn't that cause the resulting vertex coordinates to be one offwould spoil things, yes.
Just read 11 vertices per block after the 4 bytes header and you're fine.

So the vertices are not so bad (displaying 11 verts per block you can even see two steps, not on this pic, though), but autocreated face indices don't work as expected (tri stripped FIs look even worse):



autoFIs.JPG (70.52 KiB) Viewed 111 times



v -42.000000 4.000000 -30.000000 
v -42.000000 8.000000 -30.000000 
v -43.000000 4.000000 -29.000000 
v -43.000000 8.000000 -29.000000 
v -35.000000 4.000000 -29.000000 
v -35.000000 8.000000 -29.000000 
v -37.000000 4.000000 -29.000000 
v -37.000000 8.000000 -29.000000 
v -27.000000 4.000000 -29.000000 
v -27.000000 8.000000 -29.000000 
v -29.000000 4.000000 -29.000000 
#-----------------------
v -13.000000 4.000000 -29.000000 
v -13.000000 8.000000 -29.000000 
v -14.000000 4.000000 -30.000000 
v -14.000000 8.000000 -30.000000 
v -5.000000 4.000000 -29.000000 
v -5.000000 8.000000 -29.000000 
v -6.000000 4.000000 -30.000000 
v -6.000000 8.000000 -30.000000 
v 3.000000 4.000000 -29.000000 
v 3.000000 8.000000 -29.000000 
v 2.000000 4.000000 -30.000000
## Post #19
- Username: St3ve
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 21, 2016 7:07 am
- Post datetime: 2017-01-30T02:29:00+00:00
- Post Title: Re: Part way to finding a vertex header, need some pointers

Assuming my script is throwing off the mech vertices, I suppose working backwards with files or savestates is impossible and I would need to go through them by hand. I just wonder how I'll know when or if I find the mech header, the formatting must be less obvious than the terrain header or he would have found it by now.
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-30T10:31:36+00:00
- Post Title: Re: Part way to finding a vertex header, need some pointers

I'm not familiar with the PS2 savestates, what they contain exactly.
I'm surprised that they contain textures and part of a level (arena) because for PC savegames the senseful philosophy
is to save only changes of states (this is what PS2 savestates claims to be but seems it isn't?).

So I'd expect positions of mechs and characters, contents of chests, whatsoever will change in a game.

Anyways, you spoke of "parts of the mechs", where did you get them from, how do they look like?
Where do you know from that the mechs are stored in savestates?

What is the structure of PS2 archives, what do they contain?
I don't know how much you know about this (me I don't know anything, I don't have a console).

Did this unknown guy you spoke of ever extract a mech from a savestate?

btw: forget about the 11 vertices, I used the 3rd byte of the search pattern (terrain header) as a count now as suggested by you
Also for values greater than 10000.0 I set them to 1000.0

here's another point cloud, not a mech:



eeMemory-bin.jpg (155.38 KiB) Viewed 102 times


(forget about the startaddress, I used a cut part from eeMemory.bin)

Then a promissing block with assumed face indices followed but sadly it was a TIM2 data block (sky_b003).
## Post #21
- Username: St3ve
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 21, 2016 7:07 am
- Post datetime: 2017-01-30T15:16:10+00:00
- Post Title: Re: Part way to finding a vertex header, need some pointers

To my understanding, a PS2 savestate is simply a RAM dump, hence the ability to extract game assets from it. I tried switching around parts of the mechs in-game in hopes of finding different XYZ values when comparing two savestates, this did not work as I did not factor in changes to mech and inventory stats and thus thousands of differences were detected. PS2 archives differ per game but all the PS2 Front Mission entries use an unencrypted DVDIMAGE.DAT archive with a DVDIMAGE.POS file list. Micheal (the PS23Dformat guy) made it so far is unpacking the archive and finding the terrain header but hasn't found the mech header. There has to be some trace of them in the code but I just don't know how to pick up the trail.
## Post #22
- Username: St3ve
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 21, 2016 7:07 am
- Post datetime: 2017-02-02T21:03:44+00:00
- Post Title: Re: Part way to finding a vertex header, need some pointers

I've been thinking, if using a script to pull out vertices isn't working, why not pull out headers? It's probably too resource intensive but If I could put each byte into an array then loop through it while comparing entries through re.match I can see how many times said byte appears in the code. From there I can look at the less frequent bytes for variants of a one that likely involve vertices like the terrain header.
## Post #23
- Username: St3ve
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 21, 2016 7:07 am
- Post datetime: 2017-02-07T18:19:06+00:00
- Post Title: Re: Part way to finding a vertex header, need some pointers

I had this idea the other day after thinking about doing another file comparison- I'm going to write a python script that reads from either two drastically different or very similar savestates and writes the differences/shared values to a third file. Theoretically, either approach would narrow things down to just the model data and stats, at least making it easier to navigate the file. Also, I would like to thank shakotay2. I would still being staring at vertex clouds without your help.
## Post #24
- Username: St3ve
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 21, 2016 7:07 am
- Post datetime: 2017-02-10T22:11:22+00:00
- Post Title: Re: Part way to finding a vertex header, need some pointers

Made the file comparison script using 
```
b = open(r'C:\Users\Greg\Documents\Front Mission savestates\FM4 hanger one weapon.bin', 'rb')
c = open(r'C:\Users\Greg\Documents\Front Mission savestates\differences.bin', 'wb')

data1 = a.read(4)
data2 = b.read(4)

while data1 != b'' or data2 != b'':

    if data1 != data2:

        c.write(data2)

    data1 = a.read(4)
    data2 = b.read(4)

```
 and managed to create a 40 Kb file that hopefully contains a weapon, the major difference between the two savestates. I've tried getting textures out of it with TextER but it says there's nothing there which is pretty concerning. I've uploaded the file [here](https://drive.google.com/file/d/0B04lzjiwkqoEQUV5TWZ3VXVlTjQ/view?usp=sharing) since the forum doesn't take .bins.
## Post #25
- Username: St3ve
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 21, 2016 7:07 am
- Post datetime: 2017-03-04T22:07:53+00:00
- Post Title: Re: Part way to finding a vertex header, need some pointers

I managed to take a look at the differences file and found about three groups of floats capped by what might be headers.


Wrote some code.

```
import re
import bpy

coordinates = [0.0, 0.0, 0.0]
vertices = []

f = open(r'C:\Users\Greg\Documents\Front Mission savestates\differences.bin', 'rb')
data = f.read(4)

check = 4.2367777022189116e-38
check1 = 4.228643444893199e-38
check2 = 6.462348535570529e-27

while re.match(b'\x00\x80\x05\x6C', data) is None:
    data = f.read(4)

data = f.read(4)

while re.match(b'\x07\x00\x00\x50', data) is None:
    value = struct.unpack('<f', data)

    if value[0] == check or value[0] == check1 or value[0] == check2:
        value = [0.0, 1]
    coordinates[0] = value[0]

    data = f.read(4)
    value = struct.unpack('<f', data)
    if value[0] == check or value[0] == check1 or value[0] == check2:
        value = [0.0, 1]
    coordinates[1] = value[0]

    data = f.read(4)
    value = struct.unpack('<f', data)
    if value[0] == check or value[0] == check1 or value[0] == check2:
        value = [0.0, 1]
    coordinates[2] = value[0]

    vertex = (coordinates[0], coordinates[1], coordinates[2])
    vertices.append(vertex)
    print(vertex)
    data = f.read(4)

mymesh = bpy.data.meshes.new("vertices")
myobject = bpy.data.objects.new("vertices", mymesh)
bpy.context.scene.objects.link(myobject)
mymesh.from_pydata(vertices,[],[])
```


And this is the result of two of the three groups.


I have no idea what else I can do at this point. I don't understand how the terrain is so simple but the the rest of the meshes are a mystery and I'm starting to wonder if python or blender is altering the floats somehow. If anyone has ANY ideas I would love to hear them.
## Post #26
- Username: St3ve
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 21, 2016 7:07 am
- Post datetime: 2017-03-07T03:38:51+00:00
- Post Title: Re: Part way to finding a vertex header, need some pointers

Just tried my file comparison script on a savestate with a mech and one without and didn't get anything that even might have been viable. At this point, I have two theories- mech and weapon data is loaded wholesale into the memory and thus can't be splintered off with the method I'm using or I have managed to isolate the data I'm looking for, it's just not in the form of a float which is odd given terrain data is. Anyone have experience converting bytes?
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-09T15:54:00+00:00
- Post Title: Re: Part way to finding a vertex header, need some pointers

> Reply from St3ve
>
> mech and weapon data is loaded wholesale into the memory and thus can't be splintered off with the method I'm usingthis could explain it.

btw: can you apply changes to the savestates and load them successfully then?
If so you could overwrite some floats (with 00 00 00 00 or better 00 00 80 3F for example).

It's a tedious task but it should give more insight into the meaning of the changed values.
## Post #28
- Username: St3ve
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 21, 2016 7:07 am
- Post datetime: 2017-03-10T14:27:29+00:00
- Post Title: Re: Part way to finding a vertex header, need some pointers

It might be possible but at this point I'm more concerned about the floats. Is it possible for different assets to use different float types? I tried a script using doubles and got next to nothing but after months of this it seems that byte long floats akin to the terrain vertices might not be it either.
## Post #29
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-10T17:52:24+00:00
- Post Title: Re: Part way to finding a vertex header, need some pointers

> Reply from St3ve
>
> that byte long floats akin to the terrain verticesnever heard of "byte long floats".
From the point clouds I've found so far I wouldn't know why using IEEE754 floats shouldn't do the trick?

(You could try half floats or shorts, though.)
## Post #30
- Username: St3ve
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 21, 2016 7:07 am
- Post datetime: 2017-03-10T18:43:25+00:00
- Post Title: Re: Part way to finding a vertex header, need some pointers

I keep forgetting to add the 4. I haven't tried 2byte floats since struct.unpack won't accept them. I need to take a step back a learn more about mesh formatting, It could be that the vertices are somehow padded and don't directly follow each unlike the terrain, I just wish I had more examples to work with.
## Post #31
- Username: St3ve
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 21, 2016 7:07 am
- Post datetime: 2017-03-22T17:03:12+00:00
- Post Title: Re: Part way to finding a vertex header, need some pointers

I gave up and just used PCSX2ModelConverter 1.0.
