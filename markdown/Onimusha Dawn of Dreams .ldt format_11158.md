## Post #1
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2014-01-25T16:17:33+00:00
- Post Title: Onimusha Dawn of Dreams *.ldt format

hi, i manage to extract image.afs from onimusha dawn of dreams and get tons of file and i found that model file or maybe container (dunno)  is in ldt format,can anyone please look the file and maybe create an importer for noesis   all help will be appreciated.

here's i provide some sample:
[2082_pl1D00.rar](https://xentaxbackup.github.io/file/6953_2082_pl1D00.rar)
## Post #2
- Username: aagems
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-01-25T16:37:42+00:00
- Post Title: Onimusha Dawn of Dreams *.ldt format

you need to decompress those sections in those files first.

```
for
    findloc OFFSET string "CPK0"
    goto OFFSET
    idstring CPK0
    get ZSIZE long
    get SIZE long
    get DUMMY long
    savepos OFFSET
    math ZSIZE -= 16
    clog "" OFFSET ZSIZE SIZE
next
```
## Post #3
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2014-01-25T17:55:19+00:00
- Post Title: Onimusha Dawn of Dreams *.ldt format

thanks for the script chrrox    okay,after decompressing it it give me 3 file with the extension:*.oim,*.dat,and *.img. So i guess the model file is in dat file,is it a container again?sorry for being noob   any importer script/plugin possibility?
