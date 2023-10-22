## Post #1
- Username: mypantsfelldown
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Dec 14, 2019 1:53 am
- Post datetime: 2020-01-31T01:01:33+00:00
- Post Title: Can anyone decode this file?

Hey, I apologise about spamming this forum with my posts, but I've got another issue.

I'm trying to extract music from a PS2 game and most of it is in a readable format. I've managed to get PSound to convert most of it, but the loading music is different somehow. PSound cannot read it, VGMStream doesn't know what it is and I've tried a bunch of other audio converters that can't read it either. The BMS script I used to extract the archives didn't assign any of the files extensions, so I have no clue what to look for. There are two versions of each file; both versions appear to be roughly the same size from what I can see, excluding some tracks. I would appreciate any help!

[Download](https://drive.google.com/file/d/1iGevr08PhcvT_42cyT-Eijy6lJgA_BBy/view?usp=sharing)
## Post #2
- Username: allangod
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 25, 2018 6:58 am
- Post datetime: 2020-01-31T01:34:52+00:00
- Post Title: Can anyone decode this file?

Just use MFAudio, worked for me. Note that any file you gonna work with on MFAudio must have an extension (just invent one, i.e. .h, .bestextensionever). It is mono (1 channel), no offsets, and I am unsure if the frequency is 22050 or 32000hz, but if you've played the game, you probably can know by listening to it in MFAudio (has a built-in media player). Attached one of the converted files (22050hz).
[load_loop2.mp3](https://xentaxbackup.github.io/file/17432_load_loop2.mp3)
## Post #3
- Username: mypantsfelldown
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Dec 14, 2019 1:53 am
- Post datetime: 2020-01-31T01:58:58+00:00
- Post Title: Can anyone decode this file?

> Reply from allangod ↑Fri Jan 31, 2020 9:34 am at Fri Jan 31, 2020 9:34 am
>
> 
Just use MFAudio, worked for me. Note that any file you gonna work with on MFAudio must have an extension (just invent one, i.e. .h, .bestextensionever). It is mono (1 channel), no offsets, and I am unsure if the frequency is 22050 or 32000hz, but if you've played the game, you probably can know by listening to it in MFAudio (has a built-in media player). Attached one of the converted files (22050hz).
That worked, thank you! I had tried MFAudio before, but I never realised it required files to have extensions.
