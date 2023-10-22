## Post #1
- Username: guranoa
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jun 02, 2023 10:53 pm
- Post datetime: 2023-08-16T18:05:54+00:00
- Post Title: CollarxMalice compressed character sprites

Hello (if anyone is even reading this topic) there's game called CollarxMalice the game uses a .tid file format for the textures while the backgrounds can be easily converted into a png using dds2png the same cannot be said about the chracter sprites first of all there compressed into a .CL3 wich you need to use a bms script to extract it after extracting it the actual .tid appears from the extracted .CL3 file putting the extracted .tid into dds2png gives me an error. Here's the sample: [https://mega.nz/file/lEAC1B7I#8vDbX96ey ... 74Pgmwu25c](https://mega.nz/file/lEAC1B7I#8vDbX96eyPMRmcxnhCPWgiLHsZGK8khWI74Pgmwu25c)

(If anyone responds i'll be happy).
## Post #2
- Username: piken
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 25, 2021 9:55 pm
- Post datetime: 2023-08-17T07:36:10+00:00
- Post Title: CollarxMalice compressed character sprites

I'm not familiar with dds2png or bms scripts, but I can at least confirm there are graphics in the file. It uses DXT5 (also called BC3) compression, which uses 4x4 blocks of alpha and b5g6r5 pixels. The texture is 2048x2048 and starts at 0x80:

[https://www.reedbeta.com/blog/understan ... c3-and-bc5](https://www.reedbeta.com/blog/understanding-bcn-texture-compression-formats/#bc2-bc3-and-bc5)
[https://learn.microsoft.com/en-us/windo ... ession#bc3](https://learn.microsoft.com/en-us/windows/win32/direct3d10/d3d10-graphics-programming-guide-resources-block-compression#bc3)

You can extract it using the Raw Texture Cooker by daemon1.
[CollarxMalice.jpg](https://xentaxbackup.github.io/file/24245_CollarxMalice.jpg)
## Post #3
- Username: guranoa
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jun 02, 2023 10:53 pm
- Post datetime: 2023-08-17T08:22:15+00:00
- Post Title: CollarxMalice compressed character sprites

Does rawtex support .tid files or did you converted into a dds file?
## Post #4
- Username: guranoa
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jun 02, 2023 10:53 pm
- Post datetime: 2023-08-17T08:56:30+00:00
- Post Title: CollarxMalice compressed character sprites

Dosen't extract in my case.
## Post #5
- Username: guranoa
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jun 02, 2023 10:53 pm
- Post datetime: 2023-08-17T09:51:07+00:00
- Post Title: CollarxMalice compressed character sprites

Can you try to extract it in rawtexcmd? Cause in my case it dosen't recongnize the file
[Screenshot_20230817-122224_1.jpg](https://xentaxbackup.github.io/file/24246_Screenshot_20230817-122224_1.jpg)
## Post #6
- Username: nudgenudgenudge
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Apr 06, 2016 11:31 am
- Post datetime: 2023-08-17T11:16:08+00:00
- Post Title: CollarxMalice compressed character sprites

This version of dds2png can convert that tid file to a png file.
[http://www.mediafire.com/file/j3jkhfobv ... 28.7z/file](http://www.mediafire.com/file/j3jkhfobvbc0swa/dds2png_20200828.7z/file)

This may be useful if you need to convert from dds to tid files.
[http://www.mediafire.com/file/mtkg8shu2 ... 28.7z/file](http://www.mediafire.com/file/mtkg8shu2qzmbw8/dds2tid_20200828.7z/file)
Compression formats supported by dds2tid are only dxt1(bc1), dxt3(bc2) and dxt5(bc3).
## Post #7
- Username: guranoa
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jun 02, 2023 10:53 pm
- Post datetime: 2023-08-17T14:07:53+00:00
- Post Title: CollarxMalice compressed character sprites

> Reply from nudgenudgenudge ↑Thu Aug 17, 2023 7:16 pm at Thu Aug 17, 2023 7:16 pm
>
> 
This version of dds2png can convert that tid file to a png file.
http://www.mediafire.com/file/j3jkhfobv ... 28.7z/file

This may be useful if you need to convert from dds to tid files.
http://www.mediafire.com/file/mtkg8shu2 ... 28.7z/file
Compression formats supported by dds2tid are only dxt1(bc1), dxt3(bc2) and dxt5(bc3).
Nah still dosen't work unless you change the name of the .tid file.
## Post #8
- Username: nudgenudgenudge
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Apr 06, 2016 11:31 am
- Post datetime: 2023-08-17T16:17:15+00:00
- Post Title: CollarxMalice compressed character sprites

The program works fine in my environment with Windows 10 22H2 and the language is Japanese.
So it seems that the problem is caused by the language setting of Windows and the character code used for the file name.
The name of the tid file looks strange, so maybe the file name changed when you extracted the tid file from cl3.

It won't help you solve the problem, but this is the tool I use to extract the files from the cl3 file.
[http://www.mediafire.com/file/hz0s2tajz ... 28.7z/file](http://www.mediafire.com/file/hz0s2tajz003ytn/cl3_tool_20200828.7z/file)

It might be a good idea to create a batch file that first changes the file name temporarily,
converts the tid file to a png file with dds2png,
and finally restores the original file name.
