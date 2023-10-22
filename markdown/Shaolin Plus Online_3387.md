## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-03-08T20:26:41+00:00
- Post Title: Shaolin Plus Online

This game uses nif files and seems to be using zlib compression on the files.
I will attach some sample files that are compressed.
I can attach an exe or more files if they are needed.
Here is the website.
[http://sl2.runup.com.tw/03-introduction/index-04_2.php](http://sl2.runup.com.tw/03-introduction/index-04_2.php)

[](http://xs.to/xs.php?h=xs137&d=09100&f=screenshot474.jpg)


[ftp://download.runup.com.tw/sl2_combin.exe](ftp://download.runup.com.tw/sl2_combin.exe)

```
  --------------------------------------------
  003e0288 31   Adler CRC32 (0x191b3141) [32.le.1024]
  003e1288 32   Adler CRC32 (0x191b3141) [32.be.1024]
  003e0688 33   Adler CRC32 (0x01c26a37) [32.le.1024]
  003e1688 34   Adler CRC32 (0x01c26a37) [32.be.1024]
  003e0a88 35   Adler CRC32 (0xb8bc6765) [32.le.1024]
  003e1a88 36   Adler CRC32 (0xb8bc6765) [32.be.1024]
  003dfe88 83   CRC-32-IEEE 802.3 poly 0x04C11DB7 [32.le rev.1024]
  003e0e88 84   CRC-32-IEEE 802.3 poly 0x04C11DB7 [32.be rev.1024]
  000eae3c 307  SHA1 / SHA0 / RIPEMD-160 initialization [32.le.20&]
  00400bb2 309  padding used in hashing algorithms (0x80 0 ... 0) [..64]
  003dfa98 357  Zlib dist_code [..512]
  003dfc98 358  Zlib length_code [..256]
  003dfd98 359  Zlib base_length [32.le.116]
  003dfe10 361  Zlib base_dist [32.le.120]
  003dfd98 1085 Rar29 LDecode [32.le.112]
  003df450 1541 zinflate_lengthExtraBits [32.le.116]
  003df4c8 1545 zinflate_distanceExtraBits [32.le.120]
  003df4c5 1546 zinflate_distanceExtraBits [32.be.120]

- 18 signatures found in the file
```

[NPC.rar](https://xentaxbackup.github.io/file/1911_NPC.rar)
## Post #2
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2009-03-08T20:30:30+00:00
- Post Title: Shaolin Plus Online

Okey, only one thing is missing  You did not said what you want, you wrote some info and not asked for anything
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-03-08T21:18:04+00:00
- Post Title: Shaolin Plus Online

lol  can anyone decompress these files 
once they are decompressed they should be viewable in nifskope.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-27T20:13:38+00:00
- Post Title: Shaolin Plus Online

you can find a script [here](http://aluigi.org/papers/bms/shaolin_plus.bms).
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-27T22:17:39+00:00
- Post Title: Shaolin Plus Online

Thanks your script worked great on the nif and kfm files 
I am confused on tga and bmp it shows it converting the file but I am unable to read the resulting files.
I have included the original file, the converted file, and the way the file should look in this archive (it was stored un compressed in the installation)
Thanks for all your great work you are the best.
[](http://xs.to/xs.php?h=xs138&d=09181&f=slplus818.jpg)

here is a bat file for mass converting for anyone who wants to convert these quickly.

```
cd F:\quickbms
@ECHO OFF

IF "%~1"=="" GOTO usage
FOR /R "%~1" %%i IN (*.ni_) DO quickbms.exe shaolin_plus.bms "%%i" f:\slponline
ECHO Finished decrypting models.
GOTO exit

:usage
ECHO "%~0" model_folder
ECHO Or drag the model folder into this batch file.

:exit
PAUSE
```

just edit the paths to point to where your quick bms install dir is and edit the output directory to where you want them exported to.
then just drag a folder and it will convert every file in that sub folder and its sub folders.
files
[http://www.MegaShare.com/821139](http://www.MegaShare.com/821139)
