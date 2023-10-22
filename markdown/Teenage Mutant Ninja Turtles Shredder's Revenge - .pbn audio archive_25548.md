## Post #1
- Username: jackskellinghog
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Mar 11, 2012 11:08 am
- Post datetime: 2022-06-20T12:18:48+00:00
- Post Title: Teenage Mutant Ninja Turtles: Shredder's Revenge - .pbn audio archive

Looking to extract this for voice lines and sound effects, any ideas? Sprite data is under .zpbn and .zpbpx, also looking to extract that
## Post #2
- Username: jackskellinghog
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Mar 11, 2012 11:08 am
- Post datetime: 2022-06-20T17:13:57+00:00
- Post Title: Teenage Mutant Ninja Turtles: Shredder's Revenge - .pbn audio archive

[https://zenhax.com/viewtopic.php?t=7847](https://zenhax.com/viewtopic.php?t=7847)

Used this quickbms script for audio and it worked perfect. Now just need the sprite data.
## Post #3
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-06-20T18:09:03+00:00
- Post Title: Teenage Mutant Ninja Turtles: Shredder's Revenge - .pbn audio archive

[Here's](https://gist.github.com/barncastle/be026bbbab5c469f4e9e1317e95276e9#file-soundsettings-cs-L17) the structure of SoundsSettings.zpbn, the only real benefit of parsing it is for filenames. Just a note to anyone not using C#, [BinaryReader.ReadString](https://docs.microsoft.com/en-us/dotnet/api/system.io.binaryreader.readstring?view=net-6.0) uses a 7BitEncodedInt length prefix.

Textures are already documented on this [post](https://forum.xentax.com/viewtopic.php?f=10&t=23434). In short; ZLib decompress all the zxnb files and run them through your preferred [XNB converter](http://wiki.xentax.com/index.php/XNA_Game_Studio_4.0_XNB#Compatible_Programs).

Also FYI this game uses a 48kHz sample rate opposed to the usual 44.1kHz - which is also what the script uses.
## Post #4
- Username: masuele247
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 04, 2021 4:06 pm
- Post datetime: 2023-09-01T07:26:41+00:00
- Post Title: Teenage Mutant Ninja Turtles: Shredder's Revenge - .pbn audio archive

> Reply from jackskellinghog ↑Tue Jun 21, 2022 1:13 am at Tue Jun 21, 2022 1:13 am
>
> 
https://zenhax.com/viewtopic.php?t=7847

Used this quickbms script for audio and it worked perfect. Now just need the sprite data.

Link is dead, and can you explain how you did? here other guy wanting to make sound effect mods...
