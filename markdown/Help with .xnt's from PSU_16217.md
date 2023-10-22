## Post #1
- Username: Aeternal
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 28, 2016 9:54 am
- Post datetime: 2017-04-28T18:21:30+00:00
- Post Title: Help with .xnt's from PSU

I'm attempting to decrypt Phantasy Star Universe's filetypes. They use a modified version of Ninja Chunk (used in PSO). In some cases they use the same formats as PSO but they're encrypted under another compression method. In this .xnt contains various .xvr's (similar enough to .dds to the point that you can simply change the header and open it). I need help trying to get the .xvr's out. From the file names I can only assume that these are textures for the main menu options.

[https://mega.nz/#!M4Vy2ADa!q18xgaUhljrI ... S9OyVIXkVo](https://mega.nz/#!M4Vy2ADa!q18xgaUhljrI-jATyhvAC5s_6wtRcslTGS9OyVIXkVo)
## Post #2
- Username: Aeternal
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 28, 2016 9:54 am
- Post datetime: 2017-04-30T16:32:26+00:00
- Post Title: Help with .xnt's from PSU

Here's another file with more "exciting" textures inside. 

[https://mega.nz/#!E0MD1IhY!8Cz0GkvWVJmH ... dPsddV6CDg](https://mega.nz/#!E0MD1IhY!8Cz0GkvWVJmHHC21XGjGyOawS7oN2TMQWdPsddV6CDg)
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-30T21:00:47+00:00
- Post Title: Help with .xnt's from PSU

neither of your samples store texture data, look at the file size, unless they are tiny textures
they look like index files for something else or maybe it was an incomplete extraction.
## Post #4
- Username: Aeternal
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 28, 2016 9:54 am
- Post datetime: 2017-05-01T03:32:58+00:00
- Post Title: Help with .xnt's from PSU

> Reply from AceWell
>
> neither of your samples store texture data, look at the file size, unless they are tiny textures
they look like index files for something else or maybe it was an incomplete extraction.

.xnt's aren't the actual textures. They are some sort of archive for the textures. Viewing the data of the file's will show that they contain the actual textures (.xvr's). I need help with being able to extract the textures from .xnt's.
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-05-01T05:16:24+00:00
- Post Title: Help with .xnt's from PSU

> Reply from Aeternal
>
> .xnt's aren't the actual textures
i know, they contain no texture data.   

> They are some sort of archive for the textures
no it is not an archive, there is nothing to extract  

> Viewing the data of the file's will show that they contain the actual textures (.xvr's).
no textures, just texture names, looks like an index for another file like i said before.

> I need help with being able to extract the textures from .xnt's.
until you provide some samples with actual texture data there is nothing more to be done here.
## Post #6
- Username: Aeternal
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 28, 2016 9:54 am
- Post datetime: 2017-05-01T20:01:06+00:00
- Post Title: Help with .xnt's from PSU

> Reply from AceWell
>
> Aeternal wrote:.xnt's aren't the actual textures
i know, they contain no texture data.   
They are some sort of archive for the textures
no it is not an archive, there is nothing to extract  
Viewing the data of the file's will show that they contain the actual textures (.xvr's).
no textures, just texture names, looks like an index for another file like i said before.
I need help with being able to extract the textures from .xnt's.
until you provide some samples with actual texture data there is nothing more to be done here.

Ah I see. Sorry it's my first time doing this sort of research.

These .xnt's are typically accompanied by the actual model file and what I can only assume are particles (also an index file maybe?) or they are data switches of some sort that are applied on the model. These other files are .xnj's and usually .xna's (this file varies).

Here are all of the files: (the .nbl is the archive in which this room object was packed. Forgot to remove it)
[https://mega.nz/#!Rh93lLJQ!s3vL7YGVaaGj ... tLRSIDvWvA](https://mega.nz/#!Rh93lLJQ!s3vL7YGVaaGj5LJDYutjeWFBj13okb8VhtLRSIDvWvA)
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-05-02T01:15:17+00:00
- Post Title: Help with .xnt's from PSU

i still have not seen any texture data yet but there is surely a model in ob_xxx_amy.xnj  
1st submesh of 4



ob_xxx_amy_xnj.png (42.04 KiB) Viewed 67 times



what platform did your samples come from?
## Post #8
- Username: Aeternal
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 28, 2016 9:54 am
- Post datetime: 2017-05-02T02:17:04+00:00
- Post Title: Help with .xnt's from PSU

> Reply from AceWell
>
> i still have not seen any texture data yet but there is surely a model in ob_xxx_amy.xnj  
1st submesh of 4
ob_xxx_amy_xnj.png

what platform did your samples come from?

These samples came from the PC version of PSU. Extracted using Gasetools from Essen's Github.

Also, awesome work!
## Post #9
- Username: Aeternal
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 28, 2016 9:54 am
- Post datetime: 2017-06-05T18:59:25+00:00
- Post Title: Help with .xnt's from PSU

> Reply from AceWell
>
> i still have not seen any texture data yet but there is surely a model in ob_xxx_amy.xnj  
1st submesh of 4
ob_xxx_amy_xnj.png

what platform did your samples come from?

Hmm, the texture data is held in the TMLL header chunk (the other header inside the .nbl archive). Current tools can only extract the NMLL header chunk. Ya think someone could look into researching the chunk a bit more? I'm not experienced enough to research and create a proper extractor for this.
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-06-05T23:01:43+00:00
- Post Title: Help with .xnt's from PSU

from the looks of the gasetools source on github, there is some encryption and compression involved.
i would run this by aluigi on zenhax, he likes C programming and has a knack for converting tools to
simple bms scripts, post a few nbl samples and a link to the gasetools nbl source and maybe he can help. 
[https://github.com/essen/gasetools/tree/master/nbl](https://github.com/essen/gasetools/tree/master/nbl)
