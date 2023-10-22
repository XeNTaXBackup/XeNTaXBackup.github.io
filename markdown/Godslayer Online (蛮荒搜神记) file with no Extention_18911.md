## Post #1
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2018-10-09T23:43:01+00:00
- Post Title: Godslayer Online (蛮荒搜神记) file with no Extention

Hi, can someone take a look and see if these file can be extracted? 
They have no format or extension... the only thing that all files had in common is a bunch of weird text in Hex Editor for their category...
Sample 21MB ==>> [https://drive.google.com/open?id=1MwWkn ... f1O9pBb2P9](https://drive.google.com/open?id=1MwWknKVjUp2_NMTwRi3q-pf1O9pBb2P9)
The sample include some animation, model, texture, materials.... 



Game Official Site: [http://mh.changyou.com/](http://mh.changyou.com/)
Download Game Archive here: [http://ct.vpan123.com/d/11096425.html](http://ct.vpan123.com/d/11096425.html)
If you need more sample, let me know, so you don't have to download the whole game folder.
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2018-10-10T00:10:46+00:00
- Post Title: Godslayer Online (蛮荒搜神记) file with no Extention

CryTek model format, delete byte before "CryTek" in hex editor and you will be able to open models in Noesis.
## Post #3
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2018-10-10T01:23:39+00:00
- Post Title: Godslayer Online (蛮荒搜神记) file with no Extention

> Reply from zaramot
>
> CryTek model format, delete byte before "CryTek" in hex editor and you will be able to open models in Noesis.
Hi zaramot, thanks for the help... but even after I deleted the other bytes off before "CryTek..." I still can't open them in Noesis...
Do I need a plugin, rename the extension or anything specific? All I got from Noesis is the popup "File could not be preview"...


I tried to put an extension to the same file on your SS but still give me the same error popup in Noesis.
## Post #4
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2018-10-10T01:32:36+00:00
- Post Title: Godslayer Online (蛮荒搜神记) file with no Extention

Oh nvm, I was missing the "cryengine_cgf.dll" on my plugin folder... after downloaded the file from [http://www.mediafire.com/file/bc4c1ybfo ... ine_cgf.7z](http://www.mediafire.com/file/bc4c1ybfokc048d/cryengine_cgf.7z)
It fixed the problem...
Thanks again for pointing it out zaramot... Really appreciated it.
-------------------------------------------
Special thanks to E3245 at FacePunch Forum for sharing the link [https://forum.facepunch.com/f/fbx/qtzu/ ... -Plugin/1/](https://forum.facepunch.com/f/fbx/qtzu/Noesis-CryEngine-Plugin/1/)
## Post #5
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-12-17T23:54:19+00:00
- Post Title: Godslayer Online (蛮荒搜神记) file with no Extention

I recently had the opportunity to do some research on CryEngine and am having some success with CryEngine's animation conversion.
This game is no exception, but the remaining clients are very old and the data is only partial.
The game's caf was a bit complicated with a concatenated database, but it loaded successfully.

I will post a capture later. If anyone has a newer client, please contact me via PM.



npc_b_bw_634_caf.PNG (15.01 KiB) Viewed 94 times


The direction of movement of the root is wrong and if it moves horizontally it will head upwards, but it would be possible to correct this.
