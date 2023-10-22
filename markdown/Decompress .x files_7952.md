## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-29T03:20:03+00:00
- Post Title: Decompress .x files

I tried writing a bms script for this but am not getting it right.

According to some docs, if the header says bzip then it's a "MSZip Compressed Binary File"
The header is 16 bytes long, followed by a long that represents the decompressed size.

I don't know what compression that is though.
Some samples
[obj.7z](https://xentaxbackup.github.io/file/4934_obj.7z)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-29T03:58:51+00:00
- Post Title: Decompress .x files

you have the size wrong.
the format goes
0x10 Header
0x4 Total Uncompressed size
then you have chunks till you fill the size
0x2 uncompressed size
0x2 compressed size
data
this repeats till you fill the first size
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-29T04:03:15+00:00
- Post Title: Decompress .x files

OH. Hmm. That's pretty complicated.
I wonder if this applies to all bzip formats or whether this is proprietary as well, since the company provided their own converter. I'll have to look at more files from other games.

What's the compression?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-29T04:05:43+00:00
- Post Title: Decompress .x files

you can just try these tools here
[http://openbve.freeforums.org/compresse ... -t125.html](http://openbve.freeforums.org/compressed-x-is-not-intended-to-be-supported-t125.html)
then the next 2 bytes are ignored and you use the inflate compression.

just use offzip.exe -a -z -15 to see where it starts and stuff.

if you need help with a script let me know but it should be easy now.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-29T04:36:57+00:00
- Post Title: Decompress .x files

Offzip worked for the small files but it prints a lot of errors for this one:
[G_dragon.7z](https://xentaxbackup.github.io/file/4936_G_dragon.7z)
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-31T11:42:16+00:00
- Post Title: Decompress .x files

this type of file has been already discussed here on xentax, use google with the following keywords:
"xof" site:xentax.com
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-31T14:23:53+00:00
- Post Title: Decompress .x files

4 topics came up, but none of them seem to talk about how the compression works.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-31T17:54:32+00:00
- Post Title: Decompress .x files

here is a lot of info with source code to .x file parser
[http://www.xbdev.net/3dformats/x/xfileformat.php](http://www.xbdev.net/3dformats/x/xfileformat.php)
[http://user.xmission.com/~legalize/book ... 0Files.pdf](http://user.xmission.com/~legalize/book/download/21-X%20Files.pdf)
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-10T17:40:41+00:00
- Post Title: Decompress .x files

these files load into deep exploration after they are decompressed with this script.
[viewtopic.php?f=21&t=9064](http://forum.xentax.com/viewtopic.php?f=21&t=9064)

what game is it?
## Post #10
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2012-06-19T16:03:07+00:00
- Post Title: Decompress .x files

I am very interested in this subject too

so i wrote a 010 editor binary template for standard .cab files :

```
byte signature[4];
ulong reserved1;
ulong cbCabinet;
ulong reserved2;
ulong coffFiles;
ulong reserved3;
ubyte versionMinor;
ubyte versionMajor;
ushort cFolders;
ushort cFiles;
ushort flags;
ushort setID;
ushort iCabinet;
}check;

struct CFFOLDER {
ulong coffCabStart;
ushort cCFData;
ushort typeCompress;
}check;

struct CFFILE {
ulong cbFile;
ulong uoffFolderStart;
ushort iFolder;
DOSDATE date;
DOSTIME time;
ushort attribs;
byte szName[];
}check;

struct CFDATA {
ulong csum;
ushort cbData;
ushort cbUncomp;
byte ab[cbData];
}check;


```


reference : [http://msdn.microsoft.com/en-us/library/bb417343](http://msdn.microsoft.com/en-us/library/bb417343)


OUTPUT :

```
======================================================================================                                                                             
byte signature[4]                        MSCF                 0               4
ulong reserved1                          0                    4               4
ulong cbCabinet                          356                  8               4
ulong reserved2                          0                    12              4
ulong coffFiles                          44                   16              4
ulong reserved3                          0                    20              4
ubyte versionMinor                       3                    24              1
ubyte versionMajor                       1                    25              1
ushort cFolders                          1                    26              2
ushort cFiles                            1                    28              2
ushort flags                             0                    30              2
ushort setID                             0                    32              2
ushort iCabinet                          0                    34              2
                                                                             
ulong coffCabStart                       67                   36              4
ushort cCFData                           1                    40              2
ushort typeCompress                      1                    42              2
                                                                             
ulong cbFile                             1024                 44              4
ulong uoffFolderStart                    0                    48              4
ushort iFolder                           0                    52              2
DOSDATE date                             06/19/2012           54              2
DOSTIME time                             19:18:34             56              2
ushort attribs                           32                   58              2
byte szName[7]                           sparse               60              7
                                                                             
ulong csum                               360354650            67              4
ushort cbData                            281                  71              2
ushort cbUncomp                          1024                 73              2
byte ab[281]                             CK...                75              281


```


but when i tried to write its corresponding QUICKBMS script for extraction of compressed date , i can't use "comtype command" of QUICKBMS !
even by testing lzxcab , cabextract , ... compression algorithms !
PLEASE HELP ME ?

also the attachment contains : makecab.exe and expand.exe , 010 editor binary template , samples .

DirectX File Format Architecture :
[http://local.wasp.uwa.edu.au/~pbourke/d ... s/directx/](http://local.wasp.uwa.edu.au/~pbourke/dataformats/directx/)
[cabinet.zip](https://xentaxbackup.github.io/file/5500_cabinet.zip)
## Post #11
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2013-03-12T20:52:19+00:00
- Post Title: Decompress .x files

very good news ! now quickbms supports decompression of mszip ... I hope Luigi Auriemma live a thousand years !
by this way i wrote the equivalent BMS script of my previous 010 binary template for cabinet files: 

```

idstring "MSCF"
get signature long
get reserved1 long
get cbCabinet long
get reserved2 long
get coffFiles long
get reserved3 long
get versionMinor byte
get versionMajor byte
get cFolders short
get cFiles short
get flags short
get setID short
get iCabinet short
get coffCabStart long
get cCFData short
get typeCompress short
get cbFile long
get uoffFolderStart long
get iFolder short
get date short
get time short
get attribs short

get szName string

get csum long
get cbData short
get cbUncomp short

savepos offset
clog UNCAB offset cbData cbUncomp 
```


and this is my quick and dirty script for decompressing (demoting degree of) .x files
wonderful that we can use it in batch processing of many .x files simultaneously 

```

idstring "xof "
getdstring major 2
getdstring minor 2
getdstring type 4
getdstring floatsize 4
get skip 4
get unzip short
get zip short

savepos offset
clog demote offset zip unzip
```
