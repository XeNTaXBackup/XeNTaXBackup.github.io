## Post #1
- Username: aeilana
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 22, 2012 4:43 pm
- Post datetime: 2012-06-22T10:52:26+00:00
- Post Title: Phantasy Star Online 2 archives

I was wondering if anyone had a method of extracting text files from Phantasy star online 2.

[http://www.sendspace.com/file/hkl3da](http://www.sendspace.com/file/hkl3da)

This is the main file Im looking to extract from, I had to upload it to sendspace since attachments wont work for the file type.
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-06-22T15:05:04+00:00
- Post Title: Phantasy Star Online 2 archives

I tried making a BMS script but it won't work because there are no references to compression size at all. I don't think this file is compressed. It looks encrypted?

Anyway here's the script if anyone wants to 'try' fix it IF it is compressed.

```
# By MrNightmareTM
# Version 0.1a

get SIGN long
get UNK1 long
get VERSION long
get UNK2 long
get UNK4 long
get UNK3 long
get UNK6 long
get BLKEND long # EOF
savepos BLKSTRT
set OFFSET BLKSTRT
math BLKEND -= BLKSTRT
set SIZE BLKEND
get NAME basename
string NAME += "_uncompressed.dat"

comtype zlib

clog NAME OFFSET ZSIZE SIZE
```
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-22T18:18:57+00:00
- Post Title: Phantasy Star Online 2 archives

Try this: [viewtopic.php?p=71919#p71919](http://forum.xentax.com/viewtopic.php?p=71919#p71919)
## Post #4
- Username: aeilana
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 22, 2012 4:43 pm
- Post datetime: 2012-06-22T18:30:00+00:00
- Post Title: Phantasy Star Online 2 archives

> Reply from finale00
>
> Try this: viewtopic.php?p=71919#p71919
That doest work, they changed the files and now the extractor doesnt work.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-22T18:34:44+00:00
- Post Title: Phantasy Star Online 2 archives

It's probably the same format except they changed the header or something. Too bad we don't have any source to work with.

Oh, nvm, it looks like it went from version 3 to version 4 archives lol

So where do I get the client?
## Post #6
- Username: aeilana
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 22, 2012 4:43 pm
- Post datetime: 2012-06-22T18:45:02+00:00
- Post Title: Phantasy Star Online 2 archives

> Reply from finale00
>
> It's probably the same format except they changed the header or something. Too bad we don't have any source to work with.

Oh, nvm, it looks like it went from version 3 to version 4 archives lol

So where do I get the client?

[http://pso2.jp/players/download/](http://pso2.jp/players/download/)

Heres the official download, though its in Japanese.
