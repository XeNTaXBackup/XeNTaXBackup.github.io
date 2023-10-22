## Post #1
- Username: Abdul Haq
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Mar 27, 2023 9:30 pm
- Post datetime: 2023-05-27T21:35:55+00:00
- Post Title: Nioh Complete Edition | Help Create a New Localization

Hello, I want to make a new Localization for the game, and I don't know anything. Is there someone who can explain to me how to do it? I know how to modify other engines such as Unity and UE4, but this is the first time I try to modify a private engine.
## Post #2
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2023-05-31T12:51:58+00:00
- Post Title: Nioh Complete Edition | Help Create a New Localization

NIOH (1 + 2 - with minor differencies) COMPLETE EDITION - Translating Tutorial by .:i2k:.
~~~~~~~~~~~~~~~~~~~~~~~~~

Game's premiere on PC (Nioh): 2017.02.07
Game's Engine version: x
Game update: doesn't matter


PREREQUISITES - DOWNLOADS:
---------------------------------------
* - QuickBMS generic files extractor and reimporter 0.12 --- [https://aluigi.altervista.org/papers/quickbms.zip](https://aluigi.altervista.org/papers/quickbms.zip) -- (no matter if there is a newer one!)
* - nioh.bms -- [http://aluigi.org/bms/nioh.bms](http://aluigi.org/bms/nioh.bms)
* - Nioh Complete Edition DAT Text Tool by Delutto -- [https://zenhax.com/viewtopic.php?f=12&t ... h+Complete](https://zenhax.com/viewtopic.php?f=12&t=7596&hilit=Nioh+Complete)
EDIT: new Nioh Tools download source >>> CLICK HERE
* - Notepad++ installed on your Windows system -- (recommended unicode text editor) 
* - "archive_19.lnk" file (from Nioh Complete Edition\archive\ folder)

MAKE A BACKUP OF THIS FILE (or rename in place): "archive_19.lnk"!


~~~~~~~~~~~~LET'S START THE WORK!~~~~~~~~~~~~

01 ---- Launch QuickBMS with "quickbms.exe"
01/a - Select "nioh.bms"
01/b - Select "archive_19.lnk" file
01/c - Select "EXTRACTED" folder
QuickBMS will extracting all files from the *.lnk file.

02 ---- Launch Nioh Complete Edition DAT Text Tool by Delutto
Export *.dat files into *.txt files (batch command highly recommended)

English (US & UK) files: for Nioh 1
- 000000a6.dat
- 0000000b.dat
- 000000b4.dat
- 000000b8.dat
- 000000bc.dat
- 000000c0.dat
- 000000c4.dat
- 000000c8.dat
- 000000cc.dat
- 000000d0.dat
- 000000d4.dat
- 000000d8.dat
- 000000dc.dat
- 000000e0.dat
- 000000e4.dat
- 000000e8.dat
- 000000ec.dat
- 000000f1.dat
- 000000f4.dat
- 00000001.dat
- 0000002d.dat
- 0000004e.dat
- 0000006f.dat
- 0000007a.dat
- 0000009b.dat
- 0000010a.dat
- 00000017.dat
- 00000022.dat
- 00000038.dat
- 00000043.dat
- 00000059.dat
- 00000064.dat
- 00000085.dat
- 00000090.dat
- 00000100.dat

03 ---- Translate all the files!

04 ---- Launch Nioh Complete Edition DAT Text Tool by Delutto
Import *.txt files into *.dat files (batch command highly recommended)
Putt the NEW dat files in another folder with name like "TRANSLATED"

05 ---- Launch "reimport3_localizations.bat" file (in QuickBMS' folder)
05/a - Select "nioh.bms"
05/b - Select "archive_19.lnk" file
05/c - Select "TRANSLATED" folder
The selected "archive_19.lnk" file will be updated!

06 ---- Put the updated/new *.lnk file back to Nioh Complete Edition\archive\ folder and overwrite it!

07 ---- Testing ingame!

Pictures from Hungarian translation (Nioh 1):




Pictures from Hungarian translation (Nioh 2):
## Post #3
- Username: Abdul Haq
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Mar 27, 2023 9:30 pm
- Post datetime: 2023-05-31T22:36:57+00:00
- Post Title: Nioh Complete Edition | Help Create a New Localization

i can't download Nioh Complete Edition DAT Text Tool by Delutto. And can you Help me with font?
[لقطة الشاشة 2023-06-01 024411.png](https://xentaxbackup.github.io/file/23862_لقطة الشاشة 2023-06-01 024411.png)
## Post #4
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2023-06-01T07:25:25+00:00
- Post Title: Nioh Complete Edition | Help Create a New Localization

Hi,

- Here's program: Nioh Complete Edition DAT Text Tool by Delutto - works with Nioh 1-2.
[https://www.mediafire.com/file/0zn610zu ... o.exe/file](https://www.mediafire.com/file/0zn610zu1nm0w4i/Nioh_Complete_Edition_DAT_Text_Tool_by_Delutto.exe/file)

- About fonts: Sorry, I can't help you out. Hungarian language is supported by the game's engine (with mild comprimeses), so I didn't searched them in game's archives for editing.
## Post #5
- Username: Abdul Haq
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Mar 27, 2023 9:30 pm
- Post datetime: 2023-06-01T10:57:01+00:00
- Post Title: Nioh Complete Edition | Help Create a New Localization

Thank you for your response. I am trying to localize the game into Arabic, but when I change text to Arabic, the game crashes. Do you know a solution?
And one more thing, why do the menu texts not change? Like press any button and a new game
## Post #6
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2023-06-01T12:28:32+00:00
- Post Title: Nioh Complete Edition | Help Create a New Localization

Nioh 1-2 has graphics in they menus - so you have to find them in the archives manually and convert to editable format (and then back) to edit in Photoshop/GIMP or other.
I didn't bother with the menu system because our players really don't care - it's more important that submenu items are accessable. 

~~~~

About the freezing:

In the translation phase, try "Character sets" > "Arabic" > "Windows-1256" under "Encoding" in Notepad++
I suppose in your language that's default.

If that still doesn't work, then under "Encoding" choose "Convert to UTF 8-BOM" (with opened documents, ofc) - beware: ALWAYS make backups!

"UTF-8 also includes a variety of additional international characters, such as Chinese characters and Arabic characters."

Sorry if they didn't worked out - as I mentioned: I didn't care font sets 'cause I didn't have to.
## Post #7
- Username: Abdul Haq
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Mar 27, 2023 9:30 pm
- Post datetime: 2023-06-01T12:55:18+00:00
- Post Title: Nioh Complete Edition | Help Create a New Localization

Thank you again, do you know anyone or a WebSite that can help me or do you have any ideas to help me modify the Font
Fonts are inside archive_05, It contains 8 files
[لقطة الشاشة 2023-06-01 173045.png](https://xentaxbackup.github.io/file/23865_لقطة الشاشة 2023-06-01 173045.png)
