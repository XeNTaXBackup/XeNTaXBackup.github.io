## Post #1
- Username: InnocentSam2
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Apr 05, 2012 9:06 pm
- Post datetime: 2012-04-05T13:27:49+00:00
- Post Title: Dark Cloud - Strings/Texts?

Using Xeeynamo's unpacker, I've been through the files and I've been looking for the files that contain the language or text strings, and I think I've found three possibilities: .MES, .PAK or .PAC

Below are links to all three, I beg of you to decrypt these files or at least disprove what I think they are 

+rep to helper (if there is rep on this forum)

.MES: [http://dl.dropbox.com/u/17887537/Steve01_1.mes](http://dl.dropbox.com/u/17887537/Steve01_1.mes)
.PAK: [http://dl.dropbox.com/u/17887537/itemshop.pak](http://dl.dropbox.com/u/17887537/itemshop.pak)
.PAC: [http://dl.dropbox.com/u/17887537/quickchr.pac](http://dl.dropbox.com/u/17887537/quickchr.pac)
## Post #2
- Username: Xeeynamo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jan 07, 2011 6:25 pm
- Post datetime: 2012-04-06T13:13:58+00:00
- Post Title: Dark Cloud - Strings/Texts?

I can work on PAK stuff
## Post #3
- Username: 3pacalypse
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Jul 08, 2010 10:17 am
- Post datetime: 2012-11-12T12:34:22+00:00
- Post Title: Dark Cloud - Strings/Texts?

Im also looking for the text in the game, but I still havent found nothing...
## Post #4
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-11-12T14:44:34+00:00
- Post Title: Dark Cloud - Strings/Texts?

pac/pak
I saw only PS2 texture files. Header: TIM2

You can unpack them with data ripper, like Jaedernaub.
## Post #5
- Username: iamatmylimit
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 30, 2011 3:35 pm
- Post datetime: 2012-12-27T21:27:36+00:00
- Post Title: Dark Cloud - Strings/Texts?

Searching also for the text in this game. Well where its stored.
## Post #6
- Username: InnocentSam2
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Apr 05, 2012 9:06 pm
- Post datetime: 2012-12-28T17:25:27+00:00
- Post Title: Dark Cloud - Strings/Texts?

Me and Xeeynamo have looked and can't find where the strings are kept. Let us know if you find anything!

I'd personally like to find how the weapons are kept (i.e. perhaps a table file that determines all the weapons and what model they use), as this would mean making our own weapons out of models already in the game
## Post #7
- Username: 1jn14r
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 27, 2013 6:42 am
- Post datetime: 2013-09-01T19:29:44+00:00
- Post Title: Dark Cloud - Strings/Texts?

OK it seems .Pak is just like .Img and contains TM2 files. Here's the interesting bit, .Pac files contain TM2 but sometimes a .Mot. I have mad no progress on .Mes files
## Post #8
- Username: 1jn14r
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 27, 2013 6:42 am
- Post datetime: 2013-09-01T22:48:18+00:00
- Post Title: Dark Cloud - Strings/Texts?

OK .Pak can also have .mot files but .Mes is our string files, anyone know how to decrypt these?
## Post #9
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-10-04T18:56:08+00:00
- Post Title: Dark Cloud - Strings/Texts?

> Reply from 1jn14r
>
> OK .Pak can also have .mot files but .Mes is our string files, anyone know how to decrypt these?
Here are my observations about Dark Cloud 2 (which uses a very similar or identical format as Dark Cloud 1)
There are some files, which can be opened up like text files, but some of the text in quotation marks are 4byte binary integers, so they will show up like "#@$@"
For example
HitPoints = "#%@#"

So to summaries mostly ASCII, but with important things as raw 4ByteIntegers always surrounded by quotation marks.
