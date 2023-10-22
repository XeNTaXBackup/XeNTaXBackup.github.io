## Post #1
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2009-01-15T01:00:06+00:00
- Post Title: Re5 Arc files

I've been looking at the RE5 arc files and managed to figure out the container but not the compression.  I've been told it's zlib, but I don't understand compression.  If anyone could look at it, it'd be greatly appreciated.



```
Purple Font: Arc Signature
Red background: unknown, Dev calls this the directory offset and seeks to it, but I don't understand it's purpose. (the directory starts at 0x08, not 0x11)
Green background: Number of files.

Individual file headers:
Blue Background: 64 byte string; name and directory of file
Light Blue background: File length
Beigish grey background: File offset
```


Here's a link to Chris' Arc file.
[http://files.filefront.com/uPl00ChrisNo ... einfo.html](http://files.filefront.com/uPl00ChrisNormalrar/;12976248;/fileinfo.html)

thanks, James.
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-01-15T18:01:47+00:00
- Post Title: Re5 Arc files

at least there's no zlib header.
you could try adding it and using a zlib tool to extract it.
## Post #3
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2009-01-16T01:44:39+00:00
- Post Title: Re5 Arc files

Thanks, I'll look into that.  But when I say I know nothing about compressions I mean nothing <_<.  lol, I guess it's never too late to learn.
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-01-16T07:49:29+00:00
- Post Title: Re5 Arc files

[viewtopic.php?f=21&t=2579](http://forum.xentax.com/viewtopic.php?f=21&t=2579)
## Post #5
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2009-01-17T18:26:51+00:00
- Post Title: Re5 Arc files

Well sadly it isn't signed with the 78 thing.  But that's probably because they used a default quality of compression and just removed the signature.  The data is definitely compressed though, looking at it there are no 0s or anything.  Now just to look up how zlib compresses.  Thanks for that though, it always gets me motivated to start.

Edit:
Further research tells me that the correct term is DEFLATE.
