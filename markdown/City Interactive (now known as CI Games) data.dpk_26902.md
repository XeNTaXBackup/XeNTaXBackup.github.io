## Post #1
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2023-06-25T16:14:55+00:00
- Post Title: City Interactive (now known as CI Games) data.dpk

```
--------------------------------------
  00024450 28         data\menu\training\MENU_02.LWS

Error: the specified file number (24) has not been opened yet (src\file.c, 732)

Last script line before the error or that produced the error:
  20  CLog FN Offset CSize OOF CSizeOff UCSize UCSOff

- OFFSET       0x00024450
- ZSIZE        0x000005a6
- SIZE         0x0000001c
  coverage file 0     0%   63         204680983  . offset 00000040
```


Are there programs the can unpack data.dpk from all City Interactive games?

Samples:
[https://mega.nz/folder/sLpDhSAY#o359JQ1blW6gkD5kht7qsQ](https://mega.nz/folder/sLpDhSAY#o359JQ1blW6gkD5kht7qsQ)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-06-25T17:58:43+00:00
- Post Title: City Interactive (now known as CI Games) data.dpk

Try this script:
[https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/City%20Interactive%20Games/City_Interactive_DPK_script.bms)

Here is file format for reference [http://wiki.xentax.com/index.php/City_Interactive_DPK](http://wiki.xentax.com/index.php/City_Interactive_DPK)
