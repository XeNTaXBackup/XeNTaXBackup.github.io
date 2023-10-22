## Post #1
- Username: Hunter1800
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 02, 2016 7:32 am
- Post datetime: 2016-11-01T23:50:31+00:00
- Post Title: Batman the telltale series (Need help)

Hi Im a complete noob to translating video games and i want to get into it to translate it for my brother.
Id like some help w translating batman the telltale series because so far i have only come accross some tools but no instructions on how to use them...
If anyone knows how to use "TTG tools" or some other program that can help me translate please give me a detailed explanation and  keep in mind i have basically no computer knowledge apart from gaming.
## Post #2
- Username: asymetrix
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 02, 2011 2:47 am
- Post datetime: 2016-11-04T23:09:38+00:00
- Post Title: Batman the telltale series (Need help)

Hey, things you're asking are already covered in other forum [topic](http://forum.xentax.com/viewtopic.php?f=35&t=3254), so here i will just try to gather all things.

To edit game text you will need 2 tools (in fact first is included with second tool, but that not important at this moment;)):
[1. TTARCH](http://aluigi.altervista.org/papers/ttarchext.zip)
[2. TTG TOOLS](https://mega.nz/#!nFcBgZTB!U2zFlokwme1shVWOlpivUUvlC3ue6M4a87Mldcod-No)

1. First extract content of "TTG TOOLS for Batman.rar" archive to some folder, let's assume that will be "C:\TTG Tools".
2. Now extract "ttarchext.zip" archive to same folder, and replace all files when you will be asked, this will update ttarchext to newest version.
3. Before you can use TTG Tools, you have to configure working paths for app. To do this open "C:\TTG Tools\config.xml" in notepad, and edit 2 entries: pathForInputFolder, pathForOutputFolder. Content of your file should look like this:

```
<Settings xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" pathForInputFolder="C:\TTG Tools\input" pathForOutputFolder="C:\TTG Tools\Output" ASCII_N="1251" AdditionalChar="" deleteD3DTXafterImport="false" deleteDDSafterImport="false" importingOfName="true" sortSameString="true" exportRealID="false" unicodeMode="0" />

```


Ok, now everything is setup and we can start edit game files:
4. Open our extract folder "C:\TTG Tools", hold down shift key and right click on empty space in folder window, from context menu select "Open Command Window Here"
5. In new window(the black one;) enter following command:

```
ttarchext.exe -f "*_english.landb" 60 "G:\Batman Episode 1\archives\BM_pc_Batman101_data.ttarch2" "C:\TTG Tools\input"
```

ofc, you should replace "G:\Batman Episode 1\" with your custom game path. If everything goes well, you should see something like this at end: 
- 17 files found
- done
, and then you can close command window.

In "C:\TTG Tools\input" folder you should see many files like "env_asylumconstructionsite_english.landb", "env_asylumconstructionsite_vickitrinary_english.landb" etc. This are localisation files you want to edit. Godxon1 posted nice tutorial how to do this, so i just quoting his words with small modifications:

> 1) Start TTGtool, click yes, start "Auto(De)Packer
>
> 2) Choose: 58 Batman: Telltale Series
>
> 3) Click "Decrypt, Export"
>
> 4) Edit text files, that are in OUTPUT folder and copy them to INPUT folder
>
> 5) Start TTGtool, click yes, start "Auto(De)Packer
>
> 6) Choose: 58 Batman: Telltale Series
>
> 7) Click "Encrypt, Pack, Import"
>
> 8 ) *.landb files, that are in OUPUT folder move to game directory/archives and you have translated game!

for example, text for first mission of episode 1 are placed in env_mayorsoffice_english, you can start there;). Good luck.
## Post #3
- Username: thisrock84
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 02, 2019 8:20 pm
- Post datetime: 2020-04-22T11:05:05+00:00
- Post Title: Batman the telltale series (Need help)

Hello,
I am making localization for PS4. But I get errors in some games. For example, Batman: The Telltale Series, Tales from the Borderlands (all episodes). In these games, tool can extract the package but when I rebuild the package in to ttarch2, the game locks on the playstation or waiting loading screen or wait in black screen. 

Are the keys different for PS4? Is there a method you know? Because I downloaded the PC versions of these games and the tool works properly for the PC versions. It just crashes on PS4.

Thank you for your help in advance.

Note: I know that I can put the files with landb extension to the archive folder, but there are the files with the same name with landb extension for different episodes. I cannot put these files to the archive folder because it has same name. For this reason, I had to make changes to ttarch2 files.

I used;
ttarchext.exe -o -b -V 7 60 "BM_ps4_Boot_data.ttarch2" "BM_ps4_Boot_data"
ttarchext.exe -o -b 60 "BM_ps4_Boot_data.ttarch2" "BM_ps4_Boot_data"
ttarchext.exe -o -x -b 60 "BM_ps4_Boot_data.ttarch2" "BM_ps4_Boot_data"
ttarchext.exe -o -b -x -V 7 60 "BM_ps4_Boot_data.ttarch2" "BM_ps4_Boot_data"

And I also used ttg_tool original compelete edition > TTG Tools.exe > Archive packer. 
I tried these all combinations in Archive packer: version of archive 1 or 2, or compress archive, or checked encrypt archive, or checked Encrytpt Lua for new games or checked  don't encrypt lua. (I have tried 32 combinations totally)
