## Post #1
- Username: g3stapo
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Nov 21, 2019 6:59 am
- Post datetime: 2021-02-09T09:40:10+00:00
- Post Title: Nostale - Extracting zlib compression

Hello
It's just a settings file which stores text information, I think it's zlib compression, but I tried all the tools and nothing helped.Someone can tell an zlib unpacker who can do it?
I tried QuickBMS, Offzip none of this helped
[https://mega.nz/file/dpx2ULzY#MaYx7nexg ... IE8FsGEkJk](https://mega.nz/file/dpx2ULzY#MaYx7nexgoKdLFDQmGsihMX9aDrH14f6FIE8FsGEkJk)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-09T11:18:54+00:00
- Post Title: Nostale - Extracting zlib compression

It doesnt't look like ZLIB at all.
[https://i.imgur.com/EbwHqZ9.png](https://i.imgur.com/EbwHqZ9.png)

There is some weird header starting with "AC 0B 3F",
then there is list of pointers and there is this header again.

I think that compressed data starts below that and it divided to some kind of chunks
[https://i.imgur.com/iOe5SO2.png](https://i.imgur.com/iOe5SO2.png)

From what game is this sample?
## Post #3
- Username: g3stapo
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Nov 21, 2019 6:59 am
- Post datetime: 2021-02-09T13:30:52+00:00
- Post Title: Nostale - Extracting zlib compression

what could it be?
game name Nostale
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-09T13:46:13+00:00
- Post Title: Nostale - Extracting zlib compression

Well, it doesn't look familiar to me.

You can try to use aluigi's comtype scanner with last data chunk
and see if you will get any meaningful results. [https://zenhax.com/viewtopic.php?t=23](https://zenhax.com/viewtopic.php?t=23)
I have cutted it for you and uploaded as an attachment.
[sample1.zip](https://xentaxbackup.github.io/file/19500_sample1.zip)
## Post #5
- Username: g3stapo
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Nov 21, 2019 6:59 am
- Post datetime: 2021-02-09T15:34:20+00:00
- Post Title: Nostale - Extracting zlib compression

I did this, exported all the dmp, then checked them with a hex editor and found nothing familiar
## Post #6
- Username: g3stapo
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Nov 21, 2019 6:59 am
- Post datetime: 2021-02-09T15:54:50+00:00
- Post Title: Nostale - Extracting zlib compression

> Reply from ikskoks ↑Tue Feb 09, 2021 7:18 pm at Tue Feb 09, 2021 7:18 pm
>
> 
It doesnt't look like ZLIB at all.
https://i.imgur.com/EbwHqZ9.png

There is some weird header starting with "AC 0B 3F",
then there is list of pointers and there is this header again.

this list of pointers is contained in the text information of the file
