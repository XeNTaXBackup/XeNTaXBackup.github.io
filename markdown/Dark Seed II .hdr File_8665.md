## Post #1
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2012-03-30T16:02:06+00:00
- Post Title: Dark Seed II .hdr File

Hi. I've been trying to extract the sprites in Dark Seed II. There's a lot of .000 files, and after opening them in NotePad, they all contain .bmp files. Problem is, I can't get them opened, and I've tried many Google searches to find something that'll open them.

Here's one file. I'll just use this one because it has a bunch of sprites and it's under 256 KB.
[gl02_fhfh.zip](https://xentaxbackup.github.io/file/5244_gl02_fhfh.zip)
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-03-30T20:23:13+00:00
- Post Title: Dark Seed II .hdr File

This is my try to write an QuickBMS script to export/import BMPs from .000 files.

```
# script for QuickBMS http://quickbms.aluigi.org

get FILES short
for i = 0 < FILES
getdstring NAME 0xC
get SIZE long
get OFFSET long
log NAME OFFSET SIZE
next i
```
## Post #3
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2012-03-30T21:08:20+00:00
- Post Title: Dark Seed II .hdr File

Thanks, it works!... somewhat. I'm trying to get the .bmp files out of this one. It extracts them, but they come out corrupted.
[http://www.mediafire.com/?xf3y8qh34gud01y](http://www.mediafire.com/?xf3y8qh34gud01y)
## Post #4
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-03-30T21:31:22+00:00
- Post Title: Dark Seed II .hdr File

Yeah, I see that, but don't know what's wrong with them.
## Post #5
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2012-03-31T13:49:22+00:00
- Post Title: Dark Seed II .hdr File

There's also this other file called gfile.hdr and it has a lot of bmp files. But of course, I can't open it. Here it is.
[gfile.zip](https://xentaxbackup.github.io/file/5245_gfile.zip)
## Post #6
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2012-04-07T17:32:04+00:00
- Post Title: Dark Seed II .hdr File

So has anyone successfully written a script yet? I've been trying to rip sprites with screen caps, but there's too many and most of the time there's something in the foreground in front of them. Just ripping the sprites directly would be much easier.
## Post #7
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2012-04-10T18:08:59+00:00
- Post Title: Dark Seed II .hdr File

... hello?
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-04-12T21:51:20+00:00
- Post Title: Dark Seed II .hdr File

[viewtopic.php?f=28&t=1270](http://forum.xentax.com/viewtopic.php?f=28&t=1270) Please review the new forum rules.
