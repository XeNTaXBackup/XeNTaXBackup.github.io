## Post #1
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2014-02-23T20:34:04+00:00
- Post Title: Arcsys bddata.bin - Blazblue ChronoPhantasma

Sorry to dig this back up but arcsys is still using bddata.bin as the only file for storing the game files for newer games coming out and the filedump script is woefully inadequate for opening it up due to slight changes in the segs headers and a lack of filenames/file table.
Recently, a dump of the in-game music surfaced on 4-chan with names attached to the files, which got me wondering if progress was made in that area.  Maybe the ELF file has the filetable?  I'd love some more info if it's available.

[viewtopic.php?f=10&t=5208&p=51102&hilit=bddata#p51102](http://forum.xentax.com/viewtopic.php?f=10&t=5208&p=51102&hilit=bddata#p51102)  Here's aluigi's old bms script, for reference.  It could sometimes identify PAC files (header FPAC) since they're pretty common in arcsys games but still couldn't get filenames for the most part.  It could just be that I've been using the script wrong the whole time? *shrug*

I'll throw up a few files later if requested but for the most part the snippets that have been posted in the past 3 years are still relevant here.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-02-26T09:26:48+00:00
- Post Title: Arcsys bddata.bin - Blazblue ChronoPhantasma

Post the files that give problems
## Post #3
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2014-02-28T13:07:24+00:00
- Post Title: Arcsys bddata.bin - Blazblue ChronoPhantasma

As a first example, here's a couple of files dumped using the aforementioned script from the bddata.bin file in Blazblue ChronoPhantasma.

[http://www.mediafire.com/download/8vrg2 ... ta_90.segs](http://www.mediafire.com/download/8vrg2erif98cof4/bddata_90.segs)
[https://www.mediafire.com/?e1b6c7qae8zx78d](https://www.mediafire.com/?e1b6c7qae8zx78d)

Not sure what either is supposed to be but the script seems to think the latter is a DDS file, but truncated.
