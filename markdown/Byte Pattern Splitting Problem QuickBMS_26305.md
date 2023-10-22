## Post #1
- Username: Dark Frost
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Dec 25, 2021 8:51 am
- Post datetime: 2023-01-20T16:39:18+00:00
- Post Title: Byte Pattern Splitting Problem QuickBMS?

Hi ı Can use this code [https://zenhax.com/viewtopic.php?t=1843#p10024](https://zenhax.com/viewtopic.php?t=1843#p10024) but ı have problem Byte Pattern Splitting
my code is

```
do
    goto OFFSET
    get DUMMY long
    findloc NEXT_OFFSET binary "\x00\x07\x77\x77\x77\x77\x77\x77\x77\x77\x77\x77\x77\x77\x77\x77" 0 ""
    if NEXT_OFFSET == ""
        get SIZE asize
    else
        math SIZE = NEXT_OFFSET
    endif
    math SIZE += OFFSET
    log "" OFFSET SIZE
    math OFFSET = NEXT_OFFSET
while NEXT_OFFSET != ""

```

Problem is first extracted First file is fine because start with \x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00 Pattern And End With "\x00\x07\x77\x77\x77\x77\x77\x77\x77\x77\x77\x77\x77\x77\x77\x77"
I need Like This

but 2nd and another files doesnt extracted correctly because start with "\x00\x07\x77\x77\x77\x77\x77\x77\x77\x77\x77\x77\x77\x77\x77\x77" and with Nothing
How Can I Fix This ?
Sorry I Write Visual Basic But I dont Know c++
[ss1.png](https://xentaxbackup.github.io/file/23329_ss1.png)
