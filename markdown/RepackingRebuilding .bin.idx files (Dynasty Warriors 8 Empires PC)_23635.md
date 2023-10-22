## Post #1
- Username: rosalba
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Apr 24, 2020 8:21 am
- Post datetime: 2021-03-26T12:56:33+00:00
- Post Title: Repacking/Rebuilding .bin/.idx files? (Dynasty Warriors 8 Empires PC)

I've done some research around the internet and found that Koei Tecmo's games share similar containers (.bin paired with an .idx file), at least as I've seen with Dynasty Warriors games, AOT, Hyrule Warriors, and Dragon Quest.

There are several bms scripts that can extract the many versions of Koei's .bin files, but I'm wondering if there's a way to repack/rebuild the .bin file? Several topics across several forums seem to imply that it's possible for other Koei games, but unfortunately not for Dynasty Warriors. I've seen a tutorial that allows for extracting and rebuilding Hyrule Warriors' .bin file, and tool (OPPW3_ResWork/Unpacker) that allows the same thing.

OPPW3_ResWork runs into a "Out of Memory" error when I use it for DW8E, though. And the tutorial for HWL doesn't work with DW8E for obvious reasons.

So, while it is indeed possible to repack the .bin/.idx file, is there a way to do the same for DW8E? I want to try and mod the game, though this idea is relatively rare in DW, aside from the re-color of the models in DW8XL, changing normal running speeds to god-like zooms (rather entertaining), and some model swaps.

Any help will be appreciated!
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-26T13:37:53+00:00
- Post Title: Repacking/Rebuilding .bin/.idx files? (Dynasty Warriors 8 Empires PC)

Please upload some BIN/IDX samples.
## Post #3
- Username: rosalba
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Apr 24, 2020 8:21 am
- Post datetime: 2021-03-26T16:20:43+00:00
- Post Title: Repacking/Rebuilding .bin/.idx files? (Dynasty Warriors 8 Empires PC)

> Reply from ikskoks ↑Fri Mar 26, 2021 9:37 pm at Fri Mar 26, 2021 9:37 pm
>
> 
Please upload some BIN/IDX samples.
Here's the .idx/.bin files: [https://drive.google.com/file/d/12bxcv7 ... sp=sharing](https://drive.google.com/file/d/12bxcv7V1lDLfhFwAOpZ2C6VPa2-3Qkhh/view?usp=sharing)
The game only has one pair of .idx and .bin files, so the above sample file is 7GB big (in comparison to some KT games that have linkdata_a.bin, linkdata_b.bin, etc. or subdivided by parts).

However, there's a folder named "RES" in the installation folder filled with similar .bin files minus the .idx file, with sizes ranging from 1KB to 118MB. Should I also upload a sample of one of those files?
## Post #4
- Username: rosalba
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-28T21:44:48+00:00
- Post Title: Repacking/Rebuilding .bin/.idx files? (Dynasty Warriors 8 Empires PC)

I have checked your samples and here are the results
[http://wiki.xentax.com/index.php/Dynast ... es_BIN_IDX](http://wiki.xentax.com/index.php/Dynasty_Warriors_8:_Empires_BIN_IDX)

I have also created a tool to extract data
[https://github.com/bartlomiejduda/Tools ... DX_Tool.py](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Dynasty%20Warriors%208/Dynasty_Warriors_8_BIN_IDX_Tool.py)


As for repacking, it could be difficult, becasue as I saw some files are using custom ZLIB compression. I've tried to use offzip on them, but it is not working properly. Other files could be probably packed with new quickbms script or custom tool, because structure of the archive isn't that complicated.

I can also tell you that these BIN/IDX files are different that the ones from other Koei Tecmo/Arc System Works games like for example Hokuto No Ken which I had checked earlier this month [http://wiki.xentax.com/index.php/Hokuto_no_Ken_BIN_IDX](http://wiki.xentax.com/index.php/Hokuto_no_Ken_BIN_IDX)


So to sum this up - more research needs to be done here, but I think that packing of some files is possible now.
## Post #5
- Username: rosalba
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Apr 24, 2020 8:21 am
- Post datetime: 2021-03-29T09:19:07+00:00
- Post Title: Repacking/Rebuilding .bin/.idx files? (Dynasty Warriors 8 Empires PC)

> Reply from ikskoks ↑Mon Mar 29, 2021 5:44 am at Mon Mar 29, 2021 5:44 am
>
> 
I have checked your samples and here are the results
http://wiki.xentax.com/index.php/Dynast ... es_BIN_IDX

I have also created a tool to extract data
https://github.com/bartlomiejduda/Tools ... DX_Tool.py


As for repacking, it could be difficult, becasue as I saw some files are using custom ZLIB compression. I've tried to use offzip on them, but it is not working properly. Other files could be probably packed with new quickbms script or custom tool, because structure of the archive isn't that complicated.

I can also tell you that these BIN/IDX files are different that the ones from other Koei Tecmo/Arc System Works games like for example Hokuto No Ken which I had checked earlier this month http://wiki.xentax.com/index.php/Hokuto_no_Ken_BIN_IDX


So to sum this up - more research needs to be done here, but I think that packing of some files is possible now.
Oh lord thank you so much for looking into the files and providing a way to extract its contents! It might take a while to be able to rebuild this particular data compression, but this is a good step to learning more about this kind of stuff.

I'm still a beginner when it comes to things like this, but I hope to learn as much as I could 
Thank you again! I hope there'll be more progress in the future on this.
## Post #6
- Username: EvilRyu2KX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 12, 2020 5:43 am
- Post datetime: 2021-06-29T23:48:39+00:00
- Post Title: Repacking/Rebuilding .bin/.idx files? (Dynasty Warriors 8 Empires PC)

Dynasty Warriors 5/6 from PS2 are also .bin/.idx: could be this OPPW3 compatible with it? Or needs an appropriate repacker/rebuilder?
