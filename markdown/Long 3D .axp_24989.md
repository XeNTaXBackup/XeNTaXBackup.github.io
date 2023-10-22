## Post #1
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-25T23:03:30+00:00
- Post Title: Long 3D .axp

Hello! there is one script (thanks to aluigi) that could extract the data of the Model5.axp doing a tweak in certain line. 

> Reply from aluigi
>
> 
That AXPK format is covered by this script:
http://aluigi.org/bms/new_dragon_eight.bms

But there is a problem with the dumping of the files because they are recognized as those base64 files used in another sample.
Long story short, replace "clog NAME OFFSET SIZE SIZE" at line 90 with "log NAME OFFSET SIZE"

Anyways I also replaced the line 87 "clog NAME OFFSET SIZE XSIZE" with "log NAME OFFSET SIZE", with this change I was able to decompress the Material3.axp, but still don't sure about it, because the decompressed images have less size than the compressed. 

When decompressing the Material3.axp I get .dds files but without names, this is workable, the issue is that when decompressing the Model5.axp, the files are .dat and have no name, besides they have no correlation with the images and seems that some .dat files are still compressed or encrypted, so I would like know if there is a way to get the names or types of files to get the meshes! I could upload all the game if is necessary, around 4 gb zipped. Thanks for read!  

Model5.axp
[https://www.mediafire.com/file/46n03fvw ... 5.axp/file](https://www.mediafire.com/file/46n03fvwc9t5tzc/Model5.axp/file)

Material3.axp
[https://www.mediafire.com/file/2wrxgdqc ... 3.axp/file](https://www.mediafire.com/file/2wrxgdqc2hpstjb/Material3.axp/file)
