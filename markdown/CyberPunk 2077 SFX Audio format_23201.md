## Post #1
- Username: BartOss
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 15, 2020 4:39 pm
- Post datetime: 2020-12-21T02:50:55+00:00
- Post Title: CyberPunk 2077 SFX Audio format

Hey guys, I can't figure out what the kind of format it is, or how to convert this one...
In the "audio_2_soundbanks.archive" present music and sfx in bin files
music files is wem, I got renamed these in wem and after this I did convert in ogg - no problem
The rest is sfx - I've renamed it to ogg and it's works in foobar, so I can convert this, but so far just half of it. The rest audio files got unknown format for me, I can't listen it in any form, so I wondering if someone can explain how to play these files. Probably this is bank or arhive with files, because they are pretty big for one sample, so I can't belive such a big game as CyberPunk had just about 1600 sfx which was extracted except music, it' impossible if you realize the scale of the game. Thanks for any help!   

Examples: 
[https://vk.com/doc185053571_581854698](https://vk.com/doc185053571_581854698)
[https://vk.com/doc185053571_581854721](https://vk.com/doc185053571_581854721)
[https://vk.com/doc185053571_581854739](https://vk.com/doc185053571_581854739)
## Post #2
- Username: 0ther1
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Apr 30, 2020 10:56 am
- Post datetime: 2020-12-21T10:28:35+00:00
- Post Title: CyberPunk 2077 SFX Audio format

These files are single tracks each in Wwise PCM format, you can convert it with vgmstream (rename .bin to .wem first) or just manually change format at offset 20 from 0xFEFF to 0x0100 and rename to .wav. They are big because it's basically a .wav format which is normal
## Post #3
- Username: BartOss
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 15, 2020 4:39 pm
- Post datetime: 2020-12-21T21:48:45+00:00
- Post Title: CyberPunk 2077 SFX Audio format

Thank You for this ! I'll try soon as possible !
