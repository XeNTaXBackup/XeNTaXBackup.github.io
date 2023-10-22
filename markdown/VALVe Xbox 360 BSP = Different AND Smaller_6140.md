## Post #1
- Username: Friendsxix
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jan 26, 2011 1:09 pm
- Post datetime: 2011-02-26T01:03:45+00:00
- Post Title: VALVe Xbox 360 BSP = Different AND Smaller?

On the xbox 360, the BSPs are smaller, and don't work in the PC version of Left 4 Dead. The header for the PC Version is "VBSP", but the xbox 360's header is "PSBV". Maybe someone here can figure it out?

PC Version BSP: [http://www.mediafire.com/?cf80npm3na1sk28](http://www.mediafire.com/?cf80npm3na1sk28)

Xbox 360 Version BSP: [http://www.mediafire.com/?bn91mmygdq5ykcb](http://www.mediafire.com/?bn91mmygdq5ykcb)

Thanks,
~Friendsxix
## Post #2
- Username: Friendsxix
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jan 26, 2011 1:09 pm
- Post datetime: 2011-03-29T19:38:10+00:00
- Post Title: VALVe Xbox 360 BSP = Different AND Smaller?

I have looked into the BSP myself a bit, and found that the actual file has a "LZMA" Header. Is this a compression method?
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-29T21:15:14+00:00
- Post Title: VALVe Xbox 360 BSP = Different AND Smaller?

yes, LZMA is a very efficient algorithm.

anyway this archive is too much strange because it's not lzma and I have some output only using lzma2 but in that case I have many files with 0 size... mah maybe someone else has an answer:

```

comtype lzma2_86dec
endian big
idstring "PSBV"
get DUMMY long
for
    get OFFSET long
    get SIZE long
    get DUMMY1 long
    get DUMMY2 long
    if DUMMY1 < 0
        break
    endif
    if OFFSET != 0
    if SIZE != 0
        savepos TMP
        goto OFFSET
        getdstring SIGN 4
        if SIGN == "LZMA"
            get SIZE long
            get ZSIZE long
            reverselong SIZE
            reverselong ZSIZE
            savepos OFFSET
            clog "" OFFSET ZSIZE SIZE
        else
            log "" OFFSET SIZE
        endif
        goto TMP
    endif
    endif
next
```
## Post #4
- Username: Friendsxix
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jan 26, 2011 1:09 pm
- Post datetime: 2011-03-29T23:04:55+00:00
- Post Title: VALVe Xbox 360 BSP = Different AND Smaller?

The contents of this post was deleted because of possible forum rules violation.
