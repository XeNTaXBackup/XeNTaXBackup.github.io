## Post #1
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-02-12T13:55:20+00:00
- Post Title: Nintendo DS Mushishi .arc format

Hey Guys

Been a long time since I posted here.

Currently looking into the backgrounds of the game 'Mushishi - Ame Furu Sato' for the DS, looking inside the folders I find a tonne of .arc files,

All files, models, textures, backgrounds and even music, seem to be stored in these .arc files.

I've attached one of the files to test with, its pretty small.

Would really appreciate if someone could look into this, any arc tools I found online don't seem to work on this format.

Thanks.
[files.rar](https://xentaxbackup.github.io/file/6188_files.rar)
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-02-15T23:37:15+00:00
- Post Title: Nintendo DS Mushishi .arc format

Does anybody have any tips or advice on this format?
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-02-16T01:41:40+00:00
- Post Title: Nintendo DS Mushishi .arc format

with only 1 sample its really hard to know the compression type i think this is correct but who knows.
i file with compressed text would know for sure.

```
#by chrrox
#http://aluigi.altervista.org/quickbms.htm
comtype BPE
idstring "ARCH"
get files long
get nstart long
get tbloff long
get nsizeoff long
get fstart long
for i = 0 < files
goto tbloff
get ZSIZE long
get SIZE long
get OFFSET long
get noff short
get unk short #compression flag? always seems to be one
savepos tbloff
set nameoff nstart
math nameoff + noff
goto nameoff
get NAME string
math OFFSET + fstart
clog NAME OFFSET ZSIZE SIZE
next i


```

edit: I tried it on some more files and t appears correct so there you go.
## Post #4
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-02-16T15:37:31+00:00
- Post Title: Nintendo DS Mushishi .arc format

Thankyou so much Chrrox.
I have an issue with it however, I tried it even on the file that I uploaded here, and I get the following error

Invalid datatype short#compression at line 17, seems to happen regardless of what file I try

I can see that its this line : 
```
get unk short#compression flag? always seems to be one
```
 but I'm unsure how to fix it.
## Post #5
- Username: lionheartuk
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-02-16T15:51:44+00:00
- Post Title: Nintendo DS Mushishi .arc format

add a space before the #

get unk short #compression flag? always seems to be one
