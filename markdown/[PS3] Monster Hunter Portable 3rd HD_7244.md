## Post #1
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2011-08-27T10:28:59+00:00
- Post Title: [PS3] Monster Hunter Portable 3rd HD

Hello everyone,

so MHP3rd HD Version was released a few days ago. It is the first game of the <<Remastered>> Series, so it might be interesting to take a deeper look into it. The game at whole is around 4GB, whereas Gamedata is only 1,2GB and the rest are movies.

I have never messed with PS3 games since I do not own a PS3, so I just rely on info of the web. After a few minutes of research I found Mathieulths PS3/PSP Decrypter & Extractor for Retail PKG files. The tool decrypted the DATA000.PKG from the folder PS3_EXTRA/D000/ quite fine but crashed when extracting it at midway since the PKG seems to use two strange names with illegal chars for a) a ~10MB file and b) a ~1,1GB file (-> models, textures, etc. I assume). 

So I replaced those two strings:
first one was (in hex)

```
1D8288F9 AEEBE605 28A93102 3959E745 47DEAEB9 6C5C0E91 20542B3F 5B6C5121 CEA82FCD 0C18528B
```


second one was (in hex)

```
ABA026 F69CDEA3 02327899 ECADB20D 542A1BD8 4D2DB57A
```


After that nooby "fix" the extraction went well. In common sense, I don't have the original names now. But however. Logically, I am targeting the 1,1GB file. It seems to be encrypted, offzip doesn't work. I also tested codestations tool that works on MHP series (well they COULD have used the same encryption) but it also didn't work.

I uploaded the first 10MB of the file here: [http://vuvu.bplaced.net/MHP3rd/MHP3rd_HD_Data_Cut.bin](http://vuvu.bplaced.net/MHP3rd/MHP3rd_HD_Data_Cut.bin)
Might take a few mins till it is available from posting time.
I really really hope somebody manages to crack the encryption!

Thanks in advance and for your time to read this   

greetz
## Post #2
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2011-08-31T03:25:55+00:00
- Post Title: [PS3] Monster Hunter Portable 3rd HD

Seems the data is in an EDAT file from what I've seen.  I think this format cannot yet be decrypted.
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-31T09:09:14+00:00
- Post Title: [PS3] Monster Hunter Portable 3rd HD

yes all the files are encrypted except for a few small models and textures.
## Post #4
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2011-08-31T18:29:03+00:00
- Post Title: [PS3] Monster Hunter Portable 3rd HD

Oh, that's interesting, thanks for taking a look!
Speaking of EDAT filetype, there is an ISO.BIN.EDAT file also extracted: [http://vuvu.bplaced.net/MHP3rd/ISO.BIN.EDAT](http://vuvu.bplaced.net/MHP3rd/ISO.BIN.EDAT)
I am just wondering why noone seems to have found a way to decrypt those EDAT... the PS3 is jailbroken for a while and that seems to be a quite common and often used format... curious.

Oh and chrrox: those "few small models and textures"; mind hinting me how to extract those?

greetz
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-31T19:14:17+00:00
- Post Title: [PS3] Monster Hunter Portable 3rd HD

those files are about 64kb or less noting worth extracting.
Edat is the format used in npdrm encryption and no one will pot anything about it for fear of getting sued so no one has the decryption keys.
## Post #6
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2011-09-01T11:44:06+00:00
- Post Title: [PS3] Monster Hunter Portable 3rd HD

Ah okay... stupid Sony and their sueing...
## Post #7
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2011-09-07T15:49:29+00:00
- Post Title: [PS3] Monster Hunter Portable 3rd HD

Now seeing that the 3.60 SDK + NPDRM keys have been leaked: any chance to decrypt the file? :3
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-07T18:12:50+00:00
- Post Title: [PS3] Monster Hunter Portable 3rd HD

no
## Post #9
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2012-01-01T13:35:29+00:00
- Post Title: [PS3] Monster Hunter Portable 3rd HD

Up up and away~
Maybe someone got an idea now.
## Post #10
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2012-10-31T13:55:28+00:00
- Post Title: [PS3] Monster Hunter Portable 3rd HD

Bumping this since the game is playable via CFW now and it might be more interesting now since the scene is rolling again.
## Post #11
- Username: tastyxentax
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 01, 2012 4:03 am
- Post datetime: 2012-11-01T02:14:50+00:00
- Post Title: [PS3] Monster Hunter Portable 3rd HD

Hi. Is this possible yet?
