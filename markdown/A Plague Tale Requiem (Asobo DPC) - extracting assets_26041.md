## Post #1
- Username: thebestbot
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 30, 2022 3:11 am
- Post datetime: 2022-11-29T19:19:27+00:00
- Post Title: A Plague Tale: Requiem (Asobo DPC) - extracting assets

as simple as the title sounds, I need assets from the game "Plague Tale requiem", I have no progamming knowledge, only learned a bit of C++, I have access to two tools specifically for DPC file format, but I don't know how to exactly use them, also I think the encryption method is something "Asobo-Internal Cross Technology", and a site mentioned the LZ4 compression method being used in the game.

A website with some info:
[https://wiki.xentax.com/index.php/Asobo_Studio_DPC_DPS](https://wiki.xentax.com/index.php/Asobo_Studio_DPC_DPS)

A tool:
[https://github.com/widberg/dpc](https://github.com/widberg/dpc)

Another source I don't understand:
[https://zenhax.com/viewtopic.php?f=9&t=11189](https://zenhax.com/viewtopic.php?f=9&t=11189)


a reddit post:
[https://www.reddit.com/r/hacking/commen ... bo_studio/](https://www.reddit.com/r/hacking/comments/ck007e/is_there_a_way_to_open_dpc_files_from_asobo_studio/)
(note: The important thing is he mentioned some important-looking things:
Could i:

-Try to decode them using standard algorithms and brute force?

-Try to change the file name extension until [something] can open it?

-Try to decompile the game (oof...) and find the part resolving the .DPC files?

-Do something completely different...)


a plugin for multiex commander (I haven't used it yet, will do soon)
[https://www.moddb.com/games/fuel/downlo ... dpc-plugin](https://www.moddb.com/games/fuel/downloads/multiex-commander-dpc-plugin)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-30T18:51:25+00:00
- Post Title: A Plague Tale: Requiem (Asobo DPC) - extracting assets

Well, as you could read on the wiki this file format has been changed multiple times over time and each games requires some amount of effort for reverse engineering. This tool you have linked was designed specifically for "FUEL" modding and has limited support for other games.
So without any programming knowledge or at least reverse engineering knowledge, you will have a hard time with extracting ANY kind of assets from those archives.
## Post #3
- Username: thebestbot
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 30, 2022 3:11 am
- Post datetime: 2022-11-30T20:08:56+00:00
- Post Title: A Plague Tale: Requiem (Asobo DPC) - extracting assets

> Reply from ikskoks ↑Thu Dec 01, 2022 2:51 am at Thu Dec 01, 2022 2:51 am
>
> 
Well, as you could read on the wiki this file format has been changed multiple times over time and each games requires some amount of effort for reverse engineering. This tool you have linked was designed specifically for "FUEL" modding and has limited support for other games.
So without any programming knowledge or at least reverse engineering knowledge, you will have a hard time with extracting ANY kind of assets from those archives.
I understand. Thanks a lot for the reply, So guess I should continue my study again, but do you have any idea or suggestion where i should start?
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-30T20:12:07+00:00
- Post Title: A Plague Tale: Requiem (Asobo DPC) - extracting assets

> Reply from thebestbot ↑Thu Dec 01, 2022 4:08 am at Thu Dec 01, 2022 4:08 am
>
> 
I understand. Thanks a lot for the reply, So guess I should continue my study again, but do you have any idea or suggestion where i should start?

Yeah, this is a very good starting point [viewtopic.php?t=22266](https://forum.xentax.com/viewtopic.php?t=22266)
## Post #5
- Username: thebestbot
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 30, 2022 3:11 am
- Post datetime: 2022-12-01T14:53:51+00:00
- Post Title: A Plague Tale: Requiem (Asobo DPC) - extracting assets

> Reply from ikskoks ↑Thu Dec 01, 2022 4:12 am at Thu Dec 01, 2022 4:12 am
>
> 
Yeah, this is a very good starting point viewtopic.php?t=22266Thanks a lot
## Post #6
- Username: LeoKeller
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 02, 2022 8:53 pm
- Post datetime: 2022-12-02T12:54:06+00:00
- Post Title: A Plague Tale: Requiem (Asobo DPC) - extracting assets

There is no shortcut to do that?
## Post #7
- Username: thebestbot
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 30, 2022 3:11 am
- Post datetime: 2022-12-05T07:55:59+00:00
- Post Title: A Plague Tale: Requiem (Asobo DPC) - extracting assets

> Reply from LeoKeller ↑Fri Dec 02, 2022 8:54 pm at Fri Dec 02, 2022 8:54 pm
>
> 
There is no shortcut to do that?well the game is still fresh released so i actually will be honest with you, i expected to find zero tools. It all depends when someone focuses on it and makes a tool about it. If i manage to complete my work I'll let you know
## Post #8
- Username: thebestbot
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 30, 2022 3:11 am
- Post datetime: 2023-03-09T20:46:03+00:00
- Post Title: A Plague Tale: Requiem (Asobo DPC) - extracting assets

Hi I need some assets from the game "A Plague Tale: Requiem" such as models, textures, Rigs, Animations, Shaders etc.
Now the file format is DPC file format ("zouna" proprietary engine)
Objective: RE the game (using IDA), make a script to read the files and extract those into file formats.
I never found any tutorials, all are just to RE for injecting game trainers, no thank you not guidedhacking,
It's on a proprietary Format so there's no support.

These are some key points about my situation :

* I can't debug APT: Requiem due to not being able to run it on my potato pc
* can't find standard RE tutorials about games, all I know is I find a string, copy it's xref and just reverse that function. what I need is a little example 
  with somewhat detailed explanation, not: "find a string it's xref and reverse the functions"
* My coding term knowledge is kind of weak, what that means is I know a function, but when I hear it's name I'll not know what to do, learning c++ btw

Let me know if something else is possible.

Please let me know if I am missing some information and I'll update the post.
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-03-09T21:59:56+00:00
- Post Title: A Plague Tale: Requiem (Asobo DPC) - extracting assets

You've already asked this question once, so I've merged your new topic with the old one.
Please don't duplicate topics like that.


(And it's not true that you've never found any tutorials - I've sent you a link to some tutorials already, just read them)
## Post #10
- Username: thebestbot
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 30, 2022 3:11 am
- Post datetime: 2023-03-10T14:37:58+00:00
- Post Title: A Plague Tale: Requiem (Asobo DPC) - extracting assets

> Reply from ikskoks ↑Fri Mar 10, 2023 5:59 am at Fri Mar 10, 2023 5:59 am
>
> 
You've already asked this question once, so I've merged your new topic with the old one.
Please don't duplicate topics like that.


(And it's not true that you've never found any tutorials - I've sent you a link to some tutorials already, just read them)
I'm sorry to say this but it wasn't helpful, because I needed help with Datamining
## Post #11
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-03-10T20:00:53+00:00
- Post Title: A Plague Tale: Requiem (Asobo DPC) - extracting assets

> Reply from thebestbot ↑Fri Mar 10, 2023 10:37 pm at Fri Mar 10, 2023 10:37 pm
>
> 
I'm sorry to say this but it wasn't helpful, because I needed help with Datamining

So you should ask this question in some datamining discord server.
It's not datamining forum. It's reverse engineering forum and you'll mostly get help with reverse engineering issues.
## Post #12
- Username: thebestbot
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 30, 2022 3:11 am
- Post datetime: 2023-03-11T13:23:17+00:00
- Post Title: A Plague Tale: Requiem (Asobo DPC) - extracting assets

> Reply from ikskoks ↑Sat Mar 11, 2023 4:00 am at Sat Mar 11, 2023 4:00 am
>
> 
thebestbot wrote: ↑Fri Mar 10, 2023 10:37 pm
I'm sorry to say this but it wasn't helpful, because I needed help with Datamining


So you should ask this question in some datamining discord server.
It's not datamining forum. It's reverse engineering forum and you'll mostly get help with reverse engineering issues.
I did but everyone told me to ask help on Xentax even though I told them that's where I started (oof)
