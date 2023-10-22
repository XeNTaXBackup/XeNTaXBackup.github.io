## Post #1
- Username: qq99q1
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Aug 01, 2011 2:51 pm
- Post datetime: 2012-02-22T09:01:05+00:00
- Post Title: psp doa paradise

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: BakameExcalibur
- Rank: advanced
- Number of posts: 68
- Joined date: Wed Feb 02, 2011 8:02 am
- Post datetime: 2012-02-25T22:32:32+00:00
- Post Title: psp doa paradise

No idea, but I want to ask: how did you manage to get these files out? I've been looking for an extractor for months now, to no avail.
## Post #3
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-02-25T23:12:00+00:00
- Post Title: psp doa paradise

ditto, I'd like to know the extraction method. Files were encrypted when I last looked...
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-25T23:19:18+00:00
- Post Title: psp doa paradise

The PAR chunk gives you filenames and offsets relative to the start of that PAR chunk. One can probably treat this as an archive and unpack the files, but that is not important since you can just treat it like any chunk based format. Sizes can be obtained by just taking the difference of each offset (and the last texture is just filesize - last_offset).

But parsing it directly is probably the easiest since the file is small anyways.

So for example I randomly opened "dmy_aa_a_m_a_cr.tpr" and at the top I see the offset to the pmd and the pta files. pmd starts at 0x80 while pta starts at 0xE280.

Then you can just parse the pmd (model) and pta (textures) separately.

When you get to the pta offset, you just see another PAR. It'll give you the names and offsets of the textures, relative to the start of the pta offset.

All of the textures are PSP Gim's, which I'm guessing is a standard format for PSP textures, so that part should be given to you already.

Oh, and it looks like a lot of the things are aligned to 16-bytes.
Either that, or each PAR chunk can store up to 4 files.

btw, upload some map files as well. And objects.
I looked at the files a year ago but had no clue about hex-reading so deleted the game lol
