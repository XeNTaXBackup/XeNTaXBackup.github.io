## Post #1
- Username: Wizzdome13
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 02, 2021 9:14 pm
- Post datetime: 2021-11-04T10:58:24+00:00
- Post Title: Need Help with Converting Models to obj

Hey guys, so im completely new into the whole 3d data reversing thing and right now im running into some issue and would like to have some help in trying to figure this out. I want to try and convert this model and the rest of the other weapon models later on from the game "Call of Duty Online" to obj but so far i have yet to figure out exactly where to even start as im not getting anywhere.

I attached below what i wanna try and convert. If someone could help me with this please let me know as i also want to try and convert the other weapon models, thanks.
[p90.rar](https://xentaxbackup.github.io/file/21141_p90.rar)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-04T12:08:49+00:00
- Post Title: Need Help with Converting Models to obj

> Reply from Wizzdome13 ↑Thu Nov 04, 2021 6:58 pm at Thu Nov 04, 2021 6:58 pm
>
> I want to try and convert this model ... to obj
Will FBX do? 



wea_p90_p90_vmgun10.png (140.42 KiB) Viewed 80 times
## Post #3
- Username: Wizzdome13
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 02, 2021 9:14 pm
- Post datetime: 2021-11-04T12:56:05+00:00
- Post Title: Need Help with Converting Models to obj

Thank you so much for the help!   May i ask how you were able to find each coords? And i hope its not too much to ask if you could send over the converted models.
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-04T13:52:43+00:00
- Post Title: Need Help with Converting Models to obj

> Reply from Wizzdome13 ↑Thu Nov 04, 2021 8:56 pm at Thu Nov 04, 2021 8:56 pm
>
> 
May i ask how you were able to find each coords? And i hope its not too much to ask if you could send over the converted models.
For positions and texcoords, it's quite intuitive though. For normals and tangents, it's more of trail and error. Once you tried to load the entire vertex block at a go, you'll notice that there're sub-meshes involved. The vertex and the face count of the 1st mesh is respectively at address 0x146 and 0x14A, and those of the 2nd at address 0x152 and 0x156. There're some redundant records ahead at address 0x9E where each entry takes 0x54 bytes. You can also find the start address of the vertex chunk at address 0x34, the one of the index chunk at address 0x20. That should be enough for a start.

> Reply from Wizzdome13 ↑Thu Nov 04, 2021 8:56 pm at Thu Nov 04, 2021 8:56 pm
>
> 
And i hope its not too much to ask if you could send over the converted models.
For the 1st mesh, you can just use the same setting of parameters as the screenshot from my previous post shown. Meanwhile here's the PLC file for "wea_p90_p90_vmgun10":


 wea_p90_p90_vmgun10.zip
(739 Bytes) Downloaded 11 times


Just place it along with the model file and open it through the "Open" button within the "Parameter List" group box in AXE. Then you can export the model by navigating to File > Export from List.
## Post #5
- Username: Wizzdome13
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 02, 2021 9:14 pm
- Post datetime: 2021-11-06T06:37:22+00:00
- Post Title: Need Help with Converting Models to obj

Thank you so much! I appreciate all the help, but i got a problem again... So I was able to convert most of the weapons properly, but I was still having issues with the "mag_default_p90ncm_vmgun10" model apparently. No idea if this issue is with the wrong address for Normals, Texcoords or I got the wrong address in for the Vertices.
[magazinep90.PNG](https://xentaxbackup.github.io/file/21154_magazinep90.PNG)
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-06T12:43:36+00:00
- Post Title: Need Help with Converting Models to obj

What params were you using? There're two meshes in the file, which you should be able to extract by following the same routine.
## Post #7
- Username: Wizzdome13
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 02, 2021 9:14 pm
- Post datetime: 2021-11-06T21:31:26+00:00
- Post Title: Need Help with Converting Models to obj

> Reply from Bigchillghost ↑Sat Nov 06, 2021 8:43 pm at Sat Nov 06, 2021 8:43 pm
>
> 
What params were you using? There're two meshes in the file, which you should be able to extract by following the same routine. I tried both params but this was a different model file so i had to change up the addresses since they started on a different offset. I had the relative address at 0x164 and the vertex index address at 0xAF44

[](https://ibb.co/N92J5dk)

[](https://ibb.co/Y8GnFvG)
[mag_default_p90ncm_vmgun10.rar](https://xentaxbackup.github.io/file/21172_mag_default_p90ncm_vmgun10.rar)
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-07T03:00:20+00:00
- Post Title: Need Help with Converting Models to obj

> Reply from Wizzdome13 ↑Sun Nov 07, 2021 5:31 am at Sun Nov 07, 2021 5:31 am
>
> I tried both params
What both params? 

> Reply from Wizzdome13 ↑Sun Nov 07, 2021 5:31 am at Sun Nov 07, 2021 5:31 am
>
> but this was a different model file so i had to change up the addresses since they started on a different offset.
That's what it's all about: changing the params according to the file you're working on! And since all samples you provided share the same vertex layout, all you have to change are the relative address of the vertices, the address of the vertex indices, and the counts of the vertices and the indices. 

> Reply from Wizzdome13 ↑Sun Nov 07, 2021 5:31 am at Sun Nov 07, 2021 5:31 am
>
> I had the relative address at 0x164 and the vertex index address at 0xAF44
The problem is not about the addresses, but the counts you used. You should be seeing them in front of the vertex data chunk. Load the params of the two meshes from the PLC file I previously provided, check these counts within the hex editor, and try to gain a sense of what I wrote here:

> Reply from Bigchillghost ↑Thu Nov 04, 2021 9:52 pm at Thu Nov 04, 2021 9:52 pm
>
> Once you tried to load the entire vertex block at a go, you'll notice that there're sub-meshes involved. The vertex and the face count of the 1st mesh is respectively at address 0x146 and 0x14A, and those of the 2nd at address 0x152 and 0x156.
