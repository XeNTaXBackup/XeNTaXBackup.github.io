## Post #1
- Username: LadiesMan217
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Mar 18, 2016 5:33 am
- Post datetime: 2017-06-07T18:31:25+00:00
- Post Title: RE5 TEX and LMT PC to PS3 Conversion

Is there any tool that exists to convert Resident Evil 5 PC tex files to ps3 tex files? From what I've read before you have to flip the first few bytes but I don't exactly know which bytes to flip. I'm trying to import textures from pc to ps3 to make STARS Wesker work in cutscenes from the Model Swap Patch made for the pc gold edition which has support for every model for cutscenes. If I could import these models I could finally get Characters to work on cutscenes without crashing the game.
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-06-07T23:56:31+00:00
- Post Title: RE5 TEX and LMT PC to PS3 Conversion

> Reply from LadiesMan217
>
> Is there any tool that exists to convert Resident Evil 5 PC tex files to ps3 tex files? From what I've read before you have to flip the first few bytes but I don't exactly know which bytes to flip. I'm trying to import textures from pc to ps3 to make STARS Wesker work in cutscenes from the Model Swap Patch made for the pc gold edition which has support for every model for cutscenes. If I could import these models I could finally get Characters to work on cutscenes without crashing the game.

I wrote the conversion tools a long time ago which converted PS3 textures to PC when I worked on the Resident Evil 5: Gold Edition PC Mod which got cancelled. Anyway, all you have to do is endian flip the header and patch the texture type (magic differs from PC/PS3). Good luck!
## Post #3
- Username: LadiesMan217
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Mar 18, 2016 5:33 am
- Post datetime: 2017-06-08T17:55:27+00:00
- Post Title: RE5 TEX and LMT PC to PS3 Conversion

> Reply from Gh0stBlade
>
> I wrote the conversion tools a long time ago which converted PS3 textures to PC when I worked on the Resident Evil 5: Gold Edition PC Mod which got cancelled. Anyway, all you have to do is endian flip the header and patch the texture type (magic differs from PC/PS3). Good luck!
I don't know the length of said header is the thing and every TEX files seems to have a different length one, but I'll drop that one for now as textures aren't too much of a thing right now. Back in your RE5 modding days, did you ever mod lmt files? Seems everything is endian flipped when going from PC to PS3. Can you you or someone check these files to help convert these? Or maybe a quickbms script? Maybe make a tool to convert them? Wilsono made a tool to edit lmt files, it can edit ps3 and pc lmt and conversion wise only convert ps3 lmts to pc but not the other way around -_-. Any help would GREATLY be appreciated. I actually tried unpacking the pc lmt's and repacking them using ps3 mode but it doesn't work bc the unpacked assets of the lmt are also pc so ugghhh...

lmt link:
[https://www.dropbox.com/s/iicoeclpu05tx ... n.zip?dl=1](https://www.dropbox.com/s/iicoeclpu05tx7d/pl03action.zip?dl=1)

Wilsono's LMT Editor V2.0
[http://www.mediafire.com/file/5n277fyfu ... T+Tool.rar](http://www.mediafire.com/file/5n277fyfucba9c6/Resident+Evil+5+LMT+Tool.rar)

Any help would be GREATLY appreciated. I got models to successfully swap and both Jill's have cutscene support. Now I'm working on the Weskers.
## Post #4
- Username: LadiesMan217
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Mar 18, 2016 5:33 am
- Post datetime: 2017-06-14T02:19:50+00:00
- Post Title: RE5 TEX and LMT PC to PS3 Conversion

Anyone -_-
