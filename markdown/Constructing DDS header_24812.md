## Post #1
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2021-12-07T00:26:13+00:00
- Post Title: Constructing DDS header

Hello.

I exported some game files and it gave me alot of these DDS textures.

[https://drive.google.com/file/d/1SMzdFj ... sp=sharing](https://drive.google.com/file/d/1SMzdFjkxpOVIFELLirkFHLzAxmLYWZF_/view?usp=sharing)

I asked on xentax discord and someone replied saying its 256x256 BC7 without a header.
I have no idea what did he/she figured it out from. I opened the file in hex editor and can't see anything about BC7 or the resolution etc...

But I don't know how to construct a header. I guess you have to use Hex editor and insert some data in there? I looked on some hex editor tutorials etc... but I found nothing about constructing a header of a file or even some example files for comparison to see which part of the file is a header and what certain parts of that header means etc...

Can please somebody construct a header for the file so I can compare it and see what you added there and hopefully then I'll have a better understanding about how to do it so I can do it myself for other files?
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-07T09:00:13+00:00
- Post Title: Constructing DDS header

There are two ways of constructing DDS header - automatic and manual.

Easier for you would be automatic way, you can use Raw texture cooker for that [viewtopic.php?f=18&t=16461](https://forum.xentax.com/viewtopic.php?f=18&t=16461)
Here is the result [https://i.imgur.com/jOY2UvQ.png](https://i.imgur.com/jOY2UvQ.png)


You could also try manual way, but it requires some knowledge about DDS file format.
You can read about it here [http://wiki.xentax.com/index.php/DDS_Image](http://wiki.xentax.com/index.php/DDS_Image)
Then you would need to write a program (or quickbms script) to create a valid header and join it with your data.


By the way, it's not real DDS file if it has missing header. You should call it something like "test.bin" instead of "test.dds".
## Post #3
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2021-12-07T09:30:45+00:00
- Post Title: Constructing DDS header

I tried RawTex but it doesn't work for me. How come?

[](https://ibb.co/cNXTSRc)
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-07T09:44:38+00:00
- Post Title: Constructing DDS header

> Reply from martanius ↑Tue Dec 07, 2021 5:30 pm at Tue Dec 07, 2021 5:30 pm
>
> 
I tried RawTex but it doesn't work for me. How come?

Maybe you don't have texconv in the same directory. Try to read the comments in the topic I have linked.
There were people with the past with the similar issues.
## Post #5
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2021-12-08T05:13:27+00:00
- Post Title: Constructing DDS header

Well, thank you for your time and help  I tried to do something abour that rawtext, but to no success.

Anyway, I extracted the files using different script and is seems like this one extracted it properly so now I can convert it to PNG.
