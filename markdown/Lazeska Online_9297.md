## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-19T02:11:13+00:00
- Post Title: Lazeska Online

Ok i have here Lazeska game contain 3 huge files

Common.Pak = 1,202,221 kb
Character.Pak = 932,054 kb
Map.Pak = 1,871,944 kb

Any .bms to keep out samples?
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-19T02:14:30+00:00
- Post Title: Lazeska Online

[http://aluigi.altervista.org/papers/bms/lazeska.bms](http://aluigi.altervista.org/papers/bms/lazeska.bms)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-19T02:19:33+00:00
- Post Title: Lazeska Online

Models are one of the older nif versions I think.
## Post #4
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-19T02:33:47+00:00
- Post Title: Lazeska Online

Its in repository, files in game folders are stored in separated folders, all folders have same file types. (.DDS-.fkm-.nif-.kfm)
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-19T02:52:36+00:00
- Post Title: Lazeska Online

I wonder if nifskope can open it.
## Post #6
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-19T04:19:52+00:00
- Post Title: Lazeska Online

> Reply from finale00
>
> I wonder if nifskope can open it.

I try open with Nifscop and not read.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-19T04:22:14+00:00
- Post Title: Lazeska Online

We don't really have any real alternatives for nif formats unfortunately 
The game seems to use multiple nif formats. There are some 20.2.0.8's in the samples folder as well as 20.3.0.9's

nifskope should be able to load the 20.3.0.9's though I think.

It looks like it should be loadable...

EDIT: decided to get that noesis nif plugin I wrote before and tried it on some models:



I've added 20.2.0.7 and 20.2.0.8 to the list.
They are similar to 20.3.0.9 I think and so they were loaded...

No clue how the textures are assigned though. Might work if you texture it manually since I should have the UV's out.



The script is really ugly and hard to follow, because of how different formats store their data.
## Post #8
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-07-19T20:25:34+00:00
- Post Title: Lazeska Online

well some models tested of repository
## Post #9
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-19T21:27:08+00:00
- Post Title: Lazeska Online

Lol critical, are this something nif tools or its the finale plugin for noesis?.
## Post #10
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-07-19T21:40:27+00:00
- Post Title: Lazeska Online

> Reply from Rimbros
>
> Lol critical, are this something nif tools or its the finale plugin for noesis?.yeah is a nif tool my friend
## Post #11
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-19T22:49:53+00:00
- Post Title: Lazeska Online

Its the one cant export models to other formats, since i get GameAssassin cracked maybe we can try with that.
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-19T22:56:53+00:00
- Post Title: Lazeska Online

Ya I'm kind of surprised that they would write a full importer and mod tool, but then provide no real export functionality beyond obj.
## Post #13
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-07-19T23:26:47+00:00
- Post Title: Lazeska Online

> Reply from Rimbros
>
> Its the one cant export models to other formats, since i get GameAssassin cracked maybe we can try with that.yes is that, but maybe can be ripped with GA, anyway just some models are good, for me not necessary this models but is good have some tool for export this models, just for add to collection ripped games 

> Reply from finale00
>
> Ya I'm kind of surprised that they would write a full importer and mod tool, but then provide no real export functionality beyond obj.agree with that but well sure who write it have her reasons.
## Post #14
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-19T23:43:29+00:00
- Post Title: Lazeska Online

Lol, any idea to solve this games?
God Man (need bms)	
Realm Of The Titans (unpacked, need take a view of the 3D format) 	
Heroes Scions of Phoenix (bms only extract textures)
## Post #15
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-21T07:52:09+00:00
- Post Title: Lazeska Online

Ok i found a way, 
1.- run the aplication Nifviewer with 3D Ripper DX
2.- capture model.
3.- install the amazing uv-repair from tosyk page.
3.- import model .3dr in max (textures are also in capture folder)
4.- drag texture to model or textures to model parts.
5.- u see the uv maps are wrong, select mesh textured and press only mafia in the tosy plugin, and voila.
