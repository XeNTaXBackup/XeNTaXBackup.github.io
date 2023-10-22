## Post #1
- Username: Jyouji
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 10, 2012 7:49 pm
- Post datetime: 2012-02-10T12:01:36+00:00
- Post Title: [PC]Kingdoms of Amalur dds files.

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-02-10T13:36:21+00:00
- Post Title: [PC]Kingdoms of Amalur dds files.

Just delete first 16 bytes of every DDS file
## Post #3
- Username: Jyouji
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 10, 2012 7:49 pm
- Post datetime: 2012-02-11T10:39:44+00:00
- Post Title: [PC]Kingdoms of Amalur dds files.

oh cheers,  how didnt i see that
## Post #4
- Username: matreco
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Feb 17, 2012 11:56 pm
- Post datetime: 2012-02-17T15:59:51+00:00
- Post Title: [PC]Kingdoms of Amalur dds files.

It works a treat, I wonder if there is a way to batch process them.
## Post #5
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-02-17T16:22:08+00:00
- Post Title: [PC]Kingdoms of Amalur dds files.

Batch for cutting that 16 bytes?
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-17T18:33:26+00:00
- Post Title: [PC]Kingdoms of Amalur dds files.

You can use quickbms for batch processing.

```
#quickbms script

get SIZE asize
math SIZE -= 16
get NAME filename

log NAME 16 SIZE

```
## Post #7
- Username: arlega02
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Mar 25, 2012 3:21 am
- Post datetime: 2012-03-28T16:59:37+00:00
- Post Title: [PC]Kingdoms of Amalur dds files.

First, thanks for this method. But i have a problem. I did opened font files with this method and edited them and repack all. But after this, writings dont appear in game. In place of writings, black lines appearing. How can i fix this problem? Or anyone can edit font files for me?(for adding Turkish characters)
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-28T23:01:26+00:00
- Post Title: [PC]Kingdoms of Amalur dds files.

Did you remember to put the 16 bytes back.
## Post #9
- Username: dubh
- Rank: n00b
- Number of posts: 13
- Joined date: Mon May 23, 2011 4:34 pm
- Post datetime: 2013-01-13T16:43:42+00:00
- Post Title: [PC]Kingdoms of Amalur dds files.

> Reply from finale00
>
> Did you remember to put the 16 bytes back.

Would this work?

```
#quickbms script

get SIZE asize
math SIZE += 16
get NAME filename

log NAME 16 SIZE
```
## Post #10
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2013-01-13T18:52:33+00:00
- Post Title: [PC]Kingdoms of Amalur dds files.

> Reply from dubh
>
> finale00 wrote:Did you remember to put the 16 bytes back.

Would this work?
Code: Select all#Kingdom of Amalur DDS
#quickbms script

get SIZE asize
math SIZE += 16
get NAME filename

log NAME 16 SIZE

no because the bytes were removed as a result of the previous script.. you would need to copy over the bytes in a hex editor or write a script which takes them from the original file
