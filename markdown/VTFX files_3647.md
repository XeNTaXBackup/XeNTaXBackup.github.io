## Post #1
- Username: Omnicoder
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Aug 13, 2009 6:42 am
- Post datetime: 2009-08-13T07:04:57+00:00
- Post Title: VTFX files?

I know there was a thread about L4D VTFX files already but the poster seems to be gone and I can't seem to do much with these files, so I'm making a new thread. (also, this thread isn't about them being used in L4D, they are used in all Valve Xbox games. I am referring to the arcade game Portal: Still Alive in this thread)

First: what I know already:

VTFX is the XBOX360 equivalent to the VTF files used by Valve's source engine
They contain a different header then VTF files, and start with VTFX rather then VTF
They store the image data compressed (lzma?) I haven't been able to uncompress this
I think the underlaying format it stores the images in is DDS, not 100% Sure

I have tried putting a VTF header on the 'body' of a VTFX file and still no success. I also failed at replacing the VTFX header with a DDS header, I'm assuming the data must be uncompressed before that can be done. There is one VTFX file in particular I would like to convert to a usable format, which I have uploaded (below) as a reference for anyone else who wishes to help. I have 3 or 4 other people also trying to figure this out, but we're all stuck. Any help would be appreciated.

-----> [A vtfx file](http://www.2shared.com/file/7152886/6853eb72/blockfield360.html) <-----
