## Post #1
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2016-08-03T17:02:32+00:00
- Post Title: Problem with PS2 ADPCM file

Hello! I have some problems playing correctly a PS2 ADPCM file from Ben 10 Protector of Earth PS2. Does anyone know what's wrong? Thanks in advance.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-08-03T19:36:27+00:00
- Post Title: Problem with PS2 ADPCM file

It might help future readers if you mention what game this came from. I can't figure it out, anyway, maybe it was extracted wrong.
## Post #3
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2016-08-03T19:39:02+00:00
- Post Title: Problem with PS2 ADPCM file

Do you mean you can't figure it out or you can't look at it? I didn't put samples.
## Post #4
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2016-08-03T19:39:51+00:00
- Post Title: Problem with PS2 ADPCM file

I have now uploaded the whole extractions.
## Post #5
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-08-03T19:51:31+00:00
- Post Title: Problem with PS2 ADPCM file

It looks like it is missing data at the beginning, which throws off the interleave. If you cut off (or skip) the first 0x330 bytes it works perfectly with 0x400 interleave, which suggests that there are 0xd0 or 0x4d0 bytes missing.

In a PM you mentioned that this seems to be a similar format to that used in The Conduit, if that's the case then that beginning data may be stored elsewhere, compressed.
## Post #6
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2016-08-03T19:53:18+00:00
- Post Title: Problem with PS2 ADPCM file

Thank you for the information. Any ways to fix this?
## Post #7
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-08-03T19:57:56+00:00
- Post Title: Problem with PS2 ADPCM file

I doubt that I'm going to be able to fix this for you, I wasn't able to figure out how to match things up with The Conduit and I don't want to revisit that frustrating chapter of my life.

For reference my old work on this is [here](https://hcs64.com/mboard/forum.php?showthread=15780&showpage=2). There are probably associated .psm files as well if the pattern holds.
## Post #8
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2016-08-03T20:04:01+00:00
- Post Title: Problem with PS2 ADPCM file

Thanks, will look at it.
## Post #9
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-08-03T21:49:29+00:00
- Post Title: Problem with PS2 ADPCM file

Well, here's a try at converting weconduit stuff for Ben10 PS2. I didn't rename the files but it seems to run ok. No idea if it will work on the rest of the file.

[http://hcs64.com/files/ben10_ps2_00.zip](http://hcs64.com/files/ben10_ps2_00.zip)

```
cnd_dmp2genh.exe dump01.bin dump00.bin dumpUC00.bin dumpUC01.bin
```
## Post #10
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2016-08-03T21:56:45+00:00
- Post Title: Problem with PS2 ADPCM file

Thank you! I just added Wii samples because I noticed the files were higher quality. Sorry, I didn't know that before.
## Post #11
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-08-04T01:52:58+00:00
- Post Title: Problem with PS2 ADPCM file

[http://hcs64.com/files/ben10_gc_00.zip](http://hcs64.com/files/ben10_gc_00.zip)

This is very close to The Conduit, but who knows how it will work on the rest of the file...

I noticed that the earlier code wouldn't work because two of the data files were swapped. I wonder if that's what was wrong with my Conduit attempts.
## Post #12
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2016-08-04T09:46:46+00:00
- Post Title: Problem with PS2 ADPCM file

Thank you so much!
