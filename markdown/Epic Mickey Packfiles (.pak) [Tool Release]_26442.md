## Post #1
- Username: AbsoluteZero
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Aug 04, 2021 6:05 am
- Post datetime: 2023-02-07T04:54:20+00:00
- Post Title: Epic Mickey Packfiles (*.pak) [Tool Release]

I have been working on a much larger tool to do all of the asset management in Epic Mickey for modders automatically, but a lot of people seem to want this relatively soon, so here is a "preview" (if that's what you want to call it) of part of the tool, specifically packfile creation.

Koop's Packfile Tool
by Ryan Koop (AbsoluteZero)

USAGE:

```
java -jar KoopsPackfileTool=0.1.jar (-v -- enables verbose printing) [-p=DESTINATION_PACK_PATH] [-b=EXTRACTED_ASSETS_FOLDER_PATH] [list of files **INSIDE** your extracted assets folder that are being included, seperated by spaces]
```


Here is an example...

```
java -jar KoopsPackfileTool=0.1.jar -v -c="C:/test.pak" -b="C:/EpicMickey/Extracted/" "Localize/ENGLISH_NTSC_RVL.dct"
```


No license is included in the download at the moment as this is a temporary tool (until the larger, automatic one is finished) and the source code is a mess, so I will probably not be releasing it (though the final tool will be open source). If you share it, please make sure to credit me in some way (linking back to this post will suffice).

Please note that when reading packfiles, the game expects a certain ordering. For packs with only one or a few files, you shouldn't have to worry about it, but for packfiles containing levels, you will have to manually order the files you reference when executing the script.

If you need to extract your packfiles, use the QuickBMS script [here](https://rampantleaf.github.io/download/epic-mickey.bms).
If you encounter any errors, post them here and I'll fix them as soon as I can.

Enjoy!

DOWNLOAD:


 KoopsPackfileTool-0.1.zip
(15.36 KiB) Downloaded 32 times
