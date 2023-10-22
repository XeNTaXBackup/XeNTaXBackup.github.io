## Post #1
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-04-17T10:28:50+00:00
- Post Title: only some hints please ,  In-Fisherman Freshwater Trophies

the game has only one .pak archive , i tried some extractor tools on it , NO EFFECT !
i cut the archive with filecutter and uploaded the head and tail at:
[http://www.filekeeper.org/download/shared/head.zip](http://www.filekeeper.org/download/shared/head.zip)
[http://www.filekeeper.org/download/shared/tail.zip](http://www.filekeeper.org/download/shared/tail.zip)
please someone check them , at least give me some hints about the archive structure !
sincerely  
[](http://xs.to/xs.php?h=xs138&d=09165&f=scr33nshot00006346.jpg)
[](http://xs.to/xs.php?h=xs138&d=09165&f=scr33nshot00005200.jpg)
## Post #2
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-04-21T20:51:42+00:00
- Post Title: only some hints please ,  In-Fisherman Freshwater Trophies

when i inspected the archive in AXE hex editor , in graphical view of bytes , i found strange shapes (attached) !
when i scanned them subtle , i understood they are .tga images !
then i trim the area that contains image and tried to make a .tga with it , in 010 editor using a .tga template 
[http://www.sweetscape.com/010editor/templates/](http://www.sweetscape.com/010editor/templates/)
[](http://xs.to)
you see my  conclude in this image : ( you can compare the real photo in the game with that i created ! attention this image is last .tga in the end of archive , appeard in AXE hex editor ! ) :
[](http://xs.to)
now i am so angry   and my brain dont work any more please some one save me !   
I trimmed the area that contains this .tga image and uploaded it to :
[http://www.filekeeper.org/download/shar ... ad_tga.zip](http://www.filekeeper.org/download/shared/upload_tga.zip)
who can make the real .tga   
remark : these four bytes contains Width and Height information of .tga , I am sure , but explanation of it is not necessary ! 
@[123 000] WORD Width
@[189 000] WORD Height
---------------------
75275088: 191 000 198 000 071 001 237 000 189 000 160 000 177 000 138 000
75275104: 043 000 080 000 010 001 010 001 069 001 078 001 135 000 177 000
75275120: 160 000 015 001 254 000 213 000 252 000 008 001 150 000 063 000
75275136: @[123 000] @[189 000] 027 001 035 001 032 001 071 001 030 001 023
75275152: 252 000 206 000 201 000 003 001 177 000 172 000 126 000 092 000
75275168: 179 000 208 000 220 000 116 000 087 000 029 000 194 000 120 001
75275184: 073 001 237 000 099 000 114 000 023 001 157 000 133 000 240 000
---------
and these are some lines of appeared images:(attention the lines that contains Width and Height are very far from the area that contains image)
----------
81342736: 255 081 058 035 255 085 059 029 255 077 055 034 255 100 072 035   
81342752: 255 095 072 041 255 108 081 049 255 100 078 050 255 089 062 030   
81342768: 255 101 075 042 255 108 084 049 255 095 069 038 255 103 074 042   
81342784: 255 112 088 052 255 113 084 044 255 104 078 048 255 116 090 055   
81342800: 255 100 072 040 255 105 076 046 255 121 095 057 255 131 100 063   
------------
i maked that .tga with these option randomly !
-----------
struct TGAFILEHEADER TGAfh	Uncompressed, True-color Image	0h	12h	Fg:
UBYTE IDLength	0	0h	1h	Fg:
UBYTE ColorMapType	0	1h	1h	Fg:
UBYTE ImageType	2	2h	1h	Fg:
struct COLORMAPSPECIFICATION CMSpecification		3h	5h	Fg:
WORD FirstIndexEntry	0	3h	2h	Fg:
WORD ColorMapLength	16	5h	2h	Fg:
UBYTE ColorMapEntrySize	0	7h	1h	Fg:
struct IMAGESPECIFICATION ISpecification	Res: 171x180^24	8h	Ah	Fg:
WORD XOrigin	0	8h	2h	Fg:
WORD YOrigin	0	Ah	2h	Fg:
WORD Width	171	Ch	2h	Fg:
WORD Height	180	Eh	2h	Fg:
UBYTE PixelDepth	24	10h	1h	Fg:
UBYTE ImageDescriptor	32	11h	1h	Fg:
struct TGALine TGALines[123]		12h	1106Dh	Fg:
[axe.jpg](https://xentaxbackup.github.io/file/1978_axe.jpg)
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-23T03:59:12+00:00
- Post Title: only some hints please ,  In-Fisherman Freshwater Trophies

I have attached a quick script for the archive you posted
[fishtophies.zip](https://xentaxbackup.github.io/file/1984_fishtophies.zip)
## Post #4
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-04-23T09:53:39+00:00
- Post Title: only some hints please ,  In-Fisherman Freshwater Trophies

Bugtest , You are a real Conjurer   
successful
i working on the extracted files now !
thanks
