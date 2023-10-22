## Post #1
- Username: Naroax
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 31, 2014 1:44 am
- Post datetime: 2014-09-26T11:39:40+00:00
- Post Title: Text Dump

Hi  

This is my first topic, all tho, It's not a request to translate a game or extract something, It's more like " show me how ".

I'll just go straight to subject, I love reading game scripts, ( not BMS/Maxscripts lol ) i mean games transcripts, the whole script that contains everything that has been said in the game.

Text Dump from games is already possible, and to check that you can look up on the internet for MGS 1 script, so does somebody have any idea how to do that? I would love to extract texts and translate them to my native language  

Thanks in advance.

EDIT : and about not uploading any samples is because I have a game but I don't know where is the file that contains text/dialogue from the whole game.
## Post #2
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-09-26T16:32:16+00:00
- Post Title: Text Dump

Localization data are commonly stored in XML, CSV, text flat file, or a custom binary format. The first three are easy to modify, while the last is harder. To find those files, first you'll have to extract whatever archive the files are in, if applicable. Then, use a file searching program to search for a known string, and pin down the file the text is in. Open it with a hex editor or text editor, and if the format isn't too odd, you can go modify it. An important thing to consider is encoding and font support. If the game does not support the encoding you want to translate into, you're mostly out of luck. Fortunately, more games are being written with Unicode support. The font issue is a tricky one. Most fonts are rendered into a raster texture, and you'll have to make corresponding font definition files so the game can locate each glyph. This can get difficult for languages with unique characters for each word (such as with Chinese). You'll also need to find a font that actually looks nice in-game.
## Post #3
- Username: Naroax
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 31, 2014 1:44 am
- Post datetime: 2014-09-26T19:56:05+00:00
- Post Title: Text Dump

Thanks for the reply Gmman, now I'm not a coder and I'm keen to this field, only interested in texts at the moment  

care to write a quick tuto if you may of course  or are there any tools to do such thing?
## Post #4
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-09-28T01:04:59+00:00
- Post Title: Text Dump

I'm not sure if there's a catch-all localization app. In any case, the minimum tool you need is a hex editor. With a hex editor, you can explore binary files. If you state what game you're working on, maybe we can track down the file for you.
## Post #5
- Username: Naroax
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 31, 2014 1:44 am
- Post datetime: 2014-09-28T09:57:27+00:00
- Post Title: Text Dump

Thanks a lot Gmman, alright the game is Asassin's Creed 3, the English of that period was amazing so I would love to get the script for the game.
