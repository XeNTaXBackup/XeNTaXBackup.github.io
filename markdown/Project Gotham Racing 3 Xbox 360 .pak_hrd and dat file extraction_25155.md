## Post #1
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2022-03-16T13:00:09+00:00
- Post Title: Project Gotham Racing 3 Xbox 360 .pak_hrd and dat file extraction

Does anyone know how to extract .dat file after using the QuickBMS Script file to extract .pak_hrd file. I wanted to know whether both of them is a model or a texture. if anyone knows it pls I request to make a noesis script to preview the model.

archive format: [https://mega.nz/file/4KwiGDqD#0pyDuAiaX ... 7Zy1ozK9Mg](https://mega.nz/file/4KwiGDqD#0pyDuAiaXsVQW1QBivgCEtny3O2FUUDoV7Zy1ozK9Mg)
extracted file: [https://mega.nz/file/FfZHGYLA#gxd_uHDIj ... PronOd58S8](https://mega.nz/file/FfZHGYLA#gxd_uHDIj-n318K7hnV0GW4m_i_sDLzEFPronOd58S8)
## Post #2
- Username: gpktm
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 4:58 am
- Post datetime: 2022-08-27T02:28:54+00:00
- Post Title: Project Gotham Racing 3 Xbox 360 .pak_hrd and dat file extraction

Did you have any luck finding a solution for this one?
## Post #3
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2022-09-26T14:10:44+00:00
- Post Title: Project Gotham Racing 3 Xbox 360 .pak_hrd and dat file extraction

hey thx for the response for couple of month. Unfortunately, I don't have any luck on this content, sorry.
## Post #4
- Username: gpktm
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 4:58 am
- Post datetime: 2022-09-26T16:23:22+00:00
- Post Title: Project Gotham Racing 3 Xbox 360 .pak_hrd and dat file extraction

Ok, I see... I think I have found something. Do you have the VW Nardo as a pak_hrd file?
## Post #5
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2022-09-28T02:25:47+00:00
- Post Title: Project Gotham Racing 3 Xbox 360 .pak_hrd and dat file extraction

> Reply from gpktm ↑Tue Sep 27, 2022 12:23 am at Tue Sep 27, 2022 12:23 am
>
> 
Ok, I see... I think I have found something. Do you have the VW Nardo as a pak_hrd file?

Yes I have the entire game along with pak_hrd contents. I'll send you the VW Nardo file when I fire my laptop up
## Post #6
- Username: gpktm
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 4:58 am
- Post datetime: 2022-09-28T04:12:32+00:00
- Post Title: Project Gotham Racing 3 Xbox 360 .pak_hrd and dat file extraction

Excellent! Is a bit tedious process to extract the mesh but it can be done.
## Post #7
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2022-09-28T07:26:20+00:00
- Post Title: Project Gotham Racing 3 Xbox 360 .pak_hrd and dat file extraction

[https://mega.nz/file/lToR3IAT#T5ThRsTeT ... V6pCjghV6k](https://mega.nz/file/lToR3IAT#T5ThRsTeTeFnOYEwjcALVQLbg3086_xNGV6pCjghV6k)

file for W12 Nardo pak_hrd
## Post #8
- Username: gpktm
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 4:58 am
- Post datetime: 2022-10-02T11:17:07+00:00
- Post Title: Project Gotham Racing 3 Xbox 360 .pak_hrd and dat file extraction

I will post the process in steps because I don't have much time at the moment to do the whole process in a one-off post.

So, let's begin...

1. You will need the Make_H20 extractor from @Shakotay2 because the QuickBMS doesn't extract the file properly. You can find the extractor here 
[https://drive.google.com/file/d/1_IDJzf ... sp=sharing](https://drive.google.com/file/d/1_IDJzfAouRBggmY2xVTzy1jUXDx-CpJM/view?usp=sharing)

2. Follow the instructions found inside the txt file. Once you extract the content you will end up with dozens of folders containing dat files.


3. Get yourself a program showing the size of each folder so you can find where the biggest chunk of data is contained. I am using "Folder Size" by Brio, but there are many other alternatives out there. [https://alternativeto.net/software/folder-size/](https://alternativeto.net/software/folder-size/)


4. Folder Size is showing that the largest data is contained in block 96. But... when I opened block 96, it seems that there are many individual parts in there, by examining more files before the Nardo W12, I know that these are parts are mostly parts that I have found before. My guess is that is a lower LOD model or maybe a 3d model with fewer parts (eg, when the car is an opponent). So the next biggest size folder which includes only one file inside (there are actually two files but they are a pair, I will come to that later) is the folder Block_48.


5. So opening the folder Block_48 (as you can see in the image above) there are two files. Usually, in 3d game files, there is only one file that includes both the vertices coordinates and the polygons. Unfortunately, we are dealing with one of the shittiest situations where there is one file containing the vertices coordinates and another file containing the polygons.

6. Next thing you will need is the software Model Researcher (it is free). Download it, and have a quick read about how it works to get a rough idea of what we will do next. [https://mr.game-viewer.org/](https://mr.game-viewer.org/)

7. Once you open Model Researcher, load the file 00000005.dat found inside the Block_48 folder. This is the file containing the coordinates of the vertices. The way it usually works, the files containing just a number in their name are the files with the vertices and the files with a complex combination of letter and numbers is the file with the polygons eg 0003d85e.dat

8. Once you load the 00000005.dat file, set the following settings in the Model Researcher
Type: Short_signed
Padding: 22
Byte Order: Bing Endian
Invert: X



9. A quick explanation of the settings... [YOU CAN SKIP THIS STEP IF YOU WANT TO GO STRAIGHT TO THE POINT]
Offset: How many bytes do we skip at the beginning before we start reading the file
Type: I don't know exactly
Count: How many steps the software should read
Format: how to translate the reading into coordinates
Padding: how big is each step before reading the next coordinate
Pad Inter: if there is any gap between bytes or the reading is continuous
Play with the settings while you are in the Hex View tab so you can have a better understanding.

Don't ask me how I've found the correct settings because I did not. The settings were discovered by @Shakotay2 and he found them by experience. Luckily, the settings remain almost the same throughout the whole process, apart from the padding being either 22 or 14.

To give a short explanation, what we are doing now, is we are telling the software how to translate the hex into coordinates. Each vertex is located in an XYZ space. The coordinates are sometimes either a single byte per coordinate or a pair or more. In our case, every pair of bytes (this is a pair of a HEX number) represents a number in the X, Y or Z space.

For example, go to the tab "Hex View" and after that, increase the count number to 1. You will see the first six bytes E3 FF 06 85 EC 5F (each byte is a pair of hex numbers as we previously said) is being highlighted. This represents a single point (Vertex) in space.


For example...
E3FF = X location
0685 = Y location
EC5F = Z location

I am not sure if I have translated the values correct, because this actually has to do with the settings and in which order the computer reads the bytes. For example, I know that Big Endian has something to do with inverted reading starting from the end. I am not a software engineer or anyone with programming knowledge, this is just my interpretation of how it works.

So going now to the "Text" tab and clicking the "Print" button found on the left, you will see that three coordinates have been generated and going to the "3D View" tab and clicking the "Render", you will now see that point in space.


10. Now start populating the readings with more steps by increasing the "Count" value to generate more points. The maximum you can go is 17655. Once you input the number, press "Render" and you will see all the points generated in space, which looks like an interior of the W12.



That's all for now. Once I find some more free time I will come back to this...
## Post #9
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2022-10-03T07:18:12+00:00
- Post Title: Project Gotham Racing 3 Xbox 360 .pak_hrd and dat file extraction

> Reply from gpktm ↑Sun Oct 02, 2022 7:17 pm at Sun Oct 02, 2022 7:17 pm
>
> 
1. You will need the Make_H20 extractor from @Shakotay2 because the QuickBMS doesn't extract the file properly. You can find the extractor here 
https://drive.google.com/file/d/1_IDJzf ... sp=sharing
Thx for that. but for downloading Make_H20 extractor that you gave me the link, I'm unable to do it since it requires me an access to this. can u remove the access blockage so that I can download it easily?

> Reply from gpktm ↑Sun Oct 02, 2022 7:17 pm at Sun Oct 02, 2022 7:17 pm
>
> 
That's all for now. Once I find some more free time I will come back to this...
no worries, take your time on your process, because I'm so pleased that you have found something anyway. lmk if you have found something further later.
## Post #10
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-01-15T03:55:05+00:00
- Post Title: Project Gotham Racing 3 Xbox 360 .pak_hrd and dat file extraction

it's been a while since this topic is dead. have you found anything interesting?
## Post #11
- Username: Nenkai
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jul 30, 2016 7:29 am
- Post datetime: 2023-06-06T00:10:17+00:00
- Post Title: Project Gotham Racing 3 Xbox 360 .pak_hrd and dat file extraction

If there's still any interest of any kind (i.e modding), i've documented the format. It was able to parse some car model files entirely.
[https://github.com/Nenkai/010GameTempla ... pak_hrd.bt](https://github.com/Nenkai/010GameTemplates/blob/main/Project%20Gotham%20Racing/PGR_CarModel_pak_hrd.bt)
## Post #12
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-06-06T13:21:17+00:00
- Post Title: Project Gotham Racing 3 Xbox 360 .pak_hrd and dat file extraction

> Reply from Nenkai ↑Tue Jun 06, 2023 8:10 am at Tue Jun 06, 2023 8:10 am
>
> 
If there's still any interest of any kind (i.e modding), i've documented the format. It was able to parse some car model files entirely.
https://github.com/Nenkai/010GameTempla ... pak_hrd.bt

is it a plugin or something? not about modding tho but just wanted to extract car models and textures with materials
