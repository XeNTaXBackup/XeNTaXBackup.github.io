## Post #1
- Username: thedarkknight
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jan 25, 2012 8:14 am
- Post datetime: 2012-01-25T00:22:27+00:00
- Post Title: ineed help on .nmo

Hi guys, 
ineed help with .nmo file idont know how to open it in any 3d program 

please help me  !!!!!!!!!!!!!!
[A.rar](https://xentaxbackup.github.io/file/5014_A.rar)
## Post #2
- Username: Nazaroff
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Oct 11, 2010 7:30 pm
- Post datetime: 2012-01-25T17:49:34+00:00
- Post Title: ineed help on .nmo

What is it .nmo? And what is the game? If you have it - upload it if you want to get help.
## Post #3
- Username: thedarkknight
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jan 25, 2012 8:14 am
- Post datetime: 2012-01-25T19:29:05+00:00
- Post Title: ineed help on .nmo

ohh sorry i have uploaded the file 
and the game is shadow of the colossus ps2
## Post #4
- Username: lavrov
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 04, 2014 11:39 pm
- Post datetime: 2014-10-08T00:14:46+00:00
- Post Title: ineed help on .nmo

3DVIA clearly stated that .nmo file format is proprietary and won't be disclosed, but...

This open source project - [https://github.com/yesterday/Syberia](https://github.com/yesterday/Syberia) implements an .nmo reader.

I created a repository [https://github.com/artlavrov/nmotools](https://github.com/artlavrov/nmotools) with a bms script that unpacks components and objects blocks from .nmo files.

There's also a wcx plugin (gaup_pro) that unpacks two compressed blobs from .nmo but I hope to go a bit further.
## Post #5
- Username: lavrov
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 04, 2014 11:39 pm
- Post datetime: 2014-10-08T07:05:47+00:00
- Post Title: ineed help on .nmo

Looks like the file you gave starts from "xff" instead of "Nemo Fi" - maybe it's just an uncompressed version of .nmo, I don't know yet. Shadow of the Colossus is definitely made in 3DVIA, according to google.
## Post #6
- Username: lavrov
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 04, 2014 11:39 pm
- Post datetime: 2014-10-13T21:59:11+00:00
- Post Title: ineed help on .nmo

Finds out somebody already reverse engineered those xff. See this post [viewtopic.php?p=29025#p29025](http://forum.xentax.com/viewtopic.php?p=29025#p29025)

> The code to read/extract stuff from SotC is available at: http://repo.or.cz/w/dormin.git
There is also a clone on github that I forked [https://github.com/artlavrov/dormin](https://github.com/artlavrov/dormin)
