## Post #1
- Username: RoxasKennedy
- Rank: beginner
- Number of posts: 21
- Joined date: Tue May 17, 2011 6:39 pm
- Post datetime: 2011-12-17T21:25:31+00:00
- Post Title: TMNT: Smash Up - PAC files

So, I know this game is extractable. But I couldn't find a way how.
I extracted the contents of the disc and I found these .PAC files.
I researched around a bit and I found variety of tools, but none worked.   
And I hope it's not too complicated, beacuse I'm still a noob at these stuff. XD
The sample of the files:

> Code: Select allhttp://www.mediafire.com/?a91r6d3cvvlkk38
## Post #2
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2011-12-19T06:22:45+00:00
- Post Title: TMNT: Smash Up - PAC files

Use [NTCompress.exe](http://www.mediafire.com/?kdc94w0rs9dx72y) (from the newest Revolution SDK) to decompress the files, in the command prompt:

```
ntcompress.exe -x C00.PAC
```

Or whatever the PAC file is named. Then use U8Tool to unpack the *.PAC into a BRRES (model/textures) and a BRSAR (sounds) file.

(If I'm not allowed to post a file from an SDK, please feel free to sack me.)
## Post #3
- Username: RoxasKennedy
- Rank: beginner
- Number of posts: 21
- Joined date: Tue May 17, 2011 6:39 pm
- Post datetime: 2011-12-19T12:15:05+00:00
- Post Title: TMNT: Smash Up - PAC files

Thank you very much!
## Post #4
- Username: Monster2009
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 27, 2022 10:48 am
- Post datetime: 2022-05-27T16:56:56+00:00
- Post Title: TMNT: Smash Up - PAC files

I actually manage to open them, and I wonder how you could repack it?
