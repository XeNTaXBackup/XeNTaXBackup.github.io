## Post #1
- Username: Dark Frost
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Dec 25, 2021 8:51 am
- Post datetime: 2023-01-27T21:57:26+00:00
- Post Title: Quickbms script - How Can I return and after Q_OFFSET then A_OFFSET?

```
    findloc A_OFFSET binary "\x80\x00"
    goto A_OFFSET
    get A_SIZE asize
    findloc Q_OFFSET binary "\x43\x52\x49"
    goto Q_OFFSET
    get Q_SIZE asize
    if A_OFFSET == Q_OFFSET - 32
    findloc B_OFFSET binary "\x80\x01\x??\x??" 0 ""
    goto B_OFFSET
    if B_OFFSET == ""
        get B_SIZE asize
    else
       math B_OFFSET + 4 # 4 is B_OFFSET Byte
        math B_SIZE = B_OFFSET
    endif
    math B_SIZE - A_OFFSET
    string A_OFFSET + ".adx"
    log A_OFFSET A_OFFSET B_SIZE
    math A_OFFSET = B_OFFSET
    goto A_OFFSET
    else
    goto A_OFFSET
While NotEOF <> 0
cleanexit

```

I Create This Code But:
How Can I return and after Q_OFFSET then A_OFFSET
I need Confirm, check A_OFFSET is how far from Q_OFFSET, Because Sometime A_OFFSET "\x80\x00" Data too far from Q_OFFSET
my data is
[asdasdasdasd.png](https://xentaxbackup.github.io/file/23352_asdasdasdasd.png)
