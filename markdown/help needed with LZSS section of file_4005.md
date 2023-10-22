## Post #1
- Username: mutton
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 01, 2010 1:40 am
- Post datetime: 2009-12-31T21:49:05+00:00
- Post Title: help needed with LZSS section of file

Hi, this is my first post here so hopefully it's in the right place.

I'm currently developing a program that reads information from a *.cdp file (content dispatcher package for Auran's Trainz range of programs).  I can parse my way through the file ok, but the resource sections are compressed in a LZSS format.  I know the extracted size, I know the compressed size and I know where the data starts but,  does anyone know of a good routine, in vb.net that will uncompress this data.  btw the data is stored in a byte array so is easily readable.

Thanks
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-12-31T22:41:55+00:00
- Post Title: help needed with LZSS section of file

you must post a sample archive so someone can help you.
Quickbms is a great way to handle almost any archive you can think of.
## Post #3
- Username: mutton
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 01, 2010 1:40 am
- Post datetime: 2009-12-31T23:27:08+00:00
- Post Title: help needed with LZSS section of file

ok

here's a link to a freely downloadable cdp file [http://eckethump.host56.com/test.cdp](http://eckethump.host56.com/test.cdp) (trying not to use any restricted files that require a registered user to accesss)

the section im interested in begions with the ascii 'compression','lzss'

after the 'files marker; the format is:
FILES,00,00
Block length as int32
nn,filename,0     'where n is length of filename + 1 for null terminator
04,uncompressed file size as int32
bb                    
data...

bb is a byte that I believe describes the archive in some way. So far I've identified:
00 indicates an uncompressed file. Ive seen 0x19 and 0x29 used to indicate compressed file

Not sure if this file is a good one to work with it was the first I found at train.luvr.net, it does show some differences to the files I was examning.

NB, please note that the Files section can appear anywhere in the file.  The cdp is basically a sequence of nested records.  If you need more please ask.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-01-01T01:10:36+00:00
- Post Title: help needed with LZSS section of file

are these the files you want to decompress?
[http://www.bogesz.cjb.hu/](http://www.bogesz.cjb.hu/)
## Post #5
- Username: mutton
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 01, 2010 1:40 am
- Post datetime: 2010-01-01T13:39:31+00:00
- Post Title: help needed with LZSS section of file

Yes, you can download them from that site.

More uptodate files can be found here [http://www.settleandcarlisle.co.uk/](http://www.settleandcarlisle.co.uk/) also.  As well as many other places on the web.  I was being a bit tooc areful with the files I posted as most are only downloadable from the trainz download station (need to be registered), I didn't want to post anything that goes against any of the authors distribution limits.  But the ones on the settle and carlisle website are there a a public download so pleas use them.  This is indeed where the filesI've been using as examples come from.  In fact this file is the one I use to test my routines with [http://www.settleandcarlisle.co.uk/down ... otters.cdp](http://www.settleandcarlisle.co.uk/downloads/content/additional/files/austin_ld1_and_spotters.cdp).

Thanks
## Post #6
- Username: mutton
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 01, 2010 1:40 am
- Post datetime: 2010-01-06T11:34:07+00:00
- Post Title: help needed with LZSS section of file

Can anyone please confirm that the data in the above file ([http://www.settleandcarlisle.co.uk/down ... otters.cdp](http://www.settleandcarlisle.co.uk/downloads/content/additional/files/austin_ld1_and_spotters.cdp)) at offset 0x0345 is indeed packed with LZSS.  I've given up trying to find a suitable decompression routine for this data, there doesn't seem to be anything on the vb.net platform that can accomplish simple lzss decompression - most of the routines I've looked at add there own twist to the format.

What I'm actually wanting to do with this data is to extract and expand the LZSS files section as part of a program that allows the user to load a cdp file and view it's content including thumbails of the included objects which are stored in the files section as a LZSS compressed stream.  I would even consider using a cli utility to expand the stream if I could find one that worked on the data correctly.  

If anyone is interested I can supply the uncompreseed 'books.tga' to which the data at 0x345 is the compressed form.

This is really putting a hold on the development of my program as without being able to decompress this stream there aint much point in continuing the development.

Thanks
