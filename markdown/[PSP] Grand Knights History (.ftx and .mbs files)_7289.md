## Post #1
- Username: Gyoru
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 04, 2011 2:40 am
- Post datetime: 2011-09-03T18:58:44+00:00
- Post Title: [PSP] Grand Knights History (*.ftx and *.mbs files)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: kenn
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Mar 23, 2010 12:59 am
- Post datetime: 2011-09-04T02:25:21+00:00
- Post Title: [PSP] Grand Knights History (*.ftx and *.mbs files)

Did you use cpk.bms to extract the content of the cpk file?
Or you code something out.. goodjob anyway 

because this is my topic asking for the new script..
I'm just curious about the models of that game
[viewtopic.php?f=10&t=7277](http://forum.xentax.com/viewtopic.php?f=10&t=7277)
## Post #3
- Username: pasta
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 06, 2011 4:47 am
- Post datetime: 2011-09-05T20:50:46+00:00
- Post Title: [PSP] Grand Knights History (*.ftx and *.mbs files)

save this code as dumpftx.py and run:

```
"""ftx format:
    magic,'FTEX'
    4 bytes le, filesize related value
    4 bytes le, ?
    4 bytes le, count of contained files
    16 bytes, padding 0x00
    contained files information parts, 48 bytes * n:
        36 byte, filename (utf-8?)
        4 bytes le, filesize
        8 bytes, unknown
    16 * n byte, padding for 64 bytes alignment
    contained files parts:
        magic, 'FTX0'
        4 bytes le, size of contained file related value
        56 bytes, unknown (first byte is 0x40, flag?)
        filedata
        48 bytes, padding (alignment?)
"""
from __future__ import print_function
import sys, os, subprocess, struct

for inputfile in sys.argv[1:]:
    with open(inputfile, 'rb') as input:
        if input.read(4) != 'FTEX':
            print('%s is not .ftx file.' % input.name, file=sys.stderr)
            continue
        input.read(4)
        input.read(4)
        count = struct.unpack('<L', input.read(4))[0]
        input.read(16)

        fileinfos = []
        for i in range(count):
            filename = input.read(36).rstrip('\0')
            filesize = struct.unpack('<L', input.read(4))[0]
            input.read(8)
            fileinfos.append((filename, filesize, ))

        if input.tell() % 0x40:
            input.read(0x40 - input.tell() % 0x40)

        for filename, filesize in fileinfos:
            input.read(64)
            filename = os.path.join(os.path.dirname(input.name), filename)
            with open(filename, 'wb') as output:
                output.write(input.read(filesize))
            if os.path.splitext(filename)[1].lower() == '.gim':
                try:
                    subprocess.call(['gim2png', filename])
                except Exception:
                    pass
                else:
                    os.remove(filename)
            input.read(48)



```
## Post #4
- Username: pasta
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 06, 2011 4:47 am
- Post datetime: 2011-09-05T21:03:36+00:00
- Post Title: [PSP] Grand Knights History (*.ftx and *.mbs files)

and you can extract .wav files (encoded by atrac3) from *.awb and *.acb files.
save this code as dumpriff.py:

```
import sys, os
from cStringIO import StringIO

magic = 'RIFF'

for i in sys.argv[1:]:
    basename, _ = os.path.splitext(i)
    with open(i, 'rb') as input:
        output = StringIO() # null writer
        count = 1
        for chunk in iter(lambda: input.read(4096), ''):
            if magic in chunk:
                index = chunk.index(magic)
                output.write(chunk[:index])
                output = open('%s-%.3d.wav' % (basename, count), 'wb')
                count += 1
                chunk = chunk[index:]
            output.write(chunk)


```
## Post #5
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-09-07T07:47:51+00:00
- Post Title: [PSP] Grand Knights History (*.ftx and *.mbs files)

You could use a Noesis script to just load the textures directly into the texture list, which makes them exportable to any of the supported formats and has no external dependencies.

```
def registerNoesisTypes():
	handle = noesis.register("FTX Texture Bundle", ".ftx")
	noesis.setHandlerTypeCheck(handle, ftxCheckType)
	noesis.setHandlerLoadModel(handle, ftxLoad)
	return 1

class FtxFile:
	def __init__(self, bs):
		self.bs = bs
	def loadImageInfo(self):
		if self.bs.dataSize < 32:
			return 0
		self.texInfos = []
		hdrInfo = noeUnpack("<iiii", self.bs.readBytes(32)[:16])
		if hdrInfo[0] != 0x58455446 or hdrInfo[3] <= 0 or 32+hdrInfo[3]*48+32+4 >= self.bs.dataSize:
			return 0
		for i in range(0, hdrInfo[3]):
			self.texInfos.append( (noeStrFromBytes(self.bs.readBytes(32)), self.bs.readBytes(16)) )
		self.bs.seek(32, NOESEEK_REL)
		return 1
	def loadImages(self, texList = []):
		for texInfo in self.texInfos:
			texHdr = noeUnpack("<iii", self.bs.readBytes(12))
			self.bs.seek(texHdr[2]-12, NOESEEK_REL)
			tex = rapi.loadTexByHandler(self.bs.readBytes(texHdr[1]), ".gim")
			tex.name = texInfo[0]
			texList.append(tex)
		return texList

def ftxCheckType(data):
	ftx = FtxFile(NoeBitStream(data))
	if ftx.loadImageInfo() == 0:
		return 0
	return 1
def ftxLoad(data, mdlList):
	ftx = FtxFile(NoeBitStream(data))
	if ftx.loadImageInfo() == 0:
		return 0
	mdlList.append(NoeModel([], [], [], NoeModelMaterials(ftx.loadImages(), [])))
	return 1

```

(or whatever, only tested with the uploaded sample, version 3.55 or later required)
## Post #6
- Username: LordSith
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 16, 2012 2:55 am
- Post datetime: 2012-05-31T14:41:30+00:00
- Post Title: [PSP] Grand Knights History (*.ftx and *.mbs files)

> Reply from pasta
>
> save this code as dumpftx.py and run:
Code: Select all#!/usr/bin/env python2
"""ftx format:
    magic,'FTEX'
    4 bytes le, filesize related value
    4 bytes le, ?
    4 bytes le, count of contained files
    16 bytes, padding 0x00
    contained files information parts, 48 bytes * n:
        36 byte, filename (utf-8?)
        4 bytes le, filesize
        8 bytes, unknown
    16 * n byte, padding for 64 bytes alignment
    contained files parts:
        magic, 'FTX0'
        4 bytes le, size of contained file related value
        56 bytes, unknown (first byte is 0x40, flag?)
        filedata
        48 bytes, padding (alignment?)
"""
from __future__ import print_function
import sys, os, subprocess, struct

for inputfile in sys.argv[1:]:
    with open(inputfile, 'rb') as input:
        if input.read(4) != 'FTEX':
            print('%s is not .ftx file.' % input.name, file=sys.stderr)
            continue
        input.read(4)
        input.read(4)
        count = struct.unpack('<L', input.read(4))[0]
        input.read(16)

        fileinfos = []
        for i in range(count):
            filename = input.read(36).rstrip('\0')
            filesize = struct.unpack('<L', input.read(4))[0]
            input.read(8)
            fileinfos.append((filename, filesize, ))

        if input.tell() % 0x40:
            input.read(0x40 - input.tell() % 0x40)

        for filename, filesize in fileinfos:
            input.read(64)
            filename = os.path.join(os.path.dirname(input.name), filename)
            with open(filename, 'wb') as output:
                output.write(input.read(filesize))
            if os.path.splitext(filename)[1].lower() == '.gim':
                try:
                    subprocess.call(['gim2png', filename])
                except Exception:
                    pass
                else:
                    os.remove(filename)
            input.read(48)

I have done everything here with neoesis 3.866 and it always game an error on line 40 and line 26
ftxLoad
   mdlList.append(NoeModel([],[],[]
NeoModelMaterials(ftxloadImages(),[])))

I don't know what to do with that any help would be apreciated.. thanks in advance
## Post #7
- Username: curlyfriesonionrings
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 05, 2012 9:51 pm
- Post datetime: 2012-06-08T14:05:58+00:00
- Post Title: [PSP] Grand Knights History (*.ftx and *.mbs files)

You're quoting pasta's Python script but talking about Noesis errors...

I haven't tried the Neosis script, so I can't help you there. Have you tried pasta's Python dumpftx script? It works well for me. If you don't have gim2png in the same directory as the Python script, it will dump the .gim files contained in the .ftx.
