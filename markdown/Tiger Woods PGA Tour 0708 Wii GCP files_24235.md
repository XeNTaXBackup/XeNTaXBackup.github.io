## Post #1
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2021-07-13T21:51:46+00:00
- Post Title: Tiger Woods PGA Tour 07/08 Wii GCP files

Does anyone know how to unpack .gcp files from Tiger Woods PGA Tour 07 and 08 on the Wii?
Samples here:
[https://mega.nz/file/TtMDWK4Q#Lackf2869 ... aWfFCkL1Yc](https://mega.nz/file/TtMDWK4Q#Lackf2869K0PjVgx_qVgRNsB1weyzq0JwaWfFCkL1Yc)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-17T11:14:23+00:00
- Post Title: Tiger Woods PGA Tour 07/08 Wii GCP files

This script should extract data  from GCB files
[https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Tiger%20Woods%20PGA%20Tour/Tiger_Woods_GCB_script.bms)

And here is file format documentation
[http://wiki.xentax.com/index.php/Tiger_ ... A_Tour_GCB](http://wiki.xentax.com/index.php/Tiger_Woods_PGA_Tour_GCB)
## Post #3
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2021-07-18T01:40:26+00:00
- Post Title: Tiger Woods PGA Tour 07/08 Wii GCP files

Thanks, this also works for the .ps3 files of Tiger Woods 07 on PS3.
## Post #4
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2021-07-18T14:45:11+00:00
- Post Title: Tiger Woods PGA Tour 07/08 Wii GCP files

This script isn't properly unpacking all the files.
Here is the input I am working with:
[https://mega.nz/file/vgtEGTgB#pwJs759SH ... rcLcGApiJY](https://mega.nz/file/vgtEGTgB#pwJs759SHDQHtYt69fWw4Ylwiu738NHJDrcLcGApiJY)
When I run it, it extracts
002de6a0 6488       file165.bin
However the file it extracts is incomplete (when you look at it, its got apti then a size of for that chunk but the output file cuts off before the end of that chunk.
Its also incorrectly extracting files file172.bin, file180.bin, file198.bin, file206.bin, file213.bin, file226.bin, file231.bin, file237.bin, file244.bin, file271.bin, file319.bin, file330.bin, file332.bin, file335.bin, file359.bin, file363.bin, file369.bin, file60.bin, file66.bin, file75.bin and file81.bin (at least). All have the apti chunk where the output bin file is too small for the apti chunk.
A bunch of other bin files with apti chunks extract just fine.
## Post #5
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-18T18:21:00+00:00
- Post Title: Tiger Woods PGA Tour 07/08 Wii GCP files

Well, there is a way to manually fix this. I have prepared alternate version of my script
which will NOT try to decompress data:


 Tiger_Woods_GCB_script.zip
(512 Bytes) Downloaded 15 times



Then after using this script you could just merge for example file165.bin and file166.bin
in hex editor and then use offzip on this new file to decompress it and get the correct output file

```
offzip.exe -a file165_and166.bin
```


To be honest, I'm not sure how to implement this solution in quickbms to do it automatically,
so maybe someone else will be able to do this
