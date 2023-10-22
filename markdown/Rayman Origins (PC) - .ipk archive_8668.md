## Post #1
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2012-03-31T11:18:36+00:00
- Post Title: Rayman Origins (PC) - .ipk archive

Hi, folks.   Is there a way to unpack the game's main archive - bundle_PC.ipk?

I can't upload a sample file because the archive is too large and MrAdult's Filecutter isn't working right (i don't know why).

I tried to find WATTO's FileCutter but i cannot find it because watto.org is down and i can't download it.

If someone have working FileCutter, PM me so i can upload a sample file(s)
## Post #2
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2012-03-31T11:26:05+00:00
- Post Title: Rayman Origins (PC) - .ipk archive

Try to use Search next time
[viewtopic.php?f=33&t=6168&p=70009&hilit ... ins#p70009](http://forum.xentax.com/viewtopic.php?f=33&t=6168&p=70009&hilit=rayman+origins#p70009)
## Post #3
- Username: oveja
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Feb 24, 2011 4:35 am
- Post datetime: 2012-03-31T11:27:17+00:00
- Post Title: Rayman Origins (PC) - .ipk archive

pc ver. archive same x360 ver.

[viewtopic.php?f=10&t=7672](http://forum.xentax.com/viewtopic.php?f=10&t=7672)
## Post #4
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2012-03-31T13:46:29+00:00
- Post Title: Rayman Origins (PC) - .ipk archive

Thanks for the info, but the localisation file is encrypted and i think that the text must be unpacked from the .loc file or if someone can - make a Text string editor for that game.  

Nevermind, someone know where exactly are the fonts located?
## Post #5
- Username: oveja
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Feb 24, 2011 4:35 am
- Post datetime: 2012-03-31T14:59:53+00:00
- Post Title: Rayman Origins (PC) - .ipk archive

localisation.loc not encryption.

4byte : id
4byte : length(number of characters)
length*2 byte : unicode text(UTF-16BE)

example)
00 00 05 5D 00 00 00 07 00 48 00 75 00 72 00 72 00 61 00 79 00 21

00 00 05 5D = id = 1373 (Perhaps?)
00 00 00 07 = length = 7 characters
00 48 00 75 00 72 00 72 00 61 00 79 00 21 = unicode text = Hurray!
## Post #6
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2012-03-31T15:42:29+00:00
- Post Title: Rayman Origins (PC) - .ipk archive

oveja, i don't understand what u mean (i'm completely noob ), but if the file is not encrypted as you say, then the only way to read\translate the text in the file is to open it with Text editor?
## Post #7
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2012-04-02T23:33:32+00:00
- Post Title: Rayman Origins (PC) - .ipk archive

*bump*
## Post #8
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2012-04-09T10:15:14+00:00
- Post Title: Rayman Origins (PC) - .ipk archive

Try this for localisation.loc. [http://www.sendspace.com/file/h7uu4p](http://www.sendspace.com/file/h7uu4p)

Update: Extract all languages
## Post #9
- Username: xboxmaniac
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Apr 21, 2012 3:19 pm
- Post datetime: 2012-04-29T16:16:37+00:00
- Post Title: Rayman Origins (PC) - .ipk archive

> Reply from swuforce
>
> Try this for localisation.loc. http://www.sendspace.com/file/jfsus2

It extract only english language.
I want extract another languages.
How can i extract all languages ?
Thanks
