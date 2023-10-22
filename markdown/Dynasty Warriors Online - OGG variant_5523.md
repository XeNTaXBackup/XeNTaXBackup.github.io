## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-12-10T16:43:31+00:00
- Post Title: Dynasty Warriors Online - OGG variant

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-12-11T00:15:10+00:00
- Post Title: Dynasty Warriors Online - OGG variant

Oggs just have first 0x100 bytes obfuscated, there are several per .bin. This does the trick for the files you posted, apologies for python but I need the practice (as you can see I write it like C anyway...).

```
#
# Dynasty Warriors Online file extractor 0.1 by hcs

import io
from sys import argv
from struct import unpack

def unpack_file(infile, offset, name):
    infile.seek(offset)

    # check the header
    if infile.read(4) != "KOVS":
        return 0

    # read file size
    file_size = unpack('<I',infile.read(4))[0]

    # skip padding
    # TODO: check that padding is all 0s?
    infile.seek(offset+0x20)

    # read the file
    oggbuf = bytearray(file_size)
    infile.readinto(oggbuf)

    # deobfuscate
    for i in range(0,0x100):
        oggbuf[i] = oggbuf[i] ^ i

    # write to the output
    outfile = open(name,'wb')
    outfile.write(oggbuf)

    print name, file_size, "bytes"

    return 1

###

if len(argv) != 2:
    print "Decrypt Ogg files from Dynasty Warriors Online"
    print "usage: dwo_xor.py input.bin"
    exit(1)

# open input
infile_name = argv[1]
infile = open(infile_name,'rb')

# try to just dump file straightaway
if unpack_file(infile, 0, '%s.ogg' % infile_name):
    print "ok"
    exit(0)

# read known parts of header
infile.seek(0xC)
header_size, subfile_count = unpack('<IxxxxI',infile.read(12))

if header_size != 0x18 + 4*subfile_count:
    print "header consistency check failed"
    exit(1)

file_offsets = unpack('<'+'I'*subfile_count,infile.read(4*subfile_count))
for offset in file_offsets:
    if not unpack_file(infile, offset, \
        '%s_%08x.ogg' % \
        (infile_name, offset)):
        print "unpack failed"
        exit(1)

print "ok!"

```


[edit] 0.1 quick fix, in dumping the music I found that there are a few files that don't have the structure, still xored the same way, though
## Post #3
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-12-11T06:44:02+00:00
- Post Title: Dynasty Warriors Online - OGG variant

For we purists, here's 0.2, which preserves the KOVS header and exports the files as .kovs.  As of r896 vgmstream now supports these directly, with looping.

```
#
# Dynasty Warriors Online file extractor 0.2 by hcs

import io
from sys import argv
from struct import unpack

def unpack_file(infile, offset, name):
    infile.seek(offset)

    # check the header
    if infile.read(4) != "KOVS":
        return 0

    # read file size
    file_size = unpack('<I',infile.read(4))[0]

    # read the file
    infile.seek(offset)
    oggbuf = bytearray(file_size+0x20)
    infile.readinto(oggbuf)

    # write to the output
    outfile = open(name,'wb')
    outfile.write(oggbuf)

    print name, file_size, "bytes"

    return 1

###

if len(argv) != 2:
    print "Decrypt Ogg files from Dynasty Warriors Online"
    print "usage: dwo_xor.py input.bin"
    exit(1)

# open input
infile_name = argv[1]
infile = open(infile_name,'rb')

# try to just dump file straightaway
if unpack_file(infile, 0, '%s.kovs' % infile_name):
    print "ok!"
    exit(0)

# read known parts of header
infile.seek(0xC)
header_size, subfile_count = unpack('<IxxxxI',infile.read(12))

if header_size != 0x18 + 4*subfile_count:
    print "header consistency check failed"
    exit(1)

file_offsets = unpack('<'+'I'*subfile_count,infile.read(4*subfile_count))
for offset in file_offsets:
    if not unpack_file(infile, offset, \
        '%s_%08x.kovs' % \
        (infile_name, offset)):
        print "unpack failed"
        exit(1)

print "ok!"

```
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-12-11T15:35:58+00:00
- Post Title: Dynasty Warriors Online - OGG variant

Thanks HCS! =)
However... I don't work with Python so I don't know how o compile this *shame on me*... Installed python, but when I run the script I get the error

```
ImportError: No module named io
```
What do I need to install? Are there paths to be set for Windows 7? Thanks for your help! =)
## Post #5
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-12-12T00:22:38+00:00
- Post Title: Dynasty Warriors Online - OGG variant

Sorry, you probably need a later version of Python. I used 2.7.
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-12-13T19:15:23+00:00
- Post Title: Dynasty Warriors Online - OGG variant

Ok, worked, thanks!
## Post #7
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-02-04T15:23:43+00:00
- Post Title: Dynasty Warriors Online - OGG variant

Python script works fully with PC versions of Dynasty Warriors 6, Dynasty Warriors 7, Dynasty Warriors Online, Warriors Orochi Z, almost all music files of Dynasty Warriors 8 Xtreme Legends(PC version too).

Need just a little modification or separated scripts for Dynasty Warriors 5(.BIN|.IDX), Samurai Warriors 2(LINK_BGM.LNK), Warriors Orochi(LINK_BGM.BDX), some music files of Dynasty Warriors 8 Xtreme Legends(contain multiple KOVS).
