## Post #1
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-21T14:10:43+00:00
- Post Title: ZLib, deflate, splitted output data

Hi, is there somebody who knows how to use zlib deflate to generate many independent files from one output data? Like split files for rar to part01, part02, etc. but independent.

I want to get data and deflate them to fixed size blocks with defined size BUT every deflated block must be zlib file. So I can extract part1 or part5 without need to have other parts.

For example:
1) Set output length to 100000 (set avail_out to this size)
2) Get full output buffer and save it to file
3) Call deflateEnd() and avoid errors because of not end of input data
4) Continue to 2

So I don't want to get whole compressed stream and split it to files, but force deflate to create many output files until there are data on input. Then you can simply extract all files and merge them to original one. There is no problem in avail_out size, deflate method automaticaly fills output buffer to max, but how to stop it now and continue with other data on infut without getting error in deflateEnd? Is there any way how to set avail_in to 0 and stop compression? What exactly deflateEnd() do?

Thnx for any help.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-22T16:09:36+00:00
- Post Title: ZLib, deflate, splitted output data

doing it with QuickBMS is really a joke:

```
# script for QuickBMS http://quickbms.aluigi.org

get NAME filename
comtype zlib_compress
set CHUNK_SIZE long 100000  # size of the splitted chunks
get FULLSIZE asize
math CHUNKS = FULLSIZE
math CHUNKS /= CHUNK_SIZE
for i = 0 < CHUNKS
    callfunction ZDUMP 1
next i

math CHUNKS *= CHUNK_SIZE
math FULLSIZE -= CHUNKS
if FULLSIZE > 0
    math CHUNK_SIZE = FULLSIZE
    callfunction ZDUMP 1
endif

startfunction ZDUMP
    set FNAME string NAME
    string FNAME += ".part"
    string FNAME += i
    savepos OFFSET
    clog FNAME OFFSET CHUNK_SIZE CHUNK_SIZE
    math OFFSET += CHUNK_SIZE
    goto OFFSET
endfunction
```
## Post #3
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-22T16:17:28+00:00
- Post Title: ZLib, deflate, splitted output data

That's not what I want. This scripts splits input file to 100k parts then deflate them. But I want algorithm, that gets as many bytest from input to produce 100k zipped files. 

I found fitblk.c example in zlib126.zip archive and there is 3 steps method. It seems to be only way how to do it.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-22T16:31:20+00:00
- Post Title: ZLib, deflate, splitted output data

in that case you must perform a one-byte-at-time compression or avail_in at max filesize and avail_out at 100000.
I can't help more because I should write the tool from scratch to do it.
