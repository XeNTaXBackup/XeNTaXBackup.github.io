## Post #1
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2018-10-18T05:06:37+00:00
- Post Title: Mobile Suit Gundam - Crossfire

i dumped the archive with a script from an old initial D ps3 game, but found nothing further than that so just dumping some files here (i found an old script but it only gets models out unrigged)

[https://www.mediafire.com/file/cxpaz6v8 ... e.rar/file](https://www.mediafire.com/file/cxpaz6v8bdxhxvt/Zaku_2_-_Gundam_Crossfire.rar/file)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-18T10:34:37+00:00
- Post Title: Mobile Suit Gundam - Crossfire

> Reply from Rin
>
> i dumped the archive with a script from an old initial D ps3 game, but found nothing further than that
What about the textures?

> Reply from Rin
>
> i found an old script but it only gets models out unrigged
What script?
## Post #3
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2018-10-18T14:25:12+00:00
- Post Title: Mobile Suit Gundam - Crossfire

this is what i used to get objs and DDS, turns out i was doing it wrong but still unrigged models
also with this tool models are missing parts 
[viewtopic.php?f=16&t=8074](http://forum.xentax.com/viewtopic.php?f=16&t=8074)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-18T20:13:27+00:00
- Post Title: Mobile Suit Gundam - Crossfire

> Reply from Rin
>
> but still unrigged modelsyeah, howfie, how could he leave this undone? Since we extractors  (most of us) are sort of lazybones when dealing with the meshes only. 



zk2_lower0.png (107.96 KiB) Viewed 167 times
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-19T03:41:27+00:00
- Post Title: Mobile Suit Gundam - Crossfire

> Reply from Rin
>
> this is what i used to get objs and DDS
Thought you said it was a script.
## Post #6
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2018-10-19T18:38:04+00:00
- Post Title: Mobile Suit Gundam - Crossfire

yeah got mixed up, i did use a bms script to extract the .afs archives and then that old exe to turn the files into OBJ
 
```
# script for QuickBMS http://quickbms.aluigi.org

idstring "AFS"
get DUMMY byte  # it's usually 0 but in some files (MULTSPQ2.AFS) it may be different
get FILES long
savepos INFO_OFF

math NAME_OFF = FILES
math NAME_OFF *= 8
math NAME_OFF += INFO_OFF
goto NAME_OFF
get NAME_OFF long
goto INFO_OFF

for i = 0 < FILES
    get OFFSET long
    get SIZE long

   if NAME_OFF == 0
      set NAME string ""
   else
      savepos INFO_OFF
      goto NAME_OFF
      getdstring NAME 32
      getdstring DUMMY 16
      savepos NAME_OFF
      goto INFO_OFF
   endif

    log NAME OFFSET SIZE
next i
```
