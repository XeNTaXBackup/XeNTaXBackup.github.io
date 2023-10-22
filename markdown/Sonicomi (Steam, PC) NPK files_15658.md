## Post #1
- Username: williamjcm
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 29, 2016 11:11 pm
- Post datetime: 2016-12-29T15:41:59+00:00
- Post Title: Sonicomi (Steam, PC) NPK files

Hello everyone !

I'm the kind of guy who likes to listen to video game music outside of video games, and I want to get the music from the Steam release of Sonicomi ([store page here](http://store.steampowered.com/app/444140/)).

The game has multiple *.npk files that contain the game's data, each with an indicative filename.

According to the DLL files in the game folder, the music is in OGG Vorbis format (libogg.dll and libvorbis.dll can be found).

I tried using Dragon UnPACKer's HyperRipper to open the sound.npk file (since there's no music.npk or bgm.npk file, I assume this is the one).

Of course, while extracting the music is my top priority, opening the other *.npk files and extracting their contents would be great too .

Note: from what I've read, the Steam release of Sonicomi seems to be based on the PS3 release of Sonicomi.

Thanks in advance for your answer(s).

EDIT: Opening Sonicomi_Steam.exe with a hex editor and searching for "npk" brings me to a list of all *.npk files in the game directory. Mware.dll (in the game dir) might be the binary that does all the work, according to another search.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-05T17:02:40+00:00
- Post Title: Sonicomi (Steam, PC) NPK files

have you tried this?   
[https://github.com/morkt/GARbro](https://github.com/morkt/GARbro)
## Post #3
- Username: bobbeebs
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 07, 2017 2:45 am
- Post datetime: 2017-02-06T18:49:33+00:00
- Post Title: Sonicomi (Steam, PC) NPK files

The latest Garbro works to unpack and repack npk files.  However the mdl files inside seems to not be compatible with other mdl file reading programs.  Even the mdl script for the japanese Sonicomi.

Here is an example.

[http://www43.zippyshare.com/v/DZRc1DzT/file.html](http://www43.zippyshare.com/v/DZRc1DzT/file.html)
## Post #4
- Username: williamjcm
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 29, 2016 11:11 pm
- Post datetime: 2017-03-07T10:19:05+00:00
- Post Title: Sonicomi (Steam, PC) NPK files

> Reply from AceWell
>
> have you tried this?   
https://github.com/morkt/GARbro
Sorry for the late reply.

It worked perfectly.

Thanks.
