## Post #1
- Username: systemchester
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 02, 2010 9:44 am
- Post datetime: 2010-04-02T07:11:09+00:00
- Post Title: HELP FOR A NEW ONLINE GAME  unpack

i tried 4days to unpack the PAK files 
my three friends failed using QUICK BMS to unpack

i searched here for help 

maybe this game。
[http://ago.gfyoyo.com.cn/yxxz.htm](http://ago.gfyoyo.com.cn/yxxz.htm)
[http://downloadago.gfyoyo.com.cn/AGOGBCCBSETUP.exe](http://downloadago.gfyoyo.com.cn/AGOGBCCBSETUP.exe)
it  is  very  boring to upload it
it  have 2G+
i want to a quickbms script to unpack it
beg for your help
oh my poor english~~~~~
## Post #2
- Username: systemchester
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 02, 2010 9:44 am
- Post datetime: 2010-04-03T15:23:59+00:00
- Post Title: HELP FOR A NEW ONLINE GAME  unpack

[http://www.speedyshare.com/files/21755103/agdata1.pak](http://www.speedyshare.com/files/21755103/agdata1.pak)
one of the flies
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-04-03T16:41:11+00:00
- Post Title: HELP FOR A NEW ONLINE GAME  unpack

you can get the files without names like this.
just use offzip
offzip.exe -a -z -15 C:\Downloads\agdata1.pak "C:\Downloads\New folder" 0x0
[0001e149..png](https://xentaxbackup.github.io/file/2908_0001e149..png)
## Post #4
- Username: systemchester
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 02, 2010 9:44 am
- Post datetime: 2010-04-04T04:00:51+00:00
- Post Title: HELP FOR A NEW ONLINE GAME  unpack

thx chrrox
i find offzip 
[http://aluigi.altervista.org/mytoolz.htm](http://aluigi.altervista.org/mytoolz.htm)

i will be one of your fans    
so much .dat files have be unpack in agdata1.pak
i change  .dat to .png  and open the picture successfully
some .dat to .png  can't view 
i am sure they are picture files
but how to trans .dat to .png(maybe .bmp maybe .tga)
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-04-04T12:10:16+00:00
- Post Title: HELP FOR A NEW ONLINE GAME  unpack

i saw a mix of tga,jpg,bmp,png,ogg, and wav files in some of the files i looked at.
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-04-05T03:57:45+00:00
- Post Title: HELP FOR A NEW ONLINE GAME  unpack

its a modified zip format with the central directory compressed too - but that's extracted by offzip at the last block (see 00c8f11c.dat)

i noticed 26 spare bytes from the last file to the file size, which looks like the eocd and perhaps a pointer to the compressed central directory, but i failed to get anywhere else. (i just saw 05 06 as part of the eocd signature)

anyway. we can botch extracting these files with filenames 

1) in a hex editor, copy the contents of 00c8f11c.dat at the start of agdata1.pak and run this bms:

```
#  workaround bms

comtype deflate

for i = 0

  idstring "PK\x01\x02"

  savepos SKIP
  math SKIP += 16
  goto SKIP
  
  get ZSIZE long
  get SIZE long
  get NLEN short
  get ELEN short
  get CLEN short

  savepos SKIP
  math SKIP += 8
  goto SKIP

  get OFFSET long
  math OFFSET += 56516 ## size of our temp header

  getdstring NAME NLEN

  savepos SKIP
  math SKIP += ELEN
  math SKIP += CLEN
  goto SKIP


  if SIZE > 0

    if ZSIZE == SIZE

      log NAME OFFSET SIZE

    else

      clog NAME OFFSET ZSIZE SIZE

    endif

  endif


next i

```
## Post #7
- Username: systemchester
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 02, 2010 9:44 am
- Post datetime: 2010-04-06T00:58:10+00:00
- Post Title: HELP FOR A NEW ONLINE GAME  unpack

thanks both of you  very much
i learned a lot
