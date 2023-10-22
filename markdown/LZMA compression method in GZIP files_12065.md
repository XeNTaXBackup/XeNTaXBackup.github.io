## Post #1
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-08T15:10:15+00:00
- Post Title: LZMA compression method in GZIP files

Someone sent me some new 2k15 archives to work on and try to extract anything from them.

I located some zip headers and managed to parse some zip files from it but there are some other issues which i don't fully understand.

I found this (which is repeated again many times in the archive)



The first 2 bytes indicate a gzip header, but then the compression is 0x0E. Gzip as far as i know comes only with deflation method which is noted with 0x08. How the heck is this 0x0E there? Because of the zip parsing i found out that they use LZMA for the file compression and the method is noted with 0x0E in the local zip header.

I've tried decompressing raw data using python lzma libraries and with zlib as well, but nothing worked.


Does any "guru" have any idea about what the heck may be happening?
## Post #2
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-10-08T15:21:24+00:00
- Post Title: LZMA compression method in GZIP files

(Duplicate, my mouse fucked up. Please ignore.)
## Post #3
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-10-08T15:21:24+00:00
- Post Title: LZMA compression method in GZIP files

LZMA requires some encoder properties before it will decompress. With 7-Zip, they store it as 5 bytes. So if they're using the 7-Zip LZMA SDK, you'll need to find those 5 encoder properties bytes before you can do anything.
## Post #4
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-08T16:11:13+00:00
- Post Title: LZMA compression method in GZIP files

> Reply from GMMan
>
> LZMA requires some encoder properties before it will decompress. With 7-Zip, they store it as 5 bytes. So if they're using the 7-Zip LZMA SDK, you'll need to find those 5 encoder properties bytes before you can do anything.

Should i pass those excplicitly in the decompressor? or the decompressor reads them implicitly at the start of the stream?



Check this

This is from a zip archive that i managed to get out and successfuly decompress it with winrar.

This is the whole local header of the first file of the archive and you can clearly see that VERY SAME SEQUENCE HERE AS WELL: 0x091605005D then ALWAYS comes this 0x00000001 which could be something like a dictionary size?? and the first 0x09 0x16 0x05 0x00 0x5D be the encoding properties you are talking about?

I tried with decompressing the stream starting from this 091605 etc but i got an error
## Post #5
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-08T18:26:49+00:00
- Post Title: LZMA compression method in GZIP files

I think i got it working using a wrapper for the LZ SDK, using the decomppress_compat function and passing in the data starting from 5D, i guess there is where the options start 

I got some weird textures from the files though :S



I'm not asking about what is going on with the texture (i'll ask on the correct section )

But my question is, can that decompression produce corrupt decompression data? The dds header is perfect structured, but the image is very very weird, so i am wondering what could have gone wrong :S I just want to make sure that the decompression has worked.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-10-08T19:02:30+00:00
- Post Title: LZMA compression method in GZIP files

QuickBMS already supports lzma in gzip files, you can try:

```
get SIZE asize
clog "dump.dat" 0 SIZE SIZE
```
## Post #7
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-08T19:43:28+00:00
- Post Title: LZMA compression method in GZIP files

> Reply from aluigi
>
> QuickBMS already supports lzma in gzip files, you can try:
Code: Select allcomtype gzip
get SIZE asize
clog "dump.dat" 0 SIZE SIZE

Yeah it worked as well, the file was exactly the same size, and (unfortunately) looked exactly the same way. So i guess LZMA decompression worked like a charm in both cases
