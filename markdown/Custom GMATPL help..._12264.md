## Post #1
- Username: Yoshimaster96
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Nov 24, 2014 12:57 am
- Post datetime: 2014-11-23T17:18:57+00:00
- Post Title: Custom GMA/TPL help...

Need help with making custom GMA/TPL model/texture files. I got so far, but only one texture shows for some reason. Help!


 FUNNEL.zip
(5.36 KiB) Downloaded 24 times
## Post #2
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2014-12-19T14:09:34+00:00
- Post Title: Custom GMA/TPL help...

i took a peek at the graphics and they look rather simple as is, aside the fact that they seem to lack a palette (in a different file i'd assume)
here's what i found out:



judging from the data pattern, this format is tiled.

grey: number of graphics entries (0x2)
red: there's 3 of these per file;
--- first is unknown, i'd believe it's a mode flag,
--- second is the data start address (0x40 for first file)(0x840 for second file)
--- resolution of the file 2x2byte value (0x20 0x20 // 32x32 pixels for both of them)
blue: unknown
yellow: seems to be header filler/garbage data.
[derp.png](https://xentaxbackup.github.io/file/8302_derp.png)
## Post #3
- Username: Yoshimaster96
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Nov 24, 2014 12:57 am
- Post datetime: 2014-12-28T02:23:32+00:00
- Post Title: Custom GMA/TPL help...

Here's the GMA format:
[http://www.gc-forever.com/forums/viewtopic.php?p=23932](http://www.gc-forever.com/forums/viewtopic.php?p=23932)
And the TPL format:
[http://www.gc-forever.com/forums/viewto ... =35&t=2311](http://www.gc-forever.com/forums/viewtopic.php?f=35&t=2311)
