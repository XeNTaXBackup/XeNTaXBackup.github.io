## Post #1
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-21T18:39:50+00:00
- Post Title: SWF lzma decompression

I ran into a bit of trouble trying to extract resources from some flash files. Both Flash Decompiler Trillix and Sothink SWF Decompiler said the files are corrupt.
Turns out they just use lzma compression, implemented in SWF version 13. So here's a little script for decompression:

```
get VERSION byte
get SIZE long   #uncludes first 8 bytes; quickbms finds uncompressed size automatically
get ZSIZE long
math ZSIZE += 5
comtype lzma

log MEMORY_FILE 0 8
putvarchr MEMORY_FILE 0 0x46
append
clog MEMORY_FILE 12 ZSIZE SIZE
append

get NAME basename
string NAME += "_unpacked.swf"
log NAME 0 SIZE MEMORY_FILE
```
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-07-22T03:06:47+00:00
- Post Title: SWF lzma decompression

Hmm, up to 40% reduction in size.
[http://www.adobe.com/devnet/flash/artic ... ssion.html](http://www.adobe.com/devnet/flash/articles/concept-lzma-compression.html)

I like how the article says it's "based" on LZMA.
Does that mean it is a variant of LZMA? Or is this how people usually refer to implementations of algorithms?
## Post #3
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-22T05:55:16+00:00
- Post Title: SWF lzma decompression

Sounds like they're trying to make it sound more special than it is. 

Or maybe they meant to say the actual code is based on the 7-zip SDK? Here's what they say in the [spec sheet](http://wwwimages.adobe.com/content/dam/Adobe/en/devnet/swf/pdf/swf-file-format-spec.pdf):

> 0x5a, 0x57, 0x53 (“ZWS”). A ZWS indicates that the entire file after the first 8 bytes (that is, 
>
> after the FileLength field) was compressed by using the LZMA open standard: http://www.7-zip.org/sdk.html.
## Post #4
- Username: Elayna
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 08, 2014 6:43 am
- Post datetime: 2014-10-07T22:45:47+00:00
- Post Title: SWF lzma decompression

> Reply from Chipicao
>
> I ran into a bit of trouble trying to extract resources from some flash files. Both Flash Decompiler Trillix and Sothink SWF Decompiler said the files are corrupt.
Turns out they just use lzma compression, implemented in SWF version 13. So here's a little script for decompression:
Code: Select allidstring "ZWS"
get VERSION byte
get SIZE long   #uncludes first 8 bytes; quickbms finds uncompressed size automatically
get ZSIZE long
math ZSIZE += 5
comtype lzma

log MEMORY_FILE 0 8
putvarchr MEMORY_FILE 0 0x46
append
clog MEMORY_FILE 12 ZSIZE SIZE
append

get NAME basename
string NAME += "_unpacked.swf"
log NAME 0 SIZE MEMORY_FILE

Are you able to extract the XML & animation from Clash of Clan? They also use LZMA
