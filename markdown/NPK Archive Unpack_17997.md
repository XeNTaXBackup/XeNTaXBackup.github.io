## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-18T21:51:11+00:00
- Post Title: NPK Archive Unpack

Hi,

I have some NPK files from a mobile game developed by NetEase. I was able to extract the npk archives in other NetEase games, using offzip. They were compressed with zlib. This time it seems like the compression is something else. Hopefully it isn't too hard to see. I would appreciate some help with this.

Sample files : [http://www.mediafire.com/file/gtbmif2c9 ... Sample.rar](http://www.mediafire.com/file/gtbmif2c94tjcqr/NPKSample.rar)

Thanks.
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-20T03:30:24+00:00
- Post Title: NPK Archive Unpack

What's the game name? Have you tried comtype scanner already?
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-20T04:01:12+00:00
- Post Title: NPK Archive Unpack

I think it is called Forever 7th Capital in English. No, I haven't tried the comtype scanner. I will give it a try when I get back home.

From what I have seen I am leaning more towards lz4 compression, but I am not sure.

Thanks for your interest.
## Post #4
- Username: mykolag
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 19, 2011 7:22 pm
- Post datetime: 2019-08-22T12:29:56+00:00
- Post Title: NPK Archive Unpack

the NPX data is depends on FLAG (24 shift on NPX table)
 in case it's 0 -> no compression is used
 in case it's 1 -> compession zlib 
 in case it's 2 -> compression lz4

Let me know if You have a question(s)
