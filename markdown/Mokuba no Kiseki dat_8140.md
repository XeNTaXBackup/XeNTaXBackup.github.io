## Post #1
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-01-28T17:18:50+00:00
- Post Title: Mokuba no Kiseki dat

Hello, Everybody!
Could anyone please tell me how to extract data from .dat file. 
The first 4 bytes a header "FPAC"
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-28T19:23:49+00:00
- Post Title: Mokuba no Kiseki dat

```
# script for QuickBMS http://quickbms.aluigi.org

comtype gzip
idstring "FPAC"
get BASE_OFF long
math BASE_OFF *= 0x800
for i = 0
    get SIZE long
    if SIZE == 0
        cleanexit
    endif
    get ZIP short
    get OFFSET short
    math OFFSET *= 0x800
    math OFFSET += BASE_OFF

    savepos TMP
    goto OFFSET
    getdstring DUMMY 10
    get NAME string
    goto TMP

    clog NAME OFFSET SIZE SIZE
next i
```
*edit* updated
## Post #3
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-01-29T04:50:32+00:00
- Post Title: Mokuba no Kiseki dat

Thank your for your assistance.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-30T16:50:16+00:00
- Post Title: Mokuba no Kiseki dat

there was an error in the reading of the filename from the gzip file, now the script is ok
