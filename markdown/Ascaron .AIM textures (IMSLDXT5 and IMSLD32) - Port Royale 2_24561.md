## Post #1
- Username: remotequack
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 14, 2021 4:10 pm
- Post datetime: 2021-10-02T17:23:38+00:00
- Post Title: Ascaron .AIM textures (IMSLDXT5 and IMSLD32) - Port Royale 2

Hello, I'm trying to read boat textures from Port Royale 2. 
I am pretty new to ripping models and texture but I managed to find out how the meshes are read with hex2obj in an old thread ([viewtopic.php?t=22299](https://forum.xentax.com/viewtopic.php?t=22299)) from this forum.   
I saw someone alreay asked how to extract .aim files a decade ago ([viewtopic.php?t=1978](https://forum.xentax.com/viewtopic.php?t=1978)) but I didn't find the reply very heplful and after searching for a long time I didn't find anything.

What I understood is that there are 2 types of "aim" texture formats for Port Royale 2 boats if you open them in a hex editor: 
IMSLDXT5 and IMSLD32. 
Boats use either one format or the other.
I think the first one could be easier since DXT5 is a common format but I have no clue for IMSLD32. Maybe SLD stands for something ?
I also assume it's little-endian and the width and height could be 4 bytes then 4 bytes after the "IMSLDXT5"/"IMSLD32" string (since I always find 512 and 512) and there might be 2 sizes after that for the image but i'm lost there and really not sure..




Capture.PNG (89.25 KiB) Viewed 35 times



If anyone wants to help I'm attaching samples of .aim and some corresponding meshes I converted:
[https://drive.google.com/file/d/1SAlcbL ... sp=sharing](https://drive.google.com/file/d/1SAlcbLZRURjA3vG_muSjnRz8WNYECPZV/view?usp=sharing)
