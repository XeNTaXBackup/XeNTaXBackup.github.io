## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-07-15T04:49:28+00:00
- Post Title: Autolegends USSR (Moscow Racer) .trf

[Here](https://dl.dropbox.com/u/9919707/blogs/xentax.com/autolegends-ussr-pc/Textures.7z) is container for all textures in the game.
## Post #2
- Username: Tosyk
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-07-15T22:56:37+00:00
- Post Title: Autolegends USSR (Moscow Racer) .trf

```
# By MrNightmareTM
# Version 0.1

get SIGN long
get NTBLOFF long
savepos OFFSET

goto NTBLOFF
get FILES long

set NAME "textures\"

for i = 0 < FILES
get NSIZE1 long
getdstring NAME2 NSIZE1

get NSIZE2 long
getdstring NAME3 NSIZE2

get TYPE long
get SIZE long

string NAME += NAME2
string NAME += NAME3

log NAME OFFSET SIZE
set NAME ""
set NAME2 ""
math OFFSET += SIZE
next i


```


Here you go, click thanks if i helped.

Enjoy!
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-07-15T23:54:30+00:00
- Post Title: Autolegends USSR (Moscow Racer) .trf

works great, thank you
## Post #4
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-07-22T08:12:07+00:00
- Post Title: Autolegends USSR (Moscow Racer) .trf

Awesome, thank you very much!

EDIT: How to view the .mt textures?
## Post #5
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-07-22T09:54:27+00:00
- Post Title: Autolegends USSR (Moscow Racer) .trf

> Reply from RacingFreak
>
> Awesome, thank you very much!

EDIT: How to view the .mt textures?some kind of compression, no way for now, but you can post some samples in graphic research thread
