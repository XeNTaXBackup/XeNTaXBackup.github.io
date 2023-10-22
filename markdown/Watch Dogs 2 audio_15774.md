## Post #1
- Username: SammyWins
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Nov 16, 2014 1:55 pm
- Post datetime: 2017-01-22T16:38:21+00:00
- Post Title: Watch Dogs 2 audio

I can't figure out file format. I've tried to run it through ww2ogg and revorb as usual, but revorb crashes for some reason. Any ideas?
[san_francisco_sound_english 00161.zip](https://xentaxbackup.github.io/file/12265_san_francisco_sound_english 00161.zip)
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2017-01-22T20:13:22+00:00
- Post Title: Watch Dogs 2 audio

I converted it just fine using ww2ogg v0.24 and revorb. The packed codebooks switch must be used to convert it properly.

add "--pcb packed_codebooks_aoTuV_603.bin" to the command line and it should be fine.
## Post #3
- Username: SammyWins
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Nov 16, 2014 1:55 pm
- Post datetime: 2017-01-23T05:24:48+00:00
- Post Title: Watch Dogs 2 audio

> Reply from brendan19
>
> I converted it just fine using ww2ogg v0.24 and revorb. The packed codebooks switch must be used to convert it properly.

add "--pcb packed_codebooks_aoTuV_603.bin" to the command line and it should be fine.

Thanks! It works)
