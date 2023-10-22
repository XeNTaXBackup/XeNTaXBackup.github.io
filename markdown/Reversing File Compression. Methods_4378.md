## Post #1
- Username: Cyrem
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 18, 2010 12:38 pm
- Post datetime: 2010-04-24T02:22:06+00:00
- Post Title: Reversing File Compression. Methods?

So I have this compressed data file, I've done many searches on it (extension is GTC) and google runs me dry as I can get hardly anything in the search results when I search for this extension. This file begins with a whole block of 0's and there are two other files named "COMPRESS.INF" and "FILELIST.INF" with it.

So my question is, where do you start when trying to figure out a compression that seems to be unique to a game? What do you do? What programs do you use to assist you?
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-24T10:40:26+00:00
- Post Title: Reversing File Compression. Methods?

I can tell you what I do personally.

first I check if there is a zlib or deflate data in it using offzip -S and -z 15 (default) the first time and -z -15 the second one.

then I try to see if I can find the exact point where starts the raw compressed data, maybe I see something like a signature and a compressed and decompressed size fields.
when I find the possible starting of the data I launch quickbms with the comtype_scan2.bat on it:

```
quickbms comtype_scan2.bat comtype_scan2.bms compressed_file output_folder [decompressed_size_if_available]
```
(in case you are interested the needed files are located [here](http://aluigi.org/papers/bms/comtype_scan2.bat) and [here](http://aluigi.org/papers/bms/comtype_scan2.bms)

if after the process (many crashes and a couple of endless loops) I see no good results I start with the manual debugging.

note that the choice if doing first the manual debugging or comtype_scan2 depends by how looks the compressed data or if I'm unable to find where the compressed block starts.

if, after the debugging, I find the decompression function but I'm too lazy or unable to reverse it I simply dump the whole function and use it directly in quickbms with the calldll command.
## Post #3
- Username: Cyrem
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 18, 2010 12:38 pm
- Post datetime: 2010-04-24T13:25:50+00:00
- Post Title: Reversing File Compression. Methods?

> Reply from aluigi
>
> I can tell you what I do personally.

first I check if there is a zlib or deflate data in it using offzip -S and -z 15 (default) the first time and -z -15 the second one.

then I try to see if I can find the exact point where starts the raw compressed data, maybe I see something like a signature and a compressed and decompressed size fields.
when I find the possible starting of the data I launch quickbms with the comtype_scan2.bat on it:
Code: Select allquickbms comtype_scan2.bat comtype_scan2.bms compressed_file output_folder [decompressed_size_if_available](in case you are interested the needed files are located here and here

if after the process (many crashes and a couple of endless loops) I see no good results I start with the manual debugging.

note that the choice if doing first the manual debugging or comtype_scan2 depends by how looks the compressed data or if I'm unable to find where the compressed block starts.

if, after the debugging, I find the decompression function but I'm too lazy or unable to reverse it I simply dump the whole function and use it directly in quickbms with the calldll command.

Thank-you for something to get started on!

Even though I tried both those two applications, they both turn up with an unknown compression format. When you say manual debugging do you mean with a debugger program to hook onto the game?

I'm not very good with Assembly, but I have RecStudio which makes things a tad more understandable. I would upload the file but it's over 100mb.

Also, looking at the file more there seems to be uncompressed blocks inside the file. These blocks have a file path in it, however these paths are not in the "FILELIST.INF" file that I mentioned before.

If anyone else has some ideas, please go ahead and mention them.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-24T20:06:28+00:00
- Post Title: Reversing File Compression. Methods?

with manual debugging I mean just using ollydbg and the usual steps:
- bp CreateFileW
- bp ReadFile
- hw bp on the read memory
- following all the instructions performed on the memory and if they are done by one single function (good for ripping it)

recstudio could be useful only in the last stage of the job when you have already arrived to the function that performs the decompression work.
but if the function is too long is better to rip it directly then spending lot of time trying to reversing it.

judging the name of the files and the fact that filelist.inf contains some names seems just that you are in front of an index file (filelist.inf) and the raw container of the compressed files (compress.inf).
so the first one contains the info about where are offset and the compressed/uncompressed size of the files stored in the second one
## Post #5
- Username: Cyrem
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 18, 2010 12:38 pm
- Post datetime: 2010-04-24T23:47:02+00:00
- Post Title: Reversing File Compression. Methods?

> Reply from aluigi
>
> with manual debugging I mean just using ollydbg and the usual steps:
judging the name of the files and the fact that filelist.inf contains some names seems just that you are in front of an index file (filelist.inf) and the raw container of the compressed files (compress.inf).
so the first one contains the info about where are offset and the compressed/uncompressed size of the files stored in the second one

I will have a look into that.

I don't really know how to use olly, however I did find some stuff that may help. I'm not sure if I am allowed to post the extract here though.

But if you get a copy of "LEGO Racers 2.exe", and go to location "004A45AD", you'll see what I mean because under there you'll see commands "CreateFileA", "FileSetPointer", "ReadFile" and some ASCII strings "sCompressedChunkInfo array" and "Compressed data buffer".

Cheers.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-25T01:11:38+00:00
- Post Title: Reversing File Compression. Methods?

yeah I see but the steps remain the same said before
## Post #7
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2010-07-04T14:49:46+00:00
- Post Title: Reversing File Compression. Methods?

Hi aluigi, thanks for the general tips.  Your comtype scans are very useful.  I have one question, how do I know which algorithm number equals which ComType?
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-07-04T15:23:20+00:00
- Post Title: Reversing File Compression. Methods?

very simple, open the file quickbms.c (it's located in the src folder) and at about line 374 you will notice a list of COMP_* strings with a number at right each 5 lines.
that one is the number you must look at, so if you have the file 22.dmp that is correctly unpacked then it means the game uses the Xmemdecompress algorithm (COMP_XMEMLZX)
