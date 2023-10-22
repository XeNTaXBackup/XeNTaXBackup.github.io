## Post #1
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-06-24T00:30:00+00:00
- Post Title: No More Heroes: Heroes Paradise [Wii] (.rsl, .GM2)

I've done research on this only to find these files are similar to Fatal Frame 4 but the Noesis script doesn't work with NMH, Any help will be appreciated.
Example Files: [https://www.mediafire.com/file/uku2s8o7 ... P.zip/file](https://www.mediafire.com/file/uku2s8o70hmnjbk/NMHHP.zip/file)
## Post #2
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-06-24T22:14:24+00:00
- Post Title: No More Heroes: Heroes Paradise [Wii] (.rsl, .GM2)

Noesis can read some .rsl files, Unable to find the characters textures. For .GM2 got an error loading them
[error.PNG](https://xentaxbackup.github.io/file/18375_error.PNG)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-26T09:19:44+00:00
- Post Title: No More Heroes: Heroes Paradise [Wii] (.rsl, .GM2)

Well, your gm2 is a GTC0 texture, and the fmt_AgeOfWulin_gm2.py script you use is a mesh loader, isn't it? I can't seem to find a pixel parser or something like that in the script.

(Guess, you don't know what you're doing, do you?)

After an ugly "patch" the fmt_fatalframe_rsl.py gives me this:
.



LTRVJ011-GM2-test.png (43.94 KiB) Viewed 190 times
## Post #4
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-06-26T09:31:30+00:00
- Post Title: No More Heroes: Heroes Paradise [Wii] (.rsl, .GM2)

Kind of? Can you provide the fmt_fatalframe_rsl.py? I'm mainly looking to get the character textures anyway.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-26T09:44:22+00:00
- Post Title: No More Heroes: Heroes Paradise [Wii] (.rsl, .GM2)

It's not only the patched script there's also required hex editing of the gm2 file (cut of all bytes before "GCT0"). (Plus most authors don't like their cool scripts being spoiled by poor hackers like me.  )
## Post #6
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-06-26T09:57:13+00:00
- Post Title: No More Heroes: Heroes Paradise [Wii] (.rsl, .GM2)

Ah darn, I've been trying to get the textures from the wii with no results same with the PS3 version, I followed this post [viewtopic.php?f=10&t=6570&p=53763&hilit ... oes#p53763](https://forum.xentax.com/viewtopic.php?f=10&t=6570&p=53763&hilit=No+More+Heroes#p53763) however there is no PS3_TEXTURES.FPD in the file?
