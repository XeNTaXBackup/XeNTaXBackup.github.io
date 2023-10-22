## Post #1
- Username: Shakester
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 20, 2022 5:26 pm
- Post datetime: 2022-05-20T09:33:01+00:00
- Post Title: MHA: The Strongest Hero .axmd format

Looking for some help finding a tool to convert these .axmd files or import them into Blender. They were ripped from My Hero Academia: The Strongest Hero using Spiritovod's QuickBMS script. I've attached an example file in the .zip below. If someone can help me out, thank you in advance.
[AXMD Models.zip](https://xentaxbackup.github.io/file/22240_AXMD Models.zip)
## Post #2
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-05-20T11:04:21+00:00
- Post Title: MHA: The Strongest Hero .axmd format

Actually this sample is bad, as it contains only single submesh, while format in general is aimed for multiple submeshes. Here are better samples: [link](https://drive.google.com/file/d/14xoqoe-_fTo6nZyejpJjRBFak8BFLcPS/view?usp=sharing)

Also, script for extraction is available in [this topic](https://forum.xentax.com/viewtopic.php?f=10&t=25181).
## Post #3
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-05-20T13:07:29+00:00
- Post Title: MHA: The Strongest Hero .axmd format

> Reply from Spiritovod ↑Fri May 20, 2022 7:04 pm at Fri May 20, 2022 7:04 pm
>
> 
Here are better samples
edit: (fix (one) incorrect index in faces)

[fmt_axmd.zip](https://xentaxbackup.github.io/file/22242_fmt_axmd.zip)
## Post #4
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-05-20T20:25:43+00:00
- Post Title: MHA: The Strongest Hero .axmd format

> Reply from Shakester ↑Fri May 20, 2022 5:33 pm at Fri May 20, 2022 5:33 pm
>
> 
.axmd files
update: UVs and Bones (weigth too).


edit:
if error :"OverflowError: can't convert negative int to unsigned"
replace line 78 'i = bs.readShort()' to 'i = bs.readUShort()'
[fmt_axmd_v2.zip](https://xentaxbackup.github.io/file/22243_fmt_axmd_v2.zip)
## Post #5
- Username: Shakester
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 20, 2022 5:26 pm
- Post datetime: 2022-05-20T20:56:57+00:00
- Post Title: MHA: The Strongest Hero .axmd format

> Reply from Durik256 ↑Sat May 21, 2022 4:25 am at Sat May 21, 2022 4:25 am
>
> 
Shakester wrote: ↑Fri May 20, 2022 5:33 pm
.axmd files

update: UVs and Bones (weigth too).

You're the GOAT dude, thanks an absolute ton.
