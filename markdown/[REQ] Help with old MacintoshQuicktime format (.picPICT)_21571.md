## Post #1
- Username: Habanero
- Rank: n00b
- Number of posts: 19
- Joined date: Thu May 02, 2019 2:36 am
- Post datetime: 2020-01-05T00:06:37+00:00
- Post Title: [REQ] Help with old Macintosh/Quicktime format (*.pic/PICT)

I was wondering if anyone would be able to help me convert these images, or if any progress has been made. I bought an old Japanese RPG called Vampire Hurts that I might be interested in translating. First thing first is breaking open the files inside!

Some reading:
[https://forums.penny-arcade.com/discuss ... efeated-me](https://forums.penny-arcade.com/discussion/40230/pic-files-and-how-the-defeated-me)
[viewtopic.php?f=18&t=1369&p=9550&hilit=pict#p9550](https://forum.xentax.com/viewtopic.php?f=18&t=1369&p=9550&hilit=pict#p9550) (I tried the converter posted here and it just resulted in "ERROR"

Images:
[http://www.mediafire.com/file/lowxmhnh5ywrmug/bmp.zip](http://www.mediafire.com/file/lowxmhnh5ywrmug/bmp.zip)

If anyone can assist me with this, I would greatly appreciate it. Thank you.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-01-06T21:06:48+00:00
- Post Title: [REQ] Help with old Macintosh/Quicktime format (*.pic/PICT)

i don't think these pic samples are apple formats, just typical paletted/non-paletted rgb images with pic extension.
## Post #3
- Username: Habanero
- Rank: n00b
- Number of posts: 19
- Joined date: Thu May 02, 2019 2:36 am
- Post datetime: 2020-01-10T05:25:45+00:00
- Post Title: [REQ] Help with old Macintosh/Quicktime format (*.pic/PICT)

> Reply from Acewell ↑Tue Jan 07, 2020 5:06 am at Tue Jan 07, 2020 5:06 am
>
> 
i don't think these pic samples are apple formats, just typical paletted/non-paletted rgb images with pic extension.
Ahh, okay. How would I go about viewing/converting the images though? Renaming the extension to jpg, png, or bmp didn't work. I tried Manifold Viewer since it's what popped up when I googled how to open palette files, and that didn't work either.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-01-15T07:55:31+00:00
- Post Title: [REQ] Help with old Macintosh/Quicktime format (*.pic/PICT)

here is Noesis python script to open pic files from this game.  


 tex_VampireHurts_pic.zip
(699 Bytes) Downloaded 26 times
## Post #5
- Username: Habanero
- Rank: n00b
- Number of posts: 19
- Joined date: Thu May 02, 2019 2:36 am
- Post datetime: 2020-01-16T08:57:55+00:00
- Post Title: [REQ] Help with old Macintosh/Quicktime format (*.pic/PICT)

Thank you! That takes care of the images. Now all that seems to be left are [the .dat files.](https://forum.xentax.com/viewtopic.php?f=10&t=21593)

Is there a way to preserve the transparency when importing into Noesis, though? The transparency has been replaced with a black background.
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-01-17T00:10:33+00:00
- Post Title: [REQ] Help with old Macintosh/Quicktime format (*.pic/PICT)

> Reply from Habanero ↑Thu Jan 16, 2020 4:57 pm at Thu Jan 16, 2020 4:57 pm
>
> Is there a way to preserve the transparency when importing into Noesis, though? The transparency has been replaced with a black background.
i'm pretty sure any image meant to have transparency in this game is accompanied
by a file of the same name also with _a in the file name to denote "alpha" and is likely
combined and rendered by the game at runtime, for example:
v_up_ela.pic
v_up_ela_a.pic
