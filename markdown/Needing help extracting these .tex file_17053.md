## Post #1
- Username: Maren
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jul 18, 2017 11:36 pm
- Post datetime: 2017-09-22T15:09:33+00:00
- Post Title: Needing help extracting these .tex file

I got these file from a ps3 game. Anyone know how to convert it??

Please teach me, I still have lots of other .tex files of the same game need to be open it

[https://www.dropbox.com/sh/up490x544tg9 ... K-Jta?dl=0](https://www.dropbox.com/sh/up490x544tg9zzr/AAB6wIQgy1Elxh0ZDU4LK-Jta?dl=0)
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2017-09-22T16:09:34+00:00
- Post Title: Needing help extracting these .tex file

They are PNGs with added "header". If you will want to change the texture, you need to discover the meanings if the header. If not, just remove first 28 bytes (until you reach ‰PNG...) with some hex editor and save it with .png extension.
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-09-22T20:42:50+00:00
- Post Title: Needing help extracting these .tex file

this bms script will automate the cleanup of header and will write out original header for reimport i guess 

```

get NAME basename
get SIZE asize
math SIZE - 0x1c
string HEADER = NAME
string HEADER + .header
string NAME + .png
log NAME 0x1c SIZE
log HEADER 0x0 0x1c
```
## Post #4
- Username: Maren
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jul 18, 2017 11:36 pm
- Post datetime: 2017-09-29T05:13:05+00:00
- Post Title: Needing help extracting these .tex file

I extracted the file. But looks like the file is encrypted. It can't be view
