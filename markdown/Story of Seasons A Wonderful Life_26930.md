## Post #1
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2023-07-02T08:40:48+00:00
- Post Title: Story of Seasons: A Wonderful Life

Do anyone figure it out how to Exporting the model and texture from Story of Seasons: A Wonderful Life. here  a sample.[https://www.mediafire.com/folder/0hr7fppr3u9mc/HMW+L](https://www.mediafire.com/folder/0hr7fppr3u9mc/HMW+L)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-02T11:22:42+00:00
- Post Title: Story of Seasons: A Wonderful Life

Awful format. First I thought it has 56 bytes "float blocks" separated by extra bytes (in blue rectangles) but then it went totally bogus:
.



lzs_wgat.png (64.71 KiB) Viewed 96 times
## Post #3
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2023-07-02T16:06:24+00:00
- Post Title: Story of Seasons: A Wonderful Life

> Reply from blacknight411 ↑Sun Jul 02, 2023 4:40 pm at Sun Jul 02, 2023 4:40 pm
>
> 
Do anyone figure it out how to Exporting the model and texture from Story of Seasons: A Wonderful Life. here  a sample.https://www.mediafire.com/folder/0hr7fppr3u9mc/HMW+L

Can you share the password for the installed game's disc file (1.213.702.462 bytes zip compressed file)?
(I would like to get more sample files.)
## Post #4
- Username: DahniMae
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Mar 19, 2023 4:18 am
- Post datetime: 2023-07-11T17:20:12+00:00
- Post Title: Story of Seasons: A Wonderful Life

hey! please join our discord, we have a whole host of people making mods for both versions of the game and doing all sorts of stuff, if you need help getting to any of the resources please hop in here!
(The Switch and the Steam version uses the same files once the disc of the steam version is unpacked, if you'd like to get at the files extracting romfs from the switch version in emulator will give you the same ones, the only difference is the occasional texture size is bigger for steam)

[https://discord.gg/sos-rf-modding-894573835490295898](https://discord.gg/sos-rf-modding-894573835490295898)

We've been desperately looking for a way to crack these bumv2 model formats, so we'd love to help

So far I'm aware that they are the version 2 formats of the bumv1 senran kagura/to love ru series formats apparently

there's old scripts for the version 1 floating around but the version 2 changes a lot apparently so it doesn't work
## Post #5
- Username: DahniMae
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Mar 19, 2023 4:18 am
- Post datetime: 2023-07-11T17:24:35+00:00
- Post Title: Story of Seasons: A Wonderful Life

> Reply from shakotay2 ↑Sun Jul 02, 2023 7:22 pm at Sun Jul 02, 2023 7:22 pm
>
> 
Awful format. First I thought it has 56 bytes "float blocks" separated by extra bytes (in blue rectangles) but then it went totally bogus:
.
lzs_wgat.png

also, the reason everything looks like gobbledegook here is that you are opening the .lzs file directly this isnt the actual model file itself

all files in the game are archives compressed into .lzs files

you need to use our modding tools to decompress the files, and then rip open the archives

the games models are .bum formats specifically the bumv2 formats

and look like this inside them:
[https://cdn.discordapp.com/attachments/ ... /image.png](https://cdn.discordapp.com/attachments/1089796521656070145/1128376267591405628/image.png)
