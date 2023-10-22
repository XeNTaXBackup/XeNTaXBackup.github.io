## Post #1
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-08-09T22:08:26+00:00
- Post Title: MexCom Plugin to use Game Extractor Plugins

Hello

I am considering writing a MexCom plugin that would add support for Game Extractor plugins. This idea was mentioned before, mostly as a passing fancy, [here](http://forum.xentax.com/viewtopic.php?f=10&t=2471). I'm pretty sure that it won't be too hard, becuase you can use the Java Native Interface (JNI) to create a Java VM and use it from your own code. I think I'll use Rahly's Plugin Manager, although I'm having a bit of trouble with it.

Please tell me what you think: would this be useful?
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-08-11T07:11:08+00:00
- Post Title: MexCom Plugin to use Game Extractor Plugins

Certainly, that would always be nice. Rahly's Plugin manager could be a good interface, I agree!
## Post #3
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-08-11T16:08:25+00:00
- Post Title: MexCom Plugin to use Game Extractor Plugins

And considering Game Extractor is already able to use BMS scripts...
## Post #4
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-08-11T17:57:45+00:00
- Post Title: MexCom Plugin to use Game Extractor Plugins

> Reply from Zench
>
> I think I'll use Rahly's Plugin Manager, although I'm having a bit of trouble with it.I figured out what the problem is, I think. Could anyone give me a description/example code for these functions:
mpGetOptions
mpSetOption
mpIndexedInfo
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-08-11T18:44:37+00:00
- Post Title: MexCom Plugin to use Game Extractor Plugins

There is stuff here at the forum, and Rahly can fill you in as well. 

[search.php?keywords=mpGetOptions&terms= ... mit=Search](http://forum.xentax.com/search.php?keywords=mpGetOptions&terms=all&author=&sc=1&sf=all&sk=t&sd=d&sr=posts&st=0&ch=300&t=0&submit=Search)
## Post #6
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-08-25T22:17:50+00:00
- Post Title: MexCom Plugin to use Game Extractor Plugins

It's coming along fine, but I think I may have found a bug in Rahly's Plugin Manager. It crashed when I tried to use more than 51 formats, after all the calls to my mpGetOptions. Here is the call stack according to Visual Studio .NET:

```
    PluginManager.dll!mpGetOptions()  + 0x5f
    mc32.exe!0054029c()
    NTDLL.DLL!RtlpNtMakeTemporaryKey()  + 0x84fb
    NTDLL.DLL!RtlInitializeSListHead()  + 0x1075b
    90909090()
```
## Post #7
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-09-19T01:05:53+00:00
- Post Title: MexCom Plugin to use Game Extractor Plugins

Progress update: I haven't solved that bug yet, but it isn't necessary to have more than 51 plugins for testing so I am just ignoring it for now. I am currently able to list every plugin, load archives, and extract from them. Unfortunately I am not having so much luck with Rahly's Plugin Manager, so it isn't useable yet. It's the mpGetIndexedInfo and the mpFind* functions I'm having trouble implementing.
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-09-19T06:08:51+00:00
- Post Title: MexCom Plugin to use Game Extractor Plugins

Awesome! Can I test it out? 

I've also contacted Rahly, to see what is up with that bug.
## Post #9
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-09-19T14:04:31+00:00
- Post Title: MexCom Plugin to use Game Extractor Plugins

> Reply from Mr.Mouse
>
> Awesome! Can I test it out?Sure! Once I get it into a more usable state.

> Reply from Mr.Mouse
>
> I've also contacted Rahly, to see what is up with that bug.I contacted him too...
## Post #10
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2008-09-20T11:05:46+00:00
- Post Title: MexCom Plugin to use Game Extractor Plugins

Mr.Mouse, didn't get a message on this from you

Zench, you replied that it might be your problem, then i never got a response back.
## Post #11
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-09-20T16:33:34+00:00
- Post Title: MexCom Plugin to use Game Extractor Plugins

> Reply from Rahly
>
> Zench, you replied that it might be your problem, then i never got a response back.I thought it might have been, and I tried to find it, but I still can't figure it out. Since the crash is in your code, and I'm pretty sure I did not pass any bad pointers, I thought perhaps you could find out what is happening.
## Post #12
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-10-03T00:40:34+00:00
- Post Title: MexCom Plugin to use Game Extractor Plugins

Okay, here's another progress update. The bug mentioned earlier has been found and fixed (the problem was in the plugin manager). I also have a (somewhat) working version of the plugin. It is possible that this might become a MexCom feature.
