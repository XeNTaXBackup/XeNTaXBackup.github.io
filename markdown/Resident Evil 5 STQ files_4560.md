## Post #1
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2010-06-05T00:41:32+00:00
- Post Title: Resident Evil 5 STQ files

I could use some help figuring out how this format works. It doesn't actually contain any sound data so this may be in the wrong section, but it is very much related to sound.

The STQ files contain information about every streamed audio file in the game (primarily music and speech). End of the file has a list of file links, and main parts of the file has info about loop points about each sound file (maybe some other information too, like duration). I have no idea what info is in the header.

I'm trying to figure out how to do edit the file so I can replace one of the songs in the game with correct loop points info.

A little bit of specific info I've discovered about one of the music files (s_bgm020)
Duration is 1:35.637333
LoopEnd point is 1:35.552 (measured in samples it's 4586496)
LoopStart point is 0:06.602667 (measured in samples it's 316928)

I've been trying to figure out where and how the info about specific points in the music is defined, but I've had zero luck. I've got little experience with this so that certainly doesn't help.

Other recent Capcom games using MT Framework uses the same format by the way.
