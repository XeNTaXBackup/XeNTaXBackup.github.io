## Post #1
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2011-01-29T09:11:41+00:00
- Post Title: ?Spiderman Web Of Shadows PC?

Has anyone done anything with this game?
It uses the file format *.pcpack
I've used 7zip and winrar, but niether work.
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2011-01-29T12:33:42+00:00
- Post Title: ?Spiderman Web Of Shadows PC?

Some sample files would be nice...
## Post #3
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2011-01-29T20:29:01+00:00
- Post Title: ?Spiderman Web Of Shadows PC?

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-01-29T20:39:55+00:00
- Post Title: ?Spiderman Web Of Shadows PC?

Can you take a look at it too?
[viewtopic.php?f=10&t=5470](http://forum.xentax.com/viewtopic.php?f=10&t=5470)
Thanks.
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-29T21:59:05+00:00
- Post Title: ?Spiderman Web Of Shadows PC?

i gave up when it broke the first pattern i found with the chunk size..
also chuckled at the programs op tried to use on this file   

```
# allocated space is filled with 0xA1
# chunks are padded to 0x1000
# data is typically 0x80000 bytes long

get SIZE asize

for
  savepos CHUNKSTART

  if CHUNKSTART == SIZE
    cleanexit
  endif

  getdstring CHUNKID 4 # ASCII "NCH\x0"
  get CHUNKSIZE long
  getdstring OTHERHEAD 26

  getdstring CHUNKDATA CHUNKSIZE
  
  padding 0x1000
next

```


to bacter!
## Post #6
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2011-02-03T23:56:44+00:00
- Post Title: ?Spiderman Web Of Shadows PC?

soooo.... noone can help me?
## Post #7
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2011-02-15T12:59:44+00:00
- Post Title: ?Spiderman Web Of Shadows PC?

come on.... 11 days and nothing? PLEASE HELP!
