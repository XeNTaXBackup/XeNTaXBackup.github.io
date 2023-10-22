## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-05-03T09:26:46+00:00
- Post Title: Army of Two: The Devil's Cartel

I was trying to extract files from new Army of Two game, it's uses frostbite 2 engine. I used frostbite bms script and it works fine with .sb and .toc archives, but it appears that files I've extracted are compressed too, could someone take a look at them? Here's some samples [http://www.mediafire.com/?07famrqc7c4fb03](http://www.mediafire.com/?07famrqc7c4fb03) Thanks in advance!
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-05-03T22:18:02+00:00
- Post Title: Army of Two: The Devil's Cartel

did you check xbox360 version files? i didn't run luigi's comscan on these files, but if these files are from the xbox360 version, i would try comscan to see if it is using the streaming version of xmemcompress.

btw, is alice in this game too ? her quality in the previous two games were crap. hopefully she is of higher quality in this one.
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-05-04T09:54:56+00:00
- Post Title: Army of Two: The Devil's Cartel

Those files are from Xbox-360 version of the game, also  I found blueprintbundle experimental extractor for Need for Speed: The Run . The Run uses frostbite 2 engine too, so extractor seems to work, still though all extracted files appears to be some useless junk
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-05-04T19:40:50+00:00
- Post Title: Army of Two: The Devil's Cartel

The files are called .EBX files.

[http://www.bfeditor.org/forums/index.ph ... opic=15731](http://www.bfeditor.org/forums/index.php?showtopic=15731)

[http://www.bfeditor.org/forums/index.ph ... opic=15531](http://www.bfeditor.org/forums/index.php?showtopic=15531)
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-05-09T13:56:50+00:00
- Post Title: Army of Two: The Devil's Cartel

Thanks a lot OrangeC   Just now found some time to try this sbtoc dumper. Managed to make him work, it work on 50% only still it's a good start. I've extracted Weapon.sb, no names just a bunch of .chunk files. But models are there and they are reachable! Here's a pic of some weapon's parts
[aot.jpg](https://xentaxbackup.github.io/file/6390_aot.jpg)
## Post #6
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-05-09T20:26:09+00:00
- Post Title: Army of Two: The Devil's Cartel

Some update, not all extracted files are nameless. From some .sb archives files have even folder structure, names aren't perfect, but it's not a big problem. For example here's Rios primary "Alpha" outfit
[aot_model.jpg](https://xentaxbackup.github.io/file/6392_aot_model.jpg)
## Post #7
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-06-11T17:41:04+00:00
- Post Title: Army of Two: The Devil's Cartel

Decided to return to The Devil's Cartel files, and continue my study of model format to finish script. Now I have an issue, and I have no idea how to fix or solve this   All models working excellent but all characters heads are ugly transformed. Here's the picture of imported head. I will be very grateful for any help or advice 
[head.jpg](https://xentaxbackup.github.io/file/6460_head.jpg)
## Post #8
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2013-06-22T16:03:25+00:00
- Post Title: Army of Two: The Devil's Cartel

> Reply from zaramot
>
> All models working excellent but all characters heads are ugly transformed. Here's the picture of imported head. I will be very grateful for any help or advicedon't bother with this, it's a "special feature" of frostbite engine. something should be applied on those faces before actual in-game render, maybe morphs or something like that. it's definitely morphs in battlefield bad company 2.
ripping frostbite games gives exactly same shit, so you can just continue your greate work on model converting unless you want to dig deeply into the frostbite engine and figure out what is affect on faces/heads.

cheers man.
## Post #9
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2013-08-19T23:03:33+00:00
- Post Title: Army of Two: The Devil's Cartel

> Reply from zaramot
>
> Some update, not all extracted files are nameless. From some .sb archives files have even folder structure, names aren't perfect, but it's not a big problem. For example here's Rios primary "Alpha" outfit

Can you please share the your knowledge importing the meshdata? I`m currently trying to put together a Bad company 2 model I have lots of information (using intelgpa, ninja ripper etc) I have the actual model too and *.meshdata files, but I have a problem understanding how to read the *.meshdata files. Please share what you know about the FrostBite format...
## Post #10
- Username: jakkrit
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 14, 2014 8:08 pm
- Post datetime: 2016-10-09T08:01:43+00:00
- Post Title: Army of Two: The Devil's Cartel

I tried very hard to read .mesh files but failed. I don't know how to import these raw 3d files to 3ds max.
Even use Hex2obj. I still can't get it. Anybody can help me?
