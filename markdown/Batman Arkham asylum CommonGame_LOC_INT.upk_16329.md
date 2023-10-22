## Post #1
- Username: abuali
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Dec 13, 2010 12:48 am
- Post datetime: 2017-05-27T04:35:50+00:00
- Post Title: Batman Arkham asylum CommonGame_LOC_INT.upk

I'm​ trying to add Arabic characters support to the game.
The game is using two kinds of fonts in two separate .upk files

For the menu/hud it uses the file Startup_INT.upk which have inside it fonts_en.GFxMovieInfo, I have managed to modify that because it is a SWF font, a familiar extension that I knew.
After decompress the upk then using the hex editor only, because the upk unpacker/repacker it gives me error for bad name font_en.GFxMovieInfo.


But for the in-game subtitles it uses this file CommonGame_LOC_INT.upk, this file contains two the font in 2Dtexture/.font format and also an audio files.
I created an Arabic font using udk 2009, then I:
1- it is useless to use upk unpacker repacker beacuse it gives the same error as the previous file when I try that, so...

2- using the hex editor, I added all new files at the last offset of the CommonGame_LOC_INT.upk, then I edited the offset and size information of the Mediumfont to match the new files that I added, but the error came like this
The game is expecting the "old size file" but it gots the "new size file".

In other words that I need to find where the information "that I missed" for the size of that file are saved then change it to what desired...

For Startup_INT.UPK I didn't face this problem hence the information​ were in the same file, but in the other one, I don't know, might be in the same file but wirtten in different format? 

Take a look at the Japaneseation MOD, it might get you some idea ti share.

[http://blog.goo.ne.jp/koz_2006/e/236690 ... 17ce7147ee](http://blog.goo.ne.jp/koz_2006/e/236690009a219707ec1b3e17ce7147ee)
## Post #2
- Username: ‌GHOST DΕAD
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun May 21, 2017 10:36 am
- Post datetime: 2017-05-27T08:41:52+00:00
- Post Title: Batman Arkham asylum CommonGame_LOC_INT.upk

dont change size of files...
hex editor?! hex just can work on swf & fws...
but you never can edit texture2d in hex... edit texture just can edit skin mode ind mabye give eror or crasjed or pixel problem in game
give me your subtitle folder (int) and upk files and cofig folder...
انا عسادُ بکم
یا اخی... اسعی مع یودی کی ٢٠١٠
## Post #3
- Username: abuali
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Dec 13, 2010 12:48 am
- Post datetime: 2017-05-27T09:44:57+00:00
- Post Title: Batman Arkham asylum CommonGame_LOC_INT.upk

> Reply from ‌GHOST DΕAD
>
> dont change size of files...
hex editor?! hex just can work on swf & fws...
but you never can edit texture2d in hex... edit texture just can edit skin mode ind mabye give eror or crasjed or pixel problem in game
give me your subtitle folder (int) and upk files and cofig folder...
انا عسادُ بکم
یا اخی... اسعی مع یودی کی ٢٠١٠
Here's the original font files
[https://mega.nz/#!7Z9mHQxL!0wXXa8ahPPXE ... maUWFW3kFE](https://mega.nz/#!7Z9mHQxL!0wXXa8ahPPXENCGnXuI3xezb-zVqLnETbmaUWFW3kFE)
I didn't have the config file ATM nor .int.
And btw I didn't understand what you write in arabic.
