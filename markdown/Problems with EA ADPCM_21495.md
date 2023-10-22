## Post #1
- Username: mypantsfelldown
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Dec 14, 2019 1:53 am
- Post datetime: 2019-12-13T18:10:17+00:00
- Post Title: Problems with EA ADPCM

Hi there!

So recently I've been using FFMPEG to convert audio tracks from a Sims game that stores its music in EA ADPCM R3 (or so according to FFMPEG). Almost all of these tracks have converted perfectly fine except two... The resulting files are just static. After researching as much as I could find on this forum, I'm guessing this is related to some kind of endianness or reversed byte order. I'm just not sure on how to go about fixing that. [Here](https://drive.google.com/file/d/1t_poW7cR-pcoz8WkabJmOWDdbMtknJAi/view?usp=sharing) you can find the files in question. Thanks for any help!
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-12-14T00:47:12+00:00
- Post Title: Problems with EA ADPCM

Both of those files play perfectly fine with vgmstream in Foobar.  The audio is 16-bit PCM (big endian).
## Post #3
- Username: mypantsfelldown
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Dec 14, 2019 1:53 am
- Post datetime: 2019-12-14T01:17:06+00:00
- Post Title: Problems with EA ADPCM

I managed to convert the files using the method you suggested. Thanks!
