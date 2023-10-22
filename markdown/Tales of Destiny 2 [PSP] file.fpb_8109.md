## Post #1
- Username: Feit
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 27, 2011 10:14 am
- Post datetime: 2012-01-23T14:41:31+00:00
- Post Title: Tales of Destiny 2 [PSP] file.fpb

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-01-24T12:48:30+00:00
- Post Title: Tales of Destiny 2 [PSP] file.fpb

the file itself is useless, pointers are inside the executable
## Post #3
- Username: Feit
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 27, 2011 10:14 am
- Post datetime: 2012-01-24T14:00:04+00:00
- Post Title: Tales of Destiny 2 [PSP] file.fpb

what dou you mean by "pointers are inside the executable" sir?
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-24T16:22:29+00:00
- Post Title: Tales of Destiny 2 [PSP] file.fpb

I'm guessing offsets to data stored in the data file.
## Post #5
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-01-25T11:56:03+00:00
- Post Title: Tales of Destiny 2 [PSP] file.fpb

no are stored inside BOOT.BIN (or EBOOT.BIN after it's been decrypted), dunno the offset though, I'm not at home. Just look for the total dimension of the .fpb file (inverted) inside that and you will find the last pointer, just go up and you'll notice a pattern
## Post #6
- Username: Feit
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 27, 2011 10:14 am
- Post datetime: 2012-01-25T14:37:30+00:00
- Post Title: Tales of Destiny 2 [PSP] file.fpb

do you perhaps want to take a peak at the file sirs?

though its 400mb big
## Post #7
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-01-25T15:08:21+00:00
- Post Title: Tales of Destiny 2 [PSP] file.fpb

that file is just a container for one file after another, there absolutely no info inside
## Post #8
- Username: Feit
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 27, 2011 10:14 am
- Post datetime: 2012-01-25T15:19:37+00:00
- Post Title: Tales of Destiny 2 [PSP] file.fpb

they say that Basically, both PS2 and PSP versions of the game are exactly the same, the only difference in the compression algorithm: while the PS2 version uses simple combinations of LZSS + RLE, the PSP version uses a custom DEFLATE implementation.
## Post #9
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-01-26T08:53:41+00:00
- Post Title: Tales of Destiny 2 [PSP] file.fpb

it's not custom, it's raw (headerless) gzip
## Post #10
- Username: Feit
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 27, 2011 10:14 am
- Post datetime: 2012-01-26T13:31:23+00:00
- Post Title: Tales of Destiny 2 [PSP] file.fpb

then what should i do to open it sir?, just instruct me sir and i will do it, i will accept any help that will be given.
## Post #11
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-01-27T15:49:31+00:00
- Post Title: Tales of Destiny 2 [PSP] file.fpb

you need to write yourself a program to do that (or a BMS script) but note that there won't be any filename or directories so if you're looking for something in particular...well, good luck with that
