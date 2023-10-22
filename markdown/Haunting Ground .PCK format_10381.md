## Post #1
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2013-05-01T17:04:04+00:00
- Post Title: Haunting Ground .PCK format

Hi,I successful to open DATA.CVM from this game by cutting the file header  and convert it to iso,so it readable via virtual drive. i want to extract fiona model or (if can) other character too. The game model seems use .PCK format and the texture in .TEX and the stage use .PAC format. I try to open .TEX file in noesis but no luck. Is there anyone can help me,so the PCK file readable and i can extract the texture too. Thanks

BTW,i attach some sample (is it violate against forum rules or not??)
[sample.7z](https://xentaxbackup.github.io/file/6372_sample.7z)
## Post #2
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2013-05-02T02:54:36+00:00
- Post Title: Haunting Ground .PCK format

Looking the file again in hex editor,still got no clue.I'm totally lost here.I heard in other forum,someone successfully extract it,but sadly his trick not shareable
## Post #3
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2013-05-04T15:35:49+00:00
- Post Title: Haunting Ground .PCK format

Anyone?please help..
## Post #4
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-05-20T18:56:28+00:00
- Post Title: Haunting Ground .PCK format

> Reply from aagems
>
> Anyone?please help..
Here is a quickbms script to convert the texture(s) inside a .TEX file:
[http://ps23dformat.wikispaces.com/file/ ... undTEX.bms](http://ps23dformat.wikispaces.com/file/view/HauntingGroundTEX.bms)
The script must be run using the Microsoft Windows Command prompt (it will will not work by clicking quickbms.exe), you can get quickbms here:
[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
Use the script as follows and note the w in -w must be lowercase:
C:\quickbms\quickbms.exe -w C:\quickbms\HauntingGroundTEX.bms C:\HauntingGround\FIO_000.TEX C:\HauntingGround
The script will then output one txd file for each of the textures inside the .TEX file.
Use this program to then view and convert the textures (but turn the filter off, and the alpha maps off, and use the "several textures" option when exporting even though there is only one texture in each txd):
[http://www.thegtaplace.com/downloads/f4 ... txd-viewer](http://www.thegtaplace.com/downloads/f457-ps2-txd-viewer)

As for the format of the TEX files:
The first 4ByteInteger is the number of textures in the TEX file
Then every texture's header which is 0x10 bytes in length is present.
The first 4Bytes in the header are unknown
The next 2 are the X Length
The next 2 are the Y Width
The next 4 are unknown
The next 4 is the position of the data relative to the start of the header.
Format of the data:
The first part of the data are the bitmap pixels So if X=4 and Y=4 there would be decimal 16 bytes in this section.
Then after all the pixels, is the 256 color palate:
1Byte Red, 1Byte Green, 1ByteBlue, 1Byte something (usually FF, or 80 I forgot the name for it).
However the palate uses  8x2 tiles, which my quickbms scripts compenstates for.
## Post #5
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2013-05-20T20:03:54+00:00
- Post Title: Haunting Ground .PCK format

Thanks for your response furryfan, but why its not work? i use command prompt as you said but quickbms found nothing. Or maybe im doing wrong step? Here's a screenshot
## Post #6
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-05-21T11:52:52+00:00
- Post Title: Haunting Ground .PCK format

> Reply from aagems
>
> Thanks for your response furryfan, but why its not work? i use command prompt as you said but quickbms found nothing. Or maybe im doing wrong step? Here's a screenshot
You used D: for your output file. Change it to something else like
C:\sample
## Post #7
- Username: kasake
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Feb 16, 2012 3:03 pm
- Post datetime: 2013-10-06T23:01:52+00:00
- Post Title: Haunting Ground .PCK format

> Reply from FurryFan
>
> aagems wrote:Thanks for your response furryfan, but why its not work? i use command prompt as you said but quickbms found nothing. Or maybe im doing wrong step? Here's a screenshot 



You used D: for your output file. Change it to something else like
C:\sample
This isn't working for me either. I get the exact same message as aagems with 0 outputted files, even after changing the output folder to C:\
## Post #8
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-10-06T23:47:52+00:00
- Post Title: Haunting Ground .PCK format

> Reply from kasake
>
> FurryFan wrote:aagems wrote:Thanks for your response furryfan, but why its not work? i use command prompt as you said but quickbms found nothing. Or maybe im doing wrong step? Here's a screenshot 



You used D: for your output file. Change it to something else like
C:\sample
This isn't working for me either. I get the exact same message as aagems with 0 outputted files, even after changing the output folder to C:\
First thing, you NEED to use the version of quickbms that is FOUND ON THIS PAGE, AND THIS PAGE ONLY:
[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
If you downloaded quickbms from a DIFFERENT website, IT WILL NOT WORK. Do you understand that I have had more then 6 people use the wrong version. USE THE LINK ABOVE. If that link is blocked on your computer tell me, I am not a mind reader

Second thing:
aagems sent me a PM saying that he finally got it to work.

Third thing, if you want me to help you,
YOU MUST SEND ME A SCREENSHOT OF
1. What you are typing in.
2. You folder setup.

If you are serious about getting the script to work, DO WHAT I SAY.
## Post #9
- Username: kasake
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Feb 16, 2012 3:03 pm
- Post datetime: 2013-10-07T00:12:59+00:00
- Post Title: Haunting Ground .PCK format

> Reply from FurryFan
>
> First thing, you NEED to use the version of quickbms that is FOUND ON THIS PAGE, AND THIS PAGE ONLY:
http://aluigi.altervista.org/quickbms.htm
If you downloaded quickbms from a DIFFERENT website, IT WILL NOT WORK. Do you understand that I have had more then 6 people use the wrong version. USE THE LINK ABOVE. If that link is blocked on your computer tell me, I am not a mind reader

Second thing:
aagems sent me a PM saying that he finally got it to work.

Third thing, if you want me to help you,
YOU MUST SEND ME A SCREENSHOT OF
1. What you are typing in.
2. You folder setup.

If you are serious about getting the script to work, DO WHAT I SAY.
Sorry about that. I got my QuickBMS from that website, and I downloaded the .bms script from the link that you posted.

This is what I input in command prompt:
C:\quickbms\quickbms.exe -w C:\quickbms\HauntingGroundTEX.bms C:\hg\FIO_000.TEX C:\hg

Here is a pic of what I get (the Yen signs are "\", I'm on a Japanese computer):
## Post #10
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-10-07T01:40:31+00:00
- Post Title: Haunting Ground .PCK format

It may be the Japanese Characters (I had this problem with Chinese characters), or it may be the same problem the other user had (his PM did not mention the exact reason), so you should also try contacting him/her. I would also recommend the following:
Have someone that you know very well that has an English version of Windows test out the script, and ask them what they did.
See me PM that I am sending you.
## Post #11
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2018-01-06T08:13:46+00:00
- Post Title: Haunting Ground .PCK format

> Reply from FurryFan
>
> aagems wrote:Anyone?please help..
Here is a quickbms script to convert the texture(s) inside a .TEX file:
http://ps23dformat.wikispaces.com/file/ ... undTEX.bms
The script must be run using the Microsoft Windows Command prompt (it will will not work by clicking quickbms.exe), you can get quickbms here:
http://aluigi.altervista.org/quickbms.htm
Use the script as follows and note the w in -w must be lowercase:
C:\quickbms\quickbms.exe -w C:\quickbms\HauntingGroundTEX.bms C:\HauntingGround\FIO_000.TEX C:\HauntingGround
The script will then output one txd file for each of the textures inside the .TEX file.
Use this program to then view and convert the textures (but turn the filter off, and the alpha maps off, and use the "several textures" option when exporting even though there is only one texture in each txd):
http://www.thegtaplace.com/downloads/f4 ... txd-viewer

As for the format of the TEX files:
The first 4ByteInteger is the number of textures in the TEX file
Then every texture's header which is 0x10 bytes in length is present.
The first 4Bytes in the header are unknown
The next 2 are the X Length
The next 2 are the Y Width
The next 4 are unknown
The next 4 is the position of the data relative to the start of the header.
Format of the data:
The first part of the data are the bitmap pixels So if X=4 and Y=4 there would be decimal 16 bytes in this section.
Then after all the pixels, is the 256 color palate:
1Byte Red, 1Byte Green, 1ByteBlue, 1Byte something (usually FF, or 80 I forgot the name for it).
However the palate uses  8x2 tiles, which my quickbms scripts compenstates for.

Hello, I did that and it WORKS!!, thank you. BTW, I want to make a mod in one texture, Can I edit texture,1.0.TXD and then repack that in FIO_000.TEX??

Thanks
## Post #12
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2018-01-12T20:54:29+00:00
- Post Title: Haunting Ground .PCK format

5 years later ....
