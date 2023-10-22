## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-09-11T21:03:57+00:00
- Post Title: XWB Help

Okay so there is already tools to extract audio out of xwb files but i wonder if there was a way to get the names out of the filetable? since alot of xwb's don't come with a XSB for the newer games, the names appear to be in the filelisting in the header. So since these tracks are in order in data and filelisting I wonder if there was a way to create a bms scirpt or create a tool to extract the tracks with there appropriate file names?

I posted a sample.

[http://www.megaupload.com/?d=A8QG40U0](http://www.megaupload.com/?d=A8QG40U0)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-10-08T13:55:18+00:00
- Post Title: XWB Help

you could just modify aluigi's unxwb to use the description instead of the sequential names?

unxwb.c ln 699 to:

```
dostdout ? NULL : (entry_name ? entry_name : fname),
```


although your sample has an error "unexpected data" at the end - so maybe you use another tool?
if not, the description is dumped in verbose mode
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-08T17:19:27+00:00
- Post Title: XWB Help

Well that was just a cut so it wasn't the full file.

But yeah i will try your suggestion.
