## Post #1
- Username: OLogYMot
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Feb 02, 2016 12:13 am
- Post datetime: 2016-02-04T21:08:12+00:00
- Post Title: Murdered Soul Suspect Help Editing Font

I am wondering if there is any luck to adding or editing font in this game? Needed for translation. I found these:
1. "game directory\FateGame\Localization\INT\GFxUI.int"
There is a font name list in this file.
2. "game directory\FateGame\CookedPCConsole\Startup_LOC_INT.upk"
I guess this is a font package to game has. Because I extracted with “Unreal Package Extractor”. Result:


Now I want to editing font. Please help me to figure out.
## Post #2
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2016-02-05T02:59:57+00:00
- Post Title: Murdered Soul Suspect Help Editing Font

Upload content of westernfonts folder. There are RAW data of fonts.
## Post #3
- Username: OLogYMot
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Feb 02, 2016 12:13 am
- Post datetime: 2016-02-05T03:43:05+00:00
- Post Title: Murdered Soul Suspect Help Editing Font

Content of "Startup_LOC_INT.upk" file:
[http://www.mediafire.com/download/9b8a6 ... OC_INT.rar](http://www.mediafire.com/download/9b8a62z7i1b60i9/Startup_LOC_INT.rar)

Of course I need to repack them or simply open with UDK maybe works. But I can't open it. 
Error: "Unable to load package (....) PackageVersion  860, MaxExpected  868 : LicenseePackageVersion   93, MaxExpected    0."
There is a something about "LicenseePackageVersion".
## Post #4
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2016-02-06T04:30:08+00:00
- Post Title: Murdered Soul Suspect Help Editing Font

If I remember correctly this game has main font as SWF. Those are only for dialogs and some other stuff. File extension is SwfMovie.

Open Texture2D in HEX editor and check needed values for dds.
Values are in LittleEndian

24 bytes /18h adress is height
52 bytes /34h adress is width
Compression is DXT5

Now create dds in Gimp or Photoshop and set the values w/h and save as dds with DXT5 compression.

Now back to the Texture2D file.
Remove first 301 bytes then go to the end of file and again remove 52 bytes from end.
Now you must insert valid dds header from dds which you create. It's first 128 bytes.
Save Texture2D file as dds and you have done.

This tutorial can be used as revers process. But you must remember what you did previously.
In short after editing dds remove first 128 bytes and insert back previously removed data 301 bytes and 52 bytes.
Decompress UPK and insert modified files to it.

All what you will need for this game is HEX editor and some knowledge. Because this engine is sucks. 
Every game on UE3 has custom modified engine. So there is no universal tool except your hands and knowledge.

Anyway works even this game with uncompressed files?
## Post #5
- Username: Skrillex
- Rank: advanced
- Number of posts: 66
- Joined date: Sat Aug 23, 2014 1:11 am
- Post datetime: 2016-02-14T05:14:19+00:00
- Post Title: Murdered Soul Suspect Help Editing Font

> Reply from GRiNDERKILLER
>
> 
Anyway works even this game with uncompressed files?

Is there any simple solution for font sir? This way to hard and long.
