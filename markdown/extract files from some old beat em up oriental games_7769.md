## Post #1
- Username: rafhot
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 29, 2011 11:21 pm
- Post datetime: 2011-11-29T15:46:35+00:00
- Post Title: extract files from some old beat em up oriental games

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-03T17:37:55+00:00
- Post Title: extract files from some old beat em up oriental games

script for QuickBMS:

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "JoyMax File Manager!\n"
set OFFSET 0x100
set NAME string ""
set PATH string ""
callfunction EXTRACT

startfunction EXTRACT
    goto OFFSET
    string PATH += NAME
    string PATH += /

    for
        savepos MYOFF
        get TYPE byte
        getdstring NAME 0x59
        get TSTAMP longlong
        get TSTAMP longlong
        get OFFSET longlong
        get SIZE long
        get NEXT_OFF longlong
        get DUMMY short
        if TYPE == 0
            break
        elif TYPE == 1
            if NAME != "."
            if NAME != ".."
                savepos SAVE_OFF
                callfunction EXTRACT
                goto SAVE_OFF
            endif
            endif
        elif TYPE == 2
            set FNAME string PATH
            string FNAME += NAME
            log FNAME OFFSET SIZE
        else
            break
            #print "Error: unknown type 0x%TYPE|x% at offset %MYOFF|x%"
            #cleanexit
        endif
        if NEXT_OFF != 0
            goto NEXT_OFF
        endif
    next
endfunction
```

there are about 10 megabytes not covered in yain.pk2 and I don't know if it's right or not
## Post #3
- Username: rafhot
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 29, 2011 11:21 pm
- Post datetime: 2011-12-07T06:26:51+00:00
- Post Title: extract files from some old beat em up oriental games

thanks! it worked fine, but now inside the .pk2 the sprites are inside a file .spr, and i have tried all the extractors that google have showed to me without sucsses:(
