## Post #1
- Username: coolcat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 11, 2022 6:13 am
- Post datetime: 2022-11-10T22:26:16+00:00
- Post Title: muramasa demon blade (wii) unpack

hi guys.

I've tried to localize muramasa demon blade.
I used to unpack script got from game archive thread.
here [viewtopic.php?t=9143](https://forum.xentax.com/viewtopic.php?t=9143)

```
get name filename
string name + .ext
get zsize asize
math zsize - 12
set size zsize
math size * 4
clog name 12 zsize size

```


It was working well but some .ftx files didn't.

could you help me?
[place02.zip](https://xentaxbackup.github.io/file/23019_place02.zip)
