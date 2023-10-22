## Post #1
- Username: TotalWarrior
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 04, 2011 10:16 pm
- Post datetime: 2011-07-04T17:46:50+00:00
- Post Title: PC - Starship Troopers .slak

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-07-04T20:21:44+00:00
- Post Title: PC - Starship Troopers .slak

old topic:
[viewtopic.php?p=52012#p52012](http://forum.xentax.com/viewtopic.php?p=52012#p52012)
## Post #3
- Username: TotalWarrior
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 04, 2011 10:16 pm
- Post datetime: 2011-07-04T23:05:38+00:00
- Post Title: PC - Starship Troopers .slak

Awesome thanks but a lot of sounds can't be extracted/found especially the ones that play during levels. When I extract from level files no sounds are extracted.
Is the version 0.4.10b important or can I use a newer version?

I don't know if this error has something to do with it but I get some (de)compression error where the compressed zlib/deflate input is wrong or incomplete (-3) and output size is negative (-1)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-07-04T23:12:30+00:00
- Post Title: PC - Starship Troopers .slak

the version of quickbms is not important, so the current one is ok (and suggested).

if you can, please upload one of these slak archives that give the zlib problem on a files hosting website and I will take a look at it.
## Post #5
- Username: TotalWarrior
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 04, 2011 10:16 pm
- Post datetime: 2011-07-04T23:32:20+00:00
- Post Title: PC - Starship Troopers .slak

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-07-05T00:29:57+00:00
- Post Title: PC - Starship Troopers .slak

ok the problem was exactly where I imagined, the ZIP field is not the ZIP field :)
I have updated the script in the original thread.
## Post #7
- Username: TotalWarrior
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 04, 2011 10:16 pm
- Post datetime: 2011-07-05T00:59:09+00:00
- Post Title: PC - Starship Troopers .slak

Sweet! Thanks man I really appreciate your help. It works perfect now. Also I understand by reading the readme of the program that I can change the extracted sounds and reverse the extraction therefore modding the game. The game's gun sounds are pretty bad so I'll probably look into it. Pretty cool feature.
## Post #8
- Username: TotalWarrior
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 04, 2011 10:16 pm
- Post datetime: 2011-07-05T17:32:52+00:00
- Post Title: PC - Starship Troopers .slak

Update: Just tried the reimporter and it didn't work. I tried to replace one of the game's gun sounds which was like 8.8KB with another one which is like 10KB and I got
error in src file\/file.h line 161: myfopen<>
Error: Permission denied

I assume it has to do with permission so I even ran the reimporter and administrator and it still didn't work.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-07-05T17:40:59+00:00
- Post Title: PC - Starship Troopers .slak

the games installed in "c:\Program Files" are accessible in write mode by the administrator usually so if you want to edit them you must run any editor/program (like quickbms too) as administrator.

anyway if the original file is 8.8 kb you cannot replace it with a bigger one.
the rule is: size minor/equal than the original
## Post #10
- Username: TotalWarrior
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 04, 2011 10:16 pm
- Post datetime: 2011-07-05T17:57:29+00:00
- Post Title: PC - Starship Troopers .slak

I'm trying with Audacity and 10KB is the lowest I'm getting. I don't know how else I'm supposed to lower it down even more.
I assume this has to do with the size as well.
