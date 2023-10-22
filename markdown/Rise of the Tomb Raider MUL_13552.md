## Post #1
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-20T22:01:11+00:00
- Post Title: Rise of the Tomb Raider MUL

Hi,

Can anyone help me to found out structure for this file? It seems to be audio file, dont need to make working audio file from it, just need to be able to get offsets of the strings, was trying, but it seem too much for me, totally unknown format ... Thx

```
https://dl.dropboxusercontent.com/u/38234344/110_av_avalanche.rar
```
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-21T14:05:15+00:00
- Post Title: Rise of the Tomb Raider MUL

> Reply from michalss
>
> [...], just need to be able to get offsets of the strings, was trying, but it seem too much for me, totally unknown formatif you expect someone to dig into this format, I'm off.
But there's a simple solution: do a wildcard search such as for 0D5B3F3F3F3F5D with 3F being the wildcard.
(or search for 0D5B then check for 5D at offset+6)

Gives 98 finds in 14_expedition_cine.mul.
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-21T14:29:29+00:00
- Post Title: Rise of the Tomb Raider MUL

> Reply from shakotay2
>
> michalss wrote:[...], just need to be able to get offsets of the strings, was trying, but it seem too much for me, totally unknown format if you expect someone to dig into this format, I'm off.
But there's a simple solution: do a wildcard search such as for 0D5B3F3F3F3F5D with 3F being the wildcard.
(or search for 0D5B then check for 5D at offset+6)

Gives 98 finds in 14_expedition_cine.mul.

Thx this wont work, i had to write algo for this and getting all string from directly big files  but still not really proper way to do it.. Thx for trying..
