## Post #1
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2008-02-09T13:45:02+00:00
- Post Title: Smash Online

Hallo an alle, ich kann leider kein Englisch schreiben(Nur etwas).

Kommen wir gleich zur sachen.
Ich habe eine Extrahierer geschrieben was das NPK- Archiv extrahieren kann.

Das Problem ist nur das die extrahiereten Dateien komprimiert sind.

Habe mal eine Datei hochgeladen, in der Hoffnung das einer damit was anfangen kann.

Komprimierte Dateigröße: 22284 bytes
Unkomprimierte Dateigröße: 32896 bytes
[Christine_face_Default1_1.zip](https://xentaxbackup.github.io/file/1443_Christine_face_Default1_1.zip)
## Post #2
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2008-02-09T21:41:24+00:00
- Post Title: Smash Online

Ok, i try in bad english(sry ^-^)

I have written a extractor that extract the NPK- Archive from the game Smash online.

But the extracted files are compressed.

I dont know how compression it used, can anyone help me please.

a example is alredy exist (see above)

compressed size of the file: 22284 bytes
uncompressed size of the file: 32896 bytes
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-11T21:13:05+00:00
- Post Title: Smash Online

Seems to be compressed indeed.
But got no clue what it is.
## Post #4
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2008-02-12T16:37:06+00:00
- Post Title: Smash Online

> Reply from Rheini
>
> Seems to be compressed indeed.
But got no clue what it is.
Thx for your answer.
I have a another sample.

Two application.

Compressed_config.exe (are compressed)
and config.exe (are uncompressed)

the application are equal.

because the  uncompressed filesize with original application with the application in the archive to match.

sry, for my bad english.

 Compressed_config.zip
(187.75 KiB) Downloaded 45 times
## Post #5
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2008-02-12T16:48:39+00:00
- Post Title: Smash Online

And the original apllication


 config.zip
(162.49 KiB) Downloaded 55 times
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-12T19:50:10+00:00
- Post Title: Smash Online

That archive contained an exe 
How did you manage to decompress the files?

[german]Wieso ist da ne exe in dem Archiv?
Woher hast du die dekomprimierten Daten? Mitm Debugger gezogen?[/german]
## Post #7
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2008-02-13T20:17:06+00:00
- Post Title: Smash Online

> Reply from Rheini
>
> That archive contained an exe 
How did you manage to decompress the files?

[german]Wieso ist da ne exe in dem Archiv?
Woher hast du die dekomprimierten Daten? Mitm Debugger gezogen?[/german]

Nein die habe ich nicht mit dem Debugger gezogen.
Die Anwendung erschien erst, als das Update Programm die neuste Datei, heruntergeladen hat.
Dann hat warscheinlich das Patchprogramm die Anwendung aus dem Archiv extrahiert und dann dekomprimiert.

Die Dekomprimierte Dateigröße der Anwendung im Archiv übereinstimmt mit der Anwendung die bereits vorhanden war

Während des update, hat er Dateien mit der Erweiterungen *.npf heruntergeladen.
Vielleicht gibt die Erweiterung auskunft über das verwendete kompimierungsverfahren?
## Post #8
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2008-03-02T09:06:25+00:00
- Post Title: Smash Online

I have no idea what is going on in this thread. One brief glance indicates it is my old friend LZO. attached pic. That exe is compressed same way.


regards,
[Christine_face_Default1_1_D.zip](https://xentaxbackup.github.io/file/1465_Christine_face_Default1_1_D.zip)
## Post #9
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2008-03-24T12:03:21+00:00
- Post Title: Smash Online

thx silver for your help, it work
## Post #10
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-03-26T09:51:49+00:00
- Post Title: Smash Online

Hello guys, Is there a ready made tools to decompress this type of files!
I think I got some dreamcast files using this same kind of compression! 

Thanks
## Post #11
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-26T11:21:37+00:00
- Post Title: Smash Online

You might try [http://www.lzop.org/](http://www.lzop.org/)
## Post #12
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-03-26T12:08:42+00:00
- Post Title: Smash Online

I already try that before I post, 
even I use to test the file above, it didn't work. It said no a lzop file!
## Post #13
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2008-03-27T08:21:43+00:00
- Post Title: Smash Online

I don't think Lzop will decompress these files. You may have luck with Savage's decompressor in the gears of war thread in this same forum. The problem is that lzo has many variants while decompression is rather generic you need to know the exact method to compress. The only way I know to verify the compression specification is to decompress and recompress per variant until a match is made. I was thinking of expanding upon an app I use for this type of stuff and putting it up. How long I have no idea as time is never kind.

Here are the various flavors of LZO
LZO1 
LZO1A 
LZO1B 
LZO1C 
LZO1F 
LZO1X 
LZO1Y 
LZO1Z 
LZO2A
and most if not all have multiple strengths.
## Post #14
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-03-27T08:57:19+00:00
- Post Title: Smash Online

Thanks for the explanation, silver!
I'm looking forward to your tools!
## Post #15
- Username: Barny
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jan 24, 2009 11:18 pm
- Post datetime: 2009-01-24T15:33:28+00:00
- Post Title: Smash Online

Hi everyone!

I already pm'd the author of this thread, but just in case want to ask this openly.

Does anyone know how to extract this particual NPK file from Smash Online, because I didn't find a way yet. Not even Nebula SDK nnpktool.exe worked on it, saying its not a real npk file?!

I'm asking because I really would love to get my hands on those textures and models within the Resource.npk of this game.

Thanks in advance!
