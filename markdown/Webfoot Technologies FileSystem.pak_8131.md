## Post #1
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-01-26T13:03:08+00:00
- Post Title: Webfoot Technologies FileSystem.pak

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-01-28T04:08:46+00:00
- Post Title: Webfoot Technologies FileSystem.pak

Can anyone, like, help me with this?
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-28T18:04:30+00:00
- Post Title: Webfoot Technologies FileSystem.pak

I have figured the file format but I don't know what's the compression algorithm.
I have scanned the compressed block with all the over 200 algorithms available in quickbms (which include also something for nintendo) but I got no results so don't have idea.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-28T18:51:44+00:00
- Post Title: Webfoot Technologies FileSystem.pak

just for completness I post the script regarding the file format, as already said the compression algorithm is the only thing missing.
so I repeat, the following script CANNOT be used!

```
get FILES long
for i = 0 < FILES
    get CRC long
    get OFFSET long
    get FILESIZE long
    get CHUNKS long
    savepos TMP_OFF

    log MEMORY_FILE 0 0
    goto OFFSET
    for j = 0 < CHUNKS
        get NEXT_OFF long
        putarray 0 j NEXT_OFF
    next j
    savepos OFFSET
    for j = 0 < CHUNKS
        goto OFFSET
        get ZIP long
        get SIZE long
        savepos OFFSET
        getarray NEXT_OFF 0 j
        math ZSIZE = NEXT_OFF
        math ZSIZE -= OFFSET
        append
        if ZIP == 0
            log MEMORY_FILE OFFSET SIZE
        else
            clog MEMORY_FILE OFFSET ZSIZE SIZE
        endif
        append
        math OFFSET = NEXT_OFF
    next j
    get XSIZE asize MEMORY_FILE
    if XSIZE != FILESIZE
        print "different size than expected %XSIZE% %FILESIZE%"
        cleanexit
    endif
    log "" 0 FILESIZE MEMORY_FILE
    goto TMP_OFF
next i
```
## Post #5
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-01-29T00:40:53+00:00
- Post Title: Webfoot Technologies FileSystem.pak

Ouch. So it must be a proprietary packing method. Could it be encrypted too? And another thing: the reason why I wanted this unpacked was because I'd like to see if there are some model files that I can use and/or rip off the game.
