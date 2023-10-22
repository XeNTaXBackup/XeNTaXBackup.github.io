## Post #1
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-03-15T06:11:18+00:00
- Post Title: Armored Core titles [PS2] .ADX

Every Armored Core on PS2 uses ADX.

I thought this would be no problem since it's a very well researched format, but so far none of the tools I used could get it to work.

Used latest foo_vgmstream & in_vgmstream for f2k & winamp respectively, ADX2WAV, and command line of vgmstream (with -i function for "ignore loop" but that didn't help).

Here's the 1st ADX from AC3 Silent Line.

[http://www.mediafire.com/?536dk6wp1aph0zo](http://www.mediafire.com/?536dk6wp1aph0zo)
## Post #2
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2012-03-16T03:09:45+00:00
- Post Title: Armored Core titles [PS2] .ADX

This is actually an .ADS file.  Raw PCM.  Just rename the extension to ".ADS" and it should play fine in vgmstream.

Armored Core - Last Raven: SS2
Armored Core 2: ADS
Armored Core 2: SS2
Armored Core 3: ADS
Armored Core 3: ADS

These are the formats for each game, according to what I've been shown.  Also, from what I recall, ADS with PCM is exactly the same as SS2, except maybe for loop points in the header?

In any case check out the headers, you'll see the "SShd" for the ADS/SS2 files while ADX files start with 0x80 and have the plain text "(c)CRI" somewhere nearby.  Hope that helps for your future endeavors.
## Post #3
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-03-16T03:57:59+00:00
- Post Title: Armored Core titles [PS2] .ADX

Wow, I didn't even know about such thing as ADS file. But yes that did the trick, a simple renaming allows playback in vgmstream. Thanks a lot!

I usually don't look at things through hex editor, it's a bit too "deep" and technical for my level. But your advice and knowledge shared is very much appreciated.
