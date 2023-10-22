## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-21T15:21:59+00:00
- Post Title: Silkroadonline bms

I found fatduck's post about the file format and it looked pretty simple so I decided to write a converter. Or at least try. Going through chrrox's tutorial on reading the format outline and looking at some blender scripts from Szkaradek123 gave me an idea how to write it.

But going through the file, it seems like there are some differences here and there (and I've noticed the extractor I used extracted too much data, so I don't know if the files I have are even correct).

Here's fatduck's post: [http://gameresearch.5d6d.com/archiver/tid-156.html](http://gameresearch.5d6d.com/archiver/tid-156.html)

Does anyone have an importer that works for them? Just so I know that the files I have are wrong lol

Here are some files. You can tell a lot of them are wrong just by going to the bottom of the file and noticing that a a couple dozen bytes from the next file is appended to it (is clear from the header and strings). Maybe it just means there's more data than necessary, so that shouldn't be a problem if I'm following the format correctly.

It's possible that the converters I found work, except corrupt files cause them to fail.

This is what I did in python so far up to and including vertices. I'm not sure if I am reading what fatduck posted correctly

```
if version == "0110":
	
	vertArray = []
	normArray = []
	uvArray = []
	
	#file starts at 0x48      
	bmsFile.seek(0x48)
	
	#get mesh group
	charCount = unpack('<l', bmsFile.read(LONGSIZE))[0]
	meshGroup =  unpack('<%ds' %charCount, bmsFile.read(charCount))[0]
	
	#get material library
	charCount = unpack('<l', bmsFile.read(LONGSIZE))[0]
	matLib =  unpack('<%ds' %charCount, bmsFile.read(charCount))[0]
	
	#unknown int
	unkInt = unpack('<l', bmsFile.read(LONGSIZE))[0]
	
	vertCount = unpack('<l', bmsFile.read(LONGSIZE))[0]
	print "%d vertices" %vertCount
	
	for i in range(0, vertCount):
		 #get vert coords
		 verts = bmsFile.read(3*FLOATSIZE)
		 vx, vy, vz = unpack('<3f', verts)

		 #get normals
		 norms = bmsFile.read(3*FLOATSIZE)
		 nx, ny, nz = unpack('<3f', norms)
		 
		 #get tex coords
		 tex = bmsFile.read(2*FLOATSIZE)
		 tu, tv = unpack('<2f', tex)
		 
		 #ignore 12 bytes
		 bmsFile.read(12)
```

[Silkroad.7z](https://xentaxbackup.github.io/file/4370_Silkroad.7z)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-22T13:09:51+00:00
- Post Title: Silkroadonline bms

nvm, got a different extractor and the output looks fine now.
## Post #3
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-06-22T16:58:18+00:00
- Post Title: Silkroadonline bms

Please continue your work on importer and show result.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-22T18:02:39+00:00
- Post Title: Silkroadonline bms

Unfortunately, it's not a blender importer.
It is for my own set of data structures that I use for batch converting between formats (currently only exports in mqo and obj since those are easy to do).

It would probably be better to just learn blender, but I don't know if blender has batch conversion functionality which is all that I'm interested in.

It doesn't seem like I'm parsing vertices correctly since I'm getting nan's.

Maybe the format has changed, or maybe it is only for certain files.
For example the one I attach, there are 8 vertices, and there seems to be a string of 00 00 00 00 FF FF FF FF 00 00 00 00 after every 32 bytes, so I'm guessing there's 12 bytes of padding after each float, but if I say that then there are only 8 floats o.O

Weird...
[cj_thiefvill_right_14.rar](https://xentaxbackup.github.io/file/4369_cj_thiefvill_right_14.rar)
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-22T22:20:41+00:00
- Post Title: Silkroadonline bms

I've updated the first post with correct files (well, more correct than what it was before).
I've also included a variety of models, from characters to items to map assets.

The vertex structure seems a little weird cause I'm getting a lot of nan's here and there.

This is the part that does it:

```
vertCount = unpack('<l', self.inFile.read(LONGSIZE))[0]
for i in range(0, vertCount):
            
            #get vert coords
            verts = self.inFile.read(3*FLOATSIZE)
            vx, vy, vz = unpack('<3f', self.inFile.read(3*FLOATSIZE))
            
            print vx, vy, vz
            
            #get normals
            nx, ny, nz = unpack('<3f', self.inFile.read(3*FLOATSIZE))
            #get tex coords
            tu, tv = unpack('<2f', self.inFile.read(2*FLOATSIZE))

            self.inFile.read(12)

```


If I am following the format correctly, perhaps there's some extra things here and there to look out for.



I underlined some strings of 00's and FF's. They appear after every 32 bytes, which I assume is a float.
This continues until the boneCount offset. Could these be part of a float (I have no clue)

EDIT: I highlighted an extra 00 at the beginning.
## Post #6
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-06-23T10:52:54+00:00
- Post Title: Silkroadonline bms

Finale00 mayby help you this.
Please check vertsize for some files("pha_hano_brick.bms" has 52 bytes, "blade_09.bms" has 44 bytes).
[import-silkroad-2011-06-22.zip](https://xentaxbackup.github.io/file/4371_import-silkroad-2011-06-22.zip)
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-23T12:46:47+00:00
- Post Title: Silkroadonline bms

oh, didn't even notice there was difference in vertsize!
Now I am not getting any nan's for the vertices:

 

I also just realize I confuse myself and thought that float is 32-bytes instead of 32-bits  



yay  

All models use the same format. Maybe have different vert-size somewhere, but the two cases you have pointed out are what I have come across so far.
