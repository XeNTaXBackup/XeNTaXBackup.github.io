## Post #1
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2019-09-22T17:56:02+00:00
- Post Title: Ni no Kuni: links between text and voice

Good day.
I am trying to understand how voices are related to text.

I need to rename every .sgb file to the phrase from game resources. For example:
0100000.sgb -> 0100000 Get a move on, Ollie-boy!.ogg

There are some files that I think are related to this:
[https://yadi.sk/d/zqcPOqsoVVxJsQ](https://yadi.sk/d/zqcPOqsoVVxJsQ)

event\eva0010_text_en.cfg.bin contains phrases
voice\0100000.sgb - the first phrase (it's .ogg file)

The heuristic approach doesn't work - there are 9900140.sgb file here, and there is no a single event that would be called that.
## Post #2
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2019-09-23T01:12:02+00:00
- Post Title: Ni no Kuni: links between text and voice

I wrote a template for 010 Editor to view .cfg.bin files:
[https://pastebin.com/SrVykeud](https://pastebin.com/SrVykeud)

Unfortunately, it has not yet helped to find the necessary information.
## Post #3
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2019-09-26T19:38:40+00:00
- Post Title: Ni no Kuni: links between text and voice

I found battle voices, but still can’t find the subtitle binding.
## Post #4
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2019-09-28T00:49:39+00:00
- Post Title: Ni no Kuni: links between text and voice

Seems like I found it.
There are track numbers in the eva0010_en.stb file.



There is a "trifle" left - to parse the SB2 script file. т_т
## Post #5
- Username: Arigatou
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Feb 29, 2012 5:07 am
- Post datetime: 2019-11-26T01:18:41+00:00
- Post Title: Ni no Kuni: links between text and voice

Look this:
[https://zenhax.com/viewtopic.php?f=12&t=12765](https://zenhax.com/viewtopic.php?f=12&t=12765)
## Post #6
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2019-12-31T20:14:51+00:00
- Post Title: Ni no Kuni: links between text and voice

> Reply from Arigatou ↑Tue Nov 26, 2019 9:18 am at Tue Nov 26, 2019 9:18 am
>
> 
Look this:
https://zenhax.com/viewtopic.php?f=12&t=12765

> Reply from Albeoris ↑Mon Sep 23, 2019 9:12 am at Mon Sep 23, 2019 9:12 am
>
> 
I wrote a template for 010 Editor to view .cfg.bin files:
https://pastebin.com/SrVykeud

Unfortunately, it has not yet helped to find the necessary information.

Unfortunately, the file IDs are written in the .stb files, which is a compiled sequence of bytecodes. :/
