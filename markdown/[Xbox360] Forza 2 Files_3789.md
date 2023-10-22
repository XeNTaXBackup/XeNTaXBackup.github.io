## Post #1
- Username: Patriot
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Oct 05, 2009 12:37 am
- Post datetime: 2009-10-16T22:43:14+00:00
- Post Title: [Xbox360] Forza 2 Files

Forza 2 user files seem to be compressed and I can't figure out the format. There appears to be a null terminator for every file at the end of the compressed block.

.liv struct

```
int32 decompressedlen
byte  data_compressed[compressedlen]

```


.xdc struct

```
int32 compressedlen
int32 decompressedlen
byte data_compressed[compressed]

```

[Forza2Files.zip](https://xentaxbackup.github.io/file/2456_Forza2Files.zip)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-16T22:57:46+00:00
- Post Title: [Xbox360] Forza 2 Files

it contains a classical deflated block but it's not at a fixed position.
for example in 71.liv it's at offset 8, in 79.liv at offset 7 and in Thumbnail_1.xdc at offset 0x17 so it's probably necessary to use offzip (with -z -15) or a similar tool to unpack the files
## Post #3
- Username: Patriot
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Oct 05, 2009 12:37 am
- Post datetime: 2009-10-16T23:13:00+00:00
- Post Title: [Xbox360] Forza 2 Files

I receive an error using offzip.

"zlib initialization error"

I also tried to code an app using deflate and I get an error there too.

Actually, I don't quite understand how to use offzip. I get a lot of errors.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-16T23:25:19+00:00
- Post Title: [Xbox360] Forza 2 Files

I have used:
offzip -a -z -15 c:\71.liv c:\ 0
## Post #5
- Username: Patriot
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Oct 05, 2009 12:37 am
- Post datetime: 2009-10-16T23:27:44+00:00
- Post Title: [Xbox360] Forza 2 Files

I receive 
"- open input file :           -15 "
"Error : No such file or directory"

I am using version 0.3.3 from [here](http://aluigi.altervista.org/mytoolz/offzip.zip)
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-16T23:51:57+00:00
- Post Title: [Xbox360] Forza 2 Files

recheck the arguments and the spaces between them, seems that you have missed one:

```
offzip -a -z -15 c:\71.liv c:\ 0
```
## Post #7
- Username: Patriot
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Oct 05, 2009 12:37 am
- Post datetime: 2009-10-17T00:02:07+00:00
- Post Title: [Xbox360] Forza 2 Files

ok thanks a lot


How would i go about implementing that into my own app? As in which functions in the source would i use?
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-17T12:39:49+00:00
- Post Title: [Xbox360] Forza 2 Files

it's a scanning function so it's not that easy to implement like calling one function.
you should call inflate various times with the sequential data taken from the file so read the zlib manual for all the details
