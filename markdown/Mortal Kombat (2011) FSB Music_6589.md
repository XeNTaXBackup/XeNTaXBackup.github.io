## Post #1
- Username: interloko
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 27, 2009 12:53 am
- Post datetime: 2011-05-10T19:47:26+00:00
- Post Title: Mortal Kombat (2011) FSB Music

Hi, i've been extracting some MK "9" sounds, but i find some troubles with some music files.
usually i use fsbii to extract fsb files from the xxx file and then use towav for convert them.
with this sample file towav does nothing. i check some file and is FSB4.
i tried fsb_mpeg and gives me mp3 with 0 bytes, also tried with fsbext and it extract the file (not 0 byte) but with xma extension not wav or mp3
am i doing something wrong?

thanx in advance.
here is a sample from xbox version: [http://www.multiupload.com/I4J2I74QDC](http://www.multiupload.com/I4J2I74QDC)

some backgrounds has 2 types of music, legacy and new version.. legacy can be extracted but not the new version.
## Post #2
- Username: RedDeadRedemption
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jul 13, 2010 10:23 pm
- Post datetime: 2011-05-11T06:03:41+00:00
- Post Title: Mortal Kombat (2011) FSB Music

Convert FSB files with towav.
## Post #3
- Username: interloko
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 27, 2009 12:53 am
- Post datetime: 2011-05-11T14:59:13+00:00
- Post Title: Mortal Kombat (2011) FSB Music

> Reply from RedDeadRedemption
>
> Convert FSB files with towav.

> Reply from interloko
>
> with this sample file towav does nothing
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-05-12T09:26:47+00:00
- Post Title: Mortal Kombat (2011) FSB Music

You need to extract the magical FSB4s within this hideous archive.  One is at 0x1c3d-0x10de3d, the other is from 0x10de3d to the end of the file.  xmash then works nicely on both, use other tools are your own peril.
## Post #5
- Username: interloko
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 27, 2009 12:53 am
- Post datetime: 2011-05-12T15:06:23+00:00
- Post Title: Mortal Kombat (2011) FSB Music

thank you very much   .
i googled xmash and this thread comes out: [http://hcs64.com/mboard/forum.php?showt ... showpage=0](http://hcs64.com/mboard/forum.php?showthread=21123&showpage=0)
using fsbii i got 2 files from xxx, i had troubles with one of them and that was because i was using xmash 0.3.. i had a similar trouble as the user of the forum (keeping "Try Padding") so finally downloaded 0.5 and works great.

just in case someone else want it these are the steps i use:
- fsbii for fsb extracting from xxx file
- xmash extracted fsb
- towav
## Post #6
- Username: ogomez
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Mar 23, 2010 2:34 am
- Post datetime: 2011-05-29T06:37:33+00:00
- Post Title: Mortal Kombat (2011) FSB Music

Hi.
I am having trouble extracting lots of the sound effects. I was able to extract all the music just  fine with fsbii 0.6 and xmash 0.7 using an old towav (I don't knwo if there are any other versions).
However I was unable to extract any of the sound files from characters I.E this one. Can someone confirm if there are sounds in this archive?
[http://dl.dropbox.com/u/2142080/CHAR_Baraka.xxx](http://dl.dropbox.com/u/2142080/CHAR_Baraka.xxx)

Also, in some of the files i got plain static when converting the wavs.
If you download this file,
[http://dl.dropbox.com/u/2142080/SND_ENV_Hell.xxx](http://dl.dropbox.com/u/2142080/SND_ENV_Hell.xxx)
fsbii it and then xmash any of the env_hell_chain files, they come up as static.
I'd be very grateful if anyone could check this to see what's wrong or if I'm doing something wrong.
Thanks
## Post #7
- Username: interloko
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 27, 2009 12:53 am
- Post datetime: 2011-06-22T08:56:37+00:00
- Post Title: Mortal Kombat (2011) FSB Music

hi ogomez, for snd_env_ files use only fsbii and towav, xmash is not necesary.
character specific chars fxs are in char files but i can't extract them yet
## Post #8
- Username: Hernaner28
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 18, 2011 8:35 am
- Post datetime: 2011-08-18T00:37:39+00:00
- Post Title: Mortal Kombat (2011) FSB Music

Hi. I am also trying to extract sound. Specially the announcer's ones...  I do the FSBii stuff and then towav and I get many files in .wav but when I play them I don't hear anything..

PD: To extract XXX use this: [http://psx-scene.com/forums/attachments ... ebbeta.rar](http://psx-scene.com/forums/attachments/f180/29751d1313600990-mortal-kombat-character-modding-mk9ps3extrebbeta.rar)

BTW I'm using PS3 files.

EDit 1: I managed to listen to them. They are repeated and some plays well!  Now I'd like to extrac the announcer Char voices... which might be inside each CHAR file. Dunno-

EDIT 2: Managed to extract Char Announcer voices from SND_VO_ANNOUNCER_SHELL.XXX
Now I am going into getting the DLC announcer voices..!
## Post #9
- Username: Hernaner28
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 18, 2011 8:35 am
- Post datetime: 2011-08-18T15:52:03+00:00
- Post Title: Mortal Kombat (2011) FSB Music

I managed to extract some FX character sounds.. for example their projectiles sounds-
You first have to decompress and extract the CHAR file with the MK9 XXX Extractor. Then go into the SND folder and locate SND_FX_CHARACTERNAME_PS3Data.FmodEventFile    
Then you have to FSBii that file and you will get the FSB file. After that use towav.
The problem is that VO (voices) sounds are all correctly extracted but when I want to play them I don't hear anything... they're not playing.
## Post #10
- Username: interloko
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 27, 2009 12:53 am
- Post datetime: 2011-08-31T16:04:55+00:00
- Post Title: Mortal Kombat (2011) FSB Music

hey Hernaner28, the file you posted is password protected =/
## Post #11
- Username: Hernaner28
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 18, 2011 8:35 am
- Post datetime: 2011-09-01T00:24:26+00:00
- Post Title: Mortal Kombat (2011) FSB Music

Sorry. It's Scorpion2k7. He has also released a Texture tool to extract textures, pretty cool. 

BTW check out my Fatality list... [http://www.youtube.com/watch?v=_BqD1NJ6Pq0](http://www.youtube.com/watch?v=_BqD1NJ6Pq0)
