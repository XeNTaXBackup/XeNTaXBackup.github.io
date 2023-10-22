## Post #1
- Username: ayylmao
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 15, 2015 1:21 am
- Post datetime: 2015-08-06T04:52:20+00:00
- Post Title: Idolm@ster (Xbox 360) HELP

I'd like to work on translating the Xbox version of Idolm@ster using the preexisting translations from the PSP port of the game.  [I was already able to do so with a hex editor for one of the files,](https://www.youtube.com/watch?v=lOIvY1JU82s) but considering the total amount of files I would have to edit manually, accomplishing a full translation would require an unrealistically monumental amount of work since I don't have the knowledge to write an actual script editor.  So could someone help me by making one?

[Example files.](http://mfi.re/?=elnblvd2ksr4ksf)
The files provided are actually packs that contain both the script and the voice files associated with it (the .scb is the script, the .ahx are the voices files).  The file which I translated is included for reference.  [A quick bms script](http://forum.xentax.com/viewtopic.php?f=10&t=4812) to unpack them was already written 5 years ago, although there isn't any repacker.  This may not be necessary though as it's just a matter of rewriting the sizes/offsets at the top of the .bna file after editing the .scb script (the .scb is always the first file in the pack for these regular game scripts).  Editing the .scb file itself is pretty straightforward (it's basically just editing the UTF-16BE encoded null-separated strings, fixing the pointer/sizes located just above for the edited strings, and then fixing the pointers/sizes in the .scb header).  I could go into more detail if it's needed.

Thank you!
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-08-07T21:51:40+00:00
- Post Title: Idolm@ster (Xbox 360) HELP

really happy to see xenia used for testing your changes   

i'll take a look
## Post #3
- Username: ayylmao
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 15, 2015 1:21 am
- Post datetime: 2015-08-08T03:38:09+00:00
- Post Title: Idolm@ster (Xbox 360) HELP

Thanks, I really appreciate it.
## Post #4
- Username: Tokachitsukuchite
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 10, 2015 6:37 am
- Post datetime: 2015-08-09T22:41:03+00:00
- Post Title: Idolm@ster (Xbox 360) HELP

Do you have an email I could contact you at? I'd like to help you with the translation.
## Post #5
- Username: ayylmao
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 15, 2015 1:21 am
- Post datetime: 2015-08-25T19:37:11+00:00
- Post Title: Idolm@ster (Xbox 360) HELP

For the sake of transparency, here's a reconverter I wrote for the dds script found [here.](http://forum.xentax.com/viewtopic.php?f=16&t=4814) I still need help with a script editor though.

```
endian big
get size asize
math size - 0x30
putVarChr MEMORY_FILE 0x0 size long
math size - 0x50
putVarChr MEMORY_FILE 0x8 size long
goto 0x11
get width1 byte
putVarChr MEMORY_FILE 0x14 width1 byte
goto 0x10
get width2 byte
putVarChr MEMORY_FILE 0x15 width2 byte
goto 0xD
get height1 byte
putVarChr MEMORY_FILE 0x16 height1 byte
goto 0xC
get height2 byte
putVarChr MEMORY_FILE 0x17 height2 byte
goto 0x57
get type byte
if type == 0x31
putVarChr MEMORY_FILE 0x13 0x0
endif
get name filename
append
log MEMORY_FILE 0x80 SIZE
append
set count size
math count / 2
goto 0x50 MEMORY_FILE
for i = 0 < count
savepos start MEMORY_FILE
endian little
get num int MEMORY_FILE
endian big
putVarChr MEMORY_FILE start num int
next i
endian little
math size + 0x50
log name 0 size MEMORY_FILE
```
## Post #6
- Username: ayylmao
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 15, 2015 1:21 am
- Post datetime: 2015-08-30T15:14:16+00:00
- Post Title: Idolm@ster (Xbox 360) HELP

Python scripts. I guess a tl tool is just a luxury now.
Build MSG from a null-delimited, UTF-8 text file:

```
import string
import struct
import os
import codecs
import re

fileT = open(sys.argv[1], "r+b")
fileTString = str(fileT.read())
name = str(os.path.splitext(os.path.basename(fileT.name))[0])
extension = '.msg'
msgName = "".join((name, extension))
print(msgName)
msgFile = open(msgName, "w+b")
msgFile.write("\x4d\x53\x47\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x45\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x3A\x00\x00\x00\x00\x0A\xEC\x00\x10\x01\xE0\x00\x00\x00\x00")
utf16Text = fileTString.decode('utf-8-sig').encode('utf-16be')
sizeText = str(struct.pack('>L', len(utf16Text)))
msgFile.seek(36, 0)
msgFile.write(sizeText)
msgFile.seek(0, 2)
print(msgFile.tell())
textPointer = int(0)
lineAmount = int(0)
print(textPointer)
textSize = int(len(utf16Text))
print(textSize)
for line in re.split('\0', utf16Text.decode('utf-16be')):
	line = line.encode('utf-16be')
	withNulls = int(len(line)) + 2
	msgFile.write(str(struct.pack('>L', withNulls)))
	msgFile.write(str(struct.pack('>L', textPointer)))
	textPointer += withNulls
	lineAmount += 1
	textSize -= withNulls
	if textSize <= int(0):
		break
msgFile.seek(32, 0)
msgFile.write(str(struct.pack('>H', lineAmount)))
lineAmount *= int(8)
checkFiller = int(lineAmount)
checkFiller %= int(16)
msgFile.seek(0, 2)
if checkFiller != int(0):
	msgFile.write("\xCD\xCD\xCD\xCD\xCD\xCD\xCD\xCD")
	lineAmount += int(8)
lineAmount += int(16)
totalSize = int(lineAmount)
totalSize += int(len(utf16Text))
msgFile.seek(42, 0)
msgFile.write(str(struct.pack('>H', lineAmount)))
msgFile.seek(16, 0)
msgFile.write(str(struct.pack('>L', totalSize)))
totalSize += int(32)
msgFile.seek(0, 2)
msgFile.write(utf16Text)
```


Insert MSG into .SCB:

```
import string
import struct
import os

fileD = open(sys.argv[1], "r+b")
fileP = open(sys.argv[2], "r+b")
filePString = str(fileP.read())
fileDString = str(fileD.read())
fileP.seek(0, 2)
endP = str(struct.pack('>L', int(fileP.tell())))
fileP.write(fileDString)
fileP.seek(148,0)
totalSize = int(len(fileDString))
fileP.write(str(struct.pack('>L', totalSize)))
fileP.write(endP)
```


Add file to .BNA:

```
import string
import struct
import os

fileT = open(sys.argv[1], "r+b")
fileP = open(sys.argv[2], "r+b")
filePString = str(fileP.read())
fileTString = str(fileT.read())
name = str(os.path.basename(fileT.name))
size = str(struct.pack('>L', len(fileTString)))
packedOffset = str(struct.pack('>L', int(filePString.find(name))))
offsetOffset = filePString.find(packedOffset)
fileP.seek(0, 2)
endP = str(struct.pack('>L', int(fileP.tell())))
fileP.write(fileTString)
fileP.seek(offsetOffset)
fileP.seek(4, 1)
fileP.write(endP)
fileP.write(size)
fileT.close()
fileP.close()
```
