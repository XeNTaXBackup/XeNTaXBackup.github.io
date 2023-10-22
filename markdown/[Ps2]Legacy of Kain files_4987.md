## Post #1
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2010-09-07T09:34:32+00:00
- Post Title: [Ps2]Legacy of Kain files

Hi to everyone 
I tried Wheel of doom in the Ps2 Legacy of Kain Defiance (Crystal Dynamics, silikon  game, and it gives me many files. I know that .mul files are music and .raw files are a kind of textures, but I can't even imagine or open the others (.drm, .sam, .vrm, .smf)

can you help me in identifying/opening those?

I wanted to add samples but the website does not allow me. Therefore, here
[http://pcgames.gwn.com/downloads/file.p ... iance.html](http://pcgames.gwn.com/downloads/file.php/id/5792/Legacy_of_Kain_Defiance.html)
is the demo.
## Post #2
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2010-10-24T18:39:25+00:00
- Post Title: [Ps2]Legacy of Kain files

does anyone know which files are the models, the actual models of the stuff (like the Spectral Reaver or the creatures)?
## Post #3
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-10-25T06:25:23+00:00
- Post Title: [Ps2]Legacy of Kain files

Try this: [http://thelostworlds.net/](http://thelostworlds.net/)
## Post #4
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2010-10-25T07:44:47+00:00
- Post Title: [Ps2]Legacy of Kain files

i know that website :d but it says nothing about the models, only the textures!
## Post #5
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2010-10-26T12:07:04+00:00
- Post Title: [Ps2]Legacy of Kain files

Isn't this what you are looking for: [http://thelostworlds.net/Software/ModelEx.html](http://thelostworlds.net/Software/ModelEx.html)
## Post #6
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2010-10-26T12:38:52+00:00
- Post Title: [Ps2]Legacy of Kain files

no, because it opens only Soul Rever Models, and I'm looking for Defiance models...
## Post #7
- Username: ghoul
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 02, 2011 11:11 pm
- Post datetime: 2011-05-07T18:21:08+00:00
- Post Title: [Ps2]Legacy of Kain files

refresh
Maybe there is someone, who know how to convert defiance .drm files to other format ?
## Post #8
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-05-07T18:58:01+00:00
- Post Title: [Ps2]Legacy of Kain files

was hoping for Noesis, but it does not support them, yet.
## Post #9
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2011-06-03T16:41:05+00:00
- Post Title: [Ps2]Legacy of Kain files

If you want Kain or Raziel,u need tombraider laracroft and guadian of light expansion pack to rip them.Then search for unpackTRU program but you need exactly version for rip them.Good luck
## Post #10
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-06-03T16:45:11+00:00
- Post Title: [Ps2]Legacy of Kain files

what about the swords?
## Post #11
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2011-06-04T02:58:52+00:00
- Post Title: [Ps2]Legacy of Kain files

Don't know,may be you need search more in tombraider forum for another version which support Legacy of Kain: Defiance
## Post #12
- Username: ghoul
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 02, 2011 11:11 pm
- Post datetime: 2011-06-04T23:24:26+00:00
- Post Title: [Ps2]Legacy of Kain files

Swords, Kain, Raziel... If you use 3D Ripper Dx it is easy to get it. Problems are with some enemies...
## Post #13
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-06-05T06:40:44+00:00
- Post Title: [Ps2]Legacy of Kain files

like the Elder God?
## Post #14
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2013-06-01T15:17:50+00:00
- Post Title: [Ps2]Legacy of Kain files

I wonder if someone has managed to extract the audio files from the series..
## Post #15
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2013-06-03T06:01:15+00:00
- Post Title: [Ps2]Legacy of Kain files

actually, thanks to QuickBMS and its wonderful author, I have managed to finally get a look of all the files.
this is the script

> ###
>
> get FILES short
>
> get DUMMY byte
>
> get DUMMY byte
>
> for i = 0 < FILES
>
>     get NAME_CRC long
>
> next i
>
> for i = 0 < FILES
>
>     get SIZE long
>
>     get OFFSET long
>
>     get DUMMY long
>
>     log "" OFFSET SIZE
>
> next i
>
> ###

But, but, it extract a series of MUS (audio/BGM) files and a load of .dat files which I have no idea how to actually read. the result is the same form either the DAT file of the PC (GOG re-release) or the Ps2 file, extracted from the ISO.

Soul Spiral, on the other hand, yields a series of unrecognized formats: .smf, .drm, .vrm. I'd say one of those 3 could be the streamed audio (probably SMF), but no tool I have will allow me to check it. can someone help?

UPDATE: DRM files, are, in fact, archives. Turfster's tool for tomb raider legends Graverobber managed to read them for the TR game, but not for this one.

UPDATE2: the key could lie in the .MUL files extracted off the DAT archive. but, MUL2wav will crash when converting some of the files, while it will convert all the BGM.
## Post #16
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2013-06-04T07:01:42+00:00
- Post Title: Re: [Ps2]Legacy of Kain files

who could I ask in order to update-fix the MUL2WAV program? or can someone suggest alternatives?

EDIT: or if a script for extraction could be made... this is some info about MUL files
[http://www.tombraiderforums.com/showpos ... ostcount=1](http://www.tombraiderforums.com/showpost.php?p=5439809&postcount=1)
## Post #17
- Username: Jandazekon
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jan 27, 2012 6:26 pm
- Post datetime: 2017-07-04T15:49:04+00:00
- Post Title: Re: [Ps2]Legacy of Kain files

> Reply from Devilot
>
> actually, thanks to QuickBMS and its wonderful author, I have managed to finally get a look of all the files.
this is the script

###
get FILES short
get DUMMY byte
get DUMMY byte
for i = 0 < FILES
    get NAME_CRC long
next i
for i = 0 < FILES
    get SIZE long
    get OFFSET long
    get DUMMY long
    log "" OFFSET SIZE
next i
###

But, but, it extract a series of MUS (audio/BGM) files and a load of .dat files which I have no idea how to actually read. the result is the same form either the DAT file of the PC (GOG re-release) or the Ps2 file, extracted from the ISO.

Soul Spiral, on the other hand, yields a series of unrecognized formats: .smf, .drm, .vrm. I'd say one of those 3 could be the streamed audio (probably SMF), but no tool I have will allow me to check it. can someone help?

UPDATE: DRM files, are, in fact, archives. Turfster's tool for tomb raider legends Graverobber managed to read them for the TR game, but not for this one.

UPDATE2: the key could lie in the .MUL files extracted off the DAT archive. but, MUL2wav will crash when converting some of the files, while it will convert all the BGM.I think the .MUS files either contains sequenced music or pointers and/or settings to look at in the game executable file.

The .SAM files might be instrument files with loop points embedded or it's simply multiple audio files packed tightly into each other, and the instrument headers and/or sample loop points, might be in the .MUS file or connected with something that the .MUS calls with in the .EXE file of the game.

I can't guess more than that.
