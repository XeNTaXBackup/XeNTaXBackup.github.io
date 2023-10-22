## Post #1
- Username: SharingMind
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Feb 02, 2009 10:36 pm
- Post datetime: 2009-03-14T09:07:15+00:00
- Post Title: How to read this Xbox360 game save? Need help.

Hi All,

I hope one of you can help me understand how to read this game save:
It is a mere 64k. The file is a so-called CON file (container structure). If I open it up in Hex Workshop I don't see anything readable. The game was developed in Japan, but the game save is from an American xbox360.

I know the container has 1 small bin file in it with the size of 6k called tenchu.bin. I extracted that with a program called wxpirs, but it seems encrypted. I see some programming synthax as { etc..

Btw, I'd just like to see its contents for game modifying, personal use. 

Please help
## Post #2
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2009-03-15T10:51:08+00:00
- Post Title: How to read this Xbox360 game save? Need help.

I dont think so that its encrypted, its just hybrid save game format, binary and acii in one file. You can read some strings from it, but the rest is binary data (id of objects, position in world etc).

Also of offsets 5915, 22299 (maybe more) are some PNG images, probably thumbnails for "Load Game" menu
## Post #3
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2009-03-18T00:43:03+00:00
- Post Title: How to read this Xbox360 game save? Need help.

Lol, these files are more then meets the eye. First off this is a generic container format for xbox 360. It uses SHA1s to hash sections of data, and is all signed in the end by a RSA signiture using keys only found on your xbox 360. Luckily you can uses anyones keys since they are verifyable on foriegn consoles. You will need to find some container resigners on the net, along with an unbanned keyvault. Note if the signers are made by superasion or skatezero then they might not work right.

Ok down to what you want to see.


Here is a link to the actuall save game file, and it's in big endian.

[http://www.allenthinks.com/grimdoomer/F ... tenchu.bin](http://www.allenthinks.com/grimdoomer/Files/crap/tenchu.bin)
