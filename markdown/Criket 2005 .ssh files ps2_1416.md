## Post #1
- Username: maddy
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 29, 2005 4:50 am
- Post datetime: 2005-07-28T21:05:11+00:00
- Post Title: Criket 2005 .ssh files ps2???

hi,  any one can pls help me , i want a .ssh extractor / plugin , its a graphic file for Ea sports Criket 2005 but i dont know how to edit it , someone please help me. 
 have a look at it pls it was a compressed file i have decompressed it
[ac80500b90e06f511547cc8023ef90ed.rar](https://xentaxbackup.github.io/file/387_ac80500b90e06f511547cc8023ef90ed.rar)
## Post #2
- Username: maddy
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 29, 2005 4:50 am
- Post datetime: 2005-07-30T06:11:08+00:00
- Post Title: Criket 2005 .ssh files ps2???

hey, any one ........................pls help
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-30T08:48:04+00:00
- Post Title: Criket 2005 .ssh files ps2???

Have you checked these

SHP  	File format used by some programs for 3D modeling of multipart interactive triangle models
SHP 	3D Studio (DOS) shapes file
SHP 	Bitmap Picture; PrintMaster Icon Library
## Post #4
- Username: maddy
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 29, 2005 4:50 am
- Post datetime: 2005-07-30T16:00:42+00:00
- Post Title: Criket 2005 .ssh files ps2???

thnx for ur reply but i dnt want .shp i want a .ssh extractor/image viewer.
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-30T16:04:50+00:00
- Post Title: Criket 2005 .ssh files ps2???

Yes, well, if you open a .shh fiel in a hex editor you'll notice the SHPSP5 header. Shape. SHP
## Post #6
- Username: maddy
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 29, 2005 4:50 am
- Post datetime: 2005-07-30T19:28:59+00:00
- Post Title: Criket 2005 .ssh files ps2???

but i dont know anything about coding adn scripts so pls help me i want it real bad , pls make some kind of extracter/image editor, viewer for .ssh files , i ll be thankfull to u.
## Post #7
- Username: maddy
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 29, 2005 4:50 am
- Post datetime: 2005-08-01T16:02:15+00:00
- Post Title: Criket 2005 .ssh files ps2???

any one pls.......... Help.
## Post #8
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-08-01T21:28:24+00:00
- Post Title: Criket 2005 .ssh files ps2???

Has decided to disassemble this format... At everyone SSH archive displacement of files a miscellaneous.. I here without am strong .. Sorry
## Post #9
- Username: maddy
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 29, 2005 4:50 am
- Post datetime: 2005-08-02T11:46:34+00:00
- Post Title: Criket 2005 .ssh files ps2???

hey man what r u saying i cant understand,
## Post #10
- Username: maddy
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 29, 2005 4:50 am
- Post datetime: 2005-08-02T11:50:33+00:00
- Post Title: Criket 2005 .ssh files ps2???

in Ea sports Cricket 2005 pc version they use .fsh files for graphics/images/kits...  and in ps2 version intead of using .fsh they use .ssh archive files,  guys pls help.....................
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-02T11:59:53+00:00
- Post Title: Criket 2005 .ssh files ps2???

He says he tried to dissassemble the format (to figure it out). He noticed the individual images in the SSH files were not saved in some logical order (or at least he could not find out how if there was some logic). He then apologizes for not being able to help. 

Also, the .SSH files can be anything, and it takes some time to discover the true nature of these files. Time is expensive, as we will have to spend it on our daily jobs. Remember, it's just a hobby for us. We're not paid to be able to work full-time on time-consuming problems. And sometimes we can't work it out, especially since we don't have all of these games and executables ourselves.
## Post #12
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-08-02T14:01:23+00:00
- Post Title: Criket 2005 .ssh files ps2???

Hi guys,

I have had a bit of a look at it, but I can't really tell how the pixel data is stored - unfortunately I havn't looked at images much before so I don't really know if this is a common pixel-storage format or anything.

Anyway, the format is either an image (most probable) or some other 3D-related item - I conclude this because of the EAGL description tag in the file which indicates the 3D modelling language similar to OpenGL which was developed by Electonic Arts to be totally console-independant, which is why their games can usually be released on PC, PS2, XBox etc all at the same time.

Assuming it is an image, here is the format...

```
| EA Cricket 2005 (PS2) *.ssh |
+-----------------------------+

4 - Header (SHPS)
4 - File Length
4 - Version? (1)
4 - File Code (G359)
4 - Filename (batt)
4 - Header Size? (48)
4 - Group Name? (Buy )
4 - ERTS Header (ERTS)
16 - null
4 - Decompressed Image Size?
2 - Image Width/Height
2 - Image Width/Height
4 - null
4 - Unknown (8192)

X - Image Data (up to fileLength-256)

4 - EAGL Header (EAGL)
236 - Description (240 metal bin attachment for runtime texture management) (null to fill)
4 - Unknown (112)
4 - Filename (batt)
8 - null
```


I thought it may have just been an improvement on the FSH image format that EA have used for many years, but it appears to me after some research that this is not the case.

Sorry, not sure how much use I can be 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #13
- Username: maddy
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 29, 2005 4:50 am
- Post datetime: 2005-08-02T18:37:24+00:00
- Post Title: Criket 2005 .ssh files ps2???

im am sorry mr mouse to being impatient , if u guys can find some way to edit the .ssh file pls post it here , ill be waiting  for ur reply 
 & thanx for ur efforts.
## Post #14
- Username: maddy
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 29, 2005 4:50 am
- Post datetime: 2005-08-08T14:40:07+00:00
- Post Title: Criket 2005 .ssh files ps2???

guys any progress.......
## Post #15
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-08-08T21:06:00+00:00
- Post Title: Criket 2005 .ssh files ps2???

Give them time, I've seen a month go by before they had time to work on a format, or a way to edit it...
## Post #16
- Username: maddy
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 29, 2005 4:50 am
- Post datetime: 2005-08-22T20:40:04+00:00
- Post Title: 

any progress guys....... bye the way in ps2 they use .ssh files for graphics and in the pc version they use .fsh file for graphics , so i m attaching the .fsh (pc version)file which is same as  .ssh(previous attachment ,ps2 version) , might be helpfull.
[ac80500b90e06f511547cc8023ef90ed.rar](https://xentaxbackup.github.io/file/406_ac80500b90e06f511547cc8023ef90ed.rar)
## Post #17
- Username: maddy
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 29, 2005 4:50 am
- Post datetime: 2005-08-31T20:50:31+00:00
- Post Title: 

is anyone trying... pls help me, pls let me know.
## Post #18
- Username: maddy
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 29, 2005 4:50 am
- Post datetime: 2005-09-30T19:45:50+00:00
- Post Title: 

hi, has anyone found the solution, i need it pls help me, i'll be waiting.
## Post #19
- Username: mysterio
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 11, 2006 3:57 am
- Post datetime: 2006-06-11T18:16:12+00:00
- Post Title: 

Its been over a year now, I can't believe that this .ssh file can't be cracked!
## Post #20
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2009-10-24T08:53:56+00:00
- Post Title: 

Hi! Sorry for my bad english, im from Poland.

I try to open this files from FIFA STREET 1 for PS2. In hex editor i changed the header SHPS to SHPI because SHPI are *.fsh file for PC for EA games. I extracted the 0000.BIN file with fshtool. Its compressed. After delete in hex editor "eagl240 metal bin bla bla bla' i opened this file in IrfanView with raw options. And i got this(posted in attachments). Its visible game logo, but has bad colours. Any help? Sorry for my bad English.
[0000.jpg](https://xentaxbackup.github.io/file/2475_0000.jpg)
## Post #21
- Username: Max Peters
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 25, 2009 4:42 am
- Post datetime: 2009-10-25T02:22:10+00:00
- Post Title: 

Hey man, I just saw your post and this is what I've been searching for for ages. Can you please give me a detailed summary of what you did to extract that and can you please extract from this file that I have attached. Should it be compressed or decompressed? Anyway its from Fifa 10. I have decompressed it. Thanks man. If this works out, we might be able to mod the ps2 for EA games.
[t21__-53_2_4.rar](https://xentaxbackup.github.io/file/2479_t21__-53_2_4.rar)
## Post #22
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2009-10-25T07:23:40+00:00
- Post Title: 

Thanks for reply  Sorry for my bad english.

1. Change header in hex editor from SHPS to SHPI
2. Extract this file with fshtool.exe
3. Open the 0000.BIN with hex editor and delete data from "EAGL240 metal bin attachment for runtime" to end of file. Save.
4. Open this file with irfan view with raw options
5. Thats All.

I tried to open file in your attachment and i get this:
It looks like face texture. The settings for this file : 128x64/8bit greyscale

```
TXLY,tp01,1,0,256,128,0x0481fa54........
```

This is end of this file. Maybe is size of image (256x128) and offset (0x0481fa54) but file is too small for 256x128. Maybe is one more time compressed?

Thats all from me. Sorry for my bad english, maybe you understand.
[file.jpg](https://xentaxbackup.github.io/file/2481_file.jpg)
