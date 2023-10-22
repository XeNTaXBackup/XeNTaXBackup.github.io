## Post #1
- Username: tigershop
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2009 9:03 pm
- Post datetime: 2010-05-13T17:26:02+00:00
- Post Title: Disney Pixar - UP / .sdx Tools

Who could plan for the extension sdx to find it to be through the audio file to access?
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-05-14T06:33:16+00:00
- Post Title: Disney Pixar - UP / .sdx Tools

Upload a sample.  The name doesn't sound familiar, so we will probably have to look at the data itself.
## Post #3
- Username: tigershop
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2009 9:03 pm
- Post datetime: 2010-05-18T07:20:22+00:00
- Post Title: Disney Pixar - UP / .sdx Tools

A sample sent to you, hope you can help me.
[06.zip](https://xentaxbackup.github.io/file/3050_06.zip)
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-05-18T07:40:18+00:00
- Post Title: Disney Pixar - UP / .sdx Tools

Raw 16bit mono PCM with a header  , easy peasy stuff!
## Post #5
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-05-18T10:42:35+00:00
- Post Title: Disney Pixar - UP / .sdx Tools

Yeah, it looks straightforward, but a few things confuse me: why nothing until 0x4000 (I see that also in the header).  Is that maybe some reserved pre-loop?  And what are the bytes at 0x4000 which seem to mean something other than PCM?  Maybe we're counting 0x4000 from the end of the header so the PCM starts around 0x4020?  But the 0x74DC in the header suggests that the whole body from 0x4000 on is the payload, so we allow the stream to start way off of DC?

Are there any larger files that might be music?  If you could upload something more complicated, with a loop, I could deduce more.
## Post #6
- Username: tigershop
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2009 9:03 pm
- Post datetime: 2010-05-19T11:03:33+00:00
- Post Title: Disney Pixar - UP / .sdx Tools

Friend, you are right, the previous file was framed in an audio file.
But he was an example of archive file. Another example I give to you.
File that you've left is the archive.

Link - 10 mb
[http://www.zshare.net/download/76266297d79b486e/](http://www.zshare.net/download/76266297d79b486e/)
## Post #7
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-05-19T12:44:58+00:00
- Post Title: Disney Pixar - UP / .sdx Tools

The soundfiles within this archive is NOT PCM, those are ADPCM without any headers.
the closest thing ive got is by bruteforcing on G723 Codec, and i could hear some distorted speech.
## Post #8
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-05-19T14:23:07+00:00
- Post Title: Disney Pixar - UP / .sdx Tools

Looks like MS IMA with 0x24 byte frames.
