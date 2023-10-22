## Post #1
- Username: Gaara5
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 26, 2019 4:12 am
- Post datetime: 2019-03-26T13:40:24+00:00
- Post Title: Stardew valley switch wavebank

Afternoon,

I try to replace some tracks from the wavebank of stardew valley but i run in some troubles. The tutorial for the pc version doesnt work on the wavebank of the switch version. If i unpack the wavebank.xwb with unxwb.exe all .wav are corrupted. What i could gather or try to understand is that the files are not really in the .wav format instead their should be in the .xma format. So i try to different programms like xma_encode.exe, xma_parse and quickbms but i got many errors and nothing seems to work. 
So before i can repack a new wavebank for the game i would like to know what format the orignal wavebank use to replicate it. 

I am thanksful for every help i can get because i am pretty new to all this and run out of options.
I dont know if i could upload the full wavebank file for legal reasons so upload a sample file from the extract.

Examples:
1. Corrupted wav: [https://drive.google.com/file/d/1DMpGL2 ... sp=sharing](https://drive.google.com/file/d/1DMpGL2N9Wd5os0ppikTGQOeBClqIaikw/view?usp=sharing)
2. Raw unpackt with unxwb: [https://drive.google.com/file/d/1nJhfJl ... sp=sharing](https://drive.google.com/file/d/1nJhfJlSl6QJxDnecAsU8tC9Xml3-ZSib/view?usp=sharing)
3. Some documents about the format: [https://github.com/losnoco/vgmstream/bl ... meta/xwb.c](https://github.com/losnoco/vgmstream/blob/master/src/meta/xwb.c)
4. Original tutorial: [https://community.playstarbound.com/thr ... ux.127661/](https://community.playstarbound.com/threads/sound-modding-tutorial-discussion-redux.127661/)
## Post #2
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2019-04-14T20:59:01+00:00
- Post Title: Stardew valley switch wavebank

Hi Gaara5,

usually we have uploads of the audio archive (in this case the .xwb file), but I've been inactive in this forum for quite a while so things may have changed. You could try to use [xactxtract](https://forum.xentax.com/viewtopic.php?f=17&t=4391&start=15) which tells you if the files are wav, xma or xwma, but it'll work for little endian .XWBs (=used on PC) only. By the way the tutorial you linked is not quite correct in one point: files *are* 'labeled', but the 'labels' are in the corresponding xsb file.

BTW: Did you try using xWMAEncode?
