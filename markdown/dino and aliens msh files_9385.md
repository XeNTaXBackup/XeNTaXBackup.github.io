## Post #1
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-08-01T11:32:52+00:00
- Post Title: dino and aliens msh files

hello all
I would like to write a script for blender to import msh files, but I do not know what I'm doing wrong
because i get the error and don't know how to solve it
subject i write here because in 3d/2d models section no one write off, but please for the transfer
if anyone needs sample files please on pw
## Post #2
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-08-02T12:12:12+00:00
- Post Title: dino and aliens msh files

does anyone me answer?
please

who knows something about 3d models and scripts?
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-08-02T12:37:50+00:00
- Post Title: dino and aliens msh files

there's only like one person on here who writes blender scripts to rip games... some polish guy that we rarely see around anymore...

so there's limited help around here when it comes to blender scripts.
## Post #4
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-08-02T15:47:49+00:00
- Post Title: dino and aliens msh files

injury
maybe someone else will know?
here is link to demo:
[http://www.gamershell.com/download_27844.shtml](http://www.gamershell.com/download_27844.shtml)
here is script for quickbms to dat files:

```
# script for QuickBMS http://quickbms.aluigi.org

get FULLSIZE asize
for OFFSET = 0 < FULLSIZE
    get NAME string
    get SIZE long
    savepos OFFSET
    encryption xor NAME
    log NAME OFFSET SIZE
    math OFFSET += SIZE
    goto OFFSET
next
```


in demo version msh files are the same like in full version
## Post #5
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-08-25T16:18:53+00:00
- Post Title: dino and aliens msh files

maybe this someone will be interested

```
""" 
Name: 'Dino and Aliens (.msh)...'
Blender: 249
Group: 'Import'
"""
__author= "Boguslaw Radomski"
__version__= "0.01"

__bpydoc__ = """\
Dino and Aliens msh importer by Boguslaw Radomski
This script imports a Dino and Aliens msh files to Blender.
Note, This loads mesh objects only, materials and animations are not supported yet.
I do not know how to read material from a file and add support to Blender.
"""

# ***** GPL LICENSE *****
#
# This program is free software; you can redistribute it and/or
# modify it under the terms of the GNU General Public License
# as published by the Free Software Foundation; either version 2
# of the License, or (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software Foundation,
#
# --------------------------------------------------------------------------

# importing modules
import Blender
import struct

# imports a msh file to the current scene
def load_msh(filename):
	# get scene
	scn = Blender.Scene.GetCurrent()
	if scn == None:
		return "No scene to import to!"

	Blender.Window.WaitCursor(1)

	# open the file
	file = open(filename, 'rb')

	# read id to check if the file is a dino and aliens msh file
	id = file.read(3)
	if id != 'MSH':
		print 'this is not MSH file'
		return

	file.seek(29,0)

	# Create the mesh
	scn.objects.selected = []
	mesh = Blender.Mesh.New("name")
	meshOb = scn.objects.new(mesh)

	# read the number of vertices
	numVerts = struct.unpack('L', file.read(4))[0]

	# read number of triangles
	numTriangles = struct.unpack('L', file.read(4))[0]

	# read vertices
	verts = []
	for i in xrange(numVerts):
		verts.append(struct.unpack('fff', file.read(3*4)))

	# add the vertices to the mesh
	mesh.verts.extend(verts)

	# read triangles
	faces = []
	for i in xrange(numTriangles):
		# read indices (faces)
		faces.append(struct.unpack('iii', file.read(3*4)))

	# add the faces to the mesh
	mesh.faces.extend(faces)

	Blender.Window.WaitCursor(0)

	# refresh the view
	Blender.Redraw()

	# close the file
	file.close()

Blender.Window.FileSelector(load_msh, 'import msh', '*.msh')
```


i do not know only how to read materials and animation from files, because never before have not done thereof
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-25T20:37:10+00:00
- Post Title: dino and aliens msh files

No animations, still good. I think a lot of people don't really care for animations either.
## Post #7
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-08-26T05:57:17+00:00
- Post Title: dino and aliens msh files

has anyone some idea, what they mean the next values?
i do not know how to read
animation files are in .anm files
as someone wants a sample file please on pw
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-08-26T11:13:57+00:00
- Post Title: dino and aliens msh files

> Reply from Bogus
>
> has anyone some idea, what they mean the next values?
i do not know how to readnext values in which file; .msh or .anm?

I had a look at teleport_base.msh; it contains 210 faces (triangles).
Although the UV is looking like a horse-shoe you should find
the first texture set at
#   0xfa9
vt 0.979252 0.499962
vt 0.901447 0.585763
...
vt 0.910417 0.499962
vt 0.705208 0.857351
vt 0.674772 0.804343

The next 210 x 8 bytes don't look like an UV map when displaying them in  the UV editor.
#   0x1639
#vt 0.608015 0.834229
#vt 0.674772 0.804343
...

edit: hmm, teleport_screen.jpg does not really fit.
edit2: taking only the uneven (or even) vt-lines the UV map looks better (left of pic).
But it should look like the one on right side.
[](http://www.pic-upload.de/view-15770406/teleport_UV.jpg.html)

Maybe someones sees what-they-have-done-to the tex coords?

> animation files are in .anm filesFor a basic understanding of animation data
a look at [viewtopic.php?f=29&p=76831#p76831](http://forum.xentax.com/viewtopic.php?f=29&p=76831#p76831) might be helpful.

As for concret data like vilka_shock.anm I did not find a pattern.
It starts with 0x26 00 00 00 (=38, which should be the frame count).
The data following at 0x000C should all be floats:

```
 0.000000 -0.000000 3.710460
 0.000000 -0.000000 3.627165
 0.000000 -0.000000 3.700048
 0.000000 -0.000000 3.823235

 -0.000055 0.104600 -0.000281
 -0.000030 0.105238 -0.000120
 0.000020 0.106515 0.000201
 0.000059 0.107473 0.000442
 0.000046 0.107154 0.000362

 -0.104600 -0.000026 1.571075
 -0.105238 -0.000018 1.570916
 -0.106515 -0.000001 1.570596
 -0.107473 0.000011 1.570357
 -0.107154 0.000007 1.570437

 3.141592 -1.570253 1.570804
 3.141583 -1.570249 1.570804
 3.141592 -1.570240 1.570786
 -3.141589 -1.570233 1.570804
 3.141581 -1.570235 1.570804
...

```

Too much zeroes in there. (But considering something like 28 91 5A 30 as DWORD does not help.)
00 00 00  3E is 0.125 as a float - so everything "below" 00 00 00 38 will be displayed as 0.0.

Frame time values like 0.04, 0.08 for example can't be found.

Don't know; you'll have to figure it out for yourself.
## Post #9
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2012-08-26T16:44:18+00:00
- Post Title: dino and aliens msh files

> Reply from shakotay2
>
> Maybe someones sees what-they-have-done-to the tex coords ?

The answer is very simple.
The .msh file uses the UV/Face datas, so every faces have 3*2 floats as UV.
[teleport.jpg](https://xentaxbackup.github.io/file/5711_teleport.jpg)
## Post #10
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-08-26T17:12:56+00:00
- Post Title: dino and aliens msh files

thanks Karpati
at least i know
where did you get this version 3d object converter?
because there is no to download
besides .msh files are yet .cgo files
i do not know are it appeal to textures?
edit:
i mean the file box.msh, what is on position 0x115 after faces
because with this file i had easily
i know, that cube, box has 8 vertices
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-26T21:19:35+00:00
- Post Title: dino and aliens msh files

He is the developer of the program lol
## Post #12
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-08-27T05:41:06+00:00
- Post Title: dino and aliens msh files

ok
i didn't know even
but what i can I do that use it in blender?
3d object converter is payable, for free one can only watch models and convert to some formats
edit:
i mean this
[http://desmond.imageshack.us/Himg827/sc ... es=landing](http://desmond.imageshack.us/Himg827/scaled.php?server=827&filename=boxpk.png&res=landing)
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-08-27T09:57:17+00:00
- Post Title: dino and aliens msh files

Karpati already gave the answer, didn't he?
Thx to Karpati.  

There are 36 (12*3) tex coords lines with 2 floats each.

So the box faces look like this:

f 3/1 1/2 4/3 
f 2/4 4/5 1/6 
f 6/7 5/8 8/9 
f 7/10 8/11 5/12 
f 2/13 1/14 6/15 
f 5/16 6/17 1/18 
f 4/19 2/20 8/21 
f 6/22 8/23 2/24 
f 3/25 4/26 7/27 
f 8/28 7/29 4/30 
f 1/31 3/32 5/33 
f 7/34 5/35 3/36 

Means the tex coords indices are counted up from 1 to 36.
## Post #14
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-08-27T10:24:12+00:00
- Post Title: dino and aliens msh files

ok thanks
now I was left with just add it to script although will be me a little hard
surely need will to add yet loop
edit:
shakotay2 can you give me a script in which the grid is displayed in the UV editor?
please
I'm trying go further with the script, but i have problem, appears the error:
index out of range
and i do not know what further to do
## Post #15
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-08-29T07:32:42+00:00
- Post Title: dino and aliens msh files

help me someone?
please
how should peek out script for uv mapping?
because i do not know how
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-29T07:57:28+00:00
- Post Title: Re: dino and aliens msh files

Just print out the index you're trying to get and the size of your list...
Maybe you're just parsing the file wrong.
## Post #17
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-08-29T10:47:41+00:00
- Post Title: Re: dino and aliens msh files

this how shakotay2 imported texture coordinates?

for ms3d files is yes:

```
	faces = []
	uvs = []
	for i in xrange(numTriangles):
		# skip flags
		file.read(2)

		# read indices (faces)
		faces.append(struct.unpack("HHH", file.read(3*2)))

		# read normals
		normals = struct.unpack("fffffffff", file.read(3*3*4))

		# read texture coordinates
		s = struct.unpack("fff", file.read(3*4))
		t = struct.unpack("fff", file.read(3*4))

		# store texture coordinates
		uvs.append([[s[0], 1-t[0]], [s[1], 1-t[1]], [s[2], 1-t[2]]])
		
		if faces[-1][2] == 0: # Cant have zero at the third index
			faces[-1] = faces[-1][1], faces[-1][2], faces[-1][0]
			uvs[-1] = uvs[-1][1], uvs[-1][2], uvs[-1][0]
		
		# skip smooth group
		file.read(1)

		# skip group
		file.read(1)

	# add the faces to the mesh
	mesh.faces.extend(faces)

	# set texture coordinates
	for i in xrange(numTriangles):
		mesh.faces[i].uv = [Vector(uvs[i][0]), Vector(uvs[i][1]), Vector(uvs[i][2])]
```


as it will be for .msh files?
just do not know how to write it in a script
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-08-30T08:33:27+00:00
- Post Title: Re: dino and aliens msh files

1) did you integrate some debugging lines into your script like recommended by finale00?

2) I'm not very familiar with python script but I made some changes to your script
(including some "print" commands for a debug output to the blender console).

Tested box.msh: 4 of the 6 textured sides of the cube are ok, two  are not.

Don't have more time to solve this but I think you should do it.  

```
"""
Name: 'Dino and Aliens2 (.msh)...'
Blender: 249
Group: 'Import'
"""
__author= "Boguslaw Radomski"
__version__= "0.01"

__bpydoc__ = """\
Dino and Aliens msh importer by Boguslaw Radomski
This script imports a Dino and Aliens msh files to Blender.
Note, This loads mesh objects only, materials and animations are not supported yet.
I do not know how to read material from a file and add support to Blender.
"""

# ***** GPL LICENSE *****
#
# This program is free software; you can redistribute it and/or
# modify it under the terms of the GNU General Public License
# as published by the Free Software Foundation; either version 2
# of the License, or (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software Foundation,
#
# --------------------------------------------------------------------------

# importing modules
import Blender
import struct
from Blender.Mathutils import Vector

# imports a msh file to the current scene
def load_msh(filename):
   # get scene
   scn = Blender.Scene.GetCurrent()
   if scn == None:
      return "No scene to import to!"

   Blender.Window.WaitCursor(1)

   # open the file
   file = open(filename, 'rb')

   # read id to check if the file is a dino and aliens msh file
   id = file.read(3)
   if id != 'MSH':
      print 'this is not MSH file'
      return

   file.seek(29,0)

   # Create the mesh
   scn.objects.selected = []
   mesh = Blender.Mesh.New("name")
   meshOb = scn.objects.new(mesh)

   # read the number of vertices
   numVerts = struct.unpack('L', file.read(4))[0]

   # read number of triangles
   numTriangles = struct.unpack('L', file.read(4))[0]

   # read vertices
   verts = []
   for i in xrange(numVerts):
      verts.append(struct.unpack('fff', file.read(3*4)))

   # add the vertices to the mesh
   mesh.verts.extend(verts)

   # read triangles
   faces = []
   for i in xrange(numTriangles):
      # read indices (faces)
      faces.append(struct.unpack('iii', file.read(3*4)))

   # add the faces to the mesh
   mesh.faces.extend(faces)

   #--- shakotay2 start ----------------------------

   uvs = []
   # read texture coordinates
   for i in xrange(numTriangles):
     s = struct.unpack("ff", file.read(2*4))
     t = struct.unpack("ff", file.read(2*4))
     u = struct.unpack("ff", file.read(2*4))
     print s
     print t
     print u
     print '\n'

     # store texture coordinates
     uvs.append([[s[0], s[1]], [t[0], t[1]], [u[0], u[1]]])
      
   # set texture coordinates
   for i in xrange(numTriangles):
      mesh.faces[i].uv = [Vector(uvs[i][0]), Vector(uvs[i][1]), Vector(uvs[i][2])]
      print i
      print Vector(uvs[i][0])
      print Vector(uvs[i][1])
      print Vector(uvs[i][2])
      print '\n'

   #--- shakotay2 end ---------------------------------

   Blender.Window.WaitCursor(0)

   # refresh the view
   Blender.Redraw()

   # close the file
   file.close()

Blender.Window.FileSelector(load_msh, 'import msh', '*.msh')


```
## Post #19
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-08-30T10:01:34+00:00
- Post Title: Re: dino and aliens msh files

thanks it works
can in this way i will be know how to do
animation can for the time being leave
but  topic yet not closed
## Post #20
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-09-01T05:29:37+00:00
- Post Title: Re: dino and aliens msh files

whether this possible that at the beginning msh files is bone?
because i know that fruits rotate
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-09-01T08:39:13+00:00
- Post Title: Re: dino and aliens msh files

> Reply from Bogus
>
> whether this possible that at the beginning msh files is bone?I don't think so;
could you please give an example?

You can find strings like "Bip01", "Spine", "L ForeArm", "R Foot" etc. in the *.skl files.
## Post #22
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-09-01T10:00:45+00:00
- Post Title: Re: dino and aliens msh files

ananas.msh, yabloko_0,25.msh, yabloko_0,5.msh and yabloko_1.msh
the characters are also animated, but are in skl files
i do not know where they are vertices and faces a little i was looking for
script can alone write
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-09-01T10:41:04+00:00
- Post Title: Re: dino and aliens msh files

The structure of ananas.msh looks like this:

# 120 vertices
# 1.      0x25:
v 0.353530 0.739885 2.152248
v 0.641311 0.889165 3.350888
v 1.046994 0.941949 4.351346
...
v -1.456776 0.804483 -3.482513
v -0.897434 1.574350 -3.482513
v 0.007599 1.868413 -3.482513
v 0.007599 0.328678 -3.888980

# 591 face Indices (197 faces)
# 2.     0x5c5:
f 48 57 56 
f 58 57 49 
f 49 59 58 
...
f 80 81 95
f 97 90 82 
f 81 82 90 
# (vertex related) face index min/max: 1 / 120
# texture related face indices: 1..591 (not in the file)

# Texture coords
# 0xf01
vt 0.676453 0.304822
vt 0.469777 0.162897
vt 0.677072 0.072721
...
vt 0.620055 0.368678
vt 0.452570 0.264222
vt 0.676453 0.304822

# last address= 0x2178

File size is 0x2179;
so no animation/skinning related data in there.

Same with yabloko_1.msh.

The fruits are rotating only?
This doesn't require an animation file; perhaps they're just changing 
the angle of the fruits via its rotation matrix .
## Post #24
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-09-01T11:01:26+00:00
- Post Title: Re: dino and aliens msh files

this how it is that oneself rotate?
this i know because alone I started to write the script
I'm talking about this this what marked:
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-09-01T11:16:09+00:00
- Post Title: Re: dino and aliens msh files

There is only one way to prove this: you'll have to change some bytes (the 0x80 for example)
and look whether the rotation of the corresponding fruits slows down or accelerates.

(I would be surprised - but you know: "you never know..."  )

And you'll have to repack the *.msh to a *.dat file again,  I think.

(Didn't try this so far; so don't know whether it works.)
## Post #26
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-09-01T11:40:49+00:00
- Post Title: Re: dino and aliens msh files

quite nice joke
i do not know whether in this way not spoil the game
edit:
I think nothing has changed at the same speed of a rotate
