## Post #1
- Username: KorudoDaio
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 16, 2015 10:03 am
- Post datetime: 2015-09-16T02:12:32+00:00
- Post Title: DBZ Budokai .amo/amt?

Hi, I'm new here.

I'm looking for a converter to dae or OBJ for DBZ Budokai (first one) for the .AMO/.AMT files in DATA_US.AFS. I've successfully extracted the raw files, but I'm stuck there. There's a few models I want for my Brawl mod usage, mainly King Cold's cutscene model before he gets killed by Trunks.

Anyone willing to point me in the right direction? There are about 40 someodd pages of threads. D:
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-16T06:01:34+00:00
- Post Title: DBZ Budokai .amo/amt?

which platform?
For .amo I remember a Noesis python script by finale00, fmt_BakemonogatariPSP_amo.py.

He wrote a quickbms script, PSP .amo splitter, here:
[viewtopic.php?f=16&t=9546&p=77870&hilit=budokai#p77870](http://forum.xentax.com/viewtopic.php?f=16&t=9546&p=77870&hilit=budokai#p77870)

In the post from FurryFan, as of Mon Aug 27, 2012 12:24 am

for 'PS2' ext="AMG"  there's
"a quick script, that will convert the AMG files, into .3ds files"
## Post #3
- Username: KorudoDaio
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 16, 2015 10:03 am
- Post datetime: 2015-09-16T15:09:52+00:00
- Post Title: DBZ Budokai .amo/amt?

For PS2.

And I tried that script with Noesis. Gives me errors and won't export.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-16T17:05:31+00:00
- Post Title: DBZ Budokai .amo/amt?

if you uploaded the concerning .amo file I could check that
## Post #5
- Username: KorudoDaio
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 16, 2015 10:03 am
- Post datetime: 2015-09-16T17:09:37+00:00
- Post Title: DBZ Budokai .amo/amt?

> Reply from shakotay2
>
> if you uploaded the concerning .amo file I could check that

All righty, let's see here. I THINK this is the one I want, judging by the file name.

EDIT. Won't allow me to post it here, I'll get mediafire.

[https://www.mediafire.com/?o1411zbnoyprd6x](https://www.mediafire.com/?o1411zbnoyprd6x)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-16T22:09:40+00:00
- Post Title: DBZ Budokai .amo/amt?

thx for the sample! Here's some result:



AMG23ds.JPG (50.15 KiB) Viewed 185 times



It's the SubAMGs 1, 7 and 13 only and as you can see they're a little bit spoiled, especially no 7.

I used finale00's amo splitter script and the ones from FurryFan (where I had to add
 If Type == 445 ;
 set VertexType long 48 ; 
to his subAMG2_3ds script)

(While mesh000.amg was ok the splitter created an empty mesh001.amg so it's recommended to use FurryFan's amo2amg bms script instead.)
## Post #7
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2015-09-17T01:12:09+00:00
- Post Title: DBZ Budokai .amo/amt?

Try this, its incomplete though. Only played with if for a bit, too busy to finish.
[http://www.mediafire.com/download/j6069 ... udokai3.ms](http://www.mediafire.com/download/j60696zs4p1dri2/budokai3.ms)
## Post #8
- Username: KorudoDaio
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 16, 2015 10:03 am
- Post datetime: 2015-09-17T01:21:15+00:00
- Post Title: DBZ Budokai .amo/amt?

Wow, guys! Progress.

But I only wonder why it won't work for me. D: And why the heck he looks like that.

EDIT: I get PARTS of his model with the MaxScript.
