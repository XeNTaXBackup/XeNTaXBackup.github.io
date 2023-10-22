## Post #1
- Username: phill05
- Rank: beginner
- Number of posts: 37
- Joined date: Sun May 29, 2011 3:29 am
- Post datetime: 2012-06-08T13:22:11+00:00
- Post Title: Max Payne 3 - fonts

Hi,
I'm translating this game, using OpenIV and GXT editor, I found the fonts but I don't know how to get them info .dds format. Does anyone know how to do it?

Thank you
## Post #2
- Username: GooD
- Rank: beginner
- Number of posts: 29
- Joined date: Sat May 03, 2008 5:07 pm
- Post datetime: 2012-06-09T08:15:24+00:00
- Post Title: Max Payne 3 - fonts

Open font WTDs in OpenIV texture viewer then RMB click on texture name in list, and select "export".
## Post #3
- Username: phill05
- Rank: beginner
- Number of posts: 37
- Joined date: Sun May 29, 2011 3:29 am
- Post datetime: 2012-06-09T09:20:29+00:00
- Post Title: Max Payne 3 - fonts

THX
## Post #4
- Username: tuka
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 23, 2012 12:10 am
- Post datetime: 2012-06-22T16:15:15+00:00
- Post Title: Max Payne 3 - fonts

hello,

im looking for the max payne font, but i cant tell openIV the location of the game.
Any Ideas?
## Post #5
- Username: GooD
- Rank: beginner
- Number of posts: 29
- Joined date: Sat May 03, 2008 5:07 pm
- Post datetime: 2012-06-23T20:23:31+00:00
- Post Title: Max Payne 3 - fonts

> Reply from tuka
>
> hello,
im looking for the max payne font, but i cant tell openIV the location of the game.
Any Ideas?If you have any with selecting game in OpenIV you can do it manually:
1 - Run OpenIV, Select Game.
2 - Try to brows game folder.
3 - Close OpenIV.
4 - In Notepad open file "[SystemDrive]:\Users\[UserName]\AppData\Roaming\New Technology Studio\OpenIV\pc\Payne\Personality.xml"
You will see something like this:

5 - Edit "game" element, like this:

6 - Run OpenIV, select Max Payne 3.
It will work fine next.
## Post #6
- Username: tuka
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 23, 2012 12:10 am
- Post datetime: 2012-06-24T16:11:41+00:00
- Post Title: Max Payne 3 - fonts

Hey thanks!

it worked, now im fighting my way through the filejungle.
i found the fonts in the common.rpf, but there only .xml files and one big (9MB) fonts.dat

any idea how the uncompress the font out of the file?
thx in advance!

EDIT: Ok followed the steps the OP did, but again, when i click "export", the useless dialog opens just like in my previous screenshot. is openIV capable of using another "save as" dialog?
## Post #7
- Username: GooD
- Rank: beginner
- Number of posts: 29
- Joined date: Sat May 03, 2008 5:07 pm
- Post datetime: 2012-06-25T04:23:19+00:00
- Post Title: Max Payne 3 - fonts

> Reply from tuka
>
> i found the fonts in the common.rpf, but there only .xml files and one big (9MB) fonts.datThe font textures are in:
pc.rpf:/textures/allfontsinone.wtd
pc.rpf:/textures/allfontsintwo.wtd

> Reply from tuka
>
> EDIT: Ok followed the steps the OP did, but again, when i click "export", the useless dialog opens just like in my previous screenshot. is openIV capable of using another "save as" dialog?OpenIV is used system "save as" dialog. I've never tested it with others dialogs.
You can try to use "Export all" feature, besides "Export".
## Post #8
- Username: tuka
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 23, 2012 12:10 am
- Post datetime: 2012-06-25T11:25:52+00:00
- Post Title: Max Payne 3 - fonts

Ok found the Font, looks like the Slate Bold and Italic version.
I guess i cant convert the bitmap somehow to an normal OpenType Font or TrueType, right?

Thanks for your help anyway.
## Post #9
- Username: saidsrc
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Apr 18, 2011 10:38 pm
- Post datetime: 2012-09-30T14:13:37+00:00
- Post Title: Max Payne 3 - fonts

Hi there,
I am also translating MP3 to my language. I exported WTD file as a DDS file. But, I couldn't find a way to import it back to WTD file. Or maybe there could be a way to make game read the DDS file instead of WTD. 
How can I make the game use my edited DDS font file?
## Post #10
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2013-02-19T10:55:33+00:00
- Post Title: Max Payne 3 - fonts

How to convert WTD to DDS and back to WTD.
WTD using zlib compression set to 9.

How to convert it to DDS
----------------------------
1. Run OpenIV and export WTD as DDS. Then make a copy of DDS header, it is first 128 bytes and save as "DDS.hdr" It is important!
2. Export WTD with OpenIV, open WTD in HEX editor and remove first 12 bytes and save. I recomended save removed header data as "allfontsinone.hdr" 
3. Use zlib decompressor/compressor to decompress WTD.
4. After decompress open WTD in HEX editor and remove first 4096 bytes, then add DDS header from "DDS.hdr" and save as DDS. I recomended save removed data as "allfontsinone_dds.hdr"
5. Now you can edit DDS.


How to convert edited DDS back to WTD
---------------------------------------------
1. Open DDS in HEX editor and remove DDS header, it is first 128 bytes and then add backup data from "allfontsinone_dds.hdr" and save.
2. Now compress DDS with zlib and set compression to 9. 
3. Open compressed DDS with HEX editor and add backup data from "allfontsinone.hdr" and save as "allfontsinone.wtd"
4. Reimport WTD with OpenIV and check it.
5. Done!

NOTE: If will be file bigger or smaller than original it is not important.

This method is availible only for PC users  Xbox have custom compression.
## Post #11
- Username: GooD
- Rank: beginner
- Number of posts: 29
- Joined date: Sat May 03, 2008 5:07 pm
- Post datetime: 2013-07-20T20:07:24+00:00
- Post Title: Max Payne 3 - fonts

New OpenIV 1.5 is released - [http://openiv.com/](http://openiv.com/)

Now you can edit WTD Textures from Max Payne 3.

[http://www.youtube.com/watch?v=0ndIYq5fxFg](http://www.youtube.com/watch?v=0ndIYq5fxFg)
## Post #12
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2019-08-26T07:21:00+00:00
- Post Title: Max Payne 3 - fonts

Hi everyone! Can you help me edit font texture in PS3 version? I can not open it with OpenIV, perharp PS3 have custom compression.
My example files: [https://drive.google.com/file/d/1QHVxQ- ... sp=sharing](https://drive.google.com/file/d/1QHVxQ-spiuqeG4xXJukarSBaRgg1RGUJ/view?usp=sharing)
Thanks a lot!
