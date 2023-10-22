## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-04-19T10:31:21+00:00
- Post Title: King Arthur 2 .N2M

Hello, could someone help me extract files from King Arthur 2 .n2m archives? Here's sample. Thanks in advance.
[Gawain.rar](https://xentaxbackup.github.io/file/6342_Gawain.rar)
## Post #2
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-04-20T15:55:54+00:00
- Post Title: King Arthur 2 .N2M

Can you attach bigger file? 10-20 Mb
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-04-20T19:33:02+00:00
- Post Title: King Arthur 2 .N2M

Sure, no problem [http://www.mediafire.com/?cxr31lfd56ak8mq](http://www.mediafire.com/?cxr31lfd56ak8mq)
## Post #4
- Username: zaramot
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-04-21T15:15:53+00:00
- Post Title: King Arthur 2 .N2M

```
#by chrrox
idstring "C2AR"
append
getdstring null 10
get TSIZE long
do
get ZSIZE long
savepos OFFSET
if TSIZE >= 0x800000
set SIZE 0x800000
else
set SIZE TSIZE
endif
clog MEMORY_FILE OFFSET ZSIZE SIZE
math TSIZE -= SIZE
math OFFSET + ZSIZE
goto OFFSET
while TSIZE != 0
append
get NAME basename
string NAME + ".ext"
get SIZE asize MEMORY_FILE
log NAME 0 SIZE MEMORY_FILE
```
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-04-21T18:01:23+00:00
- Post Title: King Arthur 2 .N2M

Thanks you so much chrrox   Now I can look at model format, textures a straight .dds
## Post #6
- Username: Solo Dogo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 19, 2022 9:30 am
- Post datetime: 2022-06-19T01:31:43+00:00
- Post Title: King Arthur 2 .N2M

> Reply from zaramot ↑Mon Apr 22, 2013 2:01 am at Mon Apr 22, 2013 2:01 am
>
> 
Thanks you so much chrrox   Now I can look at model format, textures a straight .dds

Hey dude, you have a tool to open the .n2m mesh/model files for King Arthur 2 troops?

I tried to look for tools online but couldn't see anything, much appreciated if you can help!
