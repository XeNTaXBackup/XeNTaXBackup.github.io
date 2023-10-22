## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-10T04:46:49+00:00
- Post Title: Quickbms comtype deflate without uncompressed size?

I have some files that are compressed using deflate but I don't have any uncompressed filesizes to work with. Offzip can decompress the file fine, but how can I decompress it in the script?
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-08-10T10:01:12+00:00
- Post Title: Quickbms comtype deflate without uncompressed size?

use unzip_dynamic
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-10T19:39:50+00:00
- Post Title: Quickbms comtype deflate without uncompressed size?

Worked great

```

```


lol @ docs

> unzip_dynamic (automatic zlib/deflate and output size, cool)
