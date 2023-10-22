## Post #1
- Username: carnage
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Jun 26, 2012 10:21 pm
- Post datetime: 2014-05-05T22:14:27+00:00
- Post Title: [XBOX 360] - Help with XBLA games on GoD

Friend would like everyone's help to understand this case.
To know the GoD games (Game on Demand) or XBLA (Xbox Live Arcade), has some restrictions original consoles, that is does not apply any mod or translation in any language.

Thinking about it I have a big question, yes it is possible to apply Mods and running on the original consoles, but any change in the structure of the file appears as "File Corrupted" within the video game.
There is a check file size that can not be overcome, like the Mega DriveChacksum?


In this image you can see the options that we have, we can extract insert a new file, or replace an existing one. 
But in either case shows how corrupt the file 360 dashboard.


Now who is the "man" that will identify if the file is larger or smaller than the original?
This is a file from the Live server, a configuration file to the Xbox, or an address in the file itself?
Taking based PSOne games, I have a theory, but do not know if it is correct.
To extract all the contents have the following log.

```
Package Licences:
License 0 ID: FFFFFFFFFFFFFFFF
License 0 Bits: 0
License 0 Flags: 0
License 1 ID: 900000AD18AE7
License 1 Bits: 1
License 1 Flags: 1
License 2 ID: F00000B27166A0E6
License 2 Bits: 1
License 2 Flags: 0
License 3 ID: 0
License 3 Bits: 0
License 3 Flags: 0
License 4 ID: 0
License 4 Bits: 0
License 4 Flags: 0
License 5 ID: 0
License 5 Bits: 0
License 5 Flags: 0
License 6 ID: 0
License 6 Bits: 0
License 6 Flags: 0
License 7 ID: 0
License 7 Bits: 0
License 7 Flags: 0
License 8 ID: 0
License 8 Bits: 0
License 8 Flags: 0
License 9 ID: 0
License 9 Bits: 0
License 9 Flags: 0
License 10 ID: 0
License 10 Bits: 0
License 10 Flags: 0
License 11 ID: 0
License 11 Bits: 0
License 11 Flags: 0
License 12 ID: 0
License 12 Bits: 0
License 12 Flags: 0
License 13 ID: 0
License 13 Bits: 0
License 13 Flags: 0
License 14 ID: 0
License 14 Bits: 0
License 14 Flags: 0
License 15 ID: 0
License 15 Bits: 0
License 15 Flags: 0
Package Type: Arcade
Meta Data Version: 2
Recorded ContentSize: 621375488 bytes
Media ID: 660819452
Version: 2
Version Base: 2
Title ID: 58410A67
Platform: 0
Executable Type: 0
Disc Number: 0
Disc In Set: 0
Save Game ID: 0
Creator's Console ID: 00
Creator's Profile ID: 00
Data File Count: 0
Data File Size: 0
Series ID: 00000000000000000000000000000000
Season ID: 00000000000000000000000000000000
Season Number: 0
Epidsode Number: 0
Device ID: 0000000000000000000000000000000000000000
Languages:
English Display Title and Description:
Dust
Dust was created with XNA Game Studio.
Japanese Display Title and Description:
Dust
Dust was created with XNA Game Studio.
German Display Title and Description:
Dust
Dust was created with XNA Game Studio.
French Display Title and Description:
Dust
Dust was created with XNA Game Studio.
Spanish Display Title and Description:
Dust
Dust was created with XNA Game Studio.
Italian Display Title and Description:
Dust
Dust was created with XNA Game Studio.
Korean Display Title and Description:


Chinese Display Title and Description:


Portuguese Display Title and Description:


Publisher Name: 
Package Title: Dust
Package Transfer Type: AllowTransfer
```


Notes the Recorded contentSize and Executable Type
A indicates the file size and the other (I think) that indicates whether or not to ask the media to run.
Taking this address 621375488 and converting to Hex 0x25097000h it appears at the beginning of the file, I imagine that would be checking the file size, whichever is greater or less crash to the console.

Game Name (Identification after installing the HD)
File size converted to Hex

I wonder if this is really likely or is it just something that leads nowhere. 
Having no idea how this works, you can apply mods and translations of original games on consoles.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-05-05T23:44:14+00:00
- Post Title: [XBOX 360] - Help with XBLA games on GoD

all games are digitally signed changing anything invalidates the signature and will stop it running.
You can mod disc based games if you have a modded dvd drive and the game does not check the file signatures.
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-05-06T05:12:04+00:00
- Post Title: [XBOX 360] - Help with XBLA games on GoD

You cannot mod GOD container and run it on Non modded console, this never gonna work as chrrox mention files got signed by MS to make it run. However if you have RGH you can do whatever you want and can mod it and sign it again. Doing it for years and it works perfectly OK. Not gonna even work with DVD drive flash only, this method is only apply for GOD, XBLA, Profiles, etc.. containers!
