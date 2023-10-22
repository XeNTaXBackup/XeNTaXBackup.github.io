## Post #1
- Username: JonMagon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 12, 2018 6:13 pm
- Post datetime: 2018-04-12T11:02:27+00:00
- Post Title: Beasts and Bumpkins Tools [BBTools]

I've disassembled BB and created the tools.
Language is C# with MonoGame.

MapViewer
A tool to render the mission/savegame files


SpriteViewer
VIDEO.BOX reader


Download link: [https://github.com/JonMagon/BBTools](https://github.com/JonMagon/BBTools)
In BBTools/additions you can find pseudocode of some functions from BEASTS.EXE.
Ambient and Speach are in TODO.

Vielen Dank für Trass3r, der wirklich vieles gemacht hat.

Binaries: [https://github.com/JonMagon/BBTools/rel ... naries.zip](https://github.com/JonMagon/BBTools/releases/download/v0.1-alpha/BBTools.Binaries.zip)

My Skype: jonmagon
## Post #2
- Username: JonMagon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 12, 2018 6:13 pm
- Post datetime: 2018-04-15T12:45:27+00:00
- Post Title: Beasts and Bumpkins Tools [BBTools]

[https://github.com/JonMagon/BBTools/wik ... y-analysis](https://github.com/JonMagon/BBTools/wiki/Disassembly-analysis)
Da gibt's auch eine Anleitung zur Aktivierung des MapEditor (auf Englisch)
## Post #3
- Username: zhelatinobambino
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2018-07-28T12:34:57+00:00
- Post Title: Beasts and Bumpkins Tools [BBTools]

Nicely done!
Much better than my random tiles   : [https://web.archive.org/web/20121024005 ... om/#node-5](https://web.archive.org/web/20121024005346/http://trass3r.xentax.com/#node-5)
## Post #4
- Username: JonMagon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 12, 2018 6:13 pm
- Post datetime: 2018-08-18T11:16:00+00:00
- Post Title: Beasts and Bumpkins Tools [BBTools]

> Reply from Rheini
>
> Nicely done!
Much better than my random tiles   : https://web.archive.org/web/20121024005 ... om/#node-5
Without you, this would have been impossible.
## Post #5
- Username: zhelatinobambino
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2020-01-28T23:40:51+00:00
- Post Title: Beasts and Bumpkins Tools [BBTools]

There are also tools for decoding everything into .png and .wav files:
[https://github.com/Trass3r/OpenBB/releases](https://github.com/Trass3r/OpenBB/releases)
## Post #6
- Username: finglor
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 29, 2023 11:48 pm
- Post datetime: 2023-06-29T15:52:14+00:00
- Post Title: Beasts and Bumpkins Tools [BBTools]

Hello,

I am interested in modifying the beasts.exe in a hex editor to increase the resolution of the game. I was able to modify it and increase the size by 
searching for for 80020000E001 and replace the entire thing with 000500000004 for 1280x1024.

This makes the play area bigger like this picture [https://imgur.com/gallery/7pJkok0](https://imgur.com/gallery/7pJkok0) I also moved the portrait with these 

At offset 29714 replace 1C 02 with 9C 04 
At offset 2972D replace 7C 01 with 9C 03.

The only problem I have left are the thought bubble (not critical)
Sprites like houses and monsters sometimes disappear if they are outside the original 640x480 area. I am guessing there is some kind of clipping or frustum culling going on to increase performance.

Since you have disassebled the exe do you have any idea where  this might be?

Thanks.
## Post #7
- Username: Deanson
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 07, 2023 9:45 am
- Post datetime: 2023-07-07T05:13:26+00:00
- Post Title: Beasts and Bumpkins Tools [BBTools]

Hello,

As far as I'm concerned, modifying game files using a hex editor may prove interesting. As regards the disappearance of sprites outside the original area, it's likely that some form of clipping or frustration reduction has been implemented in the game to optimize performance.
