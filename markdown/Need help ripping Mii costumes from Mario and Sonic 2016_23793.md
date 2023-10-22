## Post #1
- Username: Spectral1998
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 26, 2021 7:56 am
- Post datetime: 2021-04-26T07:46:11+00:00
- Post Title: Need help ripping Mii costumes from Mario and Sonic 2016

Ok so I've been ripping some Mii costumes from Mario and Sonic 2016 when I discovered that the files are improperly named.

Heres an example of the improperly named files that I need help with



Now what I need help with are what's inside these files.  If you want to know what Mii Costume I'm ripping from I'll list it down below.

Mii COSTUMES THAT I NEED RIPPED

Super Sonic
Storm the Albatross 
Sonic the Werehog
Chip the Light Gaia 
Emerl the Gizoid
Marine the Raccoon
Tikal the Echidna 

If anyone can tell me what .00 file contains these characters I'd be very much appreciated. Or make a document on it and list it here  

Here is a link to the source files if you want some quick examining -- [https://www.dropbox.com/s/fie1izuezbdr0 ... es.7z?dl=0](https://www.dropbox.com/s/fie1izuezbdr0l6/Mii%20Costumes.7z?dl=0)
## Post #2
- Username: Spectral1998
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 26, 2021 7:56 am
- Post datetime: 2021-04-26T08:05:34+00:00
- Post Title: Need help ripping Mii costumes from Mario and Sonic 2016

Forgot to mention you could write a list of all the .00 files these models are stored in and tell me here
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-04-26T13:24:21+00:00
- Post Title: Need help ripping Mii costumes from Mario and Sonic 2016

well, 439 .pac.00 files, that's some work to do   Using hex2obj (view link in my sig) I can show you a general approach:
.



body_000.png (108.21 KiB) Viewed 54 times



H2O files for the next 2 sub meshes:

0x5210 1544
Vb1
40 24
0x5E20 659
121110
0x0 255

0xC608 656
Vb1
40 24
0xCB28 297
121110
0x0 255
## Post #4
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-04-26T14:55:19+00:00
- Post Title: Need help ripping Mii costumes from Mario and Sonic 2016

All tools for such games are already exist. Literally first result in google for "mario sonic 2016 pac files":
[https://www.vg-resource.com/thread-36365.html](https://www.vg-resource.com/thread-36365.html)

Required tools: older pacpack version ([link](https://drive.google.com/file/d/1K7cq7sTLpZqs6uNN1gg1H8HQyGqyImBn/view?usp=sharing)), modelfbx from any [libgens-sonicglvl](https://github.com/blueskythlikesclouds/libgens-sonicglvl/tree/experimental/bin) package, any tool for gxt/dds textures ([switch toolbox](https://github.com/KillzXGaming/Switch-Toolbox) will do). 
If you want to apply materials upon converting models to fbx, you need to convert gtx(dds) textures into normal dds first.

Sample result: [link](https://drive.google.com/file/d/1XmWBsJ6ngkPfiEvdKJX8zFyxGFFJ-9Ch/view?usp=sharing)
