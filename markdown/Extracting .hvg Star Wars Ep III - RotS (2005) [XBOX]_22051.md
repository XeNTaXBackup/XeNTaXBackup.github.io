## Post #1
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-04-22T07:26:36+00:00
- Post Title: Extracting .hvg Star Wars: Ep III - RotS (2005) [XBOX]

Hello, could someone help me extract .hvg audio files which are in .pak files, with bms script. I have samples at your disposal. I try to do something but I can't find.

.hvg samples: [https://www.mediafire.com/file/xr3wlubr ... s.zip/file](https://www.mediafire.com/file/xr3wlubr8a32srb/hvg_samples.zip/file)

And this is my code:

```
do
    goto OFFSET
    get DUMMY long
    findloc NEXT_OFFSET binary "\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00" 0 ""
    if NEXT_OFFSET == ""
        get SIZE asize
    else
        math SIZE = NEXT_OFFSET
    endif
    math SIZE -= OFFSET
   string NAME p "%08x.hvg" OFFSET
   log NAME OFFSET SIZE
    math OFFSET = NEXT_OFFSET
while NEXT_OFFSET != ""

```


Thank you
## Post #2
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-04-22T13:08:50+00:00
- Post Title: Extracting .hvg Star Wars: Ep III - RotS (2005) [XBOX]

These are convertable and playable using MFAudio and setting their Import format to Compressed then playing around with their Frequency.
You can download MFAudio [here](https://www.zophar.net/utilities/ps2util/mfaudio-1-1.html).

Here are the samples you sent, I managed to convert them using this technique: [https://www.dropbox.com/s/ls9uykowq3tfg ... s.rar?dl=0](https://www.dropbox.com/s/ls9uykowq3tfg3p/hvg%20samples.rar?dl=0)

The image I attached will help you figure out what settings to insert to convert your sounds.

Enjoy!  
[MFAudio.png](https://xentaxbackup.github.io/file/17993_MFAudio.png)
