## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-01-09T10:12:26+00:00
- Post Title: Army Of Two - The 40th Day BNK Sound

[http://www.megaupload.com/?d=GPWTVVQF](http://www.megaupload.com/?d=GPWTVVQF)

here is a sound bank from the 360 game, looks like a wwise bank but the sdk doesn't come with an unpacker for it.

Appreciate for  BMS script.

thanks
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-10T13:39:17+00:00
- Post Title: Army Of Two - The 40th Day BNK Sound

```

endian big
idstring "BKHD"
get OFFSET long
math OFFSET += 8
goto OFFSET
idstring "DIDX"
get DIDX_SIZE long

savepos BASE_OFF
math BASE_OFF += DIDX_SIZE
math BASE_OFF += 8  # DATA chunk

math FILES = DIDX_SIZE
math FILES /= 12

for i = 0 < FILES
    get DUMMY long
    get OFFSET long
    get SIZE long

    math OFFSET += BASE_OFF
    log "" OFFSET SIZE
next i

# HIRC header ignored, seems nothing useful
```
