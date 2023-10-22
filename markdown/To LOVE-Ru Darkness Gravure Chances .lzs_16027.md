## Post #1
- Username: kayaha
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-03-18T20:21:41+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .lzs

To LOVE-Ru Darkness: Gravure Chances
To LOVEる - とらぶる - ダークネス グラビアチャンス 
[http://www.cs.furyu.jp/toloveru-app/](http://www.cs.furyu.jp/toloveru-app/)

```
#by chrrox
#http://aluigi.altervista.org/quickbms.htm
comtype LZSS0
get zsize asize
get size long
math zsize -= 4
if SIZE & 0x80000000
log MEMORY_FILE 4 zsize
else
clog MEMORY_FILE 4 zsize size
endif
get files short MEMORY_FILE
goto 0 MEMORY_FILE
for i = 0 < files
get null short MEMORY_FILE
get type short MEMORY_FILE
get offset long MEMORY_FILE
get size long MEMORY_FILE
get id long MEMORY_FILE
get name basename
getdstring name2 0x30 MEMORY_FILE
string name + \
string name + name2
log name offset size MEMORY_FILE
next i

```
## Post #2
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2017-03-18T21:25:29+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .lzs

Ohh! I tried looking for the game files for this game, but couldn't find them anywhere. Can you tell me where you found them?
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-03-19T14:48:42+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .lzs

you need to be rooted to see the files.
its in
/data/data/jp.furyu.tologra
## Post #4
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2017-03-19T19:23:47+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .lzs

Oh! Thanks so much. I managed to get them.
## Post #5
- Username: Uoipka
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 21, 2017 8:44 pm
- Post datetime: 2017-03-21T12:47:19+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .lzs

I get a lot of .bum and .bsim files. How to get model like this? 
jp.furyu.tologra\dl\res\assets from there?
Please :<
## Post #6
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-03-21T14:31:44+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .lzs

> Reply from Uoipka
>
> I get a lot of .bum and .bsim files. How to get model like this? 
jp.furyu.tologra\dl\res\assets from there?
Please :<

Check here 
[viewtopic.php?f=16&t=16034](http://forum.xentax.com/viewtopic.php?f=16&t=16034)
## Post #7
- Username: Uoipka
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 21, 2017 8:44 pm
- Post datetime: 2017-03-21T16:54:36+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .lzs

> Reply from o0Crofty0o
>
> Uoipka wrote:I get a lot of .bum and .bsim files. How to get model like this? 
jp.furyu.tologra\dl\res\assets from there?
Please :<

Check here 
viewtopic.php?f=16&t=16034

So, now I can see head or body. What should I do now
## Post #8
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-03-22T00:07:38+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .lzs

Thanks for the tools chrrox. Gotta admit though, this game was a massive pain in the ass to get my hands on since I've never rooted a phone (I'm not much of a cell phone user). 

That aside, did they skip around with numbering the costumes or are those paid items that I just don't have access to because I didn't buy them. I don't understand Japanese so I have no clue what menus (int the game) were for what and didn't want to risk accidentally buying something.
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-03-22T00:53:00+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .lzs

They just skipped around the numbering. they will most likely release the other costumes later on.
## Post #10
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2017-03-22T02:55:54+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .lzs

Chroxx,can u make script for idolmaster Cinderella girls starlight stage too,please??
## Post #11
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-03-25T15:11:42+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .lzs

> Reply from Fina
>
> Chroxx,can u make script for idolmaster Cinderella girls starlight stage too,please??
Im@s CGSS using unity old version, so you can use the unitystudio
## Post #12
- Username: Nathanzica
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 15, 2017 8:16 am
- Post datetime: 2017-07-15T00:29:39+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .lzs

Which program opens .bum files?
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-15T11:05:43+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .lzs

it is mentioned in this topic how to open the files.
The program is noesis.
## Post #14
- Username: Nathanzica
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 15, 2017 8:16 am
- Post datetime: 2017-07-17T18:13:28+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .lzs

I do not find the files in /data/data/jp.furyu.tologra
## Post #15
- Username: kapatan
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri May 21, 2010 8:03 am
- Post datetime: 2017-07-25T12:59:43+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .lzs

Please tell me assets download link?
## Post #16
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-01-06T01:25:36+00:00
- Post Title: Re: To LOVE-Ru Darkness: Gravure Chances .lzs

you can let curl run on your pc for a while to get all the files.

curl -f -s "[https://cdn.toloveru-darkness-sg.com/patch/data/patch](https://cdn.toloveru-darkness-sg.com/patch/data/patch)_[0001-0009]_[0000-0009]_[1000-9999].zip" -O "#1_#2_#3.zip"
for /r %F in (*) do if %~zF==0 del "%F"

or you can use these I grabbed

[https://pastebin.com/raw/ZWAZJVdq](https://pastebin.com/raw/ZWAZJVdq)
## Post #17
- Username: kapatan
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri May 21, 2010 8:03 am
- Post datetime: 2018-01-06T11:51:02+00:00
- Post Title: Re: To LOVE-Ru Darkness: Gravure Chances .lzs

Excellent!!
Thank you for your help.
## Post #18
- Username: YGGDRASIL
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 18, 2017 5:00 pm
- Post datetime: 2018-05-15T00:01:46+00:00
- Post Title: Re: To LOVE-Ru Darkness: Gravure Chances .lzs

I used nox, but I couldn’t find any bum file. Is there any other application?
## Post #19
- Username: qopsinonstudios
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 06, 2016 7:15 pm
- Post datetime: 2021-11-01T01:13:20+00:00
- Post Title: Re: To LOVE-Ru Darkness: Gravure Chances .lzs

> Reply from chrrox ↑Sat Jan 06, 2018 9:25 am at Sat Jan 06, 2018 9:25 am
>
> 
you can let curl run on your pc for a while to get all the files.

curl -f -s "https://cdn.toloveru-darkness-sg.com/patch/data/patch_[0001-0009]_[0000-0009]_[1000-9999].zip" -O "#1_#2_#3.zip"
for /r %F in (*) do if %~zF==0 del "%F"

or you can use these I grabbed

https://pastebin.com/raw/ZWAZJVdq

Links are down since they closed the servers, can you please send the files? Thank you!
