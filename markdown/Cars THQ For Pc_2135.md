## Post #1
- Username: amira
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 07, 2006 1:03 pm
- Post datetime: 2006-10-08T04:28:13+00:00
- Post Title: Cars THQ For Pc

I need to unpak/pak .pak archives from The Cars THQ For Pc
Audio.PAK
Global.PAK
Act.PAK
[http://www.carsvideogame.com/](http://www.carsvideogame.com/)
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-08T06:53:04+00:00
- Post Title: Cars THQ For Pc

Please provide us with examples of those pak archives or a direct link to a demo.
## Post #3
- Username: amira
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 07, 2006 1:03 pm
- Post datetime: 2006-10-08T15:03:03+00:00
- Post Title: Cars THQ For Pc

> Reply from amira
>
> I need to unpak/pak .pak archives from The Cars THQ For Pc
misc.PAK
res.PAK
Audio.PAK
Global.PAK
Act.PAK
http://www.carsvideogame.com/
[http://amirachat.ifrance.com/misc.PAK](http://amirachat.ifrance.com/misc.PAK)
[http://amirachat.ifrance.com/res.PAK](http://amirachat.ifrance.com/res.PAK)
## Post #4
- Username: szevvy
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Sep 21, 2006 2:20 pm
- Post datetime: 2006-10-08T15:21:31+00:00
- Post Title: Cars THQ For Pc

```

	fileCount lots of (
		char filename[100]
		unsigned32 offset_from_end_of_header
      #actual offset is (fileCount * 108) + 4 + offset_from_end_of_header
		unsigned32 size
	)

```


Sadly, I don't know BMS but I'm sure someone here can convert it over.
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-08T17:35:38+00:00
- Post Title: Cars THQ For Pc

```
# By Mr.Mouse (thanks Szevvy)
# The format is very simple.
# ------------
# // Header
# UINT32 Number of resources
# // For each resource
# byte[100] Resource name (null-terminated, but 100 bytes reserved)
# unint32 Relative offset (minus the size of the info table + header)
# unint32 Size 
# ------------
ImpType Standard ;
Get FNum Long 0 ;
# Calculate offset of file data (RO)
Set RO Long 108 ;
Math RO *= FNum ;
Math RO += 4 ;
For T = 1 To FNum ;
GetDString FN 100 0 ;
Get FO Long 0 ;
Get FS Long 0 ;
Log FN RO FS 0 0 ;
Math RO += FS ;
Next T ;

```

[http://wiki.xentax.com/index.php/The_Cars_THQ_RES](http://wiki.xentax.com/index.php/The_Cars_THQ_RES) 

The script will extract files from the res archives only. Start up MexCom 4.3 and use the wiki for source of scripts. Then open those res files !

If it works, don't forget to VOTE for it in the Supported Games list! It's now an unofficial script, when it gets 5 votes it will become official.
## Post #6
- Username: szevvy
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Sep 21, 2006 2:20 pm
- Post datetime: 2006-10-09T13:51:29+00:00
- Post Title: Cars THQ For Pc

I hate to be a pest, and I'm grateful you guys credit people who help out - but it's spelt 'szevvy'
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-09T13:54:34+00:00
- Post Title: Cars THQ For Pc

> Reply from szevvy
>
> I hate to be a pest, and I'm grateful you guys credit people who help out - but it's spelt 'szevvy' 

Sorry, must have been blind, or drunk , or both ! Fixed !
## Post #8
- Username: amira
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 07, 2006 1:03 pm
- Post datetime: 2006-10-09T18:29:27+00:00
- Post Title: Cars THQ For Pc

> Reply from Mr.Mouse
>
> Code: Select all# The Cars THG .PAK format MexScript
# By Mr.Mouse (thanks Szevvy)
# The format is very simple.
# ------------
# // Header
# UINT32 Number of resources
# // For each resource
# byte[100] Resource name (null-terminated, but 100 bytes reserved)
# unint32 Relative offset (minus the size of the info table + header)
# unint32 Size 
# ------------
ImpType Standard ;
Get FNum Long 0 ;
# Calculate offset of file data (RO)
Set RO Long 108 ;
Math RO *= FNum ;
Math RO += 4 ;
For T = 1 To FNum ;
GetDString FN 100 0 ;
Get FO Long 0 ;
Get FS Long 0 ;
Log FN RO FS 0 0 ;
Math RO += FS ;
Next T ;

http://wiki.xentax.com/index.php/The_Cars_THQ_PAK 

The script will extract files from the res archives only. Start up MexCom 4.3 and use the wiki for source of scripts. Then open those res files !

If it works, don't forget to VOTE for it in the Supported Games list! It's now an unofficial script, when it gets 5 votes it will become official.

Hi is code is correct for all file except file wav problem no sound (audio.PAK)
thanks
[http://amirachat.ifrance.com/FRE_7Shi1.wav](http://amirachat.ifrance.com/FRE_7Shi1.wav)
[http://amirachat.ifrance.com/FRE_7Shi2.wav](http://amirachat.ifrance.com/FRE_7Shi2.wav)
[http://amirachat.ifrance.com/FRE_7Shi3.wav](http://amirachat.ifrance.com/FRE_7Shi3.wav)
[http://amirachat.ifrance.com/FRE_7Sidle1.wav](http://amirachat.ifrance.com/FRE_7Sidle1.wav)
[http://amirachat.ifrance.com/FRE_7Sidle2.wav](http://amirachat.ifrance.com/FRE_7Sidle2.wav)
[http://amirachat.ifrance.com/FRE_7Sidle3.wav](http://amirachat.ifrance.com/FRE_7Sidle3.wav)
## Post #9
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-10-09T20:18:07+00:00
- Post Title: Cars THQ For Pc

This game have a "special" wav
## Post #10
- Username: Eradicon
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Feb 11, 2011 1:20 am
- Post datetime: 2011-02-10T17:30:43+00:00
- Post Title: Cars THQ For Pc

So how can I extract the .pak files?
## Post #11
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2017-02-25T13:43:54+00:00
- Post Title: Cars THQ For Pc

It's IMA/DVI ADPCM, nibble interleave. Here's a quick (but slow) Python 2.x decoder. Run as
python cars.py input.wav output.wav

```

from io import open
from sys import argv
from struct import unpack, pack
from math import floor

IMA_Scale = \
[
    7, 8, 9, 10, 11, 12, 13, 14,
    16, 17, 19, 21, 23, 25, 28, 31,
    34, 37, 41, 45, 50, 55, 60, 66,
    73, 80, 88, 97, 107, 118, 130, 143,
    157, 173, 190, 209, 230, 253, 279, 307,
    337, 371, 408, 449, 494, 544, 598, 658,
    724, 796, 876, 963, 1060, 1166, 1282, 1411,
    1552, 1707, 1878, 2066, 2272, 2499, 2749, 3024,
    3327, 3660, 4026, 4428, 4871, 5358, 5894, 6484,
    7132, 7845, 8630, 9493, 10442, 11487, 12635, 13899,
    15289, 16818, 18500, 20350, 22385, 24623, 27086, 29794,
    32767
]

IMA_Step = \
[
    -1, -1, -1, -1, 2, 4, 6, 8,
    -1, -1, -1, -1, 2, 4, 6, 8 
]

infile = open(argv[1], "rb")
outfile = open(argv[2], "wb")

def read32(): return unpack("<I",infile.read(4))[0]
def read16(): return unpack("<H",infile.read(2))[0]
def write32(x): outfile.write(pack("<I",x))
def write16(x): outfile.write(pack("<H",x))

riff_head = infile.read(4)
if riff_head != "RIFF":
    raise Exception, "expected RIFF"
file_len = read32()
wavefmt = infile.read(8)
if wavefmt != "WAVEfmt ":
    raise Exception, "expected WAVE fmt"
header_len = read32()
if header_len != 0x14:
    raise Exception, "expected head len 0x14"
codec = read16()
if codec != 2:
    raise Exception, "expected codec 2"
channels = read16()
if channels != 2:
    raise Exception, "expected stereo"
sample_rate = read32()
byte_rate = read32()
sample_size = read16()
if sample_size != 4:
    raise Exception, "expected 4 bit samples"
block_size = read16()
if block_size != 16:
    raise Exception, "expected block size 16"
unk = read32()
if unk != 0x40*0x10000:
    raise Exception, "expecting 00 00 40 00"

data_head = infile.read(4)
if data_head != "data":
    raise Exception, "expected data chunk"
data_len = read32()

data = infile.read(data_len)
payload_size = len(data)
if payload_size != data_len:
    raise Exception, "didn't read all the data?"
sample_count = payload_size
infile.close()

# write RIFF header
outfile.write("RIFF")
write32(payload_size*4+0x24)  # total size
outfile.write("WAVEfmt ")

write32(0x10)   # fmt chunk size
write16(0x1)   # pcm codec id
write16(channels)
write32(sample_rate)
write32(sample_rate*channels*2)
write16(2*channels)  # block align
write16(16)  # bits per sample

outfile.write("data")
write32(payload_size*4)

hist = [0,0]
idx = [0,0]

def decodeima(n,c):
    global idx, hist
    stepsize = IMA_Scale[idx[c]]

    delta = stepsize >> 3
    if (n&1): delta += stepsize >> 2
    if (n&2): delta += stepsize >> 1
    if (n&4): delta += stepsize
    if (n&8):
        newsample = max(-32768, hist[c] - delta)
    else:
        newsample = min(32767, hist[c] + delta)

    idx[c] = max(0, min(88, idx[c] + IMA_Step[n]))

    return newsample

for c in data:
    b = ord(c)
    hist[0] = decodeima(b / 16, 0)
    hist[1] = decodeima(b & 0xF, 1)

    outfile.write(pack("<hh", hist[0], hist[1]))


```


edit:
Oops, I didn't realize how old this thread was when I posted, I was pointed here recently by someone looking to decode the WAVs used in this game. Hope it is still useful to someone!
