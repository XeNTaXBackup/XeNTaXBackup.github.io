## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-04-01T06:09:55+00:00
- Post Title: ZuOnline (最游记)

Hello guys, well I try figure out how unpack files of this game, I make some views in header and found that, maybe somebody can get something? .package file format.

PD: can somebody help me with script 

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "SSHEN"
goto 0x20
get DUMMY long
get DUMMY long
get NAMES_OFF long
get INFO_OFF long
get CRC_OFF long
get FILES long
get CRC long
get DUMMY long
get DUMMY long
goto INFO_OFF
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    math OFFSET += 4
    log "" OFFSET SIZE
next i
```



[https://www.dropbox.com/s/e9w0j3a9z3lti ... package.7z](https://www.dropbox.com/s/e9w0j3a9z3ltiko/ZuOnline%20package.7z)
