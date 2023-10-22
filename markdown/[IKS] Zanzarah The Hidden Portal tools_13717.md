## Post #1
- Username: Researchman
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2015-12-23T21:29:58+00:00
- Post Title: [IKS] Zanzarah: The Hidden Portal tools

Hello. I want to share with you my collection of Python scripts, which I wrote to translate Zanzarah: The Hidden Portal game.

* PAK file *
First step to make full localisation of this game is unpacking PAK archive. You don't have to repack 
this archive, because game reads new files from game directory (just like in Telltale games).

To unpack all files from DATA_0.PAK file, just use my Zanzarah PAK tool.
Usage: <script.py> DATA_0.PAK

* FBS files *
All text from this game is in two FBS files: _fb0x02.fbs and _fb0x06.fbs
My first script can unpack text to simple TXT file, so it can be translated easily even in Notepad.
To unpack all text from FBS file, just use my Zanzarah FBS unpacker.
Usage: <script.py> _fb0x02.fbs

When you finish translating text, you may want to change chars from your native language to chars recognized by game. To do that, you can use my Zanzarah Char Replacer.
Usage: <script.py> _fb0x02_skrypt.txt
But first you have to edit this tool! For example in Polish language there is letter "Ł" and i replaced it to "Â" char by this line ".replace('Ł', 'Â')". You just need to change letter on the left.

And the last step is packing text to new FBS file, you can do that using my Zanzarah FBS repacker.
Usage: <script.py> _fb0x02_skrypt.txt _fb0x02_repack_data.dat

If you want to see some examples, you can download polish translation here [http://ikskoks.pl/download/spolszczenie ... en-portal/](http://ikskoks.pl/download/spolszczenie-do-zanzarah-the-hidden-portal/)



And all tools you can download below.
Source code available!
You need Python 2.7.5 to run these tools!
[IKS ZANZARAH TOOLS.zip](https://xentaxbackup.github.io/file/10199_IKS ZANZARAH TOOLS.zip)
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-12-26T20:44:58+00:00
- Post Title: [IKS] Zanzarah: The Hidden Portal tools

This doesn't run using Python 3.5.1?
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2015-12-26T21:29:43+00:00
- Post Title: [IKS] Zanzarah: The Hidden Portal tools

> Reply from Mr.Mouse
>
> This doesn't run using Python 3.5.1?
No, sorry. Only older version are able to handle this code.
