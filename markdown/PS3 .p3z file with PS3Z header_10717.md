## Post #1
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-08-25T01:06:29+00:00
- Post Title: PS3 .p3z file with PS3Z header

Some days ago I found the way for extract textures from call of duty 3 from ps3



this texture files are not compressed, but some .cod files are inside of one single file with format p3z



I want to extract the .cod files because this files contain textures and models.

[http://www.mediafire.com/folder/2eoduzvo04zdz/AN](http://www.mediafire.com/folder/2eoduzvo04zdz/AN)

thanks
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-08-27T22:25:28+00:00
- Post Title: PS3 .p3z file with PS3Z header

Hi facepunch guy, ill take a look at the format later today.
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-28T18:15:51+00:00
- Post Title: PS3 .p3z file with PS3Z header

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype unzip_dynamic

idstring "ps3z"
get DUMMY long
get PS3ZSIZE asize
math PS3ZSIZE -= 1

do
    savepos TEMP
    get NAME string
    math TEMP += 260
    goto TEMP
    get NULLS long
    get SIZE long
    savepos OFFSET

    clog NAME OFFSET SIZE SIZE
    set NEXT = OFFSET
    math NEXT += SIZE
    goto NEXT
while NEXT != PS3ZSIZE
```
## Post #4
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-08-30T03:50:01+00:00
- Post Title: PS3 .p3z file with PS3Z header

thanks Ekey , the script works excellent!
