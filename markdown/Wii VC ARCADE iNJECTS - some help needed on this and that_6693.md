## Post #1
- Username: g0dlike
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 29, 2011 10:02 pm
- Post datetime: 2011-05-29T14:49:47+00:00
- Post Title: Wii VC ARCADE iNJECTS - some help needed on this and that

Hey everyone, 

I am working on Wii VC injections since the last 1.5 yrs, made about 250 injects for several systems like MEGA DRIVE, MASTER SYSTEM, NES, SNES, N64, MSX/MSX2, PCE-HU Card, GB, GBC, GBA and now I work on injecting Arcade games into existing VC wad files.

I managed to locate the files in the corresponding folders, seen on the pics below:

This shows a JPN host wad structure:

1.) This shows the extracted wad and whats inside, until now VC Arcade games have been uninjectable bc we did not know where the rom file is located.



2.) This shows the folder which holds the rom file, finally some progress on this heh?

Some more progress here, just unpacked a NTSCU VC Arcade wad and found that they are pretty similar to SMS wads lol.

This shows a NTSCU host wad structure:

1.) As above the extracted wad and contents.


2.) The folder which holds the rom file 

Now onto the problem, the file which holds the game rom file(s) is definatly the zaxxon.rso.zlib(incase of the USA version of Zaxxon).

I need a program, or help in finding a program which can unpack and repack this kind of files.

I know about zlib library but as we inspected the file further, it came out that it has no compression at all, furthermore zlib itself cannot unpack it.

Next thing weird is that the .rso, I know that .rso files are commonly sound files which are changed to .rso, some kind of container I guess.

All in all it sums up like this: The file in question isnt zlib'd, ccftool just adds zlib to the end of file to show that it WAS zlib, the rso file just looks like some sort of container which we need to open up.

Your help is welcome, hope we can sort this out soon 
BTW, thx to sr_corsario for pointing me to this excellent forum
## Post #2
- Username: srcorsario
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Aug 16, 2010 11:08 pm
- Post datetime: 2011-05-29T15:32:15+00:00
- Post Title: Wii VC ARCADE iNJECTS - some help needed on this and that

Some rso files.

[http://uppit.com/x18t9ygejfvi/rso_files.rar](http://uppit.com/x18t9ygejfvi/rso_files.rar)


I had a look into them and looks like to have a header with a list of file sizes... and then ... start the data... allways talking in my ignorance of course...
## Post #3
- Username: g0dlike
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 29, 2011 10:02 pm
- Post datetime: 2011-06-06T13:00:38+00:00
- Post Title: Wii VC ARCADE iNJECTS - some help needed on this and that

Anyone knows something which could help a  bit?
## Post #4
- Username: g0dlike
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 29, 2011 10:02 pm
- Post datetime: 2011-06-26T08:26:22+00:00
- Post Title: Wii VC ARCADE iNJECTS - some help needed on this and that

*bump* somebody ?  

Given hints to how correctly approach unpacking this files would be also highly appreciated
## Post #5
- Username: srcorsario
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Aug 16, 2010 11:08 pm
- Post datetime: 2011-07-10T14:18:41+00:00
- Post Title: Wii VC ARCADE iNJECTS - some help needed on this and that

Hello!


I really appreciate the work on this forum. Great and fantastic persons.

 However I cant understand the problem with this files because it looks like "easy" to do progress with it (obviouslly with people with  knowledge on compression/paking methods)

Certenlly it will "just" give us to a few of us the possibillity to try to inject some wii arcade games... but well can understand the lack of time to many of us.

Thanks any way for your interest
## Post #6
- Username: g0dlike
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 29, 2011 10:02 pm
- Post datetime: 2011-08-01T18:02:05+00:00
- Post Title: Wii VC ARCADE iNJECTS - some help needed on this and that

Bump, anyone has found something?
