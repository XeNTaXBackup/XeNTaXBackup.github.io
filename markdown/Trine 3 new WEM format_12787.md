## Post #1
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2015-04-22T08:21:17+00:00
- Post Title: Trine 3 new WEM format

So, Trine 3 WEMs (can be unpacked with official archiver tool) feature different WEMs that cannot be processed with ww2ogg:

```
 Audiokinetic Wwise RIFF/RIFX Vorbis to Ogg Vorbis converter 0.22 by hcs
 Input: audio1_fbq-0000000187.wem
 Parse error: expected 0x42 fmt if vorb missing
```

[http://i.imgur.com/l3EBqou.png](http://i.imgur.com/l3EBqou.png)

[http://rghost.net/6QTtwJF8V](http://rghost.net/6QTtwJF8V)


Any idea regarding what could be done here?

UPD: Okay, I can import it as a RAW data with Audacity but there are some issues:
[http://i.imgur.com/Vh2pfCH.png](http://i.imgur.com/Vh2pfCH.png)

some kind of compression? The Sample rate and bit depth can be detected properly. May be I'm reading WAVE_EXTENSIBLE (FE FF) incorrectly (as opposed to classic wave with linear quantization 01 00)? Not that Audacity has such advanced options for reading raw files.
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-26T05:12:11+00:00
- Post Title: Trine 3 new WEM format

Your file is the simplest plain raw PCM data. No compression. Sounds perfectly. What is the problem?
## Post #3
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-04-28T05:37:37+00:00
- Post Title: Trine 3 new WEM format

You just need to change header a bit to get playable wav pcm file.

[http://dropmefiles.com/LVL2g](http://dropmefiles.com/LVL2g)
## Post #4
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-08-21T21:35:49+00:00
- Post Title: Trine 3 new WEM format

Since i stiil receiving pm's about this format here is a simple script for music files with codec id FFFE (for FFFF use ww2ogg)

```
math SIZE -= 0x12
putVarChr MEMORY_FILE SIZE 0
log MEMORY_FILE 0 0
append
log MEMORY_FILE 0 0x26
math SIZE -= 0x26
log MEMORY_FILE 0x38 SIZE
append
get SIZE asize
math SIZE -= 0x1A
putVarChr MEMORY_FILE 0x04 SIZE long
putVarChr MEMORY_FILE 0x10 0x12 long
putVarChr MEMORY_FILE 0x14 0x01 short
putVarChr MEMORY_FILE 0x24 0x00 short
get SIZE asize MEMORY_FILE
get NAME basename
string NAME += ".wav"
log NAME 0x00 SIZE MEMORY_FILE

```
