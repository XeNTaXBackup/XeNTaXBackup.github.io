## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-19T23:36:57+00:00
- Post Title: Legend of Wukong

[http://wkz.baiyou100.com/](http://wkz.baiyou100.com/)
Here is a 3d model importer that supports bones and weights.
You will need to parent a few bones manually to make the skeleton complete.
The easiest way i do it is after you import the model i just import it into motion builder then map the bones.


bms extract script.

```
goto 0x19
get offset long
get size long
get zsize long
get baseoff long
get datasize long
get arcsize long
clog MEMORY_FILE offset zsize size
get unk01 long MEMORY_FILE
get unk02 long MEMORY_FILE
get files short MEMORY_FILE
goto 0x12 MEMORY_FILE
get folder3 string MEMORY_FILE
For tmp = tmp != size
get offset long MEMORY_FILE
get size2 long MEMORY_FILE
math offset + baseoff
if size2 == 0
get folder string MEMORY_FILE
else if size2 == 1
get folder2 string MEMORY_FILE
string folder + \
string folder + folder2
else
get name2 string MEMORY_FILE
set name folder
string name + \
string name + name2
log name offset size2
endif
savepos tmp MEMORY_FILE
next
```

[Legend of Wukong.rar](https://xentaxbackup.github.io/file/4719_Legend of Wukong.rar)
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-09-20T01:00:13+00:00
- Post Title: Legend of Wukong

thx, i will try it when the game finishes downloading. man these mirrors are slow ha ha ha.
## Post #3
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-09-20T23:08:49+00:00
- Post Title: Legend of Wukong

Good stuff mate!
## Post #4
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-09-21T00:43:30+00:00
- Post Title: Legend of Wukong

Nice models, good work chroxxx.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-21T00:56:22+00:00
- Post Title: Legend of Wukong

> Reply from howfie
>
> thx, i will try it when the game finishes downloading. man these mirrors are slow ha ha ha.

Might depend on the time of day you download.
I was getting 10-20 KB/s at one point and then 200-300 at another.
## Post #6
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-09-21T20:02:03+00:00
- Post Title: Legend of Wukong

umm well the models not look bad but I prefer other games, thanks anyway
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-21T20:25:36+00:00
- Post Title: Legend of Wukong

Here is an update bone script to fix the parenting.
Thanks a lot to reveal8n 
[Legend of Wukong Bones.rar](https://xentaxbackup.github.io/file/4722_Legend of Wukong Bones.rar)
## Post #8
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-09-30T20:56:41+00:00
- Post Title: Legend of Wukong

> Reply from CriticalError
>
> umm well the models not look bad but I prefer other games, thanks anyway

Of course but other games are really hard to decrypt and extract the models.
Only take a view of the games with 0 answers.
## Post #9
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2011-10-10T14:12:41+00:00
- Post Title: Legend of Wukong

I have some problems with texture transperance. This is the first time i using a model with two texture Diffuse and Alpha.
This is the model. You can see the "circle" of clothes has wrong tranperance.



Anyone can help me fix it ? Iam a newbie in the 3DS Max ...
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-10-10T15:50:22+00:00
- Post Title: Legend of Wukong

just turn on the opacity channel.
## Post #11
- Username: bigBear
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Oct 09, 2009 2:51 am
- Post datetime: 2011-10-10T17:46:07+00:00
- Post Title: Legend of Wukong

chrrox, I guess you like anime games, am I right?
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-10-10T21:35:20+00:00
- Post Title: Legend of Wukong

I would assume he likes cute things with cute colors.
## Post #13
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2011-10-11T07:11:46+00:00
- Post Title: Legend of Wukong

> Reply from chrrox
>
> just turn on the opacity channel.

Sorry but it dont work   . When i exam the texture, i see it has two level of Transperance, that is black and grey.
Anyway to make opacity work with 2 level of Tranperance ?
## Post #14
- Username: Cubeburner
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 11, 2011 2:53 pm
- Post datetime: 2011-10-12T09:26:48+00:00
- Post Title: Legend of Wukong

So, I got the demo of the game downloaded. What do I need to access the *.c3d files that the characters are located in? I see a lot of .PAK files, do I need an extractor?

Cheers!
## Post #15
- Username: Cubeburner
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 11, 2011 2:53 pm
- Post datetime: 2011-10-13T05:38:58+00:00
- Post Title: Legend of Wukong

Hm, ok, this is odd.

I have downloaded the scripts that have been provided as attachments, but when I go to run them in MaxScript inside my 3DS Max 2010 with Service Pack 1, I get this annoying error when it's doing some skin operations:



However, the UpdateBones.ms script works fine, and I can see character bone structure (which is great!).

The reason I am using 2010 is that 2011 fails to install (for some odd reason) on my machine, and I am not in the position to use Max 2012.

Any help would be greatly appreciated!
## Post #16
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2011-10-17T02:10:26+00:00
- Post Title: Re: Legend of Wukong

> Reply from Cubeburner
>
> Hm, ok, this is odd.

I have downloaded the scripts that have been provided as attachments, but when I go to run them in MaxScript inside my 3DS Max 2010 with Service Pack 1, I get this annoying error when it's doing some skin operations:



However, the UpdateBones.ms script works fine, and I can see character bone structure (which is great!).

The reason I am using 2010 is that 2011 fails to install (for some odd reason) on my machine, and I am not in the position to use Max 2012.

Any help would be greatly appreciated!
That is not an error, man. Remeber import bone first using bone script first, after that import mesh with mesh script.
Hope you enjoy
## Post #17
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-08-19T04:44:25+00:00
- Post Title: Re: Legend of Wukong

> Reply from chrrox
>
> http://wkz.baiyou100.com/
Here is a 3d model importer that supports bones and weights.
You will need to parent a few bones manually to make the skeleton complete.
The easiest way i do it is after you import the model i just import it into motion builder then map the bones.


bms extract script.
Code: Select allget idstring long
goto 0x19
get offset long
get size long
get zsize long
get baseoff long
get datasize long
get arcsize long
clog MEMORY_FILE offset zsize size
get unk01 long MEMORY_FILE
get unk02 long MEMORY_FILE
get files short MEMORY_FILE
goto 0x12 MEMORY_FILE
get folder3 string MEMORY_FILE
For tmp = tmp != size
get offset long MEMORY_FILE
get size2 long MEMORY_FILE
math offset + baseoff
if size2 == 0
get folder string MEMORY_FILE
else if size2 == 1
get folder2 string MEMORY_FILE
string folder + \
string folder + folder2
else
get name2 string MEMORY_FILE
set name folder
string name + \
string name + name2
log name offset size2
endif
savepos tmp MEMORY_FILE
nextThe game has been updated, the script has failed, and hope that God will continue to update the script. Thank you very much, here are links and attachments:[http://wk.lbwgame.com/](http://wk.lbwgame.com/)
## Post #18
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-08-19T04:51:54+00:00
- Post Title: Re: Legend of Wukong

> Reply from raykingnihong
>
> chrrox wrote:http://wkz.baiyou100.com/
Here is a 3d model importer that supports bones and weights.
You will need to parent a few bones manually to make the skeleton complete.
The easiest way i do it is after you import the model i just import it into motion builder then map the bones.


bms extract script.
Code: Select allget idstring long
goto 0x19
get offset long
get size long
get zsize long
get baseoff long
get datasize long
get arcsize long
clog MEMORY_FILE offset zsize size
get unk01 long MEMORY_FILE
get unk02 long MEMORY_FILE
get files short MEMORY_FILE
goto 0x12 MEMORY_FILE
get folder3 string MEMORY_FILE
For tmp = tmp != size
get offset long MEMORY_FILE
get size2 long MEMORY_FILE
math offset + baseoff
if size2 == 0
get folder string MEMORY_FILE
else if size2 == 1
get folder2 string MEMORY_FILE
string folder + \
string folder + folder2
else
get name2 string MEMORY_FILE
set name folder
string name + \
string name + name2
log name offset size2
endif
savepos tmp MEMORY_FILE
nextThe game has been updated, the script has failed, and hope that God will continue to update the script. Thank you very much, here are links and attachments:http://wk.lbwgame.com/
[sample.rar](https://xentaxbackup.github.io/file/7680_sample.rar)
## Post #19
- Username: MeisterKeule
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Aug 14, 2014 5:00 pm
- Post datetime: 2014-08-21T08:52:27+00:00
- Post Title: Re: Legend of Wukong

What about Animationen?
