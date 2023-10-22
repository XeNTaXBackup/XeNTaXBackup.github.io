## Post #1
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2014-10-03T20:24:29+00:00
- Post Title: decrypt/decompile .bin from Doom&Destiny

Hey Guys,

i want to decrypt/decompile maps and other files from the Androidgame Doom&Destiny.
I already decompiled the .apk and I'm able to read scripts (java/smali).
The Maps and other .bin files could be possibly created with the RPG Maker XP, Tiled map or/and XNA.
I'm not able to modify this files, but I really want to edit them / add new maps, monsters, items etc. to it.
It would be REALLY GREAT if you can help me with it 
I added all needed files to the Attachment (graphics[jpg,png], Maps[.bin], other game infos[.bin], all source[.java] and librarys[.dll]).

http://puu.sh/bXZAS/27800a119c.rar

EDIT:
Have checked something.
The files are probably sha1-encrypted?

> Name: assets/Content/Maps/4/Map462.bin
>
> SHA1-Digest: vackh4UmzKidgFm6sleoK+Inpts=
[http://puu.sh/bY1wx/77c23b5c77.bin](http://puu.sh/bY1wx/77c23b5c77.bin) <- Map462.bin
but some strings in this files are in plain-text
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-10-03T22:04:51+00:00
- Post Title: decrypt/decompile .bin from Doom&Destiny

The .bin files don't look encrypted at all. The SHA-1 part is a checksum, which is likely used for checking if the .bin file has been edited.
## Post #3
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2014-10-04T07:23:28+00:00
- Post Title: decrypt/decompile .bin from Doom&Destiny

Thank you for the fast answer! 
But do you know how I could "Modify" them?
Would be great If someone could help me with this
