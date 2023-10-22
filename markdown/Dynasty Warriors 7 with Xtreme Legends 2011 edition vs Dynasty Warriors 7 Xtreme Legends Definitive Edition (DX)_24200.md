## Post #1
- Username: qrst
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 03, 2021 9:56 pm
- Post datetime: 2021-07-04T17:43:56+00:00
- Post Title: Dynasty Warriors 7 with Xtreme Legends 2011 edition vs Dynasty Warriors 7 Xtreme Legends Definitive Edition (DX)

Hi everyone. I'm new here & totally a noob, and I would appreciate someone to tell me few things:
A) Is it possible to create English patch to the old Dynasty Warriors 7 with Xtreme Legends 2011 edition?
B) If it is, can someone be bothered to give me step-by-step guide to help me do the following:
1. How to open & then extract English text from .bin & .idx files? That's what I need to do with Dynasty Warriors 7 Xtreme Legends Definitive Edition (DX) files.
2. How to exchange Japanese text with English text implanting them in the same type of files? That's what I need to do with Dynasty Warriors 7 with Xtreme Legends 2011 edition files.
To summarize, I need to make a new English patch for the old Dynasty Warriors 7 with Xtreme Legends 2011 edition, only I want to use the authentic translation used in Dynasty Warriors 7 Xtreme Legends Definitive Edition (DX).
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-04T19:50:27+00:00
- Post Title: Dynasty Warriors 7 with Xtreme Legends 2011 edition vs Dynasty Warriors 7 Xtreme Legends Definitive Edition (DX)

Can you upload sample BIN/IDX files?
## Post #3
- Username: qrst
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 03, 2021 9:56 pm
- Post datetime: 2021-07-05T07:31:47+00:00
- Post Title: Dynasty Warriors 7 with Xtreme Legends 2011 edition vs Dynasty Warriors 7 Xtreme Legends Definitive Edition (DX)

Thank you for replying & sorry for the delay (I have slow limited net connection).
Here is both .idx & .bin of the English text in Dynasty Warriors 7 Xtreme Legends Definitive Edition (DX):
[https://drive.google.com/file/d/1HHtRPi ... sp=sharing](https://drive.google.com/file/d/1HHtRPilRA2KBzbyYHAtOFe95vSaCFroa/view?usp=sharing)
## Post #4
- Username: qrst
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 03, 2021 9:56 pm
- Post datetime: 2021-07-12T18:12:39+00:00
- Post Title: Dynasty Warriors 7 with Xtreme Legends 2011 edition vs Dynasty Warriors 7 Xtreme Legends Definitive Edition (DX)

Is the large file (>2 GB) a big problem?
## Post #5
- Username: qrst
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-12T19:24:45+00:00
- Post Title: Dynasty Warriors 7 with Xtreme Legends 2011 edition vs Dynasty Warriors 7 Xtreme Legends Definitive Edition (DX)

Hi, I think I forgot to reply.   

Well, format is known and you can read article about it here
[http://wiki.xentax.com/index.php/Koei_T ... TA_BIN_IDX](http://wiki.xentax.com/index.php/Koei_Tecmo_LINKDATA_BIN_IDX)

For data extraction you can use Cethleann, I don't know if it supports repacking,
so you need to check it yourself or try one of the quickbms scripts for this format.
## Post #6
- Username: qrst
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 03, 2021 9:56 pm
- Post datetime: 2021-07-15T02:15:26+00:00
- Post Title: Dynasty Warriors 7 with Xtreme Legends 2011 edition vs Dynasty Warriors 7 Xtreme Legends Definitive Edition (DX)

If it isn't too much to ask: Which file should I use Cethleann with? the bin or the idx? Also if Quickbms is better, where can I find a script for the specific game? Or is it possible to use similar game's script (in this case I found Dynasty warriors 8 script)?
## Post #7
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-15T07:24:06+00:00
- Post Title: Dynasty Warriors 7 with Xtreme Legends 2011 edition vs Dynasty Warriors 7 Xtreme Legends Definitive Edition (DX)

> Which file should I use Cethleann with? the bin or the idx?
You can use Cethleann like this:

```
Cethleann.DataExporter.exe --linkdata (Path to output the extracted files) (Path to the folder with linkdata pair)
```

So you should provide there only 2 paths, one is output directory annd the second is directory with BIN/IDX files.
Cethleann should recognize files automatically.



> where can I find a script for the specific game?
Some scripts are linked in the wiki article I mentioned earlier.
More scripts you can find probably here [https://aluigi.altervista.org/quickbms.htm](https://aluigi.altervista.org/quickbms.htm)
or somewhere on the forum in other topics.


> Or is it possible to use similar game's script
Not always scripts for other games will work, because there are some differences in the file format between games.
