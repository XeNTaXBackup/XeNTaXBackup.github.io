## Post #1
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-09-14T22:08:51+00:00
- Post Title: Wukong

This is supposed to be a chinese clone between TERA and blade and soul. There is a installer now at:

[http://wkz.baiyou100.com/](http://wkz.baiyou100.com/)

The archives are called .pak and header starts with PAK. But I could not use normal winrar or repair with winrar. Offzip gives me alot of files though. But perhaps a bms could give names etc too.

[http://www.2shared.com/file/k3DW_xM_/wukong.html](http://www.2shared.com/file/k3DW_xM_/wukong.html)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-15T21:29:19+00:00
- Post Title: Wukong

bms to extract pac files

```
goto 0x19
get offset long
get size long
get zsize long
get baseoff long
get datasize long
get arcsize long
clog MEMORY_FILE offset zsize size
get unk01 long MEMORY_FILE
get unk02 long MEMORY_FILE
get files short MEMORY_FILE
goto 0x12 MEMORY_FILE
get folder3 string MEMORY_FILE
For tmp = tmp != size
get offset long MEMORY_FILE
get size2 long MEMORY_FILE
math offset + baseoff
if size2 == 0
get folder string MEMORY_FILE
else if size2 == 1
get folder2 string MEMORY_FILE
string folder + \
string folder + folder2
else
get name2 string MEMORY_FILE
set name folder
string name + \
string name + name2
log name offset size2
endif
savepos tmp MEMORY_FILE
next

```
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-19T02:34:26+00:00
- Post Title: Wukong

I should be able to post a script soon that will import models with bones and weights and assign textures.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-19T02:37:13+00:00
- Post Title: Wukong

oh, cute models.
