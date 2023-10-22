## Post #1
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2021-08-09T10:46:41+00:00
- Post Title: EA XSH file

How to view this format. It's old EA's graphic format, but I can't open it, here is the sample:
[https://www.mediafire.com/file/rb7v2kb3 ... 0.xsh/file](https://www.mediafire.com/file/rb7v2kb39ajaewm/t22__5623_0.xsh/file)
## Post #2
- Username: greenlemonade1
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-08-09T14:32:47+00:00
- Post Title: EA XSH file

Hi, this file format is known. You can see some specification here 
[http://wiki.xentax.com/index.php/EA_SSH_FSH_Image](http://wiki.xentax.com/index.php/EA_SSH_FSH_Image)

What game is it from? Is it some NBA Live on xbox?
## Post #3
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2021-08-09T14:56:38+00:00
- Post Title: EA XSH file

> Reply from ikskoks ↑Mon Aug 09, 2021 10:32 pm at Mon Aug 09, 2021 10:32 pm
>
> 
Hi, this file format is known. You can see some specification here 
http://wiki.xentax.com/index.php/EA_SSH_FSH_Image

What game is it from? Is it some NBA Live on xbox?

Thanks mate, but how can I export it in for example png. or see the texture?
It's actually from fifa 2006 xbox classic
## Post #4
- Username: greenlemonade1
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-08-09T19:36:57+00:00
- Post Title: EA XSH file

For now there are no tools that are able to parse this kind of file.
You can sometimes get some results using TextureFinder, but that won't be possible with compressed images.
## Post #5
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2021-08-09T20:53:02+00:00
- Post Title: EA XSH file

> Reply from ikskoks ↑Tue Aug 10, 2021 3:36 am at Tue Aug 10, 2021 3:36 am
>
> 
For now there are no tools that are able to parse this kind of file.
You can sometimes get some results using TextureFinder, but that won't be possible with compressed images.

i tried  but it's hard to deal with texture finder. Can you try, just to see if it works, or to try if the files are compressed
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-08-10T09:20:32+00:00
- Post Title: EA XSH file

Yeah, I tried and your sample is compressed.
## Post #7
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2021-08-10T09:48:05+00:00
- Post Title: EA XSH file

> Reply from ikskoks ↑Tue Aug 10, 2021 5:20 pm at Tue Aug 10, 2021 5:20 pm
>
> 
Yeah, I tried and your sample is compressed.

Thank you, I will ask someone to decompress it and I will be back
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-08-15T10:30:57+00:00
- Post Title: EA XSH file

It's NOT compressed. It's swizzled.
[t22__5623_0.png](https://xentaxbackup.github.io/file/20618_t22__5623_0.png)
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-08-15T10:32:45+00:00
- Post Title: EA XSH file

Noesis script to load from this sample (first mip only):
[tex_EA_xsh.zip](https://xentaxbackup.github.io/file/20619_tex_EA_xsh.zip)
