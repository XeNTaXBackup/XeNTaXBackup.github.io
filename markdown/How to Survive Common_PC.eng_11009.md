## Post #1
- Username: reznov
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Dec 17, 2010 6:24 pm
- Post datetime: 2013-12-01T13:08:42+00:00
- Post Title: How to Survive Common_PC.eng

I Need To unpacker/repacker for How to Survive Common_PC.eng file.

Sample [Common_PC.rar](http://www.uploadmb.com/dw.php?id=1385907808)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-12-01T13:13:36+00:00
- Post Title: How to Survive Common_PC.eng

Where sample?
## Post #3
- Username: reznov
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Dec 17, 2010 6:24 pm
- Post datetime: 2013-12-02T17:41:51+00:00
- Post Title: How to Survive Common_PC.eng

> Reply from Ekey
>
> Where sample?

> reznov wrote:I Need To unpacker/repacker for How to Survive Common_PC.eng file.
>
> 
>
> Sample Common_PC.rar
## Post #4
- Username: reznov
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Dec 17, 2010 6:24 pm
- Post datetime: 2013-12-03T14:48:41+00:00
- Post Title: How to Survive Common_PC.eng

Can anyone take a look at this files.
## Post #5
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-12-05T09:28:07+00:00
- Post Title: How to Survive Common_PC.eng

Here is a script, but it unpacks only a few dds and a lot of unknow files.

```
get files1 long
get files2 long
get files3 long
get files4 long
xmath files "files1+files2+files3+files4"
getdstring unk 8
for i = 0 < files
get size long
get id long
if id = 0x58534444
getdstring ddsdata 8
get size long
endif
savepos offset
log "" offset size
math offset += size
goto offset
next i
```
## Post #6
- Username: reznov
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Dec 17, 2010 6:24 pm
- Post datetime: 2013-12-07T04:10:29+00:00
- Post Title: How to Survive Common_PC.eng

Very Thanks,my Friend. because I need To Edit string or language File For This Game.
## Post #7
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-12-07T22:05:56+00:00
- Post Title: How to Survive Common_PC.eng

hhrhhr made some lua scripts for the game. You can find them on his github. [https://github.com/hhrhhr/Lua-utils-for-How-to-Survive](https://github.com/hhrhhr/Lua-utils-for-How-to-Survive)
## Post #8
- Username: reznov
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Dec 17, 2010 6:24 pm
- Post datetime: 2013-12-08T21:07:10+00:00
- Post Title: How to Survive Common_PC.eng

> Reply from swuforce
>
> hhrhhr made some lua scripts for the game. You can find them on his github.
I have not been able to..
## Post #9
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-12-12T06:30:48+00:00
- Post Title: How to Survive Common_PC.eng

> Reply from swuforce
>
> hhrhhr made some lua scripts for the game. You can find them on his github. https://github.com/hhrhhr/Lua-utils-for-How-to-Survive

Do you have any contact please ?
## Post #10
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-12-12T14:43:48+00:00
- Post Title: How to Survive Common_PC.eng

He is a member of this forum, so i think you should try to send pm.
## Post #11
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-12-12T16:40:44+00:00
- Post Title: How to Survive Common_PC.eng

> Reply from swuforce
>
> He is a member of this forum, so i think you should try to send pm.

Thx allready contetaced him :0 All sorted
## Post #12
- Username: reznov
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Dec 17, 2010 6:24 pm
- Post datetime: 2013-12-31T01:58:13+00:00
- Post Title: How to Survive Common_PC.eng

There was no news?
## Post #13
- Username: geraldhu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Dec 03, 2014 1:06 am
- Post datetime: 2014-12-05T20:41:11+00:00
- Post Title: How to Survive Common_PC.eng

> Reply from reznov
>
> There was no news?
I try to use hhrhhr's lua,only can edit language File for A-Z 26,hard to Asian language.
