## Post #1
- Username: forarkorder
- Rank: n00b
- Number of posts: 15
- Joined date: Thu May 06, 2021 10:34 pm
- Post datetime: 2021-05-09T07:11:05+00:00
- Post Title: Is it possible to use model researcher or hex2obj? / Danball Senki Chou Custom 3DS

I need help or suggestions to extract mesh parts from Danball Senki Chou Custom 3DS. I've never seen this type of format before! 
I think these files are mesh. If so, can I use hex2obj or model researcher? 

Here's some sample.
[https://www.mediafire.com/file/a1lroa9j ... s.zip/file](https://www.mediafire.com/file/a1lroa9jgb79vo1/DA2File_samples.zip/file)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-05-09T09:19:59+00:00
- Post Title: Is it possible to use model researcher or hex2obj? / Danball Senki Chou Custom 3DS

Most data is compressed. Use this BMS script to unpack the rif container.


 rifUnpacker.zip
(562 Bytes) Downloaded 14 times



Then use the following script to decompress the resulting slz files:
[http://aluigi.altervista.org/bms/slz.bms](http://aluigi.altervista.org/bms/slz.bms)
## Post #3
- Username: forarkorder
- Rank: n00b
- Number of posts: 15
- Joined date: Thu May 06, 2021 10:34 pm
- Post datetime: 2021-05-09T10:31:16+00:00
- Post Title: Is it possible to use model researcher or hex2obj? / Danball Senki Chou Custom 3DS

As a result, Yes, I got unslz file by using two bms script.
But still I don't know how use extracted unslz file   Is it can convert 3d model file format?
Attachments is mesh file of lbxp32044.
Thanks for your help!
[MESH_0.zip](https://xentaxbackup.github.io/file/20086_MESH_0.zip)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-09T12:24:42+00:00
- Post Title: Is it possible to use model researcher or hex2obj? / Danball Senki Chou Custom 3DS

Mesh format appears to be simple, why not try it out?
.



MESH_0-unslz.png (86.52 KiB) Viewed 141 times
## Post #5
- Username: forarkorder
- Rank: n00b
- Number of posts: 15
- Joined date: Thu May 06, 2021 10:34 pm
- Post datetime: 2021-05-11T01:04:34+00:00
- Post Title: Is it possible to use model researcher or hex2obj? / Danball Senki Chou Custom 3DS

Wow It's so cool! But, I Don't know exactly how to find start address. I've found it by color of hex, is it right method...?
Is there any pattern? or rule?

+ What is UV POS? I entered some number, but I can only make a UV map at 36
[hexworkshop.PNG](https://xentaxbackup.github.io/file/20103_hexworkshop.PNG)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-11T07:02:33+00:00
- Post Title: Is it possible to use model researcher or hex2obj? / Danball Senki Chou Custom 3DS

> Reply from forarkorder ↑Tue May 11, 2021 9:04 am at Tue May 11, 2021 9:04 am
>
> 
Wow It's so cool! But, I Don't know exactly how to find start address. I've found it by color of hex, is it right method...?Usually not - but depends on what the colors mean.

> Is there any pattern? or rule?Pattern for finding start of face indices block is 0000 0100 0200, for example.
For other rules read the tutorial ('tut' button in hex2obj).
You might read Bigchillghost's tutorial, too (view link in my sig).

> + What is UV POS? I entered some number, but I can only make a UV map at 36It's where the uv data is located in FVFblock (flexible vertex format, FVF, see tut).
(You will need a deeper understanding instead of just entering random numbers.  )
## Post #7
- Username: forarkorder
- Rank: n00b
- Number of posts: 15
- Joined date: Thu May 06, 2021 10:34 pm
- Post datetime: 2021-05-13T09:37:54+00:00
- Post Title: Is it possible to use model researcher or hex2obj? / Danball Senki Chou Custom 3DS

Thank you!
## Post #8
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2021-05-16T16:20:36+00:00
- Post Title: Is it possible to use model researcher or hex2obj? / Danball Senki Chou Custom 3DS

> Reply from forarkorder ↑Tue May 11, 2021 9:04 am at Tue May 11, 2021 9:04 am
>
> 
Wow It's so cool! But, I Don't know exactly how to find start address. I've found it by color of hex, is it right method...?
Is there any pattern? or rule?

+ What is UV POS? I entered some number, but I can only make a UV map at 36
What do the colors mean? What is the name of this program?
## Post #9
- Username: forarkorder
- Rank: n00b
- Number of posts: 15
- Joined date: Thu May 06, 2021 10:34 pm
- Post datetime: 2021-05-17T01:23:28+00:00
- Post Title: Is it possible to use model researcher or hex2obj? / Danball Senki Chou Custom 3DS

> Reply from Lazov ↑Mon May 17, 2021 12:20 am at Mon May 17, 2021 12:20 am
>
> 
forarkorder wrote: ↑Tue May 11, 2021 9:04 am
Wow It's so cool! But, I Don't know exactly how to find start address. I've found it by color of hex, is it right method...?
Is there any pattern? or rule?

+ What is UV POS? I entered some number, but I can only make a UV map at 36

What do the colors mean? What is the name of this program?

The program's name is Hex Workshop. When you using data visualizer in hex workshop, you can see colors of hex.

You can find color range in this link.
[http://www.hexworkshop.com/onlinehelp/6 ... alizer.htm](http://www.hexworkshop.com/onlinehelp/650/html/Data_Visualizer.htm)
