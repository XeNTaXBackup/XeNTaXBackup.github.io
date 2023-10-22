## Post #1
- Username: mnrhacker
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 21, 2021 3:42 pm
- Post datetime: 2021-12-21T07:58:08+00:00
- Post Title: QCMP (QuickCompression) - Mod Nation Racers (PS3)

I'm trying to decompress the track files from ModNation Racers (PS3 kart game).

When I open the .TRK files in a hex-editor I see the following hex:

```
...
```

Where the first four would decode to 

```
QCMP
```


There is an old thread about Sleeping Dogs (on this forum) and a github repo that deals with decompression of QCMP. And QuickBMS has a script/plugin to decode/decompress QCMP files but when I try it I get the following error:

```
--------------------------------------
  00000040 1170056    000A0199_SUZUKUCITYMKIII_unpack.TRK

Error: the compressed zlib/deflate input is wrong or incomplete (-3)
Info:  algorithm   1
       offset      00000040
       input size  0x0004ef10 323344
       output size 0x0011da88 1170056
       result      0xffffffff -1

Error: uncompressed data (-1) bigger than allocated buffer (1170056)
       It usually means that data is not compressed or uses another algorithm

Last script line before the error or that produced the error:
  20  clog NAME dataOffset compressedSize uncompressedSize

- OFFSET       0x00000040
- ZSIZE        0x0004ef10
- SIZE         0x0011da88
  coverage file 0    99%   323384     323408     . offset 0004ef50

Press ENTER or close the window to quit
```


Is QCMP just zlib compressed streams? I tried to decompress them using Python but got various error messages.

Does anyone have any idea how to proceed?
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-12-22T00:05:46+00:00
- Post Title: QCMP (QuickCompression) - Mod Nation Racers (PS3)

I've looked into these files a bit previously, still a long way to go on them though because of all the file IDs referring to other files, etc.

Basically, "QCMP" is the start of the header for each compressed file.  This is usually a header of 0x40 bytes, then the compresssed data starts.  Offset 0x14 after "QCMP" is the compressed size (subtract 0x40 to get actual compressed size), and offset 0x1c is the decompressed size.

Sounds like your script is trying to use deflate still.  You need to set ComType QCMP in your script to tell QuickBMS what decompression method to use.
## Post #3
- Username: mnrhacker
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 21, 2021 3:42 pm
- Post datetime: 2021-12-22T07:23:35+00:00
- Post Title: QCMP (QuickCompression) - Mod Nation Racers (PS3)

Thanks for the reply.
This is the script from the QuickBMS site:

```

quickbmsver "0.8.5"

get NAME basename
get EXT extension
string NAME + "_unpack."
string NAME + EXT

endian big
idstring "QCMP"
get type short      # 1
get version short   # 1
get dataOffset long
get extraSize long
get compressedSize longlong
get uncompressedSize longlong
get uncompressedHash longlong
math compressedSize - dataOffset
clog NAME dataOffset compressedSize uncompressedSize

```


After adding ComType QCMP befor clog NAME ... it actually managed to unpack the file properly. The compressed size and uncompressed size are there and correct. Let's see how far I get.
