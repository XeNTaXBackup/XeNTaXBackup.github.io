## Post #1
- Username: pentaro
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 07, 2019 9:19 pm
- Post datetime: 2019-11-07T13:44:28+00:00
- Post Title: File formats for Initial D: Mountain Vengeance (PC)

Hi  [Somewhat cross posting this from r/initiald.](https://www.reddit.com/r/initiald/comments/drjrw8/initial_d_mountain_vengeance_modding/)

I'd like to know if anyone can help me crack/understand the file formats and structures for the PC game Initial D: Mountain Vengeance. Long story short: it's a PC budget racing game with subpar driving mechanics and a very short draw distance, among other issues (mostly to do with it being a Tokyopop adaptation of source material, which results in americanized character names and an awful soundtrack). I started out trying to translate it, then moved on to minor graphical edits and car retexturing, but now I'm thinking about slight engine modifications and/or corrections.

Except... Not being a programmer, it's hard for me to do much else that poke at the game from the outside. Through *.ini edits, I've found some things but the game does feel like a mess. There are numerous mentions in the *.inis to levels and files that simply do not exist anywhere within the game folders (or instead reference a previous game by the same studio), to the point where deleting some lines in the *.inis has no effect on the game whatsoever. On the other hand, some *.inis have options not available from within the game itself (difficulty, texture quality, etc.).

Ideally, I'd like to know how the game handles certain things, from car models to track levels, to how it renders draw distance. *.ini tampering so far reveals I can adjust how much of the track is rendered (to the point where there is no popping of scenery, for instance). It would be nice to replace the existing car and level models for better ones but for now I'm mainly concerned with how it renders draw distance (and why the pause and free camera modes don't work, but that's for later). The game was developed to consider only night time racing, and there's a constant darkness mantle ahead of the car's headlights that covers the entire level, so this must be defined somewhere else in the game.

EDIT: Here's an example:


Here the game is running with an extended draw distance and a customized set of skyboxes, but note that further down, it's pitch black. It's possible to tint RGM ambient values, but while these affect what is not bathed by headlights, it has no impact on the darkness up ahead. 

The game uses a *.cmx file format for definitions such as car tires, car smoke, hud, etc.; *.pkg format for things such as car clipping and car body; and *.lvl for levels. I can't really tell what they handle - it can be level geometry or scripts, maybe both (textures are handled outside of these, easy to find/edit in an Images folder). Maybe it is defined in the executable, I don't know.

For anyone willing to help, can I attach sample files or should I simply post the code? If I should only post the code, what format should I use? Thanks in advance
## Post #2
- Username: pentaro
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 07, 2019 9:19 pm
- Post datetime: 2019-11-09T15:28:26+00:00
- Post Title: File formats for Initial D: Mountain Vengeance (PC)

Here are some *.cmx files, along with a *.pkg and a *.level (which is quite likely the level geometry, but I don't know if it contains any traces of the info I'm trying to get at).

The file contains 6 CMX, 1 PKG and 1 LVL, and is [hosted here](http://s000.tinyupload.com/index.php?file_id=97826129731096459109).

In anyone can take a look at these...
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-09T18:09:24+00:00
- Post Title: File formats for Initial D: Mountain Vengeance (PC)

AkinaTrack_LVL_0x10ec114.png (65.92 KiB) Viewed 82 times
## Post #4
- Username: pentaro
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 07, 2019 9:19 pm
- Post datetime: 2019-11-11T10:22:10+00:00
- Post Title: File formats for Initial D: Mountain Vengeance (PC)

> Reply from shakotay2 ↑Sun Nov 10, 2019 2:09 am at Sun Nov 10, 2019 2:09 am
>
> Images

Ah, thank you! I understand now and my suspicion was right about the *.lvl format. I'm guessing the car is the *.pkg file, then?

If so, I'm still at a loss what the *.cmx files are - I can guess they handle what I said (definitions such as car tires, car smoke, hud, etc) but not exactly how they work.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-12T10:19:05+00:00
- Post Title: File formats for Initial D: Mountain Vengeance (PC)

> Reply from pentaro ↑Mon Nov 11, 2019 6:22 pm at Mon Nov 11, 2019 6:22 pm
>
> I'm guessing the car is the *.pkg file, then?Found it in the .lvl file, too. At the shown vertex address 0x1842B1E.
## Post #6
- Username: pentaro
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 07, 2019 9:19 pm
- Post datetime: 2019-11-18T19:38:14+00:00
- Post Title: File formats for Initial D: Mountain Vengeance (PC)

> Reply from shakotay2 ↑Tue Nov 12, 2019 6:19 pm at Tue Nov 12, 2019 6:19 pm
>
> 
pentaro wrote: ↑Mon Nov 11, 2019 6:22 pmI'm guessing the car is the *.pkg file, then?Found it in the .lvl file, too. At the shown vertex address 0x1842B1E.

Thank you!

Well it seems the game is worse/weirdly coded than I thought. I just tested something - namely I deleted the *.pkg for the cars and the game still runs. It installs but does not seem to use the *.pkg files for car bodies because as you've pointed out, it's used in the tracks. This is going to need more digging around it...

Thank you once again
