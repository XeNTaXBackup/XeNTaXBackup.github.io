## Post #1
- Username: eriger777
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Sep 25, 2014 5:30 am
- Post datetime: 2015-02-05T00:46:46+00:00
- Post Title: Extracting .ovl and .aux files? Elite Dangerous.

I recently got a copy of a space game and id like to be able to extract the audio/models from the game.

I've attached an example .ovl file and a .aux file below. I have no knowledge on reverse engineering file formats. So I'm sorry if I'm not the best at learning things. However i will try to do the best that I can. I was able to gather a bit of information on the web. However no one has archived this yet.

> 'The OVL and OVS files are compressed with zlib. OVL files make up parts of a virtual serialized filesystem, and are partially compressed. OVS files are completely compressed and contains most of the bulk data. Can't give you more info than that at the moment as I'm at work and I've not looked at them for a while.'
>
> Here is the top of the .aux file in hex workshop.

Quick Update: I was able to extract some of the files and get the proper name. However, I'm not able too play them. They're corupt.

I used this quickbms script.



[viewtopic.php?f=13&p=74664#p74664](http://forum.xentax.com/viewtopic.php?f=13&p=74664#p74664)

Here is the top of the .aux file in hex workshop.


Here is the .ovl file.



OVL FILE DOWNLOAD: [https://mega.co.nz/#!Cx5nHLTa!JgTCENPHM ... orLIdPibqs](https://mega.co.nz/#!Cx5nHLTa!JgTCENPHMY4MD1LeOLFhwwt8DcZr8pngforLIdPibqs)

AUX FILE DOWNLOAD: [https://mega.co.nz/#!60YAkQ5Q!6M_aexZSx ... KM7t26BaUs](https://mega.co.nz/#!60YAkQ5Q!6M_aexZSx8JyE7GQAKi1K1qD17n9ULOMGKM7t26BaUs)
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-02-05T09:43:23+00:00
- Post Title: Extracting .ovl and .aux files? Elite Dangerous.

The OVL contains zlip compressed data (see attachment).
The aux consists of multiple wwise ogg files. Run that one through a file format scanner, searching for WAV, then parse with ww2ogg (codebooks_aoTuV_603).
[AudioInit_decomp.zip](https://xentaxbackup.github.io/file/8606_AudioInit_decomp.zip)
## Post #3
- Username: eriger777
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Sep 25, 2014 5:30 am
- Post datetime: 2015-02-05T15:48:15+00:00
- Post Title: Extracting .ovl and .aux files? Elite Dangerous.

Thanks! I got the .aux working perfectly. However I'm a tad confused on what I should do as the next step on the .ovl file.
## Post #4
- Username: eriger777
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Sep 25, 2014 5:30 am
- Post datetime: 2015-02-08T01:55:00+00:00
- Post Title: Extracting .ovl and .aux files? Elite Dangerous.

Bump?
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-02-16T13:06:02+00:00
- Post Title: Extracting .ovl and .aux files? Elite Dangerous.

> Reply from eriger777
>
> Thanks! I got the .aux working perfectly. However I'm a tad confused on what I should do as the next step on the .ovl file.
Well... what is your goal?
## Post #6
- Username: eriger777
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Sep 25, 2014 5:30 am
- Post datetime: 2015-02-20T15:23:09+00:00
- Post Title: Extracting .ovl and .aux files? Elite Dangerous.

> Reply from AlphaTwentyThree
>
> eriger777 wrote:Thanks! I got the .aux working perfectly. However I'm a tad confused on what I should do as the next step on the .ovl file.
Well... what is your goal?

Id like to be able to get the textures/models. I can send you some more sample files from the models folder?
## Post #7
- Username: DancingRobot
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 30, 2015 4:35 am
- Post datetime: 2015-07-30T02:29:40+00:00
- Post Title: Extracting .ovl and .aux files? Elite Dangerous.

Was anything figured out on this?

I am interested on trying to extract some sound files also.
## Post #8
- Username: locastan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 06, 2015 9:50 pm
- Post datetime: 2015-10-13T10:33:02+00:00
- Post Title: Extracting .ovl and .aux files? Elite Dangerous.

Well...I made a little progress in trying to get the textures out of an ovl. I extracted a powerplay icon (...FORC-FDEV-D-1010\Win32\Items\UIStreams\PowerIcons\PowerIcon0\Data.ovl)

First step ofc. offzip on the ovl in question. The extracted dat file seems like a dds file with custom header:

I tried to load it as raw image format in IrfanView (64x64 32BPP RGBA) and could barely recognize a bit garbled ALD Power logo:


I then removed the FFFF and 0000 Blocks to only get the data and loaded again (64x32 32BPP RGBA):


Its not pretty, but should give the more experienced image hackers here some starting point I hope.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-15T07:44:52+00:00
- Post Title: Extracting .ovl and .aux files? Elite Dangerous.

dunno about the icon but when I extracted Data.ovs.textures_l0 from Eagle_Textures
I got this with BC2_UNORM_SRGB (unsure about palette):



eagle.JPG (125.68 KiB) Viewed 577 times
## Post #10
- Username: locastan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 06, 2015 9:50 pm
- Post datetime: 2015-10-29T08:37:01+00:00
- Post Title: Extracting .ovl and .aux files? Elite Dangerous.

That looks quite good, despite the colors. 

Here is what it looks like in game: [http://www.degacom.de/index.php?attachm ... agle3-jpg/](http://www.degacom.de/index.php?attachment/99-ship-coredynamics-eagle3-jpg/)
You definitely see those serrated parts in your texture where the paint has worn off at the edges of the ship.

Could there be some kind of alpha map or normal map superimposed causing the color shift?

What does it look like if you swap RGB->BGR or GRB?
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-29T19:22:50+00:00
- Post Title: Extracting .ovl and .aux files? Elite Dangerous.

there's no improvement - BGR looks like this for example:



BGR.JPG (122.97 KiB) Viewed 560 times


Think it's a matter of palette but I don't have the patience to assemble/get the correct one from a 30 MB file.
## Post #12
- Username: anotheruser
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 28, 2017 11:51 pm
- Post datetime: 2017-03-28T16:01:19+00:00
- Post Title: Extracting .ovl and .aux files? Elite Dangerous.

Holey Moley - what a bump!

But did anyone figure out anything about the audio?

I have a 420MB "audio_music_bnk_s.aux" file which I can't extract, despite my best efforts
