## Post #1
- Username: sumilek86
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 04, 2021 5:16 am
- Post datetime: 2021-11-04T21:43:25+00:00
- Post Title: Text from the game  - Rustler

Hi, I need some help. I'm not very technical. And I don't know if I'm posting in the right forum. I wanted to pull text from the game - Rustler. Found out that it is Unity, found and tutorial and tried different programs from UABE to UnityEx etc. Theoretically they should be in the files - resources.assets, sharedassets0.assets.... There's just text in there about licenses. I've also searched other .assets files. Unfortunately I didn't find anything. I assume the programs are on older Unity and this new one can't open everything well. Thank you very much for your help.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-06T21:47:38+00:00
- Post Title: Text from the game  - Rustler

For Unity games it's always best to use UnityEx or AssetStudio.

If you can't find the text files by just checking the assets, 
you can use total commander method [https://ikskoks.pl/searching-text-strin ... commander/](https://ikskoks.pl/searching-text-strings-using-total-commander/)
(It can search also in binary files)

After you'll find something, you can try to view file's content in some hex editor (like Hex Workshop)
and just try to change one letter in some string to check it later during gameplay.
## Post #3
- Username: sumilek86
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 04, 2021 5:16 am
- Post datetime: 2021-11-08T10:04:43+00:00
- Post Title: Text from the game  - Rustler

Thanks, I found the text and pulled it up with UnityEx. I changed a word in the text via Hex Workshop, but when I do it back via UnityEx, the game throws me an error and doesn't work.Is it possible that the game has some protection when changing the text? Could you advise me on a specific program to pull text (unitytext)? That Hex W. is a strange one for me, I'm not very good with it. Thank you
## Post #4
- Username: sumilek86
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 04, 2021 5:16 am
- Post datetime: 2021-11-08T14:31:03+00:00
- Post Title: Text from the game  - Rustler

The text is in this final file, see attachment. Someone on Zenhax pulled it up for me, but I don't know how to pull it up myself and back it up, and with what program.  The file name is ,,resources_00001.-8,,  

[https://ulozto.cz/file/SqPmLDybxl7n/res ... y4rGIzZN==](https://ulozto.cz/file/SqPmLDybxl7n/resources-00001-8#!ZGOuMwR2AGtmAQAvLmNjMzSyAmp4BT43oUucHQpmLwy4rGIzZN==)
## Post #5
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-08T22:05:45+00:00
- Post Title: Text from the game  - Rustler

> Is it possible that the game has some protection when changing the text?
It's possible. I saw many Unity games that had protected assets. In most cases it was XOR or AES.

> Could you advise me on a specific program to pull text (unitytext)?
Maybe "-8" files aren't supported by any existing tool and someone needs to write a custom exporte/importer for translation.

> but I don't know how to pull it up myself and back it up, and with what program.
You can do this with UnityEx. This tool also supports importing files.
(see this "Import files" button on this screenshot [http://wiki.xentax.com/images/b/bd/UnityEx_1.png](http://wiki.xentax.com/images/b/bd/UnityEx_1.png))
## Post #6
- Username: sumilek86
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 04, 2021 5:16 am
- Post datetime: 2021-11-09T08:40:50+00:00
- Post Title: Text from the game  - Rustler

I have this specific program from the picture and I'm returning it via import, but unfortunately it just doesn't work. Would you or anyone be able to write it to the specific file ,,resources_00001.-8,, see link? Thank you very much for your help
## Post #7
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-09T20:53:09+00:00
- Post Title: Text from the game  - Rustler

You could also try to use Unity Text [https://i.imgur.com/MUGzvYD.png](https://i.imgur.com/MUGzvYD.png)
Maybe it will work for you.

[https://forum.zoneofgames.ru/topic/47582-unitytext/](https://forum.zoneofgames.ru/topic/47582-unitytext/)
## Post #8
- Username: sumilek86
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 04, 2021 5:16 am
- Post datetime: 2021-11-09T22:50:17+00:00
- Post Title: Text from the game  - Rustler

Great, thank you very much. I'll check it out.
