## Post #1
- Username: ponlork
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jul 18, 2011 1:01 pm
- Post datetime: 2020-08-04T10:51:42+00:00
- Post Title: PS1 FF7 International LPK and NPK archives

I followed this Russian guide on how to decompress LPK and NPK archives from Playstation 1 games, I was able to decompress the .tim files but I was wondering if there's a way to recompress it back to .LPK and .NPK for modding purposes.

Here's the guide on how to decompress. I used google translate to translate it:  [https://habr.com/ru/post/347382](https://habr.com/ru/post/347382)
[DATF001.zip](https://xentaxbackup.github.io/file/18557_DATF001.zip)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-08-04T18:53:16+00:00
- Post Title: PS1 FF7 International LPK and NPK archives

There is whole long guide about modding FF7
[http://q-gears.sourceforge.net/gears.pdf](http://q-gears.sourceforge.net/gears.pdf)
## Post #3
- Username: ponlork
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jul 18, 2011 1:01 pm
- Post datetime: 2020-08-05T02:20:27+00:00
- Post Title: PS1 FF7 International LPK and NPK archives

Thank you for the ebook. Looks like a fascinating read. I'll delve into it more thoroughly later. I believe FF7 has been mostly documented but in the Japanese international version there's a  bonus 4th disc that contains these LPK and NPK archives that is more obscure and haven't really been analyzed. I tried using lzss / unlzss in ff7tools v1.3  but it couldn't decompress or recompress the archives. I finally was able to decompress it using the Russian guide but I don't know how to recompress it back to LPK.
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-08-05T13:32:23+00:00
- Post Title: PS1 FF7 International LPK and NPK archives

You are very lucky, because it seems that packing function 
has been added to this tool today 
[https://github.com/Hedzin/SquareNPK-unp ... K-unpacker](https://github.com/Hedzin/SquareNPK-unpacker/tree/master/SquareNPK-unpacker)
## Post #5
- Username: ponlork
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jul 18, 2011 1:01 pm
- Post datetime: 2020-08-05T16:20:46+00:00
- Post Title: PS1 FF7 International LPK and NPK archives

Ah yes I was asking the Russian author for some help and I finally got it to work. I mainly wanted to replace the menu in a PSX game that also uses LPK archives. The game is called RPG Maker and I wanted to make my own RPG with custom assets, however the lpk archives had me perplexed. but now I'm able to modify it.
[menu_mod.jpg](https://xentaxbackup.github.io/file/18567_menu_mod.jpg)
