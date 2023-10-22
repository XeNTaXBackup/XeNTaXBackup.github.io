## Post #1
- Username: cockafej
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Mar 31, 2018 3:14 am
- Post datetime: 2020-09-20T07:08:55+00:00
- Post Title: [SOLVED][X360] texture format

Hi,

Can anybody help me?
There is a X360 texture file, that i don't know it's texture format. (swizzled?)

What is the name of texture format 14?

52 = DXT1
54 = DXT5
71 = DXN
86 = ABGR
14 = ?

I attach the sample file
Thank you
[5.RAR](https://xentaxbackup.github.io/file/18763_5.RAR)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-09-22T06:52:08+00:00
- Post Title: [SOLVED][X360] texture format

> Reply from cockafej ↑Sun Sep 20, 2020 3:08 pm at Sun Sep 20, 2020 3:08 pm
>
> What is the name of texture format 14?
it looks like 512x256 dxt5  



5.png (67.9 KiB) Viewed 82 times
## Post #3
- Username: cockafej
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Mar 31, 2018 3:14 am
- Post datetime: 2020-09-22T13:29:33+00:00
- Post Title: [SOLVED][X360] texture format

Hi Acewell,

If I swizzle the image with simple DXT5 (54), then I get this result:



6out.png (126.71 KiB) Viewed 76 times



What is the wrong?
What am I missing?

Update:

Solved!

Before swizzle I had to swap the bytes for a short length. So it's really DXT5.
Thanks
