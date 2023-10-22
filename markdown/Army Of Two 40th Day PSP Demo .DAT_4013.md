## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-01-05T14:16:13+00:00
- Post Title: Army Of Two 40th Day PSP Demo .DAT

Here is the bigfile from the demo .DAT If someon can figure this out thanks.

[http://www.megaupload.com/?d=KHIBRVFM](http://www.megaupload.com/?d=KHIBRVFM)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-05T14:42:05+00:00
- Post Title: Army Of Two 40th Day PSP Demo .DAT

nameless files:

```
math TMP = FILES
math TMP *= 4
math TMP += 4
goto TMP
for i = 0 < FILES
    get SIZE long
    get OFFSET long
    get DUMMY long
    get DUMMY long
    math OFFSET *= 0x800
    log "" OFFSET SIZE
next i
```
