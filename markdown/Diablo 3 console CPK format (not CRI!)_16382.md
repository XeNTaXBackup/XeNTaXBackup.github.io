## Post #1
- Username: P@S@f
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Feb 23, 2011 7:33 pm
- Post datetime: 2017-06-09T18:57:59+00:00
- Post Title: Diablo 3 console CPK format (not CRI!)

In console version of Diablo 3 Blizzard used own format of archives. Extension of archives is CPK and they located at CPKs folder, but it is not CRI-CPK format.
Signature of archive is \xA1 \xB2 \xC3 \xD4 and there is also second part I think it is version of format or at least could be part of signature: \x00 \x00 \x00 \x06.
At least archive where cutscenes stored goes without any compression/encryption, since video stored in ogv format bounds of files could be easily determined by signature (OggS, theora, etc).
But header format is complicated. I was not able to find any clear values except of files count @ 0x14.
There is also plain list of filenames which order doesn't match the order of files placement in archive (at least in Cutscenes archive files stored in alphabetical order).

Results of my research:

```
DWORD dwSignature = A1 B2 C3 D4
DWORD // 00 00 00 06 always - version? part of signature?
QWORD qwSize // in Cutscenes it is size of archive from start of files (0x10000) in other archives - not
DWORD // 00 00 00 02 everywhere except Cutscenes (00) - level of compression? encryption indicator?
DWORD dwFilesCount // number of files in archive
DWORD // everywhere except cache archives = dwFilesCount
DWORD // some small number, in Act1-4 = 01
DWORD // another small number, in localization archives (xxXX_Act1-4, e.g. enGB_Act1) = 12-13
DWORD // in most cases = 01, cache archives = 08 / 07, Common = 02
DWORD // small number in range 16-1F
DWORD // equals previous
DWORD // small number in range 00-0F
DWORD // some value (not offset/size)
DWORD // always null (00 00 00 00)
DWORD // unknown value (not offset/size)
DWORD // unknown value (not offset/size)
DWORD // unknown value (not offset/size) seems like little endian
DWORD // unknown value, in cache small number in other archives - big
...
```
Next goes some structure or table or/of hashes, I don't know, size of this area depends on number of files stored in archive (more files - bigger size), which is separated from list of filenames with some set of dwords nearly similar to arithmetic series (arithmetic progression) with shift, differ from archive to archive (for example : 00, 2C, 5A, 89, B1...). Size of this set is equals to number of files stored in archive. After filelist there is blank area filled with zeroes (not fixed size, differ from archive to archive) and finally then goes the files themselves (till the EOF of archive).

Both known values (FilesCount and Size in Cutscenes) is big endian.

Here is the smallest archive example: [example.cpk](http://xww.ro?http://www.mediafire.com/file/3xjxxyrr6a3rw4m/archive.unk) (1 Mb)
Rest of archives (including Cutscenes (~1.1Gb) and CacheAct (smallest - 200 Mb) archives): PM if you need it
Default.xex (if anyone skilled in reversing Xbox binaries, I'm - not): PM me
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-06-11T01:24:58+00:00
- Post Title: Diablo 3 console CPK format (not CRI!)

in your archive.unk sample the first part after header looks obfuscated to me, i can't find a pattern.   
the next part which at 0xa0a9 begins a table of relative offsets for the file names starting at 0xcc41,
big-endian
0x00 = 0xcc41
0x2a = 0xcc6b
0x4e = 0xcc8f
etc

the data likely starts at 0x30000 and it looks zlib compressed with "78 DA" identifier
for i
----2bytes - size of uncompressed data
----2bytes - unk
----2bytes - size of compressed data
----2bytes - "78 DA" identifier
----compressed data
next

you can extract the files using offzip until a better solution is comes around.
## Post #3
- Username: P@S@f
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Feb 23, 2011 7:33 pm
- Post datetime: 2017-08-31T07:33:55+00:00
- Post Title: Diablo 3 console CPK format (not CRI!)

Solution still not came 
This is what my bookmarks in Hex Workshop looks like so far:

(Content.cpk)
I've tried look into XEX, but couldn't clearly understand what happens in archive read function, some complicated operations performed with header like

```
v36 = ((unsigned __int64)(*(__int64 *)((char *)&v33 - 4) >> 13) >> 50) + v27 + 0x3FFF;
```
which I couldn't understand (I even can't tell which variable what place represent).
I've also tried with xenia, but its debug capabilities limited.
Any help welcome.
## Post #4
- Username: warrantyvoider
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 03, 2016 9:13 pm
- Post datetime: 2017-12-01T18:40:44+00:00
- Post Title: Diablo 3 console CPK format (not CRI!)

[https://github.com/zeroKilo/CPKReaderWV](https://github.com/zeroKilo/CPKReaderWV)

for anyone looking, the header infos contain bitsizes of fields in the following blocks, so thats why it was hard to guess

greetz WV
## Post #5
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2023-07-01T15:21:17+00:00
- Post Title: Diablo 3 console CPK format (not CRI!)

switch [https://github.com/GoobyCorp/D3Edit/blo ... act_cpk.py](https://github.com/GoobyCorp/D3Edit/blob/master/Research/extract_cpk.py)
