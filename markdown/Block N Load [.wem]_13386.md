## Post #1
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2015-10-03T17:18:30+00:00
- Post Title: Block N Load [*.wem]

Can someone help extract audio from these files - [WEM](https://mega.nz/#!kwAURJYC!PAMJUY3iKYguPKElfIldLGZuLMaWOnho4umsknJS-xU)?
Other files extracted by use the programs: ww2ogg, revorb, packed_codebooks_aoTuV_603.bin

When you use programs an error: "Parse error: expected 0x42 fmt if vorb missing". I thought I could do with the help of ima_rejigger2.exe, but failed, because Codec audio files no Microsoft ADPCM, just WAV.
## Post #2
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-10-03T19:25:59+00:00
- Post Title: Block N Load [*.wem]

Half of them are vorbis and it seems you didn't notice spaces in names. In this case you need to use "" for filename (ww2ogg --pcb packed_codebooks_aoTuV_603.bin "BnL Theme V3_longer.wem"). Others are pcm and you can use [this](http://forum.xentax.com/viewtopic.php?p=108929#p108929) script.
## Post #3
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2015-10-04T03:53:33+00:00
- Post Title: Block N Load [*.wem]

> Reply from spider91
>
> Half of them are vorbis and it seems you didn't notice spaces in names. In this case you need to use "" for filename (ww2ogg --pcb packed_codebooks_aoTuV_603.bin "BnL Theme V3_longer.wem"). Others are pcm and you can use this script.
Thanks you very much.
