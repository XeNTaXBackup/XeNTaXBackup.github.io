## Post #1
- Username: hesanda
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Sep 03, 2014 12:35 pm
- Post datetime: 2017-02-03T11:04:04+00:00
- Post Title: How to Extract .Dra files

file.PNG (32.38 KiB) Viewed 57 times

I there was a online game called Secret of the solstice, that was shut down 2012. Was wondering anyway to extract the contents to get the models, sprites etc.
## Post #2
- Username: hesanda
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Sep 03, 2014 12:35 pm
- Post datetime: 2017-02-10T13:08:06+00:00
- Post Title: How to Extract .Dra files

[https://www.sendspace.com/filegroup/5%2 ... onJSLlYQQx](https://www.sendspace.com/filegroup/5%2BlhvkxEs4qmjp0rRplsYkiDe%2Ff8TYd8PQWy3dCiH%2BSOoPRwtHC%2BetXVfrHpCavjEvueC%2Bkg%2BOK5JNf0R2UBTfWbU90IGfWVnxbwkI1mTYvuj2spUH9icsonJSLlYQQx)

here are the files i uploaded maybe someone can help figure out how to extract them
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-22T20:21:03+00:00
- Post Title: How to Extract .Dra files

this bms script will split your GBKEF.DRA sample  

```
goto 0x10
get FILES long
goto 0x15
for i = 0 < FILES
    get FILENUM long
    get OFFSET long
    savepos TMP
    goto OFFSET
    get SKIP long
    get SIZE long
    math SIZE + 13
    math NAME = OFFSET
    string NAME + ".dat"
    log NAME OFFSET SIZE
    goto TMP
next i
```


they don't look like textures to me though,
i would guess the textures are in the GTEXC.* files and the names are in the GTEXC.LST file
## Post #4
- Username: dumchoi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 28, 2017 11:37 am
- Post datetime: 2017-04-29T03:28:26+00:00
- Post Title: How to Extract .Dra files

Thanks for the info
[ทางเข้า จีคลับ](https://www.gclub88.com/)
