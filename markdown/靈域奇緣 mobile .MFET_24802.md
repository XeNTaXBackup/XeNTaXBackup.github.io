## Post #1
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2021-12-01T14:35:19+00:00
- Post Title: 靈域奇緣 mobile .MFET

Name : 靈域奇緣
Content stored in : .MPQ  
APK : [https://apkcombo.com/ling-yu-qi-yuan/com.gdns0607.lyqy/](https://apkcombo.com/ling-yu-qi-yuan/com.gdns0607.lyqy/)

Hi guys, could anyway take a look on this archive ? 

Here header : 

Thanks in advance ,
Drawing
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-12-01T20:28:43+00:00
- Post Title: 靈域奇緣 mobile .MFET

Simple format 

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "MFFS0001"
get ARCHIVE_SIZE longlong
idstring "MFET"
get FILES long

for i = 0 < FILES
   get DUMMY longlong
   get DUMMY long
   get NSIZE short
   getdstring NAME NSIZE
   get NSIZE long
   get HSIZE short
   getdstring HASH HSIZE
   get OFFSET long
   get SIZE long
   get CRC long
   get RESERVED long
   get HSIZE2 short
   getdstring HASH2 HSIZE2
   putarray 0 i NAME
   putarray 1 i OFFSET
   putarray 2 i SIZE
next i

idstring "MFTK"
savepos BASE_OFFSET

for i = 0 < FILES
   getarray NAME 0 i
   getarray OFFSET 1 i
   getarray SIZE 2 i
   math OFFSET += BASE_OFFSET
   log NAME OFFSET SIZE
next i
```
## Post #3
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2021-12-02T14:01:05+00:00
- Post Title: 靈域奇緣 mobile .MFET

Thanks Ekey
