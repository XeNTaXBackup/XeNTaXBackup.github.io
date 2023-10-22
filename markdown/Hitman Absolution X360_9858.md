## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-11-11T19:44:59+00:00
- Post Title: Hitman Absolution X360

Seems these files use some encryption scheme or something because i canot access any data, However the header appears to be the same for all files so maybe someone can figure this out. Ran offzip but no dice.

PM me for file.
## Post #2
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2012-11-17T05:28:26+00:00
- Post Title: Hitman Absolution X360

*sigh*

How can people not know the header for xbcompressed files by now?  Just use "xbdecompress" from the SDK to decompress them.
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-11-17T20:10:45+00:00
- Post Title: Hitman Absolution X360

Thanks!
## Post #4
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2012-11-17T22:29:58+00:00
- Post Title: Hitman Absolution X360

You're still going to have to figure out some of the file formats after decompressing.  The videos are easy to extract though, just remove the extra bytes before the magic header for BINK files of "BIKi".  Also, the one file "engine.ini.scrambled" is not compressed with "xbcompress", it is actually encrypted somehow and I have not quite figured it out, although I am too busy playing the game and not too worried about figuring out many of the file formats quite yet.
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-11-18T04:47:56+00:00
- Post Title: Hitman Absolution X360

Well i was just looking for the Audio files anyway.
