## Post #1
- Username: hgdagon
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 07, 2014 10:39 am
- Post datetime: 2015-05-16T00:40:48+00:00
- Post Title: [REQ] ReVOLUTION *.arc archives

ReVOLUTION is a pretty obscure game made by FUNLabs in 2002. And it uses it's own archive formats. Below is a link to an archive containing several *.arc files from the game. Would really appreciate an extraction script. Thanks in advance.

```
https://cloud.mail.ru/public/3sLKJAS6Hgdd/Revexamples.zip
```
## Post #2
- Username: hgdagon
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-05-16T20:27:02+00:00
- Post Title: [REQ] ReVOLUTION *.arc archives

Not a consistent format at all. Each .arc file is completely different. Most of them contain zlib deflate data. I would just use Aluigi's offzip to extract the compressed data.
## Post #3
- Username: hgdagon
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 07, 2014 10:39 am
- Post datetime: 2015-05-17T00:15:54+00:00
- Post Title: [REQ] ReVOLUTION *.arc archives

> Reply from Gh0stBlade
>
> Not a consistent format at all. Each .arc file is completely different. Most of them contain zlib deflate data. I would just use Aluigi's offzip to extract the compressed data.
I probably should've mentioned in the first post, that files dated September 2002 are from original 1.0 version of the game, and those dated October 2002 are from 1.1 patch. The latter are being extracted to another subfolder in order to override the old ones, so it's not a "patch data" per se, the game reads both types. Are files with the same timestamp different? 

As for offzip, it worked, but doesn't recognize filenames. Anyway, thanks a lot.
## Post #4
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-05-18T14:43:45+00:00
- Post Title: [REQ] ReVOLUTION *.arc archives

> Reply from hgdagon
>
> Gh0stBlade wrote:Not a consistent format at all. Each .arc file is completely different. Most of them contain zlib deflate data. I would just use Aluigi's offzip to extract the compressed data.
I probably should've mentioned in the first post, that files dated September 2002 are from original 1.0 version of the game, and those dated October 2002 are from 1.1 patch. The latter are being extracted to another subfolder in order to override the old ones, so it's not a "patch data" per se, the game reads both types. Are files with the same timestamp different? 

As for offzip, it worked, but doesn't recognize filenames. Anyway, thanks a lot.
Same inconsistency it seems.
