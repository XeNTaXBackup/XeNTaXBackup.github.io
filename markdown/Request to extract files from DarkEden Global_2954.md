## Post #1
- Username: zonex
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 01, 2008 6:31 am
- Post datetime: 2008-03-01T00:47:11+00:00
- Post Title: Request to extract files from DarkEden Global

Hello,
I was trying to figure out a way to add extraction support for the game data file for DarkEden Global in the darkeden.dpk.
The file header seems to consist of 512bytes. It starts off with 78 01 CD 00 F8 DB E5 and the rest of the 512 bytes are just 00. From what I've read the 78 01 would suggest that it was created with Zlib. This is about as far as I was able to get. I'm sure someone with more experience with file formats would probably have a better idea of how darkeden.dpk was made and how to extract the files from it. 

I can't attach the file header or footer since they are too big and zipping them does nothing to shrink them (not supprised lol).
darkeden.dpk itself is over 500mb.

Good thing though is that the game can be downloaded freely from:
[http://www.joymax.com/darkeden/](http://www.joymax.com/darkeden/)

Thanks in advance
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-01T09:29:07+00:00
- Post Title: Request to extract files from DarkEden Global

Well you might try zlibc: [viewtopic.php?f=21&t=2022](http://forum.xentax.com/viewtopic.php?f=21&t=2022)
but if the rest of header is full of zeros, that part normally can't be compressed.
## Post #3
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2008-03-01T17:24:00+00:00
- Post Title: Request to extract files from DarkEden Global

I'll look at that now
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-03-01T20:08:29+00:00
- Post Title: Request to extract files from DarkEden Global

Why don't you use the FIleCutter from Watto or me to cut a few pieces for us to analyse?
## Post #5
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2008-03-01T20:29:48+00:00
- Post Title: Request to extract files from DarkEden Global

I tried to install a DarkDenTh (Thailand) and there is no archive like dpk,all files are unpacked.... but textures are in special format (ispk and ispki)...
## Post #6
- Username: zonex
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 01, 2008 6:31 am
- Post datetime: 2008-03-01T21:18:40+00:00
- Post Title: Request to extract files from DarkEden Global

I did use the file cutter but the smallest I was able to get the files were 512kb for the head and footer (for some reason the 256kb isn't working for me) which is too big to attach to the post. I uploaded the header and footer of the darkeden.dpk file on RapidShare. Here's the link

[http://rapidshare.de/files/38718729/darkeden.zip.html](http://rapidshare.de/files/38718729/darkeden.zip.html)

Also for those who might have not noticed, you can also download the whole game for free from the DarkEden Global website: 

[http://www.joymax.com/darkeden/](http://www.joymax.com/darkeden/)

I also found this direct link to the DarkEden Global installer so no registration is necessary:

[http://files1.games.internode.on.net/do ... adid=14022](http://files1.games.internode.on.net/download-ad.php?downloadid=14022)

Also I don't want the files from DarkEden Thailand, I want the unpacked data files from DarkEden Global because it will probably contain all the english game text which I want to use to patch the text in the Japanese version of the game.

Also, before someone suggests just using the DarkEden International files which are english, I already have them. Yes they are english but the International version is a early version of DarkEden and is missing over 50% of current game text in current versions.

So it important for me to be able to extract the files from the DarkEden Global darkeden.dpk file and not some other version.

Thank You for all your replies so far!
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-03-02T22:20:08+00:00
- Post Title: Request to extract files from DarkEden Global

It seems to me that the dpi file is some sort of index file for the dpk file. The DPK file seems to have a header of 512 in lenght, then some part that COULD have some ZLib part, but that part did not decompress with Zlib. Then there's a huuuge part until the end. I'm using OllyDbg to look at the code itself. This will take some time, but could yield results as to compression/encoding process.
