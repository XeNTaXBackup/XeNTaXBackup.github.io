## Post #1
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2012-02-22T09:34:30+00:00
- Post Title: Why these swf cann't open? Please help.

Hi, Guys.
There is a game. 
Lost Chronicles - Fall of Caesar
there are a lot of files in \data\swf, 
These files must be swf, but its Filename suffix is klf, and cann't open with flash player.
Can anybody help me?
Tell me how to open these .klf?
[pause_menu.rar](https://xentaxbackup.github.io/file/5099_pause_menu.rar)
## Post #2
- Username: aeon
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 14, 2006 8:20 pm
- Post datetime: 2012-02-22T19:31:42+00:00
- Post Title: Why these swf cann't open? Please help.

what makes you think that is swf file? it does not look like swf at all.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-22T20:37:37+00:00
- Post Title: Why these swf cann't open? Please help.

They're in a folder called "swf" so presumably they must be swf files.
## Post #4
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2012-02-24T04:35:24+00:00
- Post Title: Why these swf cann't open? Please help.

Because these files were encryped or modified. So it does not look like swf at all.
If you know swf file structure you can analyse the sample.
If the sample can play by flashplayer it should display  image like 123.jpg.
[123.jpg](https://xentaxbackup.github.io/file/5104_123.jpg)
## Post #5
- Username: aeon
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 14, 2006 8:20 pm
- Post datetime: 2012-02-25T19:37:25+00:00
- Post Title: Why these swf cann't open? Please help.

that file is  neither normal swf nor crypted one , it's some sort of metafile containing pictures of game menu
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-02-28T03:12:51+00:00
- Post Title: Why these swf cann't open? Please help.

this is a KLF file which seems to contain KLP files. KLP files contain a small chunk of compressed data and a footer, which looks like it contains JPEG data.

here is a quick n dirty [http://aluigi.org/quickbms.htm](http://aluigi.org/quickbms.htm) script to dump this JPEG footer data:

```

idstring "K\0\0\0L\0\0\0F\0\0\0"

get DUMMY long
get FILES long

for f = 0 < FILES

  get STRLEN1 long
  getdstring STR1 STRLEN1
  get STRLEN2 long
  getdstring STR2 STRLEN2
  get DATALEN long

  savepos OFFSET

  # KLF data is compressed with zlib, but we can skip that

  get ZSIZE long
  get SIZE long
  savepos OFFSET2
  math OFFSET2 += ZSIZE

  math REM = DATALEN
  math REM -= ZSIZE
  math REM -= 8 # edit

  string IMG_STR p= "%s__tail.jpg" STR1

  log IMG_sTR OFFSET2 REM

  math OFFSET += DATALEN
  goto OFFSET

next f

```


the compressed data chunk probably describes the image to stop it bleeding like it does in my extracted file  
[background__tail.jpg](https://xentaxbackup.github.io/file/5112_background__tail.jpg)
## Post #7
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2012-03-18T02:22:24+00:00
- Post Title: Why these swf cann't open? Please help.

It seems that I made a mistake. Thanks, very much.
I have other questions. 
There is other .klf, but this klf can not export with BMS.
Why?  what's the difference with two pause_menu.klf?
And I want to know if I Modified some pictures. How to pack these images back to .klf?
[pause_menu.rar](https://xentaxbackup.github.io/file/5202_pause_menu.rar)
