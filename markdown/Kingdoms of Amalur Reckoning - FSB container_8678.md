## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-01T18:37:15+00:00
- Post Title: Kingdoms of Amalur: Reckoning - FSB container

Could anyonw please try to extract the MP3 tracks from the main FSB file of this game? I've tried various tools (fsbext, fsb_mpeg, mp3extract) but to no avail.
Thanks for your help!
[http://www.sendspace.com/file/h1wu0q](http://www.sendspace.com/file/h1wu0q)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-01T20:50:29+00:00
- Post Title: Kingdoms of Amalur: Reckoning - FSB container

Try ToWav
[ToWav.zip](https://xentaxbackup.github.io/file/5248_ToWav.zip)
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-01T21:15:38+00:00
- Post Title: Kingdoms of Amalur: Reckoning - FSB container

Nope, doesn't work either. :-\
Anyone else got any ideas?
## Post #4
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2012-06-02T06:25:24+00:00
- Post Title: Kingdoms of Amalur: Reckoning - FSB container

ToWav and fsbext correctly extracts mp3 data, but mp3s is compressed, I think.

First six bites is constant - яы @.. (FF FB A0 40 00 0C). Next is mp3 file data.

Examples:
Adessa_Interiors_Intro

```
яы @..ѓN7E.xBr]жшvhВj.©U.n<ЇYуњ¤]і".3Sу.¦<aЈБй6.гt4ЃBгжb&..:ґјG.+..—§Ј.-Јє»аxbZнЕЯG^!{[”An’Фv).d.«0ЬѕёybЃ8FB$0Ў…Яd..ЇяH.J.э!&ч„‘AЕЯИЅїђ(¶@аа<њ.Ђ.А$.ЃP.aі’.|.I$h..тГтHszЏ....¤.Ю..о`В..ОO`.И!јЊ®F?ьЊ.КцЯууї#).].F.!„пш8p1LNх;.яД
```

Adessa_Interiors_Ioop

```
яы @...·6WVfd.y‡КэНTђНС.S\цЂ.бЄй.ґ°....C.—j·dvЂ.AќHM«.ш_Wк.ВE.qЂВй¤р.тНLЌSLw(‘lЩI.Еб‚.ҐsUкK.`;.T.„.rzн®.ш6АFа±Р..,§1tjuq?“C° [@т”ЮК_—M†©,_.PХК&Rrvќe‚Ј.Ѕ¬КV....p...Я··Ђ..а4р.ЄЏ.ФТ.,Д!i#=.HФ¦}2§е~E‡=I1pdG -«;к.·А$h0...ЉезЬ Y.”
```
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-02T08:32:24+00:00
- Post Title: Kingdoms of Amalur: Reckoning - FSB container

maybe they are multichannel or similar.
it's not the first time that I see mp3 with a correct header (0xff ...) but they are unplayable.
and for sure it's not a problem of fsbext :)
## Post #6
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2012-06-02T16:15:25+00:00
- Post Title: Kingdoms of Amalur: Reckoning - FSB container

fsbext shows next information about fsb and files information:
FSB4 version 4.0 mode 64 
delta,24-47 44100 2 16

* snip *
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-06-12T17:25:45+00:00
- Post Title: Kingdoms of Amalur: Reckoning - FSB container

Just to let everybody know, this fsb container has a byte padding of 32, so just run the batch

```
fsb_mpeg %1 -p 4 -b 32
```
## Post #8
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2012-06-12T18:24:15+00:00
- Post Title: Kingdoms of Amalur: Reckoning - FSB container

AlphaTwentyThree, for what tool use this batch?
## Post #9
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2012-06-12T20:09:05+00:00
- Post Title: Kingdoms of Amalur: Reckoning - FSB container

[FSB MPEG](http://hcs64.com/files/fsb_mpeg012.zip) is the tool
## Post #10
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2020-09-26T20:24:17+00:00
- Post Title: Kingdoms of Amalur: Reckoning - FSB container

about r Re-Reckoning bms script found *.ksdf file 
any idea about this one 
thank's
