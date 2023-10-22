## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-12-27T16:05:35+00:00
- Post Title: Musketeers 3 (pc) *.gdp Archives

Hi all,
can anyone help me to unpack *.gdp archives?

samples: >>[SMALL](http://dl.dropbox.com/u/9919707/blogs/xentax.com/m3-pc/dataengine.zip)<< | >>[MIDDLE](http://dl.dropbox.com/u/9919707/blogs/xentax.com/m3-pc/models.zip)<<
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-27T21:17:07+00:00
- Post Title: Musketeers 3 (pc) *.gdp Archives

experimental and ugly script... but works:

```
# script for QuickBMS http://quickbms.aluigi.org

comtype lzf
idstring "GDP"
set PATH string ""
set NAME string ""
get xPATH_NEXT asize
callfunction EXTRACT

startfunction EXTRACT
    math PATH_NEXT = xPATH_NEXT
    string PATH += NAME
    string PATH += /
    for
        savepos MYOFF
        if MYOFF >= PATH_NEXT
            break
        endif

        get TYPE byte
        if TYPE == 4
            get ENTRY_SIZE long
            get xPATH_NEXT long
            get PATH_PREV long
            get NAME string
            if xPATH_NEXT == 0
                string PATH += NAME
                string PATH += /
            else
                callfunction EXTRACT
            endif
        else
            get ENTRY_SIZE long
            get NEXT long
            get OFFSET long
            get SIZE long
            get DUMMY byte
            get TSTAMP longlong
            get XSIZE long
            get DUMMY long
            get DUMMY long
            get NAME string
            set FNAME string PATH
            string FNAME += NAME
            if TYPE & 0x80
                clog FNAME OFFSET SIZE XSIZE
            else
                log FNAME OFFSET SIZE
            endif
            math OFFSET += SIZE
            goto OFFSET
        endif
    next
endfunction
```
