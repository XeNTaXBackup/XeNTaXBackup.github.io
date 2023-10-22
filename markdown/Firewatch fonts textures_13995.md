## Post #1
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-02-20T10:10:57+00:00
- Post Title: Firewatch fonts textures

Hi,

Can anyone have a look on this textures pls ? Looks like ATI2 but not sure.. Cannot figure it out..

```
https://dl.dropboxusercontent.com/u/38234344/Revers%20Engineering/Fonts%20Firewatch.rar
```
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-02-24T22:11:42+00:00
- Post Title: Firewatch fonts textures

Looks like a .dds file with a custom header.
Delete the first 0x38 bytes of the .tex file and insert this .dds header instead:

```
44 44 53 20 7C 00 00 00 07 10 02 00 00 08 00 00 00 04 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 20 00 00 00 02 00 00 00 00 00 00 00 08 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 FF 00 00 00 08 10 40 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
```
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-02-25T07:21:34+00:00
- Post Title: Firewatch fonts textures

> Reply from herbert3000
>
> Looks like a .dds file with a custom header.
Delete the first 0x38 bytes of the .tex file and insert this .dds header instead:
Code: Select all44 44 53 20 7C 00 00 00 07 10 02 00 00 08 00 00 00 04 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 20 00 00 00 02 00 00 00 00 00 00 00 08 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 FF 00 00 00 08 10 40 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00

Sorry i allready found it days ago, of course it is dds  i knew it before, i was not only sure about dds header..
## Post #4
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2016-03-14T15:23:47+00:00
- Post Title: Firewatch fonts textures

just 8bit greyscale image
