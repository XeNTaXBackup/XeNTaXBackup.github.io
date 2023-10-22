## Post #1
- Username: yiwang
- Rank: beginner
- Number of posts: 21
- Joined date: Sat Apr 28, 2012 9:30 am
- Post datetime: 2014-12-30T14:54:13+00:00
- Post Title: [PS3]Gundam Breaker 2  PCK

PCK How to open
[1.png](https://xentaxbackup.github.io/file/8399_1.png)
## Post #2
- Username: yiwang
- Rank: beginner
- Number of posts: 21
- Joined date: Sat Apr 28, 2012 9:30 am
- Post datetime: 2014-12-30T14:57:33+00:00
- Post Title: [PS3]Gundam Breaker 2  PCK

PCK File
[pck.zip](https://xentaxbackup.github.io/file/8400_pck.zip)
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-12-30T15:31:19+00:00
- Post Title: [PS3]Gundam Breaker 2  PCK

Well, some files are duplicated and i temporary added hash at the end of file name 

```
# 
# Written by Ekey (h4x0r)
# 
# script for QuickBMS http://quickbms.aluigi.org

endian BIG
idstring "\x00cap"

goto 0x80
get FILES long
get DUMMY long #?

set OFFSET long FILES
math OFFSET *= 264
math OFFSET += 264

for i = 0 < FILES
    getdstring NAME 256
    get HASH long
    get DZSIZE long
    savepos TEMP
	
    goto OFFSET
      idstring "BILZ"
      get SIZE long
      get ZSIZE long
      get FLAG long #7 ?
      savepos DOFFSET
	  
      string NEWNAME p= "%s_%08X" NAME HASH
      clog NEWNAME DOFFSET ZSIZE SIZE
	
    math OFFSET += DZSIZE
    goto TEMP
next i
```
