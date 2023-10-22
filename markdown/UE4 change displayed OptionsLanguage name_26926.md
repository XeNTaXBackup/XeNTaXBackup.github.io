## Post #1
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2023-07-01T15:49:55+00:00
- Post Title: UE4: change displayed Options/Language name

Here is my case:
[](https://ibb.co/jT42yyG)

How can I convert "English" -> "Italiano" string in the Options/Language, in UE4 games? Where should I typically search those language strings...? I'm much more experienced with Unity and don't know Unreal Engine that much...
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-07-01T21:48:38+00:00
- Post Title: UE4: change displayed Options/Language name

> Where should I typically search those language strings...?

They should be usually inside of PAK files. Here is an example location for Postal 4
"\POSTAL 4 - No Regerts\Postal4\Content\Paks"

You can use any tools from the wiki to unpack them [http://wiki.xentax.com/index.php/List_o ... gine_Tools](http://wiki.xentax.com/index.php/List_of_Unreal_Engine_Tools)

Then you can search through unpacked files to find texts.
Usually they should be in UEXP, UASSET or INT files.
You can use this method to search [https://ikskoks.pl/searching-text-strin ... commander/](https://ikskoks.pl/searching-text-strings-using-total-commander/)
## Post #3
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2023-07-02T06:32:49+00:00
- Post Title: UE4: change displayed Options/Language name

Yes, of course. These are the basics I already knew. Wanted to know from more experienced users with UE if there are typical paths/filenames to look for such language strings displaying the available languages... Please, notice they are the strings used for the supported languages, not a normal in-game text to localize.

I found a file containing exactly those language strings in the same order of the pic above:

[](https://ibb.co/51dwbpm)

... but it didn't work: even after changing it with a hex-editor in-game still shows Options/Language: "English"

Or maybe they are textures?
## Post #4
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2023-07-02T08:13:17+00:00
- Post Title: UE4: change displayed Options/Language name

Here is the file list:
[https://1drv.ms/t/s!ApMUGr0cuN39gsZyTHh ... g?e=FaXa2Z](https://1drv.ms/t/s!ApMUGr0cuN39gsZyTHhc3EnQnIvncg?e=FaXa2Z)
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-07-02T10:09:22+00:00
- Post Title: UE4: change displayed Options/Language name

> if there are typical paths/filenames to look for such language strings displaying the available languages...

Not sure if I can call myself UE4 expert, but I have modded few UE4 games and I know that each game
can handle such things in a different way. That's why engines like Unity or UE4 even exists - because you can
customize whatever you want - even those language strings.

But anyway, if you can't find what you're looking for in the unpacked files from "Paks" directory,
maybe you should extend your search range to the main game directory using total commander method.
There is a chance that those strings are in the main executable.

By the way, I've checked how it is done in Postal 4 and this game doesn't have any strings for language selection at all.


> Or maybe they are textures?
Yes, it is possible. If you won't be able to find them as strings, your next step should be to go through all textures in the game.
## Post #6
- Username: enarkay
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 26, 2023 12:46 pm
- Post datetime: 2023-07-02T10:35:07+00:00
- Post Title: UE4: change displayed Options/Language name

Coming from github to over here for answering your question. Fortunately, the game has a demo on the steam store page so I was able to download the demo and take a look at the files. It's a texture, not a string.

The texture you're looking for is in the following : ZingangGame\Game\UI\Common\LanguageTexture\T_UI_SelectLanguage.uasset



20230702_193319.png (98.18 KiB) Viewed 123 times



But from next time, at least include some basic information such as the name of the game and the Unreal Engine version when you're asking questions so others can have an easier time helping you out
## Post #7
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2023-07-02T12:59:38+00:00
- Post Title: UE4: change displayed Options/Language name

Uh! What a cohincidence I just found the same analyzing the list of files by their name/dir structure:

```
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage.uasset
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage.uexp

ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage_Sprite_Han.uasset
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage_Sprite_Han.uexp

CROPPED SINGLE LANGUAGES:
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage_Sprite_Language_0.uasset
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage_Sprite_Language_0.uexp
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage_Sprite_Language_1.uasset
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage_Sprite_Language_1.uexp
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage_Sprite_Language_2.uasset
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage_Sprite_Language_2.uexp
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage_Sprite_Language_3.uasset
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage_Sprite_Language_3.uexp
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage_Sprite_Language_4.uasset
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage_Sprite_Language_4.uexp
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage_Sprite_Language_5.uasset
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage_Sprite_Language_5.uexp
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage_Sprite_Language_6.uasset
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage_Sprite_Language_6.uexp
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage_Sprite_Language_7.uasset
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage_Sprite_Language_7.uexp
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage_Sprite_Language_8.uasset
ZingangGame\Content\UI\Common\LanguageTexture\T_UI_SelectLanguage_Sprite_Language_8.uexp
```


...but you seem 1 step ahead    : what tool did you use to display the texture? I need to replace "English" slot with "Italiano".
Can it be edited? Sorry for my UE/UE tools ignorance...

EDIT: I was able to extract the texture with FModel, but how to reimport the modified PNG?
## Post #8
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2023-07-02T14:51:08+00:00
- Post Title: UE4: change displayed Options/Language name

Here are modified PNG and DXT5: [https://1drv.ms/f/s!ApMUGr0cuN39gsoKLt1 ... w?e=p4X6ji](https://1drv.ms/f/s!ApMUGr0cuN39gsoKLt1Wg2A04HqZrw?e=p4X6ji) 
I tried to paste DXT5 into original .uexp as described at [http://modderbase.com/showthread.php?tid=57](http://modderbase.com/showthread.php?tid=57) but the game crashes at launch with corrupt data...
## Post #9
- Username: enarkay
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 26, 2023 12:46 pm
- Post datetime: 2023-07-02T18:29:54+00:00
- Post Title: UE4: change displayed Options/Language name

LanguageTexture.zip
(26.33 KiB) Downloaded 14 times



Here you go
## Post #10
- Username: enarkay
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 26, 2023 12:46 pm
- Post datetime: 2023-07-02T18:30:25+00:00
- Post Title: UE4: change displayed Options/Language name

zinganggame.jpg (83.45 KiB) Viewed 96 times



Tested in-game to make sure it works without breaking.
## Post #11
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2023-07-02T18:36:51+00:00
- Post Title: UE4: change displayed Options/Language name

Thank you, in the meanwhile I was able to solve it by myself (the "guide" to copy & paste DXT data into the .uexp was wrong, had to find the right offset where to paste the DXT5 data by trial & error) 

Do you know a 3rd party tool to simplify texture replacements like this for the future, or did you use a hex-editor as well?
