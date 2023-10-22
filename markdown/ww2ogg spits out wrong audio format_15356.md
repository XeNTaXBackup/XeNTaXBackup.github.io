## Post #1
- Username: seriouscitizenl
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 12, 2016 2:39 pm
- Post datetime: 2016-10-12T06:47:29+00:00
- Post Title: ww2ogg spits out wrong audio format

So I have [this wwise/wav file](file) and I run it through ww2ogg this way

> ww2ogg.exe 660566263.wav --pcb Tools\packed_codebooks_aoTuV_603.bin

and it spits out [this weird ogg](file)

Upon further inspection, ww2ogg produces an ogg file that is 18kHz 2-Channel and that when opened, it looks like this



It becomes apparent ww2ogg is spitting out the wrong format when the file should really be 32kHz 1 Channel, 32kHz also being in line with the other audio files in the same pck.

Now, it all looks pretty obvious, force ww2ogg to somehow interpret the wwise file as another format. This is where I don't know what to do and how. I've tried a bunch of commands and I've gone nowhere. Any help is appreciated.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-10-14T19:37:49+00:00
- Post Title: ww2ogg spits out wrong audio format

The solution is to force unmodified packets:

```
ww2ogg 660566263.wav --no-mod-packets --pcb packed_codebooks_aoTuV_603.bin
```

This is mentioned in the Troubleshooting section of the readme, though this switch was only introduced in ww2ogg 0.24. I discovered that the logic I was using to detect mod packets just wasn't working all the time, so I added the ability to force it manually.

P.S. stereo and mono Vorbis are structured very differently, if you tried to force this as mono (which you can do by setting byte 0x17 to 1 in the original RIFX), the codebooks are still for stereo so it will fail when parsing anything with coupling (as there are not enough channels to couple between).
## Post #3
- Username: seriouscitizenl
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 12, 2016 2:39 pm
- Post datetime: 2016-10-20T11:12:53+00:00
- Post Title: ww2ogg spits out wrong audio format

Forgot to reply to the thread. Tried it the other day and it worked! So thank you for that.
