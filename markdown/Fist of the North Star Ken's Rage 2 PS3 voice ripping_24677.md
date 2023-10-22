## Post #1
- Username: giorgione
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 03, 2015 8:00 pm
- Post datetime: 2021-11-02T08:52:15+00:00
- Post Title: Fist of the North Star: Ken's Rage 2 PS3 voice ripping

Hello, I've got an interest in ripping some voices from this game, I found this 10 years old thread  
[viewtopic.php?f=21&t=6290](https://forum.xentax.com/viewtopic.php?f=21&t=6290) 
for the first game tho, and x360, however I did try the method suggested there: there is indeed a voice.pac file, and I used this script for quickbms:

```
reverselong FILES
for i = 0 < FILES
    padding 0x800
    savepos OFFSET
    getdstring RIFF_SIGN 4
    get SIZE long
    math SIZE += 8
    log "" OFFSET SIZE
    math OFFSET += SIZE
    goto OFFSET
next i
```


I have no idea if it is correct in any way but I got 11kish *.wav files, which of course are not ready for use, here is one of them:
[https://www.mediafire.com/file/snofar0e ... 2.wav/file](https://www.mediafire.com/file/snofar0e6pyx1qk/000000a2.wav/file)

If someone could help me here it would be great, again I'm also not sure if I even unpacked these files correctly, needless to say I'm a complete ignoramus on the matter.
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-11-02T12:25:25+00:00
- Post Title: Fist of the North Star: Ken's Rage 2 PS3 voice ripping

If you rename the files to *.at3 they will play in Foobar/vgmstream.
## Post #3
- Username: giorgione
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 03, 2015 8:00 pm
- Post datetime: 2021-11-02T16:21:05+00:00
- Post Title: Fist of the North Star: Ken's Rage 2 PS3 voice ripping

> Reply from DKDave ↑Tue Nov 02, 2021 8:25 pm at Tue Nov 02, 2021 8:25 pm
>
> 
If you rename the files to *.at3 they will play in Foobar/vgmstream.

terrific, thanks! I also see I can use foobar to convert them, this was much less of a headache than I imagined.
