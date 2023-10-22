## Post #1
- Username: PvZABFan
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 22, 2018 3:33 pm
- Post datetime: 2018-06-22T07:42:37+00:00
- Post Title: Need help with Plants vs Zombies Garden Warfare 2 .SB/.TOC

Most of the .SB and .TOC files of this game extract normally, but certain ones will not unpack (it's either map files or files containing music.) If anyone could help me with this, it'd be wonderful.

.SB example: [https://drive.google.com/open?id=1GoR49 ... E7jJ697eR9](https://drive.google.com/open?id=1GoR49bLqLL3yipRbNat-c1E7jJ697eR9)

.TOC example: [https://drive.google.com/open?id=1h53W3 ... 87_-QC2v6c](https://drive.google.com/open?id=1h53W3Lhideb6hYU8f9giO887_-QC2v6c)
## Post #2
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-06-22T18:40:16+00:00
- Post Title: Need help with Plants vs Zombies Garden Warfare 2 .SB/.TOC

I've stated this somewhere in the forum, the game extracts fine, every single asset, except one main file which is a sb/toc pair where the SB archive "\Data\Win32\commonchunks.sb" is 6.58GB in size, python script that extracts the game and its dll decompressor does NOT support 4GB+ in size, thats why your missing important chunks for various assets, thus nothing works, nothing that si out there will extract those large archives, unless there is and I am missing something, Battlefield Hardline faces same issue with some Xpacks, it is what it is.
Or maybe your performing a different kind of extraction?
## Post #3
- Username: PvZABFan
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 22, 2018 3:33 pm
- Post datetime: 2018-06-22T19:46:52+00:00
- Post Title: Need help with Plants vs Zombies Garden Warfare 2 .SB/.TOC

I was using a quickbms script, it didn't seem to work with certain .SB and .TOC, but worked with all the others.
## Post #4
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-06-22T21:33:00+00:00
- Post Title: Need help with Plants vs Zombies Garden Warfare 2 .SB/.TOC

> Reply from PvZABFan
>
> I was using a quickbms script, it didn't seem to work with certain .SB and .TOC, but worked with all the others.
Ah, that script unfortunately is not good for your purpose, it was never updated to support bundle extraction from superbundles, it simply doesn't extract everything, and if I remember correctly its chunk files are still compressed while the python decompresses them.
## Post #5
- Username: PvZABFan
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 22, 2018 3:33 pm
- Post datetime: 2018-06-23T00:53:33+00:00
- Post Title: Need help with Plants vs Zombies Garden Warfare 2 .SB/.TOC

Do you have a link to this python script? And if you do, how do I use it?
## Post #6
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-06-23T03:51:04+00:00
- Post Title: Need help with Plants vs Zombies Garden Warfare 2 .SB/.TOC

> Reply from PvZABFan
>
> Do you have a link to this python script? And if you do, how do I use it?
The forum is full of them its from Battlefield 4 game since they use same format and game engine, but I do not recommend it since it can NOT extract that large archive I mentioned above, better wait till a solution will surface, basically it will be incomplete as well, and you'll get even more frustrated.
## Post #7
- Username: PvZABFan
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 22, 2018 3:33 pm
- Post datetime: 2018-06-23T03:53:52+00:00
- Post Title: Need help with Plants vs Zombies Garden Warfare 2 .SB/.TOC

I am mainly looking for the music files, which are stored in the map files and that one i sent. And i found the script, i just got an error on it, something about error 193.
## Post #8
- Username: PvZABFan
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 22, 2018 3:33 pm
- Post datetime: 2018-06-23T19:13:00+00:00
- Post Title: Need help with Plants vs Zombies Garden Warfare 2 .SB/.TOC

Ok, I have done a lot of research and testing like 10 different python scripts, none of them worked. I can't find anything that works to get these files unpacked. If anyone could send me a working tool, please do.
## Post #9
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-06-23T23:37:42+00:00
- Post Title: Need help with Plants vs Zombies Garden Warfare 2 .SB/.TOC

> Reply from PvZABFan
>
> I have done a lot of research and testing like 10 different python scripts.
I highly doubt you've found and tried 10 python scripts, but lets say you did, great, then explain your steps so I can at least assist with what I know and to get the game extracted, because trust me, I've been doing research on these Frostbite games for far too long ever since NFS The Run came out, but messing with these python scripts for over two years and a half now and all of them work but in their own way with the required paths in place so on and so forth.
I am far from being knowledgeable in this but I can help as long as you state correctly what you did, what you used and why it didn't work as should.
## Post #10
- Username: PvZABFan
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 22, 2018 3:33 pm
- Post datetime: 2018-06-24T01:32:36+00:00
- Post Title: Need help with Plants vs Zombies Garden Warfare 2 .SB/.TOC

So 1, i put the location of the game and the location of where i wanted to dump the files, and 2, i saved the script and then ran it. All of them gave me an error after trying to extract the files. I had to go through a bunch of reinstalling python to 2.7.6 and stuff and it was annoying. I spent all of last night looking for scripts to only get fails.

The scripts i used were for other EA games such as SWBF and battlefield 4. I did the exact directions to all the scripts yet everything failed.
## Post #11
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-06-24T02:47:37+00:00
- Post Title: Need help with Plants vs Zombies Garden Warfare 2 .SB/.TOC

Assuming it was 32 bit of python you installed, because 64 bit is out of the question, what was the error that the IDLE console window showed in red?
Because if you used any BF4 python script then right click on it to run it with "Edit with IDLE" making the right adjustments then  hit F5 on your keyboard it will ask you to save hit ok then it should start extraction with blue text, if not a red text error block was shown what was the error?
## Post #12
- Username: PvZABFan
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 22, 2018 3:33 pm
- Post datetime: 2018-06-24T02:50:11+00:00
- Post Title: Need help with Plants vs Zombies Garden Warfare 2 .SB/.TOC

OH. I know what i did wrong. I installed 64 bit. I really need to pay attention.
## Post #13
- Username: PvZABFan
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 22, 2018 3:33 pm
- Post datetime: 2018-06-24T03:06:39+00:00
- Post Title: Need help with Plants vs Zombies Garden Warfare 2 .SB/.TOC

Now it works! Thanks for telling me it was 32 bit!
## Post #14
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-06-24T23:38:57+00:00
- Post Title: Need help with Plants vs Zombies Garden Warfare 2 .SB/.TOC

> Reply from PvZABFan
>
> Now it works! Thanks for telling me it was 32 bit!
How did the extraction end? Any particular block errors showed up?
## Post #15
- Username: PvZABFan
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 22, 2018 3:33 pm
- Post datetime: 2018-06-25T00:30:22+00:00
- Post Title: Need help with Plants vs Zombies Garden Warfare 2 .SB/.TOC

I managed to extract everything except that 6 GB file, and due to this i am missing half of the music files from the game.
## Post #16
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-06-25T01:28:59+00:00
- Post Title: Re: Need help with Plants vs Zombies Garden Warfare 2 .SB/.T

> Reply from PvZABFan
>
> I managed to extract everything except that 6 GB file, and due to this i am missing half of the music files from the game.
Well, as I've said, it is what it is, so far I found NO solutions.
That archive is trivial to the whole game assets extraction.
## Post #17
- Username: PvZABFan
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 22, 2018 3:33 pm
- Post datetime: 2018-07-18T08:44:35+00:00
- Post Title: Re: Need help with Plants vs Zombies Garden Warfare 2 .SB/.T

> Reply from mono24
>
> PvZABFan wrote:I managed to extract everything except that 6 GB file, and due to this i am missing half of the music files from the game.
Well, as I've said, it is what it is, so far I found NO solutions.
That archive is trivial to the whole game assets extraction.

I did it! Installed chunks contained most of the needed files required to get what I wanted (sound files)!
