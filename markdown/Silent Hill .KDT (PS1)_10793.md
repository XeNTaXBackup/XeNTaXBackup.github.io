## Post #1
- Username: peronmls
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 05, 2011 6:21 am
- Post datetime: 2013-09-21T19:45:08+00:00
- Post Title: Silent Hill .KDT (PS1)

The KDT is a custom sequence and I would really, really like to get it converted to mid.

Can anyone help me or convert this this for me. or info. I reaaaallllly need these in mid form.
Nobody has even made it readable in VGMTrans yet.

So anyone please help!   

[http://www.mediafire.com/?6sbdlcbpbbs3boc](http://www.mediafire.com/?6sbdlcbpbbs3boc)
## Post #2
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2013-09-24T01:26:34+00:00
- Post Title: Silent Hill .KDT (PS1)

I don't know how to call it, but real audio file inside "SND" directory of extracted "SILENT" archive with name "A2.VAB".

```
A2.VAB -> 118 016 bytes
```

For convert this file, use "PSound 2.00" tool. 
Press file -> scan file, select "A2.VAB", then press start button.
You will can listen here six sounds inside with 22050Hz/Mono, this is not special sound or music, it's kind of MIDI notes, but very specific, you can record it in-game only with right sequence, just listen some dark ambients.
So you can save files with pressing: file -> convert, and save wav file, here some results:


 A2_00002.mp3
(30.03 KiB) Downloaded 26 times


upd: i got your mind, you want to convert midi tracks to PC-like format, i think it's impossible, only in-game recording.
## Post #3
- Username: peronmls
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 05, 2011 6:21 am
- Post datetime: 2013-09-24T17:19:51+00:00
- Post Title: Silent Hill .KDT (PS1)

> Reply from SILENTpavel
>
> I don't know how to call it, but real audio file inside "SND" directory of extracted "SILENT" archive with name "A2.VAB".
Code: Select allA2.KDT -> 3 328 bytes
A2.VAB -> 118 016 bytes
For convert this file, use "PSound 2.00" tool. 
Press file -> scan file, select "A2.VAB", then press start button.
You will can listen here six sounds inside with 22050Hz/Mono, this is not special sound or music, it's kind of MIDI notes, but very specific, you can record it in-game only with right sequence, just listen some dark ambients.
So you can save files with pressing: file -> convert, and save wav file, here some results:
A2_00002.mp3
upd: i got your mind, you want to convert midi tracks to PC-like format, i think it's impossible, only in-game recording.

Yea i just want the mid. I dont think its impossible. I want it because there is a a lot of unused tracks in this game. If not that i would like some kind of support with VGMTrans that can read it. oooorr if someone could make an importer for the silent hill extractor. Theres only an extractor and not an import it. I could swap the track. IS reverse engineering that shextactor possible for you or some one.
## Post #4
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2013-09-24T23:52:11+00:00
- Post Title: Silent Hill .KDT (PS1)

> Theres only an extractor and not an import it
not only, take a look here:
[viewtopic.php?f=32&t=10313](http://forum.xentax.com/viewtopic.php?f=32&t=10313)

> I want it because there is a a lot of unused tracks in this game.
You really sure? You know names of files, that unused inside SND folder? There is some Complete soundtracks you can find somwhere in net with recorded midi in-game.

> oooorr if someone could make an importer for the silent hill extractor. Theres only an extractor and not an import it
It's don't need actually, because you can import files (smaller then original) with HEX editor, just write to me names of unused MIDI tracks and i will see, what i can do, but i can't promise too much.
## Post #5
- Username: peronmls
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 05, 2011 6:21 am
- Post datetime: 2013-09-25T02:37:46+00:00
- Post Title: Silent Hill .KDT (PS1)

I have all of those. There is no importer. First you need to see if you can even switch them around. Replace the track that plays when that flying thing crashes through the window of the cafe. If you don't not which track that it them tell me. I'm not on the computer at the moment. 

A note. I tired switching them with a hex editor in sh3 and it hangs when I load my save so I I'm sure it won't work with hexing. I could be wrong. Also sh1-4 have tons of unused tracks that I have found that nobody has put up. I know 1 has them but I have never heard them yet until I can make a Psf or have the unused tracks switch with he used ones.
## Post #6
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2013-12-01T19:06:05+00:00
- Post Title: Silent Hill .KDT (PS1)

here, that's how we can extract sh track music:

[http://www.neillcorlett.com/psf/](http://www.neillcorlett.com/psf/)
## Post #7
- Username: peronmls
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 05, 2011 6:21 am
- Post datetime: 2013-12-03T04:31:16+00:00
- Post Title: Silent Hill .KDT (PS1)

Well yeah i know that. I don't know MIPS or how to make a custom driver. I' m slightly understand SH2 and 3 .TD
## Post #8
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2013-12-20T16:46:37+00:00
- Post Title: Silent Hill .KDT (PS1)

> Reply from peronmls
>
> I don't know MIPS or how to make a custom driver.
take a look here

also found your another thread here: [http://www.hcs64.com/mboard/forum.php?showthread=36213](http://www.hcs64.com/mboard/forum.php?showthread=36213)
[ex.jpg](https://xentaxbackup.github.io/file/6865_ex.jpg)
## Post #9
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2013-12-23T08:28:23+00:00
- Post Title: Silent Hill .KDT (PS1)

would that method work for any game?
## Post #10
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2013-12-23T14:56:54+00:00
- Post Title: Silent Hill .KDT (PS1)

> Reply from Devilot
>
> would that method work for any game?
What method? PSF finder?
## Post #11
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2013-12-23T15:04:08+00:00
- Post Title: Silent Hill .KDT (PS1)

the one in the screenshot
## Post #12
- Username: peronmls
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 05, 2011 6:21 am
- Post datetime: 2014-01-09T16:39:38+00:00
- Post Title: Silent Hill .KDT (PS1)

I guess I can try that.
