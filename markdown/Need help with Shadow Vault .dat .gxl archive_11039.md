## Post #1
- Username: SlappyT
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 13, 2013 2:22 am
- Post datetime: 2013-12-13T06:19:39+00:00
- Post Title: Need help with Shadow Vault .dat .gxl archive

Hi Guys.

I need a help with extracting .dat and .gxl achives from Shadow Vault game ([http://www.strategyinformer.com/pc/shadowvault/](http://www.strategyinformer.com/pc/shadowvault/)).
It is a 3D tactical RPG game with Fallout style and I would like to translate it.

Here is screen of both files in hex editor: 

It looks like the archive are XORed or something. I ran the .exe file in disasembler to find out what happens.

I was looking for kernel32.CreateFile() method to catch the start of working with file but without experiences I do not know what to search for. 

Some my guesses for XOR strings: 
**BCCxhl 
j3xw 
#.0 
18F89C 
128 
1136

Here is a link with sample of format: [http://graphical-installer.com/temp/shadow-vault.zip](http://graphical-installer.com/temp/shadow-vault.zip)

As I am author of Graphical Installer (NSIS and Inno Setup installer extension: [http://graphical-installer.com/](http://graphical-installer.com/)) I am offering you a Commercial license of this product for help with this formats.

Thanks!
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-12-15T03:03:47+00:00
- Post Title: Need help with Shadow Vault .dat .gxl archive

> Reply from SlappyT
>
> Hi Guys.

I need a help with extracting .dat and .gxl achives from Shadow Vault game (http://www.strategyinformer.com/pc/shadowvault/).
It is a 3D tactical RPG game with Fallout style and I would like to translate it.

Here is screen of both files in hex editor: 

It looks like the archive are XORed or something. I ran the .exe file in disasembler to find out what happens.

I was looking for kernel32.CreateFile() method to catch the start of working with file but without experiences I do not know what to search for. 

Some my guesses for XOR strings: 
**BCCxhl 
j3xw 
#.0 
18F89C 
128 
1136

Here is a link with sample of format: http://graphical-installer.com/temp/shadow-vault.zip

As I am author of Graphical Installer (NSIS and Inno Setup installer extension: http://graphical-installer.com/) I am offering you a Commercial license of this product for help with this formats.

Thanks!

I'll take a look

Btw your installers are pretty awesome good job on it
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-12-15T20:52:01+00:00
- Post Title: Need help with Shadow Vault .dat .gxl archive

It's would be great if you can upload full game.
## Post #4
- Username: SlappyT
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 13, 2013 2:22 am
- Post datetime: 2014-03-17T07:46:02+00:00
- Post Title: Need help with Shadow Vault .dat .gxl archive

> Reply from Ekey
>
> It's would be great if you can upload full game.

Here we go: [https://mega.co.nz/#!45EzVCRI!QHNtzyS66 ... WoGj5PABQQ](https://mega.co.nz/#!45EzVCRI!QHNtzyS66t4A2SVfbjmYTTZ21WujiaIEgWoGj5PABQQ)
## Post #5
- Username: dniel888
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Dec 17, 2014 7:01 am
- Post datetime: 2014-12-21T14:29:50+00:00
- Post Title: Need help with Shadow Vault .dat .gxl archive

the .dat archives encrypted so you need to decrypt them with that script:

```
# (c) 18/12/2013 by dniel888
# script for QuickBMS http://quickbms.aluigi.org

endian big
set XOR_KEY binary "\xEB\x60\xA3\x1F\x9C\xA3\xF9\xC0\x9D\x14\x9F\xFE\xE3\x83\x5A\x3A\xB3\x09\x9B\x0D\x49\x0E\x94\x39\xEC\xD3\xDB\x9E\x64\xF2\xAD\x58\x4D\xF6\x00\x43\xD5\x4D\x3E\xA0\x2F\x38\x1F\x87\xA3\x6F\xC5\xA6\x39\x50\x41\x8C\x65\x7A\x67\xFC\x34\x86\x38\x60\xC2\x9C\xDE\xE0\x0D\x24\x39\x48\x29\xDB\x74\x8F\x73\xC5\xB0\x54\xEC\x95\x49\xAB\xDB\xD0\x2B\xE9\x03\x4A\x42\x81\xDA\xD2\x5B\x27\x35\x4D\x5D\x39\x20\x66\x93\x53\x61\x57\x49\x31\x8C\xE8\x2E\xA5\x2B\x3D\x82\x0B\x15\x23\xCE\x24\x49\x2F\x4B\x31\x90\xB3\x6C\x7B\x22\x45\x4A\xDC\x80\xDA\x8D\xDE\x9B\x47\x9C\xDD\x7D\xE4\x2E\x76\x28\xE2\xA4\xAE\xEF\x73\x29\xF2\x88\xD1\xF8\x9A\x0E\x4A\x36\x1E\xBE\x9A\x1C\xF6\x73\x63\xBD\xB3\x39\xEB\xF7\xBA\xB5\x72\x1D\xBA\x32\xB7\x37\xF8\xC5\x28\x21\x2C\xAF\x9B\x0A\x02\x1C\xC4\xCE\xBB\xBE\x3B\xDD\x39\xE1\xD2\xB0\xDC\xD1\x88\x12\xD5\x9C\x2A\x5D\x87\x4E\x28\xD8\x21\x1B\x85\xE2\x4E\xB6\x7D\x8D\x00\xA6\x3C\x2C\xA7\x03\xF7\x6A\xB5\x9F\x09\xC5\xA0\x19\xAB\x4F\x32\x24\xE8\x66\x58\x64\x67\xF4\x84\x69\x56\x38\xE5\x0B\xB4\xD8\x0E\xC7\xA7\xCC\x8C\x48\x83\xB0\xAA\xB8\x26\x0E\x73\xD3\x73\x36\xE9\x53\x31\xDD\x3A\x6E\xEF\x87\xFF\xE8\x90\xF3\x0C\x02\x90\x85\x24\xD5\xB6\x48\x27\xD2\x7F\xEB\x65\xC6\xA2\x2F\xF1\xBF\xD2\xF6\x34\xD5\x9B\xBA\x04\xA8\x09\xDA\x40\x5E\xFD\x3E\xDA\x43\x38\x75\x48\x74\xBD\xFB\xFA\x1C\x7F\xE2\x0D\x34\x7C\x36\xCF\x89\xD5\xE0\x8E\x86\x34\x61\x91\xB9\x51\x43\x20\xF3\xDB\x05\xE1\x37\x71\xCD\x29\x9E\x9B\x9A\x03\x88\x0D\x26\x82\x95\x5F\x81\xD4\xB3\xED\xE9\xC0\x05\xE2\xC2\xF0\xE5\x42\xE0\xF8\xF8\x89\x4D\x9D\x76\x68\xEF\xB5\xB5\x9C\xD6\x73\x07\xB1\x52\x2C\xED\xC5\x95\xD1\x86\x30\x25\xFE\x3C\xD2\x76\x9F\x3A\xB5\x56\xF7\xB8\x26\x94\xEE\x34\x70\x7E\xA9\x93\x61\xF9\x61\xCE\xF8\x45\xD5\x02\x1E\xFF\x91\xFF\xA3\x44\xF9\xF2\xD4\xDD\xBF\xBD\x6A\x8F\x78\x45\x3E\x30\x8A\xB4\xCE\x5A\x30\x90\xC8\x82\x84\x00\x78\x64\x7E\xA6\xF8\x35\xD5\xBF\x7D\x14\xF7\x5A\xCB\x3F\x49\x9B\x8E\x79\x55\x47\x6A\xAA\x78\xAF\x7F\x9D\x70\x9A\xCE\xC6\xE6\x5C\xD7\xD6\x34\x0A\x24\x6D\x46\xF4\x6F\xFB\xE7\x9C\x0B\xE3\x45\x52\x43\xC2\x44\xCB\xFC\x1F\x82\xC6\xFA\x9A\x28\x3A\x79\x89\x9B\xED\xD2\xC0\xE7\x0A\xDB\x81\x6D\x4D\xEB\x78\x7A\x68\xC3\x36\x01\xE3\x22\x9A\x25\x0D\x9D\x9E\xAF\xF1\xFA\xDA\x40\xA9\xBC\xA5\x77\xB6\x40\x88\x3F\x77\xE4\xCC\xAA\xE6\x65\x9F\x37\x82\x62\xE1\x45\xFF\xC2\x6A\x5F\x4B\xFC\x84\xB3\xE9\x42\x1C\x61\xDA\x5C\x9D\xC5\x61\x1C\x0F\x74\x6D\xBC\x05\x26\x32\x9F\x97\x8F\x50\xFE\xED\x8C\x36\x41\x99\x30\x8F\x6D\xDA\x6A\x99\x62\x50\x8D\x88\xD6\x45\xFB\xEE\x86\xF0\x23\x99\xB9\x20\xCD\xF0\xEC\x1B\xF8\x67\xB8\xDC\x35\x22\xC6\x48\x07\x7F\x93\xB5\x4E\x8E\x81\x98\xB2\x47\x4B\x58\x72\x5D\xCE\xBF\x23\x8D\x33\x2A\x43\x13\x75\xF3\xFF\x1C\x23\xCD\xBE\x96\x0B\x0C\xDA\x2A\x04\x94\xEA\x5D\x1D\x44\x42\x8F\x5B\x1A\x19\x61\x79\x45\x5B\x0A\xA8\x29\xD8\xB2\x82\x77\x5F\x0E\xAC\x92\xF7\xD0\xDE\xB3\x78\xD8\xEF\xBB\x51\x1C\xD9\xD2\xC7\xCC\x16\xF8\x2E\x0C\x43\xC1\x9B\x51\xE3\xF9\x80\xF9\xBF\x09\x19\xB8\xFD\xD6\x3B\xA1\xAE\xFB\xE4\xD6\xC5\x93\x95\xC6\x3A\xE9\x7B\x69\xDA\x21\xF5\x7C\x29\x22\x6C\x6F\x21\x28\xC9\x12\x7E\x95\x86\xFC\x63\x36\xA2\xA0\x08\x54\xA8\x44\xD9\x0A\x3F\xB0\x73\x59\xDF\xE3\x3E\x27\x6A\x8B\x70\x48\xEF\x8B\x38\xD9\xD1\x15\x04\x0F\x71\xB1\x36\x60\x39\x54\x26\x9E\x2B\xE4\x0C\xEE\xBE\xF3\x2B\x1A\x4D\xD1\xF5\x9C\xF8\x79\xA5\x43\xA9\x34\xBE\x9D\x39\xF9\xC9\xF2\x2A\x35\x40\x32\x38\x64\x6F\xE7\x0A\xE8\x72\x4A\xE4\xDB\x3E\x48\x90\xF7\xB7\xB2\x33\xA0\xAA\x8C\x60\xB2\x2B\x52\x22\x7D\xC3\xBA\x9E\xF5\x1D\xD9\x3B\xC6\xFF\x26\x69\xBD\xF3\xC8\x5A\x58\x8A\x21\x7C\x53\x22\xD7\x89\x1D\xB8\x4A\xEF\x4F\x04\x05\x1A\x18\xA6\x67\x6C\x00\xAA\xEB\x71\xEC\x2D\xFC\x4E\xE1\xF8\x0E\x16\x65\xAF\x04\x81\x27\xA6\x51\xFA\x81\x66\x88\x1B\xAA\xFD\xCB\x18\xE9\x30\xF8\xFB\x94\x63\x88\xD8\xF0\x10\x72\xF3\xA5\x0B\x18\xCD\x7F\xD8\x6F\x43\x0D\x67\xE3\xCE\x7D\xAD\x7B\x6A\x01\x21\xA1\x73\xA3\x6C\xE9\x91\xA7\xCC\x78\x70\xC5\x09\xB6\x1F\x08\x82\x9A\x70\x0A\x80\xFE\x30\x01\x24\x61\x4C\x91\xF4\xB9\xF8\x80\xF9\x49\xD1\x7A\xF7\xB2\x68\x7D\xD9\x49\x74\x64\x42\xD8\x7B\x78\x21\x5F\x9E\xC7\x3A\x64\x12\x6E\x1D\x58\x6F\xBA\x0D\x7D\x50\x90\xAF\x2C\x25\x14\x48\x46\xC4\x32\x51\x6C\x8C\xFA\x3A\x8B\xE7\xAD\xC2\xA2\x19\x3B\x74\x72\xAC\x43\xFA\xA6\x9B\x1F\x43\xE0\x3D"

get NAME filename
string NAME l= NAME #NAME to smallcase

get SIZE asize

putvarchr MEMORY_FILE SIZE 0 #pre allocate
log MEMORY_FILE 0 0

#####################################################
strlen LEN NAME #genarates the offset of the xor_key
set NAME_START NAME
set TEMP LEN
math TEMP -= 4
string NAME_START >= TEMP
set SUM LEN
math SUM *= 0x1EEF
getvarchr TEMP NAME_START 0 long
math SUM += TEMP
for i = 0 < LEN
    getvarchr TEMP NAME i byte
    math TEMP *= 0x2F
    math SUM += TEMP
next i
math SUM %= 0x3CB
print "offset: %SUM|h%";
#####################################################
# The decryption of the rot encrypt 
set NAME_TEMP NAME

for i = 0 < LEN
    set TEMP 0
    getvarchr TEMP NAME_TEMP i byte
    math TEMP += 0x01
    putvarchr NAME_TEMP i TEMP byte
next i
print "KEY_ROT: %NAME|h%"
print "KEY_ROT: %NAME_TEMP|h%"
encryption "rot" NAME_TEMP

log MEMORY_FILE 0 SIZE
encryption "" ""

print "KEY_XOR offset: %SUM|h%"
print "KEY_XOR : %XOR_KEY|h%"

#####################################################
# The decryption of the xor encrypt 
set POS SUM
for i = 0 < SIZE
    math POS %= 0x3CB

    getvarchr TEMP MEMORY_FILE i
    getvarchr KEY  XOR_KEY     POS
    math TEMP ^= KEY
    putvarchr MEMORY_FILE i TEMP
    math POS += 1
next i

log NAME 0 SIZE MEMORY_FILE
#####################################################

```


after that, extract the archive with that script:

```
# (c) 18/12/2013 by dniel888
# script for QuickBMS http://quickbms.aluigi.org

idstring "DATA"
get files long
get dummy longlong

set START_POINT 40 # each file take 32+4+4
math START_POINT *= files
math START_POINT += 0x10 # first line

for i = 0 < files
    get OFFSET long
    math OFFSET += START_POINT
    
    get SIZE long
    getdstring NAME 0x20
    
    log NAME OFFSET SIZE
    
next i

```

then, extract the GXL(Graphics library) format with this script:

```
# (c) 18/12/2013 by dniel888
# script for QuickBMS http://quickbms.aluigi.org

get UNK long
idstring "GFXL"    # Graphics library
get FILES long

get NAME1 long
get UNK long
get UNK long
get OFFSET1 long
get UNK long

math FILES -= 1 # for the first file

for i = 0 < FILES
    get NAME2 long
    get UNK long
    get UNK long
    get OFFSET2 long
    get UNK long
    
    set SIZE OFFSET2
    math SIZE -= OFFSET1
    
    string NAME1 += ".gfx"
    log NAME1 OFFSET1 SIZE 
    
    set OFFSET1 OFFSET2
    set NAME1 NAME2
next i

get SIZE asize
math SIZE -= OFFSET1

string NAME1 += ".gfx"
log NAME1 OFFSET1 SIZE

```


for the gfx files, I have created a viewer: 
download : [https://mega.nz/#F!48sk2YpA!7dPnIj1HaXJ3tR-IRWVqOw](https://mega.nz/#F!48sk2YpA!7dPnIj1HaXJ3tR-IRWVqOw)
virus scan: [https://www.virustotal.com/file/f074525 ... 419171768/](https://www.virustotal.com/file/f07452539ec510cf89121a9fd301a6391955718ad651ec8274cf81d7add08523/analysis/1419171768/)
## Post #6
- Username: Slappy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jul 17, 2012 5:28 pm
- Post datetime: 2014-12-23T06:34:08+00:00
- Post Title: Need help with Shadow Vault .dat .gxl archive

Fantastic job, big thanks!

The decrypting and extraction works great but the GFX viewer is not working for me 
The .gfx is some kind of DDS texture pack? Maybe it would be better to convert it to serie of .dds pictures (via command line)

I am little dissapointed of the game because there are still 2 unknown file types: .scn and .bck which look like another archive containing levels data. If we could crack this I would be entirely satisfied 

Anyway as I said: full license of Graphical Installer is yours, see PM. Thanks!
## Post #7
- Username: dniel888
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Dec 17, 2014 7:01 am
- Post datetime: 2014-12-23T19:29:16+00:00
- Post Title: Need help with Shadow Vault .dat .gxl archive

is the GFXViewer running?

here is the header of the GFX format :
GFX Header
{
UInt32 ID
UInt32 "GFX "
Byte    EncType1
Byte    EnctType2
UInt16 0x0000 ?
Byte    BitsPerPixel
Byte    TransparentFlag (0xFF - on, 0x00 off)
UInt16 NumBlocks (0-400)
UInt16 Width
UInt16 Height
UInt16 UNK1
UInt16 UNK2
UInt32 TransparentColor1
UInt32 TransparentColor2 ?
UInt64 0x0000 0000
}
The Encryption is one of the following:
1 - sort of packBits 8 bit key
2 - sort of packBits 16 bit key
3 - LZRW1KH

I'm not expert for graphic file formats, so I don't know how to build GFX->DDS convertor.
## Post #8
- Username: Slappy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jul 17, 2012 5:28 pm
- Post datetime: 2014-12-28T16:28:41+00:00
- Post Title: Need help with Shadow Vault .dat .gxl archive

> Reply from dniel888
>
> is the GFXViewer running?

here is the header of the GFX format :
GFX Header
{
UInt32 ID
UInt32 "GFX "
Byte    EncType1
Byte    EnctType2
UInt16 0x0000 ?
Byte    BitsPerPixel
Byte    TransparentFlag (0xFF - on, 0x00 off)
UInt16 NumBlocks (0-400)
UInt16 Width
UInt16 Height
UInt16 UNK1
UInt16 UNK2
UInt32 TransparentColor1
UInt32 TransparentColor2 ?
UInt64 0x0000 0000
}
The Encryption is one of the following:
1 - sort of packBits 8 bit key
2 - sort of packBits 16 bit key
3 - LZRW1KH

I'm not expert for graphic file formats, so I don't know how to build GFX->DDS convertor.

This headers looks fine, thanks.
The GFXViewer starts correctly but when I open some file it does nothing -better to say CPU is running 100% for this process but nothings happens (I wait for a long time, tried several various files).

From the encryption I tried LZRW1KH with no success.
For 1/2 encryption - this is the same s .dat files encryption? Or is there some easier XOR?
## Post #9
- Username: dniel888
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Dec 17, 2014 7:01 am
- Post datetime: 2014-12-28T17:22:42+00:00
- Post Title: Need help with Shadow Vault .dat .gxl archive

try to load GXL archives from the DAT files, because some GXL archives that out of the DAT archive uses DXT5 (encryption type 8 ) and the viewer doesn't support them.

EDIT: viewer updated,bugs fixed.
## Post #10
- Username: Slappy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jul 17, 2012 5:28 pm
- Post datetime: 2015-01-02T10:12:00+00:00
- Post Title: Need help with Shadow Vault .dat .gxl archive

> Reply from dniel888
>
> try to load GXL archives from the DAT files, because some GXL archives that out of the DAT archive uses DXT5 (encryption type 8 ) and the viewer doesn't support them.

EDIT: viewer updated,bugs fixed.

The viewer is now working perfectly thanks!

Can you share it's sources?

I also solved the .bck file format and partially also the .scn I will post the description here.
## Post #11
- Username: dniel888
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Dec 17, 2014 7:01 am
- Post datetime: 2015-01-02T13:15:51+00:00
- Post Title: Need help with Shadow Vault .dat .gxl archive

> Reply from Slappy
>
> dniel888 wrote:try to load GXL archives from the DAT files, because some GXL archives that out of the DAT archive uses DXT5 (encryption type 8 ) and the viewer doesn't support them.

EDIT: viewer updated,bugs fixed.

The viewer is now working perfectly thanks!

Can you share it's sources?

I also solved the .bck file format and partially also the .scn I will post the description here.

I uploaded the source to the folder.
## Post #12
- Username: IgoreshaZhu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 12, 2021 8:17 pm
- Post datetime: 2021-06-12T12:23:07+00:00
- Post Title: Need help with Shadow Vault .dat .gxl archive

Good day! Can you help with extracting the .axl files? Dragon Unpacker can't see some audio files and i can't found right script.

Here's link to this file: [https://drive.google.com/file/d/17Nt9Zg ... sp=sharing](https://drive.google.com/file/d/17Nt9ZgnZ9cGwaz7ir1jH7tMfqVd3h5LR/view?usp=sharing)
## Post #13
- Username: dniel888
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Dec 17, 2014 7:01 am
- Post datetime: 2021-06-12T16:21:44+00:00
- Post Title: Need help with Shadow Vault .dat .gxl archive

From a very quick look at this .axl format it looks as follows:
1. It starts with 4 byte magic AUDL (probably followed by the number of files).
2. It continues with what seems like list of the file offset followed by their lengths (this is very common). The offsets are all relative to the MAGIC AUDX (for your file you need to add 0x6A8 for each offset.
3. After this table it seems to have the files themselves. It seems to me that the entropy is very high so these files are probably encrypted. You have to guess/RE the encryption.

It should be relatively easy to create a script, but this format is actually very nice to learn the basics from so I leave the script writing for others as I don't have much time currently.
## Post #14
- Username: Kazumadesu
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 06, 2023 5:53 pm
- Post datetime: 2023-09-06T10:02:29+00:00
- Post Title: Need help with Shadow Vault .dat .gxl archive

> Reply from dniel888 ↑Sun Dec 21, 2014 10:29 pm at Sun Dec 21, 2014 10:29 pm
>
> 
the .dat archives encrypted so you need to decrypt them with that script:
Code: Select all# decompress the .dat files from Shadow Vault
# (c) 18/12/2013 by dniel888
# script for QuickBMS http://quickbms.aluigi.org

endian big
set XOR_KEY binary "\xEB\x60\xA3\x1F\x9C\xA3\xF9\xC0\x9D\x14\x9F\xFE\xE3\x83\x5A\x3A\xB3\x09\x9B\x0D\x49\x0E\x94\x39\xEC\xD3\xDB\x9E\x64\xF2\xAD\x58\x4D\xF6\x00\x43\xD5\x4D\x3E\xA0\x2F\x38\x1F\x87\xA3\x6F\xC5\xA6\x39\x50\x41\x8C\x65\x7A\x67\xFC\x34\x86\x38\x60\xC2\x9C\xDE\xE0\x0D\x24\x39\x48\x29\xDB\x74\x8F\x73\xC5\xB0\x54\xEC\x95\x49\xAB\xDB\xD0\x2B\xE9\x03\x4A\x42\x81\xDA\xD2\x5B\x27\x35\x4D\x5D\x39\x20\x66\x93\x53\x61\x57\x49\x31\x8C\xE8\x2E\xA5\x2B\x3D\x82\x0B\x15\x23\xCE\x24\x49\x2F\x4B\x31\x90\xB3\x6C\x7B\x22\x45\x4A\xDC\x80\xDA\x8D\xDE\x9B\x47\x9C\xDD\x7D\xE4\x2E\x76\x28\xE2\xA4\xAE\xEF\x73\x29\xF2\x88\xD1\xF8\x9A\x0E\x4A\x36\x1E\xBE\x9A\x1C\xF6\x73\x63\xBD\xB3\x39\xEB\xF7\xBA\xB5\x72\x1D\xBA\x32\xB7\x37\xF8\xC5\x28\x21\x2C\xAF\x9B\x0A\x02\x1C\xC4\xCE\xBB\xBE\x3B\xDD\x39\xE1\xD2\xB0\xDC\xD1\x88\x12\xD5\x9C\x2A\x5D\x87\x4E\x28\xD8\x21\x1B\x85\xE2\x4E\xB6\x7D\x8D\x00\xA6\x3C\x2C\xA7\x03\xF7\x6A\xB5\x9F\x09\xC5\xA0\x19\xAB\x4F\x32\x24\xE8\x66\x58\x64\x67\xF4\x84\x69\x56\x38\xE5\x0B\xB4\xD8\x0E\xC7\xA7\xCC\x8C\x48\x83\xB0\xAA\xB8\x26\x0E\x73\xD3\x73\x36\xE9\x53\x31\xDD\x3A\x6E\xEF\x87\xFF\xE8\x90\xF3\x0C\x02\x90\x85\x24\xD5\xB6\x48\x27\xD2\x7F\xEB\x65\xC6\xA2\x2F\xF1\xBF\xD2\xF6\x34\xD5\x9B\xBA\x04\xA8\x09\xDA\x40\x5E\xFD\x3E\xDA\x43\x38\x75\x48\x74\xBD\xFB\xFA\x1C\x7F\xE2\x0D\x34\x7C\x36\xCF\x89\xD5\xE0\x8E\x86\x34\x61\x91\xB9\x51\x43\x20\xF3\xDB\x05\xE1\x37\x71\xCD\x29\x9E\x9B\x9A\x03\x88\x0D\x26\x82\x95\x5F\x81\xD4\xB3\xED\xE9\xC0\x05\xE2\xC2\xF0\xE5\x42\xE0\xF8\xF8\x89\x4D\x9D\x76\x68\xEF\xB5\xB5\x9C\xD6\x73\x07\xB1\x52\x2C\xED\xC5\x95\xD1\x86\x30\x25\xFE\x3C\xD2\x76\x9F\x3A\xB5\x56\xF7\xB8\x26\x94\xEE\x34\x70\x7E\xA9\x93\x61\xF9\x61\xCE\xF8\x45\xD5\x02\x1E\xFF\x91\xFF\xA3\x44\xF9\xF2\xD4\xDD\xBF\xBD\x6A\x8F\x78\x45\x3E\x30\x8A\xB4\xCE\x5A\x30\x90\xC8\x82\x84\x00\x78\x64\x7E\xA6\xF8\x35\xD5\xBF\x7D\x14\xF7\x5A\xCB\x3F\x49\x9B\x8E\x79\x55\x47\x6A\xAA\x78\xAF\x7F\x9D\x70\x9A\xCE\xC6\xE6\x5C\xD7\xD6\x34\x0A\x24\x6D\x46\xF4\x6F\xFB\xE7\x9C\x0B\xE3\x45\x52\x43\xC2\x44\xCB\xFC\x1F\x82\xC6\xFA\x9A\x28\x3A\x79\x89\x9B\xED\xD2\xC0\xE7\x0A\xDB\x81\x6D\x4D\xEB\x78\x7A\x68\xC3\x36\x01\xE3\x22\x9A\x25\x0D\x9D\x9E\xAF\xF1\xFA\xDA\x40\xA9\xBC\xA5\x77\xB6\x40\x88\x3F\x77\xE4\xCC\xAA\xE6\x65\x9F\x37\x82\x62\xE1\x45\xFF\xC2\x6A\x5F\x4B\xFC\x84\xB3\xE9\x42\x1C\x61\xDA\x5C\x9D\xC5\x61\x1C\x0F\x74\x6D\xBC\x05\x26\x32\x9F\x97\x8F\x50\xFE\xED\x8C\x36\x41\x99\x30\x8F\x6D\xDA\x6A\x99\x62\x50\x8D\x88\xD6\x45\xFB\xEE\x86\xF0\x23\x99\xB9\x20\xCD\xF0\xEC\x1B\xF8\x67\xB8\xDC\x35\x22\xC6\x48\x07\x7F\x93\xB5\x4E\x8E\x81\x98\xB2\x47\x4B\x58\x72\x5D\xCE\xBF\x23\x8D\x33\x2A\x43\x13\x75\xF3\xFF\x1C\x23\xCD\xBE\x96\x0B\x0C\xDA\x2A\x04\x94\xEA\x5D\x1D\x44\x42\x8F\x5B\x1A\x19\x61\x79\x45\x5B\x0A\xA8\x29\xD8\xB2\x82\x77\x5F\x0E\xAC\x92\xF7\xD0\xDE\xB3\x78\xD8\xEF\xBB\x51\x1C\xD9\xD2\xC7\xCC\x16\xF8\x2E\x0C\x43\xC1\x9B\x51\xE3\xF9\x80\xF9\xBF\x09\x19\xB8\xFD\xD6\x3B\xA1\xAE\xFB\xE4\xD6\xC5\x93\x95\xC6\x3A\xE9\x7B\x69\xDA\x21\xF5\x7C\x29\x22\x6C\x6F\x21\x28\xC9\x12\x7E\x95\x86\xFC\x63\x36\xA2\xA0\x08\x54\xA8\x44\xD9\x0A\x3F\xB0\x73\x59\xDF\xE3\x3E\x27\x6A\x8B\x70\x48\xEF\x8B\x38\xD9\xD1\x15\x04\x0F\x71\xB1\x36\x60\x39\x54\x26\x9E\x2B\xE4\x0C\xEE\xBE\xF3\x2B\x1A\x4D\xD1\xF5\x9C\xF8\x79\xA5\x43\xA9\x34\xBE\x9D\x39\xF9\xC9\xF2\x2A\x35\x40\x32\x38\x64\x6F\xE7\x0A\xE8\x72\x4A\xE4\xDB\x3E\x48\x90\xF7\xB7\xB2\x33\xA0\xAA\x8C\x60\xB2\x2B\x52\x22\x7D\xC3\xBA\x9E\xF5\x1D\xD9\x3B\xC6\xFF\x26\x69\xBD\xF3\xC8\x5A\x58\x8A\x21\x7C\x53\x22\xD7\x89\x1D\xB8\x4A\xEF\x4F\x04\x05\x1A\x18\xA6\x67\x6C\x00\xAA\xEB\x71\xEC\x2D\xFC\x4E\xE1\xF8\x0E\x16\x65\xAF\x04\x81\x27\xA6\x51\xFA\x81\x66\x88\x1B\xAA\xFD\xCB\x18\xE9\x30\xF8\xFB\x94\x63\x88\xD8\xF0\x10\x72\xF3\xA5\x0B\x18\xCD\x7F\xD8\x6F\x43\x0D\x67\xE3\xCE\x7D\xAD\x7B\x6A\x01\x21\xA1\x73\xA3\x6C\xE9\x91\xA7\xCC\x78\x70\xC5\x09\xB6\x1F\x08\x82\x9A\x70\x0A\x80\xFE\x30\x01\x24\x61\x4C\x91\xF4\xB9\xF8\x80\xF9\x49\xD1\x7A\xF7\xB2\x68\x7D\xD9\x49\x74\x64\x42\xD8\x7B\x78\x21\x5F\x9E\xC7\x3A\x64\x12\x6E\x1D\x58\x6F\xBA\x0D\x7D\x50\x90\xAF\x2C\x25\x14\x48\x46\xC4\x32\x51\x6C\x8C\xFA\x3A\x8B\xE7\xAD\xC2\xA2\x19\x3B\x74\x72\xAC\x43\xFA\xA6\x9B\x1F\x43\xE0\x3D"

get NAME filename
string NAME l= NAME #NAME to smallcase

get SIZE asize

putvarchr MEMORY_FILE SIZE 0 #pre allocate
log MEMORY_FILE 0 0

#####################################################
strlen LEN NAME #genarates the offset of the xor_key
set NAME_START NAME
set TEMP LEN
math TEMP -= 4
string NAME_START >= TEMP
set SUM LEN
math SUM *= 0x1EEF
getvarchr TEMP NAME_START 0 long
math SUM += TEMP
for i = 0 < LEN
    getvarchr TEMP NAME i byte
    math TEMP *= 0x2F
    math SUM += TEMP
next i
math SUM %= 0x3CB
print "offset: %SUM|h%";
#####################################################
# The decryption of the rot encrypt 
set NAME_TEMP NAME

for i = 0 < LEN
    set TEMP 0
    getvarchr TEMP NAME_TEMP i byte
    math TEMP += 0x01
    putvarchr NAME_TEMP i TEMP byte
next i
print "KEY_ROT: %NAME|h%"
print "KEY_ROT: %NAME_TEMP|h%"
encryption "rot" NAME_TEMP

log MEMORY_FILE 0 SIZE
encryption "" ""

print "KEY_XOR offset: %SUM|h%"
print "KEY_XOR : %XOR_KEY|h%"

#####################################################
# The decryption of the xor encrypt 
set POS SUM
for i = 0 < SIZE
    math POS %= 0x3CB

    getvarchr TEMP MEMORY_FILE i
    getvarchr KEY  XOR_KEY     POS
    math TEMP ^= KEY
    putvarchr MEMORY_FILE i TEMP
    math POS += 1
next i

log NAME 0 SIZE MEMORY_FILE
#####################################################


after that, extract the archive with that script:
Code: Select all# extracts the .dat files from Shadow Vault (http://www.gamespot.com/shadow-vault)
# (c) 18/12/2013 by dniel888
# script for QuickBMS http://quickbms.aluigi.org

idstring "DATA"
get files long
get dummy longlong

set START_POINT 40 # each file take 32+4+4
math START_POINT *= files
math START_POINT += 0x10 # first line

for i = 0 < files
    get OFFSET long
    math OFFSET += START_POINT
    
    get SIZE long
    getdstring NAME 0x20
    
    log NAME OFFSET SIZE
    
next i

then, extract the GXL(Graphics library) format with this script:
Code: Select all# extracts the .gxl files from Shadow Vault (http://www.gamespot.com/shadow-vault)
# (c) 18/12/2013 by dniel888
# script for QuickBMS http://quickbms.aluigi.org

get UNK long
idstring "GFXL"    # Graphics library
get FILES long

get NAME1 long
get UNK long
get UNK long
get OFFSET1 long
get UNK long

math FILES -= 1 # for the first file

for i = 0 < FILES
    get NAME2 long
    get UNK long
    get UNK long
    get OFFSET2 long
    get UNK long
    
    set SIZE OFFSET2
    math SIZE -= OFFSET1
    
    string NAME1 += ".gfx"
    log NAME1 OFFSET1 SIZE 
    
    set OFFSET1 OFFSET2
    set NAME1 NAME2
next i

get SIZE asize
math SIZE -= OFFSET1

string NAME1 += ".gfx"
log NAME1 OFFSET1 SIZE


for the gfx files, I have created a viewer: 
download : https://mega.nz/#F!48sk2YpA!7dPnIj1HaXJ3tR-IRWVqOw
virus scan: https://www.virustotal.com/file/f074525 ... 419171768/

Hello, I tried using the gxl script but it showed me an error. How can I fix it?
- signature of 4 bytes at offset 0x00000004 doesn't match the one
  expected by the script:
  this one: ""
  0e 00 06 00                                       ....
  expected: "GFXL"
  47 46 58 4c                                       GFXL
- 0 files found in 0 seconds
  coverage file 0     1%   8          688        . offset 00000008

Here's the file that I wanted to extract: [https://mega.nz/file/tzd3nZgR#AKVZIhPv9 ... fhTohEdsuM](https://mega.nz/file/tzd3nZgR#AKVZIhPv9Da-m0CVvMXoHzTDD5e_0WzPGfhTohEdsuM)
## Post #15
- Username: dniel888
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Dec 17, 2014 7:01 am
- Post datetime: 2023-09-06T13:03:32+00:00
- Post Title: Need help with Shadow Vault .dat .gxl archive

> Reply from Kazumadesu ↑Wed Sep 06, 2023 6:02 pm at Wed Sep 06, 2023 6:02 pm
>
> 
dniel888 wrote: ↑Sun Dec 21, 2014 10:29 pm
the .dat archives encrypted so you need to decrypt them with that script:
Code: Select all# decompress the .dat files from Shadow Vault
# (c) 18/12/2013 by dniel888
# script for QuickBMS http://quickbms.aluigi.org

endian big
set XOR_KEY binary "\xEB\x60\xA3\x1F\x9C\xA3\xF9\xC0\x9D\x14\x9F\xFE\xE3\x83\x5A\x3A\xB3\x09\x9B\x0D\x49\x0E\x94\x39\xEC\xD3\xDB\x9E\x64\xF2\xAD\x58\x4D\xF6\x00\x43\xD5\x4D\x3E\xA0\x2F\x38\x1F\x87\xA3\x6F\xC5\xA6\x39\x50\x41\x8C\x65\x7A\x67\xFC\x34\x86\x38\x60\xC2\x9C\xDE\xE0\x0D\x24\x39\x48\x29\xDB\x74\x8F\x73\xC5\xB0\x54\xEC\x95\x49\xAB\xDB\xD0\x2B\xE9\x03\x4A\x42\x81\xDA\xD2\x5B\x27\x35\x4D\x5D\x39\x20\x66\x93\x53\x61\x57\x49\x31\x8C\xE8\x2E\xA5\x2B\x3D\x82\x0B\x15\x23\xCE\x24\x49\x2F\x4B\x31\x90\xB3\x6C\x7B\x22\x45\x4A\xDC\x80\xDA\x8D\xDE\x9B\x47\x9C\xDD\x7D\xE4\x2E\x76\x28\xE2\xA4\xAE\xEF\x73\x29\xF2\x88\xD1\xF8\x9A\x0E\x4A\x36\x1E\xBE\x9A\x1C\xF6\x73\x63\xBD\xB3\x39\xEB\xF7\xBA\xB5\x72\x1D\xBA\x32\xB7\x37\xF8\xC5\x28\x21\x2C\xAF\x9B\x0A\x02\x1C\xC4\xCE\xBB\xBE\x3B\xDD\x39\xE1\xD2\xB0\xDC\xD1\x88\x12\xD5\x9C\x2A\x5D\x87\x4E\x28\xD8\x21\x1B\x85\xE2\x4E\xB6\x7D\x8D\x00\xA6\x3C\x2C\xA7\x03\xF7\x6A\xB5\x9F\x09\xC5\xA0\x19\xAB\x4F\x32\x24\xE8\x66\x58\x64\x67\xF4\x84\x69\x56\x38\xE5\x0B\xB4\xD8\x0E\xC7\xA7\xCC\x8C\x48\x83\xB0\xAA\xB8\x26\x0E\x73\xD3\x73\x36\xE9\x53\x31\xDD\x3A\x6E\xEF\x87\xFF\xE8\x90\xF3\x0C\x02\x90\x85\x24\xD5\xB6\x48\x27\xD2\x7F\xEB\x65\xC6\xA2\x2F\xF1\xBF\xD2\xF6\x34\xD5\x9B\xBA\x04\xA8\x09\xDA\x40\x5E\xFD\x3E\xDA\x43\x38\x75\x48\x74\xBD\xFB\xFA\x1C\x7F\xE2\x0D\x34\x7C\x36\xCF\x89\xD5\xE0\x8E\x86\x34\x61\x91\xB9\x51\x43\x20\xF3\xDB\x05\xE1\x37\x71\xCD\x29\x9E\x9B\x9A\x03\x88\x0D\x26\x82\x95\x5F\x81\xD4\xB3\xED\xE9\xC0\x05\xE2\xC2\xF0\xE5\x42\xE0\xF8\xF8\x89\x4D\x9D\x76\x68\xEF\xB5\xB5\x9C\xD6\x73\x07\xB1\x52\x2C\xED\xC5\x95\xD1\x86\x30\x25\xFE\x3C\xD2\x76\x9F\x3A\xB5\x56\xF7\xB8\x26\x94\xEE\x34\x70\x7E\xA9\x93\x61\xF9\x61\xCE\xF8\x45\xD5\x02\x1E\xFF\x91\xFF\xA3\x44\xF9\xF2\xD4\xDD\xBF\xBD\x6A\x8F\x78\x45\x3E\x30\x8A\xB4\xCE\x5A\x30\x90\xC8\x82\x84\x00\x78\x64\x7E\xA6\xF8\x35\xD5\xBF\x7D\x14\xF7\x5A\xCB\x3F\x49\x9B\x8E\x79\x55\x47\x6A\xAA\x78\xAF\x7F\x9D\x70\x9A\xCE\xC6\xE6\x5C\xD7\xD6\x34\x0A\x24\x6D\x46\xF4\x6F\xFB\xE7\x9C\x0B\xE3\x45\x52\x43\xC2\x44\xCB\xFC\x1F\x82\xC6\xFA\x9A\x28\x3A\x79\x89\x9B\xED\xD2\xC0\xE7\x0A\xDB\x81\x6D\x4D\xEB\x78\x7A\x68\xC3\x36\x01\xE3\x22\x9A\x25\x0D\x9D\x9E\xAF\xF1\xFA\xDA\x40\xA9\xBC\xA5\x77\xB6\x40\x88\x3F\x77\xE4\xCC\xAA\xE6\x65\x9F\x37\x82\x62\xE1\x45\xFF\xC2\x6A\x5F\x4B\xFC\x84\xB3\xE9\x42\x1C\x61\xDA\x5C\x9D\xC5\x61\x1C\x0F\x74\x6D\xBC\x05\x26\x32\x9F\x97\x8F\x50\xFE\xED\x8C\x36\x41\x99\x30\x8F\x6D\xDA\x6A\x99\x62\x50\x8D\x88\xD6\x45\xFB\xEE\x86\xF0\x23\x99\xB9\x20\xCD\xF0\xEC\x1B\xF8\x67\xB8\xDC\x35\x22\xC6\x48\x07\x7F\x93\xB5\x4E\x8E\x81\x98\xB2\x47\x4B\x58\x72\x5D\xCE\xBF\x23\x8D\x33\x2A\x43\x13\x75\xF3\xFF\x1C\x23\xCD\xBE\x96\x0B\x0C\xDA\x2A\x04\x94\xEA\x5D\x1D\x44\x42\x8F\x5B\x1A\x19\x61\x79\x45\x5B\x0A\xA8\x29\xD8\xB2\x82\x77\x5F\x0E\xAC\x92\xF7\xD0\xDE\xB3\x78\xD8\xEF\xBB\x51\x1C\xD9\xD2\xC7\xCC\x16\xF8\x2E\x0C\x43\xC1\x9B\x51\xE3\xF9\x80\xF9\xBF\x09\x19\xB8\xFD\xD6\x3B\xA1\xAE\xFB\xE4\xD6\xC5\x93\x95\xC6\x3A\xE9\x7B\x69\xDA\x21\xF5\x7C\x29\x22\x6C\x6F\x21\x28\xC9\x12\x7E\x95\x86\xFC\x63\x36\xA2\xA0\x08\x54\xA8\x44\xD9\x0A\x3F\xB0\x73\x59\xDF\xE3\x3E\x27\x6A\x8B\x70\x48\xEF\x8B\x38\xD9\xD1\x15\x04\x0F\x71\xB1\x36\x60\x39\x54\x26\x9E\x2B\xE4\x0C\xEE\xBE\xF3\x2B\x1A\x4D\xD1\xF5\x9C\xF8\x79\xA5\x43\xA9\x34\xBE\x9D\x39\xF9\xC9\xF2\x2A\x35\x40\x32\x38\x64\x6F\xE7\x0A\xE8\x72\x4A\xE4\xDB\x3E\x48\x90\xF7\xB7\xB2\x33\xA0\xAA\x8C\x60\xB2\x2B\x52\x22\x7D\xC3\xBA\x9E\xF5\x1D\xD9\x3B\xC6\xFF\x26\x69\xBD\xF3\xC8\x5A\x58\x8A\x21\x7C\x53\x22\xD7\x89\x1D\xB8\x4A\xEF\x4F\x04\x05\x1A\x18\xA6\x67\x6C\x00\xAA\xEB\x71\xEC\x2D\xFC\x4E\xE1\xF8\x0E\x16\x65\xAF\x04\x81\x27\xA6\x51\xFA\x81\x66\x88\x1B\xAA\xFD\xCB\x18\xE9\x30\xF8\xFB\x94\x63\x88\xD8\xF0\x10\x72\xF3\xA5\x0B\x18\xCD\x7F\xD8\x6F\x43\x0D\x67\xE3\xCE\x7D\xAD\x7B\x6A\x01\x21\xA1\x73\xA3\x6C\xE9\x91\xA7\xCC\x78\x70\xC5\x09\xB6\x1F\x08\x82\x9A\x70\x0A\x80\xFE\x30\x01\x24\x61\x4C\x91\xF4\xB9\xF8\x80\xF9\x49\xD1\x7A\xF7\xB2\x68\x7D\xD9\x49\x74\x64\x42\xD8\x7B\x78\x21\x5F\x9E\xC7\x3A\x64\x12\x6E\x1D\x58\x6F\xBA\x0D\x7D\x50\x90\xAF\x2C\x25\x14\x48\x46\xC4\x32\x51\x6C\x8C\xFA\x3A\x8B\xE7\xAD\xC2\xA2\x19\x3B\x74\x72\xAC\x43\xFA\xA6\x9B\x1F\x43\xE0\x3D"

get NAME filename
string NAME l= NAME #NAME to smallcase

get SIZE asize

putvarchr MEMORY_FILE SIZE 0 #pre allocate
log MEMORY_FILE 0 0

#####################################################
strlen LEN NAME #genarates the offset of the xor_key
set NAME_START NAME
set TEMP LEN
math TEMP -= 4
string NAME_START >= TEMP
set SUM LEN
math SUM *= 0x1EEF
getvarchr TEMP NAME_START 0 long
math SUM += TEMP
for i = 0 < LEN
    getvarchr TEMP NAME i byte
    math TEMP *= 0x2F
    math SUM += TEMP
next i
math SUM %= 0x3CB
print "offset: %SUM|h%";
#####################################################
# The decryption of the rot encrypt 
set NAME_TEMP NAME

for i = 0 < LEN
    set TEMP 0
    getvarchr TEMP NAME_TEMP i byte
    math TEMP += 0x01
    putvarchr NAME_TEMP i TEMP byte
next i
print "KEY_ROT: %NAME|h%"
print "KEY_ROT: %NAME_TEMP|h%"
encryption "rot" NAME_TEMP

log MEMORY_FILE 0 SIZE
encryption "" ""

print "KEY_XOR offset: %SUM|h%"
print "KEY_XOR : %XOR_KEY|h%"

#####################################################
# The decryption of the xor encrypt 
set POS SUM
for i = 0 < SIZE
    math POS %= 0x3CB

    getvarchr TEMP MEMORY_FILE i
    getvarchr KEY  XOR_KEY     POS
    math TEMP ^= KEY
    putvarchr MEMORY_FILE i TEMP
    math POS += 1
next i

log NAME 0 SIZE MEMORY_FILE
#####################################################


after that, extract the archive with that script:
Code: Select all# extracts the .dat files from Shadow Vault (http://www.gamespot.com/shadow-vault)
# (c) 18/12/2013 by dniel888
# script for QuickBMS http://quickbms.aluigi.org

idstring "DATA"
get files long
get dummy longlong

set START_POINT 40 # each file take 32+4+4
math START_POINT *= files
math START_POINT += 0x10 # first line

for i = 0 < files
    get OFFSET long
    math OFFSET += START_POINT
    
    get SIZE long
    getdstring NAME 0x20
    
    log NAME OFFSET SIZE
    
next i

then, extract the GXL(Graphics library) format with this script:
Code: Select all# extracts the .gxl files from Shadow Vault (http://www.gamespot.com/shadow-vault)
# (c) 18/12/2013 by dniel888
# script for QuickBMS http://quickbms.aluigi.org

get UNK long
idstring "GFXL"    # Graphics library
get FILES long

get NAME1 long
get UNK long
get UNK long
get OFFSET1 long
get UNK long

math FILES -= 1 # for the first file

for i = 0 < FILES
    get NAME2 long
    get UNK long
    get UNK long
    get OFFSET2 long
    get UNK long
    
    set SIZE OFFSET2
    math SIZE -= OFFSET1
    
    string NAME1 += ".gfx"
    log NAME1 OFFSET1 SIZE 
    
    set OFFSET1 OFFSET2
    set NAME1 NAME2
next i

get SIZE asize
math SIZE -= OFFSET1

string NAME1 += ".gfx"
log NAME1 OFFSET1 SIZE


for the gfx files, I have created a viewer: 
download : https://mega.nz/#F!48sk2YpA!7dPnIj1HaXJ3tR-IRWVqOw
virus scan: https://www.virustotal.com/file/f074525 ... 419171768/


Hello, I tried using the gxl script but it showed me an error. How can I fix it?
- signature of 4 bytes at offset 0x00000004 doesn't match the one
  expected by the script:
  this one: ""
  0e 00 06 00                                       ....
  expected: "GFXL"
  47 46 58 4c                                       GFXL
- 0 files found in 0 seconds
  coverage file 0     1%   8          688        . offset 00000008

Here's the file that I wanted to extract: https://mega.nz/file/tzd3nZgR#AKVZIhPv9 ... fhTohEdsuM
The file that you sent is not in the same format of the GFXL files of the script. You can see that it has a different signature "GXL" at the start.
## Post #16
- Username: Kazumadesu
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 06, 2023 5:53 pm
- Post datetime: 2023-09-06T14:19:24+00:00
- Post Title: Re: Need help with Shadow Vault .dat .gxl archive

Oh, thank you
