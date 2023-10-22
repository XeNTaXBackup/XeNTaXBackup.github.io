## Post #1
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-02-20T21:26:04+00:00
- Post Title: Unreal Engine Mesh Format

Hi, could somebody help me to get model out of this file with hex2obj please? 
https://mega.nz/#!18FW3CiS!ZxFaAgQ25pzs ... fFw6VXK2YA

Btw, i cant use umodel with that model.
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-02-20T22:06:51+00:00
- Post Title: Unreal Engine Mesh Format

Edit : 
Image scaling is weird for embedded images. Leaving a direct link to image : [https://i.imgur.com/E9tABZN.png](https://i.imgur.com/E9tABZN.png)
## Post #3
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-02-22T19:23:03+00:00
- Post Title: Unreal Engine Mesh Format

> Reply from akderebur ↑Thu Feb 21, 2019 6:06 am at Thu Feb 21, 2019 6:06 am
>
> 

Thanks for help, but can i ask how did you found FVFsize values and uvpos?
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-02-22T20:20:52+00:00
- Post Title: Unreal Engine Mesh Format

I can't say much for index/vertex/uv start positions. I just scroll down in hex editor and look for what might be index/vertex buffer. They were easy to spot in this sample. There might be offsets inside the file pointing to these data, and you would ideally find the data based on that, if you are going for a proper tool/script.

For the block size (FVFsize) you can usually look for a recurring pattern in the vertex buffer, if there is any. You can see that "FF 00 00 00" appears every 32 bytes, so I concluded FVFSize is 32.
