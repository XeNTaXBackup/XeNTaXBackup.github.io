## Post #1
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-08-14T09:44:05+00:00
- Post Title: Champion Dreams ( hours rider ) , 3d data + animation data !

the game has a hybrid style (story + ride)
and all files are separated !
I hope you interested for 3d models and animating of them like me too !
i uploaded sample anim + models + DIR /s here :
[http://www.filekeeper.org/download/shared/xentax.rar](http://www.filekeeper.org/download/shared/xentax.rar)
[](http://xs.to)
## Post #2
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-08-15T10:08:33+00:00
- Post Title: Champion Dreams ( hours rider ) , 3d data + animation data !

I showed the graphical view of bytes for the , Horse.nmo , Jade_Civil.nmo , that included in uploaded pak !
these are samle characters of the game .
if we watch the graph , we will find many regular shapes !
if someone check these files and discuss about , how vertex data and face indices aligned , i am so grateful   

[](http://xs.to)
## Post #3
- Username: shekofte
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-15T12:42:33+00:00
- Post Title: Champion Dreams ( hours rider ) , 3d data + animation data !

You need to extract the data first.
QUICKBMS SCRIPT

```
get NAME filename
get NAME1 filename
math files += 2
goto 0x1C
get ZSIZE1 long
get ZSIZE2 long
get SIZE2 long
goto 0x3C
get SIZE1 long
savepos OFFSET
savepos OFFSET1
for i = 0 < FILES
if i == 1
string NAME -= 4
string NAME += ".s"
clog NAME OFFSET1 ZSIZE1 SIZE1
else if i == 0
string NAME1 -= 4
string NAME1 += ".f"
math OFFSET += ZSIZE1
clog NAME1 OFFSET ZSIZE2 SIZE2
endif
next i

```

[ChampionDreams.rar](https://xentaxbackup.github.io/file/2281_ChampionDreams.rar)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-08-16T16:18:46+00:00
- Post Title: Champion Dreams ( hours rider ) , 3d data + animation data !

the game uses the Virtools framework so you can use [unvirt](http://aluigi.org/papers.htm#unvirt) to extract all the files (usually there are only "components" and "objects").
## Post #5
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-08-16T16:29:22+00:00
- Post Title: Champion Dreams ( hours rider ) , 3d data + animation data !

ERUDITE chrrox Bugtest
so much thanks   

result :

```
- open script c.bms
- set output folder ext

  offset   filesize   filename
------------------------------
  00000c1f 1027708    Horse.f
  00000040 8784       Horse.s

- 2 files found
```
## Post #6
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-08-16T23:59:51+00:00
- Post Title: Champion Dreams ( hours rider ) , 3d data + animation data !

thanks , dexterous
now the format is clear

[](http://xs.to)
whether a tool that relevant to this file type exist ?
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-11T19:19:22+00:00
- Post Title: Champion Dreams ( hours rider ) , 3d data + animation data !

Shekofte, what is up with the link to that site? It says: "Image", but there is no image, just the site.
## Post #8
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-10-12T11:05:42+00:00
- Post Title: Champion Dreams ( hours rider ) , 3d data + animation data !

Hi Mr.Mouse
i comeback after long time <--O----->>
the problem is related to xs.to host server ! i am not Guilty !
i checked some of my other post , this problem occured in them too !!!
unfortunately i have not any backup on my HDD
my country blocked uploading of images to most of huge photo sharing services !
xs.to is the only one that i know ?
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-12T11:25:12+00:00
- Post Title: Champion Dreams ( hours rider ) , 3d data + animation data !

Hmm. Perhaps we can install an image upload facility for members at a later stage. Only for those very important images. *thinks*
