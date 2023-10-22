## Post #1
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-08-17T17:32:02+00:00
- Post Title: [PSP] Angry Birds

Hi,
If somebody wants to export/reimport .gim files from .arc archives of PSP Angry Birds, I wrote this script for QuickBMS. I have used it to help me with redrawing few textures.   

[](http://www.imagebam.com/image/419a9b145510854) [](http://www.imagebam.com/image/9a5536145510857) 

```
for i = 0 < FILES
    get NAMESZ byte
    getdstring NAME NAMESZ 
    get OFFSET long
    savepos POS
    goto OFFSET
    get SIZE long
    savepos OFFSET
    log NAME OFFSET SIZE
    goto POS
next i

```


Note: If you export your reimported .gim files, they will have size of the original ones (just with trailing zeros), because script doesn't recalculate size of imported files.
