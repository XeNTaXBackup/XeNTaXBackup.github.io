## Post #1
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2012-08-20T12:38:43+00:00
- Post Title: Lua script

Can someone help me decompile the attached lua script?

luadec always comes back with 'luadec: boot.luac:1: unexpected symbol near 'char(2)'' which isn't very helpful.
I've tried adding the lua 5.1 header to the file (its currently missing) and I get the same result.
[boot.zip](https://xentaxbackup.github.io/file/5696_boot.zip)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-20T16:27:24+00:00
- Post Title: Lua script

Header not missing because this script compiled with [LuaJIT](http://luajit.org/download.html)
## Post #3
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2012-08-20T16:55:08+00:00
- Post Title: Lua script

Thanks, how did you work out they were compiled with luajit? Just in case I come across them again it'd be helpful to know how to identify them.
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-21T06:27:09+00:00
- Post Title: Lua script

JuaJIT used in Legend of Grimrock. I made the video how decompiling scripts by BYTE CODE.

Video [here](http://www20.zippyshare.com/v/34753967/file.html)

> Reply from twisted
>
> it'd be helpful to know how to identify them.

Header -> 
```
.....LJ
```
## Post #5
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2012-08-21T11:25:54+00:00
- Post Title: Lua script

Thanks, would you be able to look at the code I posted in the grimrock thread? can't seem to recreate a section of code.
