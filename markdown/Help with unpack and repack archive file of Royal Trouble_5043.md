## Post #1
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-09-15T23:52:13+00:00
- Post Title: Help with unpack and repack archive file of Royal Trouble

Can anyone help with unpacking and repacking the archive file of Royal Trouble?
It seems be compressed.

A sample can be download here.
[http://www.playfirst.com/game/royal-trouble/windows](http://www.playfirst.com/game/royal-trouble/windows)
## Post #2
- Username: thesnow
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 11, 2010 1:52 pm
- Post datetime: 2010-09-16T04:03:50+00:00
- Post Title: Help with unpack and repack archive file of Royal Trouble

i have download this game.

the arc is BZIP2
## Post #3
- Username: thesnow
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 11, 2010 1:52 pm
- Post datetime: 2010-09-16T06:31:10+00:00
- Post Title: Help with unpack and repack archive file of Royal Trouble

maybe like:

> {
>
> flag1    long
>
> flag2    long
>
>     {
>
>     NameSize    long
>
>     Name[size]    char
>
>     isDir        byte
>
>     offset        long
>
>     flag3        long
>
>     flag4        long
>
>     sizeof(packed)    long
>
>     sizeof(data)    long
>
>     }
>
> data    byte
>
> }
## Post #4
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-09-21T23:55:26+00:00
- Post Title: Help with unpack and repack archive file of Royal Trouble

> Reply from thesnow
>
> maybe like:
{
flag1    long
flag2    long
    {
    NameSize    long
    Name[size]    char
    isDir        byte
    offset        long
    flag3        long
    flag4        long
    sizeof(packed)    long
    sizeof(data)    long
    }
data    byte
}

Very thanks! Can you make a bms script fot it?
