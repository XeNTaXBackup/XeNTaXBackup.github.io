## Post #1
- Username: xxnewfolderxx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 26, 2006 11:37 pm
- Post datetime: 2006-05-26T15:53:58+00:00
- Post Title: Rage of Mages 2 - 256 and 16a formats

Hi, 
Is it possible to add the support of these graphical formats?
The images are in *.256 and *.16 formats, inside them is a bmp picture that is bigger, so there some compresion possible
The are extractors that can extract those bmp's from there but the arent any tools that could inject modified files back

allods.km.ru/1102006.rar - 256 file
allods.km.ru/0014033.rar - 16a file
allods.km.ru/pluginsrc.rar - sources of a plugin for a viewer/extractor
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-05-26T17:25:43+00:00
- Post Title: Rage of Mages 2 - 256 and 16a formats

Well, let's see what I could just looking at the files, 

The .256 and .16 files start with a palette for 256 colours. Each colour is R G B and Alpha (4 bytes). That makes 0x400 in total. Then come three 32-bit values. The first two might represent width and height, perhaps. The third gives the size of the picture data that comes after the third 32-bit value. 
Then at the end of the file there's still one 32-bit value (or perhaps two 16-bit values), in the files you sent this is 0100 0080. 

They look like parts of RLE compressed .BMP files.

[EDIT]I was right for the most part, looked at the source code briefly. The info at the back are indeed two 16-bit values. The first one is the number of "sprites" (wow that's an old term still!) apparently. So in both files you sent there's only one sprite. The other value is a tag about some tricks needed to pad the picture data with some buffer value so the data in the extracted  .BMP matches the size of the original bmp.
## Post #3
- Username: xxnewfolderxx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 26, 2006 11:37 pm
- Post datetime: 2006-05-26T21:54:57+00:00
- Post Title: Rage of Mages 2 - 256 and 16a formats

You're right about the RLE algoritm - found some info on other forum 

The picture is compressed using RLE algoritm(*.256)

Byte
76 543210
00 xxxxxx - show xxxxxx pixels
01 xxxxxx - show xxxxxx pixels color 0 from pallete
02 xxxxxx - show xxxxxx lines of pixels with color 0 from pallete ( i translated it from russian so there may be mistakes)

First 1024 bytes - pallette, and each color contains 4 bytes 
the last always 0
8 bytes: 4 bytes width and 4 bytes height

Problems with the image itself:

height 48
width 72

Beginning 1032 (Offset from begining)
End 3557 (Offset from begining)
Difference -  2525 but width and height make 48*72=3456

where did the 931 bytes go???? 

4 byte from files end = sprite count.
also translated from russian
original forum post - 
[http://www.extractor.ru/ipb/index.php?s ... 0%E8%F2%EC](http://www.extractor.ru/ipb/index.php?showtopic=1137&hl=%E0%EB%E3%EE%F0%E8%F2%EC)
## Post #4
- Username: xxnewfolderxx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 26, 2006 11:37 pm
- Post datetime: 2006-06-01T11:47:57+00:00
- Post Title: Rage of Mages 2 - 256 and 16a formats

Well i tryed to insert a bmp file in hex workshop after the 1032 byte
It showed only the part of the picture(working) and could be extracted but the image still was about 40kb (no compression) but anyone have any idea where exactly does the image data end?
