## Post #1
- Username: Osomatsufan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 02, 2020 1:43 am
- Post datetime: 2020-12-01T18:06:51+00:00
- Post Title: Help extracting audio clips from japanese android game?

Hello. I have been trying to extract the songs from this game: [https://apps.qoo-app.com/en/app/3636](https://apps.qoo-app.com/en/app/3636)

However, I had only a little success. From what I gathered, it is a Unity game, so I could extract the songs that are in the apk. However, it is one of these games that install extra data after installed, so there are many many songs that are not in the apk itself.

From here, what I was able to do was copying the files from the "\Android\data\com.avex.pine.towerdefense\files" directory after having the game installed on my phone. It had similar files to the extracted .apk, but none of the regular tools (like Unity Assets Bundle Extractor or Asset Studio) seemed to work. They *could* open the files, but there were no Audio Clips in there.

Upon closer inspection, I noticed that the song files were not in the same files as the others. Instead, they looked like standalone files, named like "sounds___bgm___bgm_<XX>", where <XX> is a number, such as "sounds___bgm___bgm_02". But they have no file extension. The ogg extractor I found somewhere does not work and neither do the regular unity extraction tools. Media players can't identify this file and all this Online File Type Checker could gather was that this is a binary file. Great.

Here is a sample file: [http://www.mediafire.com/file/nzyywgfdi ... gm_58/file](http://www.mediafire.com/file/nzyywgfdiicnep8/sounds_bgm_bgm_58/file)

What I could gather was that it seems to follow the file structure from the original project, but besides that...

I have no idea of how to procceed. Anyone have any ideas, please? =(
