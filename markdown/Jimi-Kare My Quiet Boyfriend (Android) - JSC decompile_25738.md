## Post #1
- Username: luatsenpai
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Apr 21, 2020 8:08 am
- Post datetime: 2022-08-26T00:42:01+00:00
- Post Title: Jimi-Kare My Quiet Boyfriend (Android) - JSC decompile

Hello, i want decompile and compille again jsc file
I open libcocos2djs.so with IDA, but can't find the decryption key


Link game: [https://apkpure.com/jimi-kare-my-quiet- ... imikare.en](https://apkpure.com/jimi-kare-my-quiet-boyfriend/jp.seec.sim.zimikare.en)
Somebody help me, thank
[project.zip](https://xentaxbackup.github.io/file/22698_project.zip)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-09-04T15:59:49+00:00
- Post Title: Jimi-Kare My Quiet Boyfriend (Android) - JSC decompile

JSC files from this game are not compressed or encrypted, so you don't need to search for key.
(You can tell it by looking at the file in hex editor - if you can see some strings, then JSC is probably NOT encrypted/compressed).

In this case they are compiled JavaScript bytecode files (by SpiderMonkey Engine).
For decompilation you can try this [https://github.com/irelance/jsc-decompile-mozjs-34](https://github.com/irelance/jsc-decompile-mozjs-34)
or this [https://github.com/takaaptech/cocos2d-jsc-decompiler](https://github.com/takaaptech/cocos2d-jsc-decompiler)

More info about the format here [http://wiki.xentax.com/index.php/Cocos2d_JSC](http://wiki.xentax.com/index.php/Cocos2d_JSC)
## Post #3
- Username: luatsenpai
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Apr 21, 2020 8:08 am
- Post datetime: 2022-09-06T00:35:51+00:00
- Post Title: Jimi-Kare My Quiet Boyfriend (Android) - JSC decompile

> Reply from ikskoks ↑Sun Sep 04, 2022 11:59 pm at Sun Sep 04, 2022 11:59 pm
>
> 
JSC files from this game are not compressed or encrypted, so you don't need to search for key.
(You can tell it by looking at the file in hex editor - if you can see some strings, then JSC is probably NOT encrypted/compressed).

In this case they are compiled JavaScript bytecode files (by SpiderMonkey Engine).
For decompilation you can try this https://github.com/irelance/jsc-decompile-mozjs-34
or this https://github.com/takaaptech/cocos2d-jsc-decompiler

More info about the format here http://wiki.xentax.com/index.php/Cocos2d-x_JSC

I try first tool but it doesn't work and second tool I don't have linux
what should I do?
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-09-06T19:11:26+00:00
- Post Title: Jimi-Kare My Quiet Boyfriend (Android) - JSC decompile

Well, as far as I know those are the only two SpiderMonkey decompilers available on the internet, so your options are limited.
You can try to setup linux as a virtual machine. Linux is FREE and also virtualbox is FREE - just use them. 

Check also tutorials I have shared on the wiki. They can explain step by step how to decompile correctly.
But they are in chineese, so you can use Google Chrome to translate them.
