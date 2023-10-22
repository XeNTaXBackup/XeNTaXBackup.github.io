## Post #1
- Username: biplexive
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 19, 2015 6:40 am
- Post datetime: 2015-08-21T11:57:06+00:00
- Post Title: 3d models from quickbms

Hi, I have some models from unity asset bundles extracted from quickbms, although they are unusable and have no extension, they come up as TYPE_43 and I am using the unityextract.bms script, these models are originally .nif files, I have tried programs such as NifSkope, to no avail.


I don't know how to use them, and don't know much about model formats, and couldn't find any of the vert numbers using hex2obj, I hope someone can help.
Here are some sample files: [https://drive.google.com/file/d/0B_-GS3 ... sp=sharing](https://drive.google.com/file/d/0B_-GS3PsP41CTFVGVENKX2YyVE0/view?usp=sharing)


Thanks
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-21T14:43:09+00:00
- Post Title: 3d models from quickbms

> Reply from biplexive
>
> , and couldn't find any of the vert numbers using hex2obj, I hope someone can help.from MOB_Cerberus_0 I can say that the vertex data (at 0xC00 or 0xC14?) isn't easy to solve - maybe compressed.

There are 47 "frames", 64 bytes sized with floats, starting at 0x2c and a DWord face indices table (7467 FIs -> 1656 vertices) at 0xF2E8.
## Post #3
- Username: biplexive
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 19, 2015 6:40 am
- Post datetime: 2015-08-21T19:37:32+00:00
- Post Title: 3d models from quickbms

> Reply from shakotay2
>
> biplexive wrote:, and couldn't find any of the vert numbers using hex2obj, I hope someone can help.from MOB_Cerberus_0 I can say that the vertex data (at 0xC00 or 0xC14?) isn't easy to solve - maybe compressed.

There are 47 "frames", 64 bytes sized with floats, starting at 0x2c and a DWord face indices table (7467 FIs -> 1656 vertices) at 0xF2E8.

Thanks for the reply, I really appreciate it. I don't really understand it though. Have you been able to get anything to show up from any of the models?
