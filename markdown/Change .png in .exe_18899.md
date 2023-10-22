## Post #1
- Username: Wolfik
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jun 22, 2011 7:25 pm
- Post datetime: 2018-10-06T13:01:00+00:00
- Post Title: Change .png in .exe

Pls help.
Change .png in .exe (is it .png/.fnt)
ResHacker etc view only icons but no font.png
Multiextractor this file extract but I do not know how to import the modified file back.



Thanks for help.
## Post #2
- Username: peter2005
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Mar 25, 2016 3:26 pm
- Post datetime: 2018-10-06T15:32:33+00:00
- Post Title: Change .png in .exe

The only easy solution is to replace a png with the same (filesize) png. So, if your png has the same size as the one you want to replace, you can do it with hex editor.
## Post #3
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2018-10-06T15:46:28+00:00
- Post Title: Change .png in .exe

The same applies to .fnt file. Same size and hex editor.

Why you need to replace that files?

EDIT:
Ahh okey, now I know why. Not all fonts are read from Data\Fonts folder. 
So if you make new BMFont png+fnt files (smaller or equal in size) you can replace them in .exe.
## Post #4
- Username: Wolfik
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jun 22, 2011 7:25 pm
- Post datetime: 2018-10-06T17:20:01+00:00
- Post Title: Change .png in .exe

Thanks all.
It will be a problem, I can not do much work in hex. (HxD)
I do not know how to select only png data and how to insert a smaller file.
Is there no other way to re-import png? bms?
## Post #5
- Username: peter2005
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Mar 25, 2016 3:26 pm
- Post datetime: 2018-10-06T19:18:24+00:00
- Post Title: Change .png in .exe

1. open both files (.exe and .png) in hxd
2. select all .png bytes and use ctrl+c
3. find starting position(first byte) of .png in .exe file
4. 'paste write' content there
5. save .exe file
## Post #6
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2018-10-07T08:13:48+00:00
- Post Title: Change .png in .exe

You can use this script to export and import that PNG and FNT file. Attachment also contains two batch files. 

0) Make backup of game's .exe file.
1) Put all three files and quickbms.exe into main game folder and run _export.bat.
2) Exported files will be in the "EXPORT" folder.
3) Edit them (or replace). New files have to be smaller or equal in size!
4) Run _import.bat and run the game.


```
set PNGSIZE 0xA500	# 42240 bytes
set PNGNAME "arial20_as_bm_font_0.png"
set FNTSIZE 0xC68A	# 50826 bytes
set FNTNAME "arial20_as_bm_font_0.fnt"

log PNGNAME OFFSET PNGSIZE
math OFFSET + PNGSIZE
log FNTNAME OFFSET FNTSIZE

```

[Dark_Tales_5_script.zip](https://xentaxbackup.github.io/file/14980_Dark_Tales_5_script.zip)
## Post #7
- Username: Wolfik
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jun 22, 2011 7:25 pm
- Post datetime: 2018-10-07T09:25:24+00:00
- Post Title: Change .png in .exe

Yes , game works.
Very thanks.
## Post #8
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2018-10-07T12:35:55+00:00
- Post Title: Change .png in .exe

So this is Czecho-Slovak thread it seems.

Tak teda čaute.
## Post #9
- Username: Wolfik
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jun 22, 2011 7:25 pm
- Post datetime: 2018-10-08T11:54:48+00:00
- Post Title: Change .png in .exe

> Reply from merlinsvk
>
> So this is Czecho-Slovak thread it seems.

Tak teda čaute.

Zdar a ještě jednou dík
## Post #10
- Username: peter2005
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Mar 25, 2016 3:26 pm
- Post datetime: 2018-10-08T19:32:30+00:00
- Post Title: Change .png in .exe

piste anglicky lebo nas vykopnu   

hope that not using english won't get us banned
