## Post #1
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2012-03-22T14:44:24+00:00
- Post Title: 010 editor 24bit uint

Hi, I'm currently writing a 010 editor template script and I'm having trouble reading some file offsets in the contents table as they are stored as a 24bit uint and 010 editor does not support type casting.

I've tried bitfields but they don't seem to calculate the offset correctly and always display 0. Does anyone know a work around for this?

Thanks in advance.
## Post #2
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2012-03-22T16:39:27+00:00
- Post Title: 010 editor 24bit uint

Managed to get the bitfields to work so never mind!
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-22T17:11:26+00:00
- Post Title: 010 editor 24bit uint

How did you solve it? Maybe others might run into the same problem.
## Post #4
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2012-03-22T22:48:00+00:00
- Post Title: 010 editor 24bit uint

My mistake was using bytes instead of bits, so I had typed:

```
uint flag : 1

```


when it should have been:

```
uint flag : 8

```
