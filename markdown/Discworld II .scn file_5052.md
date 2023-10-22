## Post #1
- Username: Johnny
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Mar 17, 2010 1:21 am
- Post datetime: 2010-09-17T07:44:06+00:00
- Post Title: Discworld II .scn file

Hi,

I am a translator and would like to translate Discworld II to Polish. The problem is, my language has additional characters, that the game doesn't support. I know the font is in DW2.SCN 

 DW2.zip
(23.23 KiB) Downloaded 30 times


I am looking for a program, that would help me unpack, and pack this file.

Here is some information about SCN format: [http://rewiki.regengedanken.de/wiki/.SCN](http://rewiki.regengedanken.de/wiki/.SCN) and [http://automagically.de/tinsel.html](http://automagically.de/tinsel.html)

Johnny
## Post #2
- Username: Johnny
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Mar 17, 2010 1:21 am
- Post datetime: 2010-10-04T19:08:53+00:00
- Post Title: Discworld II .scn file

bump
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-10-06T20:29:45+00:00
- Post Title: Discworld II .scn file

well, but there aren't any blocks (according to your links) which are specifically fonts, so the bitmap resources are your best bet.

however, graphics are in a complicated format - the IMAGELIST block pointing to parts of the IMAGEDESC block which only describes the graphics files the bitmap data is in the block id 0x0019.

parse the blocks and dump the graphics:

```

for
  get BLOCKID short
  idstring "43"
  get NEXTBLOCK long
  savepos BLOCKSTART

  if NEXTBLOCK == 0 
    math NEXTBLOCK = SIZE
  endif

  math BLOCKSIZE = NEXTBLOCK
  math BLOCKSIZE -= BLOCKSTART

  # process block

  if BLOCKID == 0x19

    # dump block
    log "DW2_GRAPHICS" BLOCKSTART BLOCKSIZE

  endif

  # ------

  if NEXTBLOCK == SIZE
    break
  endif

  goto NEXTBLOCK

next

```


you will also need these blocks, but they use relative pointers

IMAGEDESC == 6 - see format spec links in op
IMAGELIST == 7 - int image_desc_pointer, int 0
## Post #4
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-20T23:45:48+00:00
- Post Title: Discworld II .scn file

someone know somethinks about smp from Discworld noir
## Post #5
- Username: Jibun
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 16, 2020 11:07 pm
- Post datetime: 2020-05-16T16:15:25+00:00
- Post Title: Discworld II .scn file

Hello Johnny,

I know it's been a while since you posted this, but I am also trying to translate the game and I understand you had no problem changing the texts of the game even though you had a problem with the font.
Could you explain to me how did you do it? because I have tried to change the content in the ENGLISH1.txt file and then the game crashes when it tries to load the first texts. I guess the .txt has memory positions in it (hence the weird characters) and directly modifyng it breaks it.

Thanks.
