## Post #1
- Username: elybelbely
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 05, 2018 9:27 pm
- Post datetime: 2018-11-02T09:33:10+00:00
- Post Title: we happy few localization

I want to translate we happy few
so I unpacked "GlimpseGame-WindowsNoEditor" and got "GlimpseGame.locres" in "\Content\Localization\GlimpseGame\en" and translated a few lines and packed again using "quickbms" but nothing changed! and I cant find font files to change them.
any help?
## Post #2
- Username: elybelbely
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 05, 2018 9:27 pm
- Post datetime: 2019-02-28T10:58:02+00:00
- Post Title: we happy few localization

ANY Help? I translated the game. but I need to change the font. There is txt help in game but it's just for steam. I want to edit font without steam.

> ----------------------------------------------------
>
> We Happy Few : Steam Workshop Community Localization
>
> ----------------------------------------------------
>
> 
>
> We Happy Few enables players to take localization (translating the game into a different language)
>
> into their own hands, by allowing them to publish custom translations to Steam as Workshop items.
>
> If anyother player subscribes to this localization item, the new language will appear ingame under
>
> the language options.
>
> 
>
> This README documents this process and the accompanying SteamWorkshopPublisher tool.
>
> 
>
> ----------
>
> QUICKSTART
>
> ----------
>
> 
>
> * To create a new localization:
>
> 
>
> 	1) first accept http://steamcommunity.com/sharedfiles/w ... lagreement if you haven't yet
>
> 
>
> 	2) in <SteamLibrary>\steamapps\common\WeHappyFew\GlimpseGame\Localization\:
>
> 	   copy GlimseGame-native.po to GlimpseGame-mine.po
>
> 
>
> 	3) edit GlimpseGame-mine.po with https://poedit.net/
>
> 
>
> 	4) run the following command in <SteamLibrary>\steamapps\common\WeHappyFew\Engine\Binaries\Win64:
>
> 
>
> 		SteamWorkshopPublisher.exe -createLocalization -culture=<two letter language iso code>
>
> 		-languageName="<name you want to show up in the language options ingame>"
>
> 		-poFile="<full path to GlimpseGame-mine.po>" -nativePoFile="<full path to GlimpseGame-native.po>"
>
> 		-title="<Steam Workshop item title>" -description="<Steam Workshop item description>"
>
> 		<optional custom font support via -replaceFonts , see Custom Font Support section below>
>
> 
>
> 	5) write down the published file id the tool reports
>
> 
>
> * To update an existing localization:
>
> 
>
> 	1) make the necessary edits & updates
>
> 	2) run the same command but with -updateLocalization in stead of -createLocalization
>
> 		and add the parameter -publishedFileId=<the id you wrote down>
>
> 
>
> * To get a new language ingame:
>
> 
>
> 	1) go to We Happy Few's Steam Workshop in the steam client
>
> 	2) subscribe to the localization item of your choice
>
> 	3) new language should appear as a language option ingame
>
> 
>
> 
>
> --------------------------------------------
>
> Creating a new localization for We Happy Few
>
> --------------------------------------------
>
> 
>
> Our localization files use the Portable Object or .po file format, an industry standard localization
>
> format. To create a new localization, you will have to create a copy of GlimpseGame-native.po and
>
> replace the English translations with translations in the language you want to add. You'll find
>
> this native .po file in <SteamLibrary>\steamapps\common\WeHappyFew\GlimpseGame\Localization\
>
> 
>
> To edit .po files you can use PoEdit, which is available as a free download at https://poedit.net/
>
> 
>
> To publish this new translation to the Steam Workshop, we have provided a command line tool:
>
> SteamWorkshopPublisher.exe. This tool is installed with the game, you'll find it by default at
>
> <SteamLibrary>\steamapps\common\WeHappyFew\Engine\Binaries\Win64 . You need to provide this tool
>
> with several parameters:
>
> 
>
> - a command, which can be createLocalization or updateLocalization
>
> - the culture iso code of the language you add
>
> - the name of the language as it will show up ingame
>
> - the full path of the original GlimpseGame-native.po file you used to create your translation
>
> - the full path of your own edited localization, eg GlimpseGame-mydutchtranslation.po
>
> - a title and description you want your  item to have in the Steam Workshop
>
> 
>
> Example command:
>
> 
>
> 	SteamWorkshopPublisher.exe -createLocalization -culture=nl -languageName="Dutch"
>
> 	-poFile="c:\temp\GlimpseGame-dutch.po>" -nativePoFile="c:\temp\GlimpseGame-native.po"
>
> 	-title="Dutch Translation" -description="My translation of We Happy Few in Dutch"
>
> 
>
> The workshop item will automatically be published as a public item.
>
> 
>
> -------------------
>
> Custom Font Support
>
> -------------------
>
> 
>
> The fonts used in We Happy Few are not able to render all conceivable scripts. If your localized 
>
> language needs custom fonts to support a specific script - eg thai, japanese or chinese characters,
>
> the tool now offers support for replacing fonts in the game with custom provided fonts. You have the
>
> option to either replace all fonts with a single font, or replace individual fonts with one of
>
> your chosing, or a combination of both - replacing several fonts with a fallback for the rest. This
>
> allows you to support any language while maintaining a visually pleasant UI experience. Replacement fonts
>
> will only be used for those unicode characters that are present in the custom font. If the game wants to
>
> render characters your custom font does not support, it will fall back to the fonts present in the game.
>
> 
>
> To enable this system, we have added an additional command line parameter -replaceFonts that can be passed
>
> when creating or updating a localization. Here are two examples on how to use it:
>
> 
>
>     1) -replaceFonts "<path to font>"
>
> 
>
> 	when ran with a single path to a font, this font will replace *all* ingame fonts for the characters
>
> 	it contains. Characters not present in the font will still be rendered with the usual ingame fonts.
>
> 
>
> 	2) -replaceFonts "<originalFontName1>;<path1>;<originalFontName2>;<path2>"
>
> 
>
> 	when called with a ;-separated list like above, the game will replace font face originalFontName1
>
> 	with the font at path1 and font face originalFontName2 with the font found at path2
>
> 
>
> 	3) -replaceFonts "<originalFontName1>;<path1>;<originalFontName2>;<path2>;<fallbackPath>"
>
> 
>
> 	you can also add an additional path at the end as a general fallback - it will replace 1 and 2 like
>
> 	before, but it will also replace all other fonts with the one specified at fallbackPath.
>
> 
>
> Note that we also support wildcards at the end of the original fontname. For instance:
>
> 
>
> -replaceFonts="SemplicitaLight;c:\fonts\thaiPlicitaLight.ttf;Semplicita*;c:\fonts\thaiPlicita.ttf;c:\fonts\thaiDefault.ttf"
>
> 
>
> will ensure the following substitutions:
>
> 
>
> 'SemplicitaLight'                          -> c:\fonts\thaiPlicitaLight.ttf
>
> All other fonts starting with 'Semplicita' -> c:\fonts\thaiPlicita.ttf
>
> All other fonts                            -> c:\fonts\thaiDefault.ttf
>
> 
>
> ------------------
>
> Publishing Remarks
>
> ------------------
>
> 
>
> 1) In order for SteamWorkshopPublisher to work, your local Steam Client must be running & logged on
>
> 
>
> 2) Anyone who wants to publish to the Steam Workshop needs to accept Valve's workshop legal agreement.
>
> 	If you have not accepted this agreement yet, your published items will not be public until you have.
>
> 	If that is the case, the tool should inform you of this, including a link to the agreement:
>
> http://steamcommunity.com/sharedfiles/w ... lagreement
>
> 
>
> 3) When you publish an item, the tool will give you the corresponding PublishedFileId. Write this down if
>
> 	you want to be able to update your item.
>
> 
>
> ---------------------------------
>
> Updating an existing localization
>
> ---------------------------------
>
> 
>
> The process for updating an existing localisation is almost the same. Edit your localization, and then
>
> run the same command as you used for creating the localization, only specifying -updateLocalization as
>
> command in stead of -createLocalization, and adding the parameter -publishedFileId=xxxxx passing the
>
> id you received when you created the item.
>
> 
>
> If you have lost this id, you can look it up by opening your workshop item in the Steam Workshop. The
>
> url at the top will have this form: http://steamcommunity.com/sharedfiles/f ... /?id=<your id>&searchtext=
>
> 
>
> -------------------------
>
> Installing a localization
>
> -------------------------
>
> 
>
> To get a new language, it suffices to subscribe to the workshop item in the Steam Workshop.
>
> 
>
> Once subscribed, when you next launch We Happy Few, the new language should appear as an option in the
>
> language selection dropdown. There are some exceptions you should be aware of:
>
> 
>
> 1) You cannot provide community localization for the languages We Happy Few ships with (English and French)
>
> 2) If the language still does not appear, something has gone wrong in the process

These are files in "GlimpseGame-WindowsNoEditor[.pak]\Content\UI\Fonts"
[http://www.filetolink.com/03f618f368](http://www.filetolink.com/03f618f368)
## Post #3
- Username: nourancairo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Mar 02, 2019 12:05 am
- Post datetime: 2019-03-01T16:14:17+00:00
- Post Title: we happy few localization

انت بتعرف تستخدم   quick bms  ????     قولى  ازاى استخدمه مع لعبه  la noire     

وهو  بيطلع ملفات اللغة  وبيدمجها باللعبة   ولا استخدامه ايه ؟؟؟؟
