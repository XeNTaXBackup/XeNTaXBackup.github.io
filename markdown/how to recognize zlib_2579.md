## Post #1
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-04-11T23:40:56+00:00
- Post Title: how to recognize zlib?

Are there any characteristics?
Please don't just say, try it out by decompressing it, sometimes you have archives with header information where you can't say for sure where the header ends and data starts.
## Post #2
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2007-04-12T03:49:09+00:00
- Post Title: how to recognize zlib?

> Reply from Rheini
>
> Are there any characteristics?
Please don't just say, try it out by decompressing it, sometimes you have archives with header information where you can't say for sure where the header ends and data starts.

usually starts 78    then a few other possibilities. Feel free to correct if I get this wrong off the top of my head.

78 01 - No Compression/low
78 9C - Default Compression
78 DA - Best Compression

If the file begins like this than it is a good sign. If your offsets land on something like this that is also a very good indication. Please note there can be multiple compressed packages in a file though.  

Most of the time you can also decompress the package without the size (decompressed, compressed) parameters, but if you want to rebuild files correctly you may need this.
