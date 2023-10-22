## Post #1
- Username: Oscar92player
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Feb 05, 2016 2:13 am
- Post datetime: 2016-11-13T21:40:22+00:00
- Post Title: [PSP] Final Fantasy III .pgf and .rssa files

Hi everyone!

I was searching a method to decrypt the font files from the PSP version of FF3. I tried using GLIntercept with the PPSSPP emulator, but that only shows the letters used at the moment you play the game (for example, if you see the command "Attack", using GLIntercept only decrypts the letters A, t, a, c, and k and not the complete font template).

I searched then with the UMD Gen in the rom files, and I found a few folders that contains 2D data from the different languages of the version. Inside every folder, there is one called "Font" and inside, the font files used for that language. The files contains a .pgf format, but I don't know how to extract or decrypt them.

Also, I found 2D files, that are supposed to be HUD graphics, with .rssa format, but I the same as bellow. I don't know how to decrypt them.

I uploaded some of the files here:
[FF3 Font files PGF](https://mega.nz/#!MRMFGaKb!CXGR6OSHnNrw_33zxhhQRTxW8urTMJKEbh_Lu2V68Jw)
[FF3 2D files RSSA](https://mega.nz/#!cMUxDRIZ!kasUtgA6dqgnVZdbSMKZyv6ckO7NvPJS520L4YZhP2o)

Can you help me, please?
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-12-07T02:14:32+00:00
- Post Title: [PSP] Final Fantasy III .pgf and .rssa files

> Reply from Oscar92player
>
> Also, I found 2D files, that are supposed to be HUD graphics, with .rssa format, but I the same as bellow. I don't know how to decrypt them.

I uploaded some of the files here:
....
FF3 2D files RSSA
the rssa samples contain gim format images which can be viewed in Noesis.   

this BMS script will cut the gim from the rssa samples.  

```

get EXT extension
if EXT == rssa
    get SIZE asize
    get NAME basename
    string NAME + .gim
    findloc OFFSET binary "\x4d\x49\x47\x2e"
    math SIZE - OFFSET
    log NAME OFFSET SIZE
else
    CleanExit
endif
```
## Post #3
- Username: Oscar92player
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Feb 05, 2016 2:13 am
- Post datetime: 2018-12-07T10:37:24+00:00
- Post Title: [PSP] Final Fantasy III .pgf and .rssa files

> Reply from Acewell
>
> Oscar92player wrote:Also, I found 2D files, that are supposed to be HUD graphics, with .rssa format, but I the same as bellow. I don't know how to decrypt them.

I uploaded some of the files here:
....
FF3 2D files RSSA
the rssa samples contain gim format images which can be viewed in Noesis.   

this BMS script will cut the gim from the rssa samples.  
Code: Select all# script for QuickBMS http://aluigi.altervista.org/quickbms.htm

get EXT extension
if EXT == rssa
    get SIZE asize
    get NAME basename
    string NAME + .gim
    findloc OFFSET binary "\x4d\x49\x47\x2e"
    math SIZE - OFFSET
    log NAME OFFSET SIZE
else
    CleanExit
endif

Thanks! This worked very well with those files. Now I need to know how to extract the PGF ones, that contains the game font...
