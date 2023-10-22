## Post #1
- Username: Russell
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 21, 2006 5:39 pm
- Post datetime: 2010-06-05T01:45:41+00:00
- Post Title: ROTH wav data

Hi

If you've seen the audio files realms of the haunting contains, you'll notice they are a riff container (with an inverted/BE RIFF id) containing a wFormatTag of 42, which isn't a registered type of course

So anyway I had a look at the sample data, the only thing I discovered is the rightmost (or leftmost? can't remember) is the sign bit, so you set the current byte to a + or - value

Any more information on decoding this would be great
## Post #2
- Username: Russell
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 21, 2006 5:39 pm
- Post datetime: 2010-06-06T02:19:16+00:00
- Post Title: ROTH wav data

I should've uploaded an unmodified sample 
[0007.zip](https://xentaxbackup.github.io/file/3115_0007.zip)
## Post #3
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-06-06T03:55:41+00:00
- Post Title: ROTH wav data

Actually, 42 is [registered](http://www.iana.org/assignments/wave-avi-codec-registry), for G.721, but this ain't it (G.721 doesn't have 0 nibbles).
## Post #4
- Username: Russell
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 21, 2006 5:39 pm
- Post datetime: 2010-06-10T07:14:35+00:00
- Post Title: ROTH wav data

> Reply from hcs
>
> Actually, 42 is registered, for G.721, but this ain't it (G.721 doesn't have 0 nibbles).

Woops that was meant to be 42 in decimal, 0x002A I meant
## Post #5
- Username: Russell
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 21, 2006 5:39 pm
- Post datetime: 2010-06-19T15:23:17+00:00
- Post Title: ROTH wav data

I think I figured it out

It uses the same DPCM table as GDV's (Gremlin Digital Video) audio section: [http://wiki.multimedia.cx/index.php?tit ... dio_Format](http://wiki.multimedia.cx/index.php?title=Gremlin_Digital_Video#Audio_Format)

Hope this helps anyone else
