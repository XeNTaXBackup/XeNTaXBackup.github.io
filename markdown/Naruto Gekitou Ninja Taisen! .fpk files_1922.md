## Post #1
- Username: LostRyoga
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 27, 2006 10:27 am
- Post datetime: 2006-05-27T03:32:04+00:00
- Post Title: Naruto: Gekitou Ninja Taisen! .fpk files

Could you please take a look at the format for the GameCube Naruto: Gekitou Ninja Taisen! 1-4 games?  I'm pretty sure they all use the same format (*.fpk).  All four games have the same extensions, and are pretty much just updated versions of the 1st game.  They should contain, models, textures, and sounds.  Heres a sample for the 1st game, I can provide samples for the other games as well.

 The files in the /char/ folder, with the naming system of 3 letters plus 3000 (example chr3000.fpk) appear to have C Header files in them when the file is viewed with a hex editor.  I would have liked to upload one of them, but the file size is to large.... 456k.  I did try to use the File Cutter suggested in the sticky, but it did not produce any files.  All it did was give me two empty 'ok' windows, and a 'pak' folder with a 456k complete.bin.
[ali0000.zip](https://xentaxbackup.github.io/file/751_ali0000.zip)
## Post #2
- Username: LostRyoga
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 27, 2006 10:27 am
- Post datetime: 2006-07-11T02:09:25+00:00
- Post Title: Naruto: Gekitou Ninja Taisen! .fpk files

Just found out this format is also in Bloody Roar Extreme, GameCube, and apparently X-Box ( [http://forums.xbox-scene.com/index.php?showtopic=525346](http://forums.xbox-scene.com/index.php?showtopic=525346)
).  Both games are made by Eighting.  It is possible that they have used it in their other games as well.
## Post #3
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2006-07-11T02:47:15+00:00
- Post Title: Naruto: Gekitou Ninja Taisen! .fpk files

It may be along the lines of the same format but it is not the same most likely. This appears to be Big-Endian while xbox will be Little-Endian.

Anyhow looked at file came up with something like this.

[4] - Int (Null?)
[4] - Number of Files 
[4] - Could be String/Entry size
[4] - File/asset size (could be EoF if this wasn't split)

For each Entry (starts after header):
string (Null Terminated)
[4] - Null?
[4] - Offset
[4] - Size
[4] - Unknown
