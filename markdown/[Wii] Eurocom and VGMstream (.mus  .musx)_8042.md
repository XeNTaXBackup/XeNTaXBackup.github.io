## Post #1
- Username: BlueDrake
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 11, 2012 1:19 pm
- Post datetime: 2012-01-13T03:20:49+00:00
- Post Title: [Wii] Eurocom and VGMstream (.mus | .musx)

So now all the game files are extracted and nameless: [viewtopic.php?f=10&t=8026](http://forum.xentax.com/viewtopic.php?f=10&t=8026)
Which is great, but now my problem is VGMstream not reading the .mus files correctly:



First off the file extension needs to be renamed from .mus to .musx or else VGMstream ignores it completely.

However the files come out a mess and checking the original reveals that VGMstream is using the wrong encoder anyway.

Any suggestions? Below is the file opened in the image.

[http://www.sendspace.com/file/9yot0s](http://www.sendspace.com/file/9yot0s)
## Post #2
- Username: fastelbja
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Dec 09, 2007 3:05 am
- Post datetime: 2012-02-23T21:47:37+00:00
- Post Title: [Wii] Eurocom and VGMstream (.mus | .musx)

The Musx format in vgmstream handle only compressed DATA (for example IMA on the Eurocom DAT4 Format)
The file you provide is an PCM file. Import this one under Audacity as RAW File (mono/ 26Khz) and you'll be able to hear to your file

cheers
## Post #3
- Username: BlueDrake
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 11, 2012 1:19 pm
- Post datetime: 2012-03-27T20:45:57+00:00
- Post Title: [Wii] Eurocom and VGMstream (.mus | .musx)

Thanks, never would have thought about importing raw

After some fiddling it is actually 26kHz Mono 16-bit PCM with Big-Endian Byte order
## Post #4
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2012-05-09T04:19:25+00:00
- Post Title: [Wii] Eurocom and VGMstream (.mus | .musx)

That's odd. I might have to play around with vgmstream to set a flag to distinguish between ADPCM and PCM if it doesn't already exist and is being ignored.
## Post #5
- Username: jmarti856
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Aug 29, 2015 8:45 pm
- Post datetime: 2023-09-03T19:19:18+00:00
- Post Title: [Wii] Eurocom and VGMstream (.mus | .musx)

Here is a tool that can encode and decode the custom eurocom adpcm: [https://github.com/eurotools/es-eurocom ... er-decoder](https://github.com/eurotools/es-eurocom-adpcm-encoder-decoder)
and here is a tool that can open the SFX files for some games to see the file-format and all properties: [https://github.com/eurotools/eurosound-explorer](https://github.com/eurotools/eurosound-explorer)
