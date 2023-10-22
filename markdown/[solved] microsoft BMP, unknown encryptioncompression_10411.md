## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-05-12T00:51:06+00:00
- Post Title: [solved] microsoft BMP, unknown encryption/compression

Someone sent me some samples but didn't tell me the name of the source.
Anyways at the top you can see something that looks like "BM6" so presumably it's just an obfuscated BMP file.



Look like anything?
[data.zip](https://xentaxbackup.github.io/file/6394_data.zip)
## Post #2
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2013-05-13T15:14:32+00:00
- Post Title: [solved] microsoft BMP, unknown encryption/compression

Could be LZSS or something similar. Try to figure out what this is from!

Edit: yeah, it's LZSS. Not perfect, but managed to decompress it some:


Edit 2: fixed
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-05-14T01:47:28+00:00
- Post Title: [solved] microsoft BMP, unknown encryption/compression

Can you send me the tool/source? I want to see how it works. I read the algorithm but lol I don't know how to apply it.
## Post #4
- Username: finale00
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-05-14T03:46:14+00:00
- Post Title: [solved] microsoft BMP, unknown encryption/compression

quickbms script

```
get name basename
get size asize
get ext EXTENSION
string name + _.
string name + ext
clog name offset size size

```


source code
[https://code.google.com/p/puyotools/sou ... on/lz01.cs](https://code.google.com/p/puyotools/source/browse/trunk/PuyoTools/Puyo%20Tools/Modules/Compression/lz01.cs)
## Post #5
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2013-05-14T11:45:25+00:00
- Post Title: [solved] microsoft BMP, unknown encryption/compression

Here's the source for my tool. When it says "Failed to decompress" and still produces a valid .bmp, it means the input file was too large.
[http://sktest.aruarose.com/BmpDecompress.7z](http://sktest.aruarose.com/BmpDecompress.7z)
