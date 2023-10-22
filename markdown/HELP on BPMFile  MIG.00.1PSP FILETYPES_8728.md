## Post #1
- Username: 2012Z
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Mar 12, 2012 3:31 am
- Post datetime: 2012-04-09T06:34:18+00:00
- Post Title: HELP on BPMFile / MIG.00.1PSP FILETYPES

Need help on opening this kind of file (see link below).
I think this is an image file.
It's file header looks like this:
------------------------------------------------------------------
BPMFile BG              MIG.00.1PSP    P  P     0                 0   @   @          @                  8"$@0+"H#K(:3&R+<:/V1B?3\6AC;HA1_: JF:e>&HICPI:jD,MNFVO=TSHwF.mM6PX]XWJ]VDJ4][PuT;V\iO:d]Ka`TQ<haO{ZA^aqU?........
------------------------------------------------------------------
I need help on converting this kind of file; converted to BMP or JPEG (what ever is possible) and viceversa.

Thanks always.
## Post #2
- Username: 2012Z
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Mar 12, 2012 3:31 am
- Post datetime: 2012-04-09T06:36:28+00:00
- Post Title: HELP on BPMFile / MIG.00.1PSP FILETYPES

Here's a sample file:
<link removed due forum rules violation>
## Post #3
- Username: 2012Z
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Mar 12, 2012 3:31 am
- Post datetime: 2012-04-09T06:57:02+00:00
- Post Title: HELP on BPMFile / MIG.00.1PSP FILETYPES

I've tried using GimConv but still it's an unknown format.
Nothing converted.
## Post #4
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-04-09T07:05:36+00:00
- Post Title: HELP on BPMFile / MIG.00.1PSP FILETYPES

Just use [gitmo](http://www.richwhitehouse.com/filemirror/gitmo11.zip)
[http://www.richwhitehouse.com/index.php ... hp#prjmp88](http://www.richwhitehouse.com/index.php?content=inc_projects.php#prjmp88)
Set search options to find
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-09T07:40:52+00:00
- Post Title: HELP on BPMFile / MIG.00.1PSP FILETYPES

Just remove the first 48 bytes and rename it to .gim
Assuming a bpm file contains only one texture.

The second integer is kind of suspicious.
## Post #6
- Username: 2012Z
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Mar 12, 2012 3:31 am
- Post datetime: 2012-04-09T09:36:04+00:00
- Post Title: HELP on BPMFile / MIG.00.1PSP FILETYPES

Many thanks...
## Post #7
- Username: 2012Z
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Mar 12, 2012 3:31 am
- Post datetime: 2012-04-09T09:47:09+00:00
- Post Title: HELP on BPMFile / MIG.00.1PSP FILETYPES

Work Done:






Well it's not yet 100%...

Thanks dj082502 for helping me out.
## Post #8
- Username: 2012Z
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Mar 12, 2012 3:31 am
- Post datetime: 2012-04-09T11:21:17+00:00
- Post Title: HELP on BPMFile / MIG.00.1PSP FILETYPES

Some BPMFile type can't be converted. It's still an image file.
Here's the sample files:
<link removed due forum rules violation>

Looking forward for more shared ideas.
Thanks always.
## Post #9
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-04-09T12:17:36+00:00
- Post Title: HELP on BPMFile / MIG.00.1PSP FILETYPES

I scanned ResultTitle.bpm, but found nothing.
## Post #10
- Username: 2012Z
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Mar 12, 2012 3:31 am
- Post datetime: 2012-04-10T02:04:54+00:00
- Post Title: HELP on BPMFile / MIG.00.1PSP FILETYPES

Ok, what I did was change it's file extension from .BPM to .GIM.
It converted some files, probably those are really GIM image files.
Now, how can I convert it back to GIM or BPM. Any idea?
Thanks again.
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-10T02:19:23+00:00
- Post Title: HELP on BPMFile / MIG.00.1PSP FILETYPES

Ya, I mentioned it earlier, but that second integer determines how many textures there are.
Fortunately most of the ones you modified had only one.

Main.bpm has 25 of them.
Unfortunately it seems like there's only one of those GIM headers, so maybe it's stored in a different way rather than just having 25 separate textures in the same archive.
## Post #12
- Username: 2012Z
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Mar 12, 2012 3:31 am
- Post datetime: 2012-04-10T02:30:37+00:00
- Post Title: HELP on BPMFile / MIG.00.1PSP FILETYPES

@ finale00

Yep, I noticed it.. I look into each file for it's file header but some are different from each other.
Sorry, this file type is new to me. I don't know any program that can handle this.
So, any idea how to extract/convert this file?

Thanks for your reply.
## Post #13
- Username: 2012Z
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Mar 12, 2012 3:31 am
- Post datetime: 2012-04-14T20:55:46+00:00
- Post Title: HELP on BPMFile / MIG.00.1PSP FILETYPES

How bout this file?
<link removed due forum rules violation>

It's from the PS2 version and I can't get exactly what file format is this....
Please help....

Thanks always
## Post #14
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-04-14T21:09:11+00:00
- Post Title: HELP on BPMFile / MIG.00.1PSP FILETYPES

Read the new rules. Fast.
