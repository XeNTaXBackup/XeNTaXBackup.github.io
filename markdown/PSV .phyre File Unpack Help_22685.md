## Post #1
- Username: Maverick69
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 23, 2020 12:46 am
- Post datetime: 2020-09-13T13:57:17+00:00
- Post Title: PSV .phyre File Unpack Help

Hello everyone~
I extracted a PSV game and got the files inside VPK file.
However, i found that files are encrypted as .phyre type.
I look for the post who talks about how to decrypt those files and successfully unpack .dds.phyre texture files.

But I still cannot extract the 3D models after I spend 2 whole days to read and do the Hex2Obj tutorial.  

Would someone help me extract this 3D model ? (It propose can unpack a head model)
[http://www.mediafire.com/file/vb5uyalai ... 6.zip/file](http://www.mediafire.com/file/vb5uyalainh2f5g/hf0206.zip/file)
Please and Thanks.
## Post #2
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-09-13T18:20:05+00:00
- Post Title: PSV .phyre File Unpack Help

UVs are HF_UV



hf0206.dae.phyre.png (62.92 KiB) Viewed 182 times


What's the name of the game? Maybe someone has already made a tool for him.
## Post #3
- Username: Maverick69
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 23, 2020 12:46 am
- Post datetime: 2020-09-14T08:50:37+00:00
- Post Title: PSV .phyre File Unpack Help

> Reply from reh ↑Mon Sep 14, 2020 2:20 am at Mon Sep 14, 2020 2:20 am
>
> 
UVs are HF_UV
hf0206.dae.phyre.png
What's the name of the game? Maybe someone has already made a tool for him.

Thank you very much!!! Thank you!!!
I follow the data on your picture, i successfully extract the model.

However, the UV map cannot extract even I confirmed the input is correct for many time. 



test.png (54.23 KiB) Viewed 159 times


So, when texture input to the model, it becomes transparent. If it is possible, could you share the UV maps file for me?

These data is come from Japanese anime PSV game "mahouka koukou no rettousei out of order".
Unfortunately, I cannot found any unpack data from the Internet.

Although I hope that all the model can be extract, I cannot find any tool to convert those resources easily (Sorry for I really don't understand hex2obj).

Anyway, really thankful for your help! Thank you very much!
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-09-14T16:26:14+00:00
- Post Title: PSV .phyre File Unpack Help

Use HF_UV as reh said. (And remove the 0x before the uv address 19344.)
.



hf0206-dae-phyre.png (28.15 KiB) Viewed 139 times



btw: don't open multiple threads on the same issue, please
## Post #5
- Username: Maverick69
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 23, 2020 12:46 am
- Post datetime: 2020-09-14T17:27:30+00:00
- Post Title: PSV .phyre File Unpack Help

> Reply from shakotay2 ↑Tue Sep 15, 2020 12:26 am at Tue Sep 15, 2020 12:26 am
>
> 
Use HF_UV as reh said. (And remove the 0x before the uv address 19344.)
.
hf0206-dae-phyre.png

btw: don't open multiple threads on the same issue, please

Thank you for your remind and your tutorials material. I can get the UVs now.

Also, would you tell me how to load/combine the UVs into the Obj model? (I try to find the key word UV mapping/ UV wrapping/ UV load.... still cannot find the tutorial with steps that load the obj UV into the model)

Thank you very much. (Sorry for I am a rookie of 3D model. I am totally blank inside this area. )
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-09-14T17:57:51+00:00
- Post Title: PSV .phyre File Unpack Help

Use File/SaveAs mesh in hex2obj. The uvs are the lines with "vt" in the created wavefront obj file (usually in same folder as the model file).
## Post #7
- Username: Maverick69
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 23, 2020 12:46 am
- Post datetime: 2020-09-15T12:49:18+00:00
- Post Title: PSV .phyre File Unpack Help

> Reply from shakotay2 ↑Tue Sep 15, 2020 1:57 am at Tue Sep 15, 2020 1:57 am
>
> 
Use File/SaveAs mesh in hex2obj. The uvs are the lines with "vt" in the created wavefront obj file (usually in same folder as the model file).

Thank you very much~
