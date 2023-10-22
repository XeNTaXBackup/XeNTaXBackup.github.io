## Post #1
- Username: kas1m
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 09, 2012 1:04 am
- Post datetime: 2013-09-22T19:13:16+00:00
- Post Title: [PS3] GTA V *.awc audio

I discovered that it is not encrypted and has mp3 in it(cuz there is planty LAME3.97 marks in it). 
And if you'll cut all header data from bytes "54 41 44 41" to bytes "FF FB" you could actually play it as MP3 file (32000 Hz / 24-bit / 1 channels).
But it will repeate some segments, because there is 2 channels: you will hear couple of seconds of one channel sound and then it will repeat the same sound for another channel.
After first look, it seems that channel data separated by blocks of zero bytes. 
So if you are programmer you could help us to reverse that container. If my guess is right
You just have to code simple tool that reads first block of data from "FF EB" to "zero block"(this block can be different size, but it will be > 8 bytes) and writes this block(without zeroes) into another file, then it should skip next block of data(from first zero block to next zero block. It will be another channel data.) and then write next block, then skip block, etc. It will be first channel data. Then it should do the same to another channel.
PS
I'm downloading visual studio right now, but I didn't code for ages, and it could took great amount of time to write that simple tool.
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-09-22T20:08:04+00:00
- Post Title: [PS3] GTA V *.awc audio

Yes please if someone can reverse this, it would be great!!
## Post #3
- Username: kas1m
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 09, 2012 1:04 am
- Post datetime: 2013-09-23T05:31:03+00:00
- Post Title: [PS3] GTA V *.awc audio

No, unfortunately it wasn't that simple.
But seems that all sound separated by large zero blocks in container(more than 20kb). There is 14 seconds sound data(7 for left and 7 for right channels) and then large zero block, that includes some header...
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2013-09-23T06:36:54+00:00
- Post Title: [PS3] GTA V *.awc audio

Can you PM me a sample (preferably the first 10MB, or a single archive under 10MB).

I'll try and see if I can make anything of it
## Post #5
- Username: kas1m
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 09, 2012 1:04 am
- Post datetime: 2013-09-23T14:27:27+00:00
- Post Title: [PS3] GTA V *.awc audio

> Reply from brendan19
>
> Can you PM me a sample (preferably the first 10MB, or a single archive under 10MB).

I'll try and see if I can make anything of it
done.
PS
I wrote aweful code that split awc files, but result is totally unaceptable, as channel files has different lenght, and you can hear scratches in almost every joint of two segments. 
We have to lern about headers, that placed in large zero blocks, but I really can't get what info is placed in it. =(
## Post #6
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2013-09-24T00:17:28+00:00
- Post Title: [PS3] GTA V *.awc audio

> Reply from brendan19
>
> Can you PM me a sample (preferably the first 10MB, or a single archive under 10MB).

I'll try and see if I can make anything of it

Let me know if you need any other samples. I've got the AWCs extracted, and if you change the extension to MP3 they actually play in VLC with no other modification, but like kas1m described, they repeat after a variable amount of time depending on the song.

I just REALLY want to get the score into a playable format
## Post #7
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2013-09-24T14:41:30+00:00
- Post Title: [PS3] GTA V *.awc audio

Pretty sure the MP3's are VBR because the frames vary in length at different parts. The frames change every so often in length so de-interleaving them using Alpha23's BMS script probably won't help because they won't divide evenly into separate parts.

Some segments run double the length of others.

Also, the sync word changes throughout the file to different positions. There might be something to that yet, I'm not sure.
