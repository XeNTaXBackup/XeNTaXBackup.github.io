## Post #1
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2014-07-09T05:56:21+00:00
- Post Title: Batman: Arkham Asylum [PC][FMOD]

The game use FMOD audio engine for music. But fmod file is containers, which uses as part of .umap files(old version of UE3, later - 2010-2011 - uses audio separation from other in UE packages).
Files already found and extracted, but has encryption, as I understand - fsbext knows about some variants of it.
hcs64 tools dont understand files, because dont have any standart for fmod files.
Nova Extractor could extract it as MP3, but not right and some files dont extracted.
Few samples - [http://multiupload.biz/yw0jvtpxsrrc/BAA ... iz.7z.html](http://multiupload.biz/yw0jvtpxsrrc/BAAfmod_MultiUpload.biz.7z.html)

Looking a way for extracting.
## Post #2
- Username: mauzerX
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jul 01, 2010 8:48 pm
- Post datetime: 2014-07-09T13:15:38+00:00
- Post Title: Batman: Arkham Asylum [PC][FMOD]

with hcs64 tools:
1)fsbii extract .fsb from .RFMODSound
2)fsb_mpeg extract .mp3 from .fsb and split multichannels .mp3
## Post #3
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2014-07-09T17:10:30+00:00
- Post Title: Batman: Arkham Asylum [PC][FMOD]

Thanks.
