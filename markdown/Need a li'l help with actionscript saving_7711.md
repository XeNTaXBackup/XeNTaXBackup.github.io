## Post #1
- Username: get8p
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 18, 2011 11:24 pm
- Post datetime: 2011-11-19T13:06:51+00:00
- Post Title: Need a li'l help with actionscript saving

Ok, so what I got is swf game, which saves on a computer. Piece of it's code responsible for saving:

> function displaySaveData()
>
> {...
>
>     {
>
> _root["saveGameInfo" + s] = SharedObject.getLocal(cookieName + s);
>
>         duplicateMovieClip(_root.saveData.gameDataBox, "gameDataBox" + s, s);
>
>         saveData["gameDataBox" + s]._x = 211;
>
>         saveData["gameDataBox" + s]._y = 30 + ySpacing;
>
>         saveData["gameDataBox" + s].myNum = s;
>
>         if (_root["saveGameInfo" + s].data.gameSaved == true && _level0.player.account.loggedIn == true)
>
>     {
>
>         saveData["gameDataBox" + s].saveGameName = _root["saveGameInfo" + s].data.saveGameName;
>
>         saveData["gameDataBox" + s]._alpha = 100;
>
>         saveData["gameDataBox" + s].bn.enabled = true;
>
>     }
>
> ...

So, at Win7 it save the files at

> C:\Users\%USERNAME%\AppData\Roaming\Macromedia\Flash Player\#SharedObjects\%FOLDER%\localhost\...
where "..." - is the path to where was .swf file when it was saving.

For example

> ...\localhost\game.swf
- which means that the .swf was at root of some disc, when it was saving. btw, "game.swf" in this path is also a folder, where the savefiles stores.

or

> ...\localhost\Users\%USERNAME%\Desktop\game.swf
- which means that the .swf was at Desktop, when it was saving.

As I understand, _root is variable, and the computer itself shows it a way to cookie storage.
What I want to do is force the game save files to it's folder, for example, to "./save/". But I can't do that, as there is no folder in the code written for_root variable. So either I gotta change it's to some other variable, and indicate it's destination folder, or indicate the destination folder for _root in the code.

Any help/tips appreciated.
