## Post #1
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-02-02T16:16:27+00:00
- Post Title: Common .WGM fusion game format.

Hello fine folks. Lately I've been trying to recover graphics and music from a Fusion game as you may or may not know. I was hoping someone here could help out with this by decrypting and unpacking the file supplied here. The problem is, I'm not sure whether it contains graphics, or sound files. Judging by the size of them, it could possible be either, or maybe even both. However, I need these files for a video project I'm working on and It's urgent I get these within three months. If anyone can figure these out it would be very helpful to me, even if they are just sound bytes, it would make me one step closer to completing my project.

In the following zip file you will find a folder labeled "MMF". In this folder are the files in question.
[http://www.filefactory.com/file/a2h20ag/n/MMF.zip](http://www.filefactory.com/file/a2h20ag/n/MMF.zip)

Filefront Mirror:
[http://www.filefront.com/15485927/MMF.zip](http://www.filefront.com/15485927/MMF.zip)

I certainly hope someone can unpack these for me in some way, and I REALLY hope they don't just contain further unusable formats, but if they do, I'll be back with them of course.

Thank you for taking the time to read, and if you can help out, please do!
## Post #2
- Username: EldritchDecross
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 27, 2010 10:39 am
- Post datetime: 2010-04-08T00:08:03+00:00
- Post Title: Common .WGM fusion game format.

I've been searching for the answer to these as well. Unfortunately no one I know has worked on them with any results.

Anyway, here's another example, from the same developer, and from a similar game.
[http://www.sendspace.com/file/910x6q](http://www.sendspace.com/file/910x6q)
## Post #3
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2010-04-08T05:29:59+00:00
- Post Title: Common .WGM fusion game format.

I have the structure mapped out, but I fail at BMS. So here is the struct (little endian):

```
     char[0x04] id; // WGM1
     short unk_1;
     char[0x64] info;
     int file_count;
     ENTRY[file_count] files;
}

public struct ENTRY {
     char unk_1;
     char[0x04] name;
     int dummy;
     int size;
     char[size] data;
}
```
## Post #4
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-04-08T13:21:55+00:00
- Post Title: Common .WGM fusion game format.

So what is it I do with this? I'm not much of a programmer, and I don't know how to compile things...
## Post #5
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2010-04-08T14:27:12+00:00
- Post Title: Common .WGM fusion game format.

I would find someone to make a BMS script out of it.
## Post #6
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-04-08T15:23:20+00:00
- Post Title: Common .WGM fusion game format.

I wish I were smarter about scripting...

Anyway, do you have any suggestions on who could do this? I'm probably not very popular around here with all the annoying requests I make for help.
## Post #7
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2010-04-08T15:24:02+00:00
- Post Title: Common .WGM fusion game format.

I'm sure aluigi could do it.
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-08T17:01:01+00:00
- Post Title: Common .WGM fusion game format.

wow just arrived at home :)

```
    idstring WGM1
    get unk_1 short
    getdstring info 0x64
    get file_count long
    #ENTRY[file_count] files;
#}

for i = 0 < file_count
#public struct ENTRY {
    get unk_1 char
    getdstring name 0x04
    get dummy long
    get size long
    savepos offset
    log name offset size
    math offset += size
    goto offset
    #char[size] data;
#}
next i
```
I'm sure this can be also a goot example for who wants to learn to write the scripts
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-04-08T17:09:45+00:00
- Post Title: Common .WGM fusion game format.

you beat me to it i was about to post a script lol
## Post #10
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-04-08T17:28:35+00:00
- Post Title: Common .WGM fusion game format.

So are the internal files uh...graphics files or what? It just outputs extensionless files.
For convenience purposes I've added an example to these files.
[http://www.sendspace.com/file/2oaco2](http://www.sendspace.com/file/2oaco2)
## Post #11
- Username: EldritchDecross
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 27, 2010 10:39 am
- Post datetime: 2010-04-08T22:29:53+00:00
- Post Title: Common .WGM fusion game format.

For other convenience purposes, I've just zipped up all the extracted files so people can take a look at them. I'm using sendspace as well.

[http://www.sendspace.com/file/i5h8q6](http://www.sendspace.com/file/i5h8q6)

Now think people, if we manage to get the graphics out of these things we will have unlocked a whole new world of extraction! Remember this is for the whole community!
## Post #12
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-04-09T14:36:22+00:00
- Post Title: Common .WGM fusion game format.

Looking at these in a hex editor reveals that the first uh...bit? of the 'ins' titled files contains a 'WSP1' line. I can assume this may be the file extension. (However searching the internet only results in "Windows service Pack 1" and related files.) Unfortunately, I'm not very good at hex or finding things otu via hex, but in my experience so far I assume the first line in a hex string is the file extension. I have no idea, don't criticize me if I'm wrong... I assume these are the graphics files.

On inspection of the numerically titled files such as 00d1, results in finding a WSF1 type. Also noticed in these files is a WAV file. I assume these contain the music files.
