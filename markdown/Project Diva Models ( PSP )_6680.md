## Post #1
- Username: Chimera
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Feb 24, 2011 11:31 pm
- Post datetime: 2011-05-27T21:12:42+00:00
- Post Title: Project Diva Models ( PSP )

Forgive me if this has already been posted but Is there anyway to extract the project Diva models ? 

I've seen tons of models of it online but theres no tutorial on extracting it 


or is there a way already on getting these models ripped ?

* oh and I googled before posting this
## Post #2
- Username: linhikaru7
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jan 31, 2011 2:45 pm
- Post datetime: 2011-05-28T22:16:12+00:00
- Post Title: Project Diva Models ( PSP )

There is a solid method of ripping the models from Dreamy Theatre [viewtopic.php?f=16&t=5484](http://forum.xentax.com/viewtopic.php?f=16&t=5484), but as for the PSP games itself? Little more than some rumors, and a few people who have claimed to extract them, but don't have much to show for it, or just aren't interested in helping other people duplicate their successes.

I really hope that this thread catches the eye of someone smarter and more skilled than I, because I would love it if the models and textures became available for reference. And I'm sure the flourishing MMD community would wet their pants. Actually, probably the whole darn fandom would have a field day.
## Post #3
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-05-29T00:35:04+00:00
- Post Title: Project Diva Models ( PSP )

theres a dos tool floating around, where someone just specified the offsets of the geometry in a single file from the psp game.

I think its just misinformation, but that's far from a working importer. although I can varify that another hacker (japanese) was successful in cracking the format. however he was also responsible for many other format break through. none of which he has shared publically, so don't hold your breathe.

I had a look at the format myself, and just ran into circles.. the header is beyond my current knowledge.

also the PS3 and PSP models are quite different, the PSP version also has more costumes.
## Post #4
- Username: Chimera
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Feb 24, 2011 11:31 pm
- Post datetime: 2011-05-29T15:06:39+00:00
- Post Title: Project Diva Models ( PSP )

> Reply from linhikaru7
>
> There is a solid method of ripping the models from Dreamy Theatre viewtopic.php?f=16&t=5484, but as for the PSP games itself? Little more than some rumors, and a few people who have claimed to extract them, but don't have much to show for it, or just aren't interested in helping other people duplicate their successes.

I really hope that this thread catches the eye of someone smarter and more skilled than I, because I would love it if the models and textures became available for reference. And I'm sure the flourishing MMD community would wet their pants. Actually, probably the whole darn fandom would have a field day.

Thank you for the link but I do not have that game so I can't extract from it :/

thanks  I too would hope that it catches someones eye, I saw a lot of project diva rips for mmd but it seems that no one has an extractor for it :/

> Reply from mariokart64n
>
> theres a dos tool floating around, where someone just specified the offsets of the geometry in a single file from the psp game.

I think its just misinformation, but that's far from a working importer. although I can varify that another hacker (japanese) was successful in cracking the format. however he was also responsible for many other format break through. none of which he has shared publically, so don't hold your breathe.

I had a look at the format myself, and just ran into circles.. the header is beyond my current knowledge.

also the PS3 and PSP models are quite different, the PSP version also has more costumes.

Oh I see thank you Mariokart 
and thanks for trying !
## Post #5
- Username: Julinha
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Sep 15, 2010 9:24 am
- Post datetime: 2011-06-05T17:28:31+00:00
- Post Title: Project Diva Models ( PSP )

There is a program that allows you edit textures.
AFS Tool and AFS Tool 2nd,but I can't open it in my computer,i think I will need Japanese VB6(Visual Basic 6) and TTSNeo,but I already have installed here.The language of my computer is Portuguese(Brazil),I don't know if the program will open on computers with English language.

You can download it here : [http://loda.jp/supermoonlight/?id=76](http://loda.jp/supermoonlight/?id=76)
## Post #6
- Username: linhikaru7
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jan 31, 2011 2:45 pm
- Post datetime: 2011-06-07T23:20:28+00:00
- Post Title: Project Diva Models ( PSP )

Oh! I may be able to help with this! I don't have the Japanese version of XP installed, however I have the MUI for it, and currently I have things set to by default accept Japanese encoding.

... ... ...

Okay, I got the program to run. I'm sure if anybody would like to reproduce my success, but I'm gonna just shoot that out there anyway.

Installed this. [http://tts.utopiat.net/runtime/files/vb6run.zip](http://tts.utopiat.net/runtime/files/vb6run.zip)
Followed by this. [http://tts.utopiat.net/files/archive/tt ... 5.2148.exe](http://tts.utopiat.net/files/archive/ttsneo1.85.2148.exe)
It won't run unless you change some regional and language settings. You can find them in the Control Panel. Under Regional Options select "Japanese". Now, in order to get the Japanese to display correctly head to the Advanced tab and change the Language for non-Unicode programs to Japanese. This won't really impair your ability to use XP, I found the changes minor. You might need the install disc, might not. Oh, and east asian fonts would be a good idea as well!
Hopefully this will work for someone other than me, otherwise, I'll feel really silly.

From here, the program works, but when I load up the game, it gives me the message "CPK file was not created." followed by some other message that I didn't bother trying to translate. The README file gives me a machine translation that I am to manually do something with a file called isoafr.tmp (it actually tell to "vomit" the address and subsequently delete the address), but I have yet to locate it. Japanese message boards say that the file should here "D:\AFS\Isoafr.tmp" or thereabouts depending on which drive things are on I suppose.

Also! You can dump the afs files AFS Explorer [http://www.pes-patch.com/2008/10/afs-explorer-37.html](http://www.pes-patch.com/2008/10/afs-explorer-37.html). DivaDataList.afs however doesn't dump completely and there are some missing files. The other two seem to dump comprehensively.

One last things, on the Japanese message they said that if you change the last two characters of the binary code of certain IGB files from 66 to 00 (or possibly, just add 00 and definitely not 66) they can be read? I'm just going to copy and paste the actual text, and maybe someone can make heads or tails of it. Link to the page is here [http://gamecode2010.blog97.fc2.com/blog-entry-24.html](http://gamecode2010.blog97.fc2.com/blog-entry-24.html). Caution, most of the texture editing isn't so much recoloring as "YAY NAKEDNESS", so don't follow the links at work or church or anything.

> 82 ：名無しさん＠お腹いっぱい。：2009/07/17(金) 15:20:13 ID:/5I7RAnk
>
> >>66
>
> どうやってigbのファイルサイズを変えたんだ？
>
> コマンドプロンプトからfsutilコマンドで変えてみたんだが、フリーズしてしまう
>
> 
>
> 
>
> 83 ：名無しさん＠お腹いっぱい。：2009/07/17(金) 15:27:12 ID:7etbBi3E
>
> 俺は>>66じゃ無いけどバイナリエディタで末尾に00追加しただけでいけた
>
> 
>
> 
>
> 84 ：66：2009/07/17(金) 15:30:02 ID:HhfEt0uh
>
> >>81
>
> メイコ水着のカイトとかオススメ
>
> 
>
> >>82
>
> バイナリエディタで末尾に書き足して調整してるだけ
>
> 00hとかFFhとかで埋めてみてるんだけど、どう書き替えても上手く行く物は行くし
>
> 駄目な物はどう書き替えてもフリーズするっぽい
>
> igbの構造が分かってる人なら、こんな間抜けな方法は取ってないと思うけどね…

Please pardon me if this message is really awkward, I really don't know much but I figured that if there was even a slim chance of helping some way, I should just go for it.
## Post #7
- Username: Julinha
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Sep 15, 2010 9:24 am
- Post datetime: 2011-06-08T19:54:44+00:00
- Post Title: Project Diva Models ( PSP )

When I open AFS Tool 2nd ,appears this message [http://img703.imageshack.us/img703/3903/wtfmv.png](http://img703.imageshack.us/img703/3903/wtfmv.png) ): I don't know why.
## Post #8
- Username: linhikaru7
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jan 31, 2011 2:45 pm
- Post datetime: 2011-06-08T23:04:10+00:00
- Post Title: Project Diva Models ( PSP )

Okay, my Japanese skills are extremely questionable, but it looks like it can't extract the files inside because the size of the game image is wrong, or has been altered.

I suggest you re-rip the disc image from the Project DIVA UMD, be careful not to apply any patches or try and trim it in any way.

(Mind you, when I suggest something, it's a case of the blind leading the blind.)
## Post #9
- Username: Julinha
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Sep 15, 2010 9:24 am
- Post datetime: 2011-06-09T16:21:37+00:00
- Post Title: Project Diva Models ( PSP )

I tried open the program on another computer(with Windows 7),but the window turns white.
Here : [http://img822.imageshack.us/img822/6602/semttulopov.png](http://img822.imageshack.us/img822/6602/semttulopov.png)
Please help me TT_TT
## Post #10
- Username: linhikaru7
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jan 31, 2011 2:45 pm
- Post datetime: 2011-06-10T06:37:49+00:00
- Post Title: Project Diva Models ( PSP )

In order for TTSNeo to run, Visual Basic 6.0 runtime needs to be installed. Even then, some features might not work. If it still doesn't work, you should pull up the run command and input these.

regsvr32 /u MSFLXGRD.OCX
regsvr32 MSFLXGRD.OCX

This is just from what I gleaned at the web page, I haven't upgraded to 7 yet, so I can't help much.
## Post #11
- Username: Julinha
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Sep 15, 2010 9:24 am
- Post datetime: 2011-06-14T18:36:04+00:00
- Post Title: Project Diva Models ( PSP )

FFFFFFFFFFFFFFFFFFF , I try do it but don't work ;^;
Well,thanks for trying help me ;^;
## Post #12
- Username: Julinha
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Sep 15, 2010 9:24 am
- Post datetime: 2011-06-23T18:39:33+00:00
- Post Title: Project Diva Models ( PSP )

I found these sites that maybe can help to open igb files o.o or no.I don't know if this can help,because I don't understand nothing about programming/hex/anything
Here : [http://www.cute.or.jp/~makuchan/pce/diva2.html](http://www.cute.or.jp/~makuchan/pce/diva2.html)
[http://www.cute.or.jp/~makuchan/pce/diva.html](http://www.cute.or.jp/~makuchan/pce/diva.html)
## Post #13
- Username: BolinhaRedonda
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 12, 2011 10:26 am
- Post datetime: 2012-01-06T06:26:04+00:00
- Post Title: Project Diva Models ( PSP )

Have you guys found anything?
