## Post #1
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2021-12-28T00:27:48+00:00
- Post Title: Port Royale 3 .mesh files

Hi, i try to convert the .mesh files to .obj oder similar usable format. I thought its possible with xnaLara mesh importer to blender, but it dont works with v2.79. After extract the .fuk files, i got .mesh .dds .tex .vbuf and .ibuf files. 

Anyone knows a tool to convert or can anaylize the mesh format?
[cannon0.zip](https://xentaxbackup.github.io/file/21473_cannon0.zip)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-28T07:06:46+00:00
- Post Title: Port Royale 3 .mesh files

Using AXE (with Multi Sources mode):



cannon0.png (231 KiB) Viewed 176 times
## Post #3
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-12-28T08:09:38+00:00
- Post Title: Port Royale 3 .mesh files

only for cannon0_baseshape.ibuf
[fmt_ibuf.zip](https://xentaxbackup.github.io/file/21516_fmt_ibuf.zip)
## Post #4
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2022-01-04T09:45:00+00:00
- Post Title: Port Royale 3 .mesh files

> Reply from Durik256 ↑Tue Dec 28, 2021 4:09 pm at Tue Dec 28, 2021 4:09 pm
>
> 

Thanks, but it doesnt work at all. For the most meshes i got this error:



So i attached another example, where i got the error too. Can you help me pls?
[bananabush0.zip](https://xentaxbackup.github.io/file/21511_bananabush0.zip)
## Post #5
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-04T15:31:43+00:00
- Post Title: Port Royale 3 .mesh files

> Reply from olli9000 ↑Tue Jan 04, 2022 5:45 pm at Tue Jan 04, 2022 5:45 pm
>
> 
but it doesnt work at all. For the most meshes i got this error:

i update plugin, but "bananabush0" dont work  
can you post more models?
## Post #6
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2022-01-04T21:52:11+00:00
- Post Title: Port Royale 3 .mesh files

> Reply from Durik256 ↑Tue Jan 04, 2022 11:31 pm at Tue Jan 04, 2022 11:31 pm
>
> 
can you post more models?

Yes sure, thank you.

[https://www.mediafire.com/file/ew5rme22 ... s.zip/file](https://www.mediafire.com/file/ew5rme22afno59j/pr3_models.zip/file)
## Post #7
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-05T03:38:25+00:00
- Post Title: Port Royale 3 .mesh files

> Reply from olli9000 ↑Wed Jan 05, 2022 5:52 am at Wed Jan 05, 2022 5:52 am
>
> 
Yes sure, thank you.
ok i fixed that. problem only with normals at block size 16

[fmt_ibuf.zip](https://xentaxbackup.github.io/file/21526_fmt_ibuf.zip)
## Post #8
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2022-01-12T03:00:42+00:00
- Post Title: Port Royale 3 .mesh files

Thank you very much! I was wondering to preview the textures in the view. I can see the mesh but no textures.. i got them as .dds files, but it would be very helpful to see it in noesis. Or iam missing a plugin for the .tex files?
## Post #9
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2022-01-12T08:15:01+00:00
- Post Title: Port Royale 3 .mesh files

I updated the script and solved the problem. DDS files should be in the same folder as the .ibuf file
[fmt_ibuf.zip](https://xentaxbackup.github.io/file/21587_fmt_ibuf.zip)
