## Post #1
- Username: nilelle
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 23, 2020 4:54 am
- Post datetime: 2020-07-24T16:32:57+00:00
- Post Title: Halo Master Chief Collection Localization

I found EN_Global.bin file but I am not sure whether it is subtitle file. Can any one help me where is the subtitle file and how I can open it?I opened this file with hex editor.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-24T22:14:38+00:00
- Post Title: Halo Master Chief Collection Localization

You can use programs like Total Commander to search for text in this game
[https://imgur.com/a/ocdz6BL](https://imgur.com/a/ocdz6BL)
## Post #3
- Username: nilelle
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 23, 2020 4:54 am
- Post datetime: 2020-07-24T23:18:11+00:00
- Post Title: Halo Master Chief Collection Localization

I couldnt use can you describe more clear?
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-25T09:31:07+00:00
- Post Title: Halo Master Chief Collection Localization

Ok, try like this:
1. Extract data from PAK to some folder (using UE4 pak unpacker or whatever [https://zenhax.com/viewtopic.php?f=9&t=1005](https://zenhax.com/viewtopic.php?f=9&t=1005) )
2. Open Total Commander
3. Go to directory with unpacked files
4. Click ALT+F7
5. Type text from game which you want to search for
6. Search the text
7. Go to result file, open it in hex editor and analyze the file
## Post #5
- Username: nilelle
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 23, 2020 4:54 am
- Post datetime: 2020-07-25T17:12:30+00:00
- Post Title: Halo Master Chief Collection Localization

I opened it but pak file isn't subtitle file it's look like engine localization. I tried translate the EN_global.bin file but hex editor is character limit.When I translated a word sentences came together.I need like a text tool or another program.Here is the file.
[EN_Global.7z](https://xentaxbackup.github.io/file/18518_EN_Global.7z)
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-26T17:53:51+00:00
- Post Title: Halo Master Chief Collection Localization

As I have searched the web, I saw that this game is on UE4 engine which uses PAK files for storing content.
After you unpack PAK with UE4 unpacker tool, you could search for text as I told you and you probably would find
bunch of locres files which are covered by some other tools already.

So if you want to be really sure where the text is stored, you need to search for some string from game in
hex editor and replace that string. If you see changes in game, then you would be sure that you are
dealing with language file that game uses.
