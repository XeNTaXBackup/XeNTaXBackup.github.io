## Post #1
- Username: Sasakimika
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Aug 22, 2022 10:41 pm
- Post datetime: 2023-06-17T15:43:01+00:00
- Post Title: (psp) Gta Vice City Stories XTX file - japan rom

Hello, everyone 
I want to translate gta vice city stories game into my language
But i have a problem that i don't know how to edit the xtx file and i don't have much knowledge about it
After a while of searching I found a russian guy working on it but his page is dead
Here is link: [https://gtaforums.com/topic/408669-modd ... /#comments](https://gtaforums.com/topic/408669-modding-lcsvcs/page/10/#comments)
Can someone help me, thanks a lot
Sorry, i'm not good at english
[FSFONTSJP1.zip](https://xentaxbackup.github.io/file/23953_FSFONTSJP1.zip)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-06-18T05:16:17+00:00
- Post Title: (psp) Gta Vice City Stories XTX file - japan rom

XTX format is texture format used for Vice City Stories.
There are two tools that are able to open this kind of file:

GTA Stories Texture Explorer --> [https://libertycity.net/files/gta-vice- ... r-2.0.html](https://libertycity.net/files/gta-vice-city-stories/57785-gta-stories-texture-explorer-2.0.html)
GTA Stories Tex --> [https://web.archive.org/web/20230116162 ... iesTex.rar](https://web.archive.org/web/20230116162652/http://gtamodding.ru/w/images/1/18/GTAStoriesTex.rar)

Your sample can be opened in GTA Stories Texture Explorer
[https://i.imgur.com/L5KnH4P.png](https://i.imgur.com/L5KnH4P.png)

(just select "alpha mode" and "enable swizzling" in the view settings)

Then you can export image as TIM2 file.
Then you can use any tool from the wiki to edit this file [http://wiki.xentax.com/index.php/TM2_TIM2_Image](http://wiki.xentax.com/index.php/TM2_TIM2_Image)
(or just save it to bmp and convert to tim2 later if it's easier for you)
And then after editing the image, you can use GTA Stories Texture Explorer to import it back to XTX file.


By the way, there is also a way to edit XTX manually using hex editor,
here is a very short tutorial about that [https://gtaforums.com/topic/468524-comp ... 1060315161](https://gtaforums.com/topic/468524-complete-vcs-advanced-hacking-docs/#comment-1060315161)

Edit: I've added this format to the wiki for future reference [http://wiki.xentax.com/index.php/GTA_Series_XTX_CHK](http://wiki.xentax.com/index.php/GTA_Series_XTX_CHK)
## Post #3
- Username: Sasakimika
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Aug 22, 2022 10:41 pm
- Post datetime: 2023-06-18T10:51:43+00:00
- Post Title: (psp) Gta Vice City Stories XTX file - japan rom

thanks a lot, but i have one more question, does this file contain height and width parameters of characters? If so, how can it be modified?
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-06-18T12:45:04+00:00
- Post Title: (psp) Gta Vice City Stories XTX file - japan rom

> does this file contain height and width parameters of characters? If so, how can it be modified?

No, XTX /CHK files don't contain any coordinates, only image data is there.
Easiest way to mod the font is to just replace some characters in XTX file (by editing image data)
and then just use those characters after translating the text - with some script that will replace characters
automatically for you. Here is an generic example  --> [https://github.com/bartlomiejduda/Tools ... EPLACER.py](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/REGULAR_CHAR_REPLACER.py)

But if you really want to edit coordinates, you need to find file holding this data and edit it in hex editor
(or reverse engineer the file format if the case is complicated)
## Post #5
- Username: Sasakimika
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Aug 22, 2022 10:41 pm
- Post datetime: 2023-06-20T16:01:26+00:00
- Post Title: (psp) Gta Vice City Stories XTX file - japan rom

After a while of researching, I found out that the font data is in the game.dtz file, so I used offzip to export it because g3DTZ doesn't have a re-import feature.
Here is my offzip command: offzip.exe -z -a game.dtz out
And it only outputs GAME_unpack.DTZ file containing font and image data
It seems that its structure is different from the EU version, I don't know well about hex and how to export image files
Here is link dtz file: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1sFkR2FH5y79HiTnH-XC_kXmM8HauJvOF?usp=sharing)
Can you or someone teach me how to find the offset of image
P/s: I tried GTA Stories DTZ Explorer but it doesn't read it
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-06-20T17:53:12+00:00
- Post Title: (psp) Gta Vice City Stories XTX file - japan rom

First, GAME.DTZ must be decompressed with offzip as you mentioned.
Once it's done, you can search for coordinates.

Everything you need to find font coordinates is explained here [https://gtamods.com/wiki/Game.dtz#Font_Data](https://gtamods.com/wiki/Game.dtz#Font_Data)
So the article says that you have to go to offset 0xF4 to get to the array of pointers.
For PSP version you have exactly 3 pointers at offset 5466628  (04 6A 53 00 as hex).

Once you get there, you can follow any of these pointers to get to the font info section.
For example, if you'll follow first pointer, you'll end up at offset 5466344. Move 8 bytes forward and you'll get offset to character data - 5117232 (30 15 4E 00 as hex).



screenshot000484.png (163.81 KiB) Viewed 61 times



And it is first table with coordinates:



screenshot000484_2.png (207.12 KiB) Viewed 61 times



You can edit it in hex editor (by following file format from thhe wiki) or get to the other character data tables in the same way I have described above.
