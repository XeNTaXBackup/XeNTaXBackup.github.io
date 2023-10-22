## Post #1
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-27T05:51:58+00:00
- Post Title: Kuon PS2 models .vmd

Hi, I am trying to extract models from this game. These models are made with a A LOT of submeshes, I did not find faces data so probably are autogenerated... This is my research so far, maybe this helps:




All submeshes have the same format but a lot of them don't have the pointer to next submesh, bytes are 00 00 00 00. That is so weird..

I don't know what is at 0x405C(in first submesh), that value changes in other submeshes, I found these different values: 30 02 00 00, 70 02 00 00, 
B0 02 00 00, 30 03 00 00, 70 03 00 00 and B0 03 00 00.

Here is a sample:


 c001.rar
(81.32 KiB) Downloaded 17 times



Thanks!
## Post #2
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-27T07:31:45+00:00
- Post Title: Kuon PS2 models .vmd

OK, in first submesh header at 0x405C it is a pointer. There is a small table there, maybe for textures or materials. 

About  submesh header with no pointer to next submesh, you can find an example at 0x5A30, like I said there are a lot of submesh headers like that and I still don't know why...
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-27T11:41:39+00:00
- Post Title: Kuon PS2 models .vmd

Maybe groups of objects? The next to start at 0x5C90.  01 00, so first sub mesh of that group, probably.

Sub meshes of first group look like so:
.



vmd-10.png (56.25 KiB) Viewed 86 times
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-27T14:52:56+00:00
- Post Title: Kuon PS2 models .vmd

2nd group, 16 sub meshes:
.



vmd_2nd_group.png (60.12 KiB) Viewed 78 times
## Post #5
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-27T19:22:14+00:00
- Post Title: Kuon PS2 models .vmd

> Reply from shakotay2 ↑Thu Apr 27, 2023 7:41 pm at Thu Apr 27, 2023 7:41 pm
>
> 
Maybe groups of objects? The next to start at 0x5C90.  01 00, so first sub mesh of that group, probably.

So 01 00 is the start of a new group?, that could be true. That means the last submesh of a group does not have pointer to next submesh. And you can find individual submeshes with 01 00, some of those don't have the pointer to next submesh, so those don't belong to a group. For example at 0x8670, there are about 8 submeshes with 01 00 with no pointer to next submesh.

Well, it looks like that, I am stilll not really sure, lol