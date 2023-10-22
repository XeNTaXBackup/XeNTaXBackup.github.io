## Post #1
- Username: iCode
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Apr 03, 2017 4:53 am
- Post datetime: 2017-04-11T12:45:39+00:00
- Post Title: Trying to view this .tex file

Could anyone tell me how to view .tex files, nothing will open them without errors.

Thanks
[controller_layout_win.zip](https://xentaxbackup.github.io/file/12763_controller_layout_win.zip)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-11T15:32:13+00:00
- Post Title: Trying to view this .tex file

controller_layout_win_tex.png (61.84 KiB) Viewed 130 times


512x512 dxt5 image with 52 byte header
width at 0x28 and height at 0x32
## Post #3
- Username: iCode
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Apr 03, 2017 4:53 am
- Post datetime: 2017-04-11T18:57:42+00:00
- Post Title: Trying to view this .tex file

Thank you so much

Would you mind telling me how you done this and how I can do it with other .tex files, how are you supposed to know what settings to choose.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-12T13:13:39+00:00
- Post Title: Trying to view this .tex file

> Reply from iCode
>
> Would you mind telling me how you done this and how I can do it with other .tex files
just input the settings like you see in the image, 
-set the width of the image
-set the shift to account for where the data actually starts
-set the pixel format

> how are you supposed to know what settings to choose.
by trial and error   

there is no guarantee all of your images are the same pixel format or size etc
if you have more samples i will try to make a Noesis python script to open them.   
also what is the game name where the samples come from?
from the image it looks like an X360 controller so i think we know the platform at least.
## Post #5
- Username: iCode
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Apr 03, 2017 4:53 am
- Post datetime: 2017-04-12T18:26:18+00:00
- Post Title: Trying to view this .tex file

Thanks for that 

I'll try and explain what I'm trying to do

I'm trying to replace the xbox buttons with ps3/ps4 buttons using photoshop and then restoring the .tex so that it shows up in game.

I managed to get it working with a game before all I had to do was put the .tex in "game name/data\gui\" and it worked but other games haven't been as simple and I have no idea what to do.

With this game Ghostbusters: The Video Game (2009) it uses .POD which I managed to extract but now I'm trying to find the correct xbox texture to replace it with PS buttons. But no doubt I'll need to repack it into the .POD file which I have no idea how to.
[xbox360_buttons.zip](https://xentaxbackup.github.io/file/12768_xbox360_buttons.zip)
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-13T14:55:06+00:00
- Post Title: Trying to view this .tex file

i updated the Ghostbusters script here to open your 2 samples   
[viewtopic.php?p=125821#p125821](http://forum.xentax.com/viewtopic.php?p=125821#p125821)

i can't really help with the modding/repacking stuff since that is not my area.
