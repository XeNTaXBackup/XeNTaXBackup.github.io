## Post #1
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-10-10T07:59:20+00:00
- Post Title: BattleField 4 (.cat .cas)

Firstly a bit of dev humor   



I've tried looking through the code for the encryption key but no luck
## Post #2
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-10-10T22:42:52+00:00
- Post Title: BattleField 4 (.cat .cas)

You can extract all data with a script  by  "Frankelstner" from bfeditor.org
also work for bf3.

with this you can extract all *.chunk files (sound, model , textures, anims) and the .itexture data, DBX data, etc

[http://www.bfeditor.org/forums/index.ph ... 15731&st=0](http://www.bfeditor.org/forums/index.php?showtopic=15731&st=0)

(I don't know if can I post links from other forums here.)
## Post #3
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-10-11T03:17:47+00:00
- Post Title: BattleField 4 (.cat .cas)

> Reply from luxox18
>
> You can extract all data with a script  by  "Frankelstner" from bfeditor.org
also work for bf3.

with this you can extract all *.chunk files (sound, model , textures, anims) and the .itexture data, DBX data, etc

http://www.bfeditor.org/forums/index.ph ... 15731&st=0

(I don't know if can I post links from other forums here.)

ah thanks has anyone worked on the model geometry data chunks?
## Post #4
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-10-11T21:15:42+00:00
- Post Title: BattleField 4 (.cat .cas)

> Reply from cra0
>
> ah thanks has anyone worked on the model geometry data chunks?

Only on textures and sounds
## Post #5
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2013-10-29T18:38:06+00:00
- Post Title: BattleField 4 (.cat .cas)

Hi tried with the python code but i get errors

```
  File "dumper.py", line 418, in <module>
    main()
  File "dumper.py", line 415, in main
    dump(fname,outputfolder)
  File "dumper.py", line 229, in dump
    casHandlePayload(entry,ebxPath+entry.elems["name"].content+".ebx")
  File "dumper.py", line 379, in casHandlePayload
    catEntry=cat.entries[entry.elems["sha1"].content]
KeyError: '\xdf+\xdb\xc7(\xef\x18\xbe\xa9d\x16\x00TV\xebT\xfc\xd6\x1c\xb3'
```


Where i can get/found a BMS/Py working with Battlefiled 4?

Thanks
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-07-02T07:39:11+00:00
- Post Title: BattleField 4 (.cat .cas)

> Reply from luxox18
>
> You can extract all data with a script  by  "Frankelstner" from bfeditor.org
also work for bf3.

with this you can extract all *.chunk files (sound, model , textures, anims) and the .itexture data, DBX data, etc

http://www.bfeditor.org/forums/index.ph ... 15731&st=0

That site is down, you can find the scripts here

```
http://www.mediafire.com/download/kniqderdgp5q3ce/BF_Four_Python_Scripts.zip
```

Video showing how to use
[https://www.youtube.com/watch?v=fR4dSlG ... LUHUfcuvSA](https://www.youtube.com/watch?v=fR4dSlGxN-4&list=UU0N16omoshHu4LUHUfcuvSA)


This looks like it could work too
[http://sourceforge.net/projects/daitools/](http://sourceforge.net/projects/daitools/)
## Post #7
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-07-04T20:46:38+00:00
- Post Title: BattleField 4 (.cat .cas)

> Reply from AceWell
>
> luxox18 wrote:You can extract all data with a script  by  "Frankelstner" from bfeditor.org
also work for bf3.

with this you can extract all *.chunk files (sound, model , textures, anims) and the .itexture data, DBX data, etc

http://www.bfeditor.org/forums/index.ph ... 15731&st=0

That site is down, you can find the scripts here
Code: Select allhttp://www.mediafire.com/download/kniqderdgp5q3ce/BF_Four_Python_Scripts.zip
Video showing how to use
https://www.youtube.com/watch?v=fR4dSlG ... LUHUfcuvSA


This looks like it could work too
http://sourceforge.net/projects/daitools/

The python script doesn't seem to work on the SWBF cas files but the DAITools does but it wont extract anything from it cause it just crashes
## Post #8
- Username: ginev
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Feb 15, 2016 6:53 pm
- Post datetime: 2016-09-11T19:40:28+00:00
- Post Title: BattleField 4 (.cat .cas)

Man i am following your tutorial here but on the end when i click Run Module i am getting this:

Traceback (most recent call last):
  File "D:\Games\Zlo_Battlefield_3_Multiplayer\BATTLEFIELD 3 EXTRACTOR\dumper.py", line 1, in <module>
    import sbtoc
  File "D:\Games\Zlo_Battlefield_3_Multiplayer\BATTLEFIELD 3 EXTRACTOR\sbtoc.py", line 7, in <module>
    from collections import OrderedDict
ImportError: cannot import name OrderedDict
>>> 


This is how its looking my path lines in the dumper.py

catName=r"D:\Games\Zlo_Battlefield_3_Multiplayer\Battlefield 3\Data\cas.cat" #use "" or r"" if you have no cat; doing so will make the script ignore patchedCatName
patchedCatName=r"D:\Games\Zlo_Battlefield_3_Multiplayer\Battlefield 3\Update\Patch\Data\cas.cat" #used only when tocRoot contains "Update"

tocRoot=r"\Battlefield 3\Update"
##tocRoot=r"D:\Games\Zlo_Battlefield_3_Multiplayer\Battlefield 3\Data\Win32"

outputfolder="D:\Games\Zlo_Battlefield_3_Multiplayer\Battlefield 3\EXTRACTS"


What i am doing wrong?Please help me if you read this. :S
