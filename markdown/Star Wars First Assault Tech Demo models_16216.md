## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-28T17:55:46+00:00
- Post Title: Star Wars First Assault Tech Demo models

Tool checked and working on all skeletal models from that demo.

Drag .skeletalmesh file onto .exe and it will extract model into 3 formats: .OBJ, .SMD and .ASCII. Only SMD file will have proper skeleton connected to bones. If NameTable.txt produced by Extract.exe will be in the same folder, bones will have proper names.

a quick solution for textures:
- run bms script on TFC, this will unpack all textures in raw format
- open them with noesis plugin (will not work for all of them, but most big ones)




[StarWars_FA_model.rar](https://xentaxbackup.github.io/file/12831_StarWars_FA_model.rar)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-29T11:45:14+00:00
- Post Title: Star Wars First Assault Tech Demo models

Umodel must be able to extract all textures from this game, but for some reason it refuses to get most of them. Maybe just needs some options. Anyway, you should be able to get any texture either with umodel or raw extraction tools provided here.

If you have troubles finding particular texture, just open its .Texture2D file and look for image offset in .TFC package. BMS script will unpack them with names according to these offsets. Like here for this blasterRifle, its usually there after those FFFFFFFFFFFFFFFFF, I marked it green:
## Post #3
- Username: ginev
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Feb 15, 2016 6:53 pm
- Post datetime: 2017-04-29T18:05:17+00:00
- Post Title: Star Wars First Assault Tech Demo models

Hey is it possible to release the game so we can download it.I have seen that you released some link in facepunch but the link dont work.Could you upload it somewhere else?

EDIT:Ahh never mind i get it.Thanks alot man!!!
## Post #4
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-04-30T01:21:29+00:00
- Post Title: Star Wars First Assault Tech Demo models

Thanks for the work on this i posted some sample files a few weeks ago and no one cared to look at so it's nice that you got it working.

Question though what is the command line for animations instead of skeletalmesh?
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-30T05:26:04+00:00
- Post Title: Star Wars First Assault Tech Demo models

> Reply from JakeGreen
>
> Thanks for the work on this i posted some sample files a few weeks ago and no one cared to look at so it's nice that you got it working.

Question though what is the command like for animations instead of skeletalmesh?

command for what?
## Post #6
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-05-02T05:50:51+00:00
- Post Title: Star Wars First Assault Tech Demo models

i didn't type it right the first time anyways well you pointed out that -filter=skeletalmesh extracts models with bones but what would you put in place of skeletalmesh for animations?
## Post #7
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2017-05-02T15:50:29+00:00
- Post Title: Star Wars First Assault Tech Demo models

Seems like UModel can extract all major animations , so if you combine it with this tool it should work perfectly fine on import
## Post #8
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-05-03T06:56:58+00:00
- Post Title: Star Wars First Assault Tech Demo models

> Reply from Highflex
>
> Seems like UModel can extract all major animations , so if you combine it with this tool it should work perfectly fine on import

How did you get umodel to extract the animations because when i try to do that the CMD Umodel opens moves really fast and nothing gets exported.
## Post #9
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2017-05-03T09:32:38+00:00
- Post Title: Star Wars First Assault Tech Demo models

> Reply from JakeGreen
>
> Highflex wrote:Seems like UModel can extract all major animations , so if you combine it with this tool it should work perfectly fine on import 

How did you get umodel to extract the animations because when i try to do that the CMD Umodel opens moves really fast and nothing gets exported.

If you just check Animation it should process them ( then you can see detailed info about each anim sequence ), although there seeems to be a issue with the compression tracks so the export is not valid, i will see if i can fix this in my custom build of UE Viewer.
## Post #10
- Username: Chaotic1870
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Nov 30, 2020 2:14 pm
- Post datetime: 2020-12-07T15:42:54+00:00
- Post Title: Star Wars First Assault Tech Demo models

i am 3 years late, but may i ask how to get the skeletalmesh? UModel seems to dislike First Assaults skeletal Meshes and all its grabbing are the 3rd person models which are downscaled by alot, thanks in advance!
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-12-10T07:05:25+00:00
- Post Title: Star Wars First Assault Tech Demo models

> Reply from Chaotic1870 ↑Mon Dec 07, 2020 11:42 pm at Mon Dec 07, 2020 11:42 pm
>
> 
i am 3 years late, but may i ask how to get the skeletalmesh? UModel seems to dislike First Assaults skeletal Meshes and all its grabbing are the 3rd person models which are downscaled by alot, thanks in advance!
umodel must extract them. Dont convert them, just extract assets.
## Post #12
- Username: Chaotic1870
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Nov 30, 2020 2:14 pm
- Post datetime: 2020-12-10T14:25:39+00:00
- Post Title: Star Wars First Assault Tech Demo models

How do i get umodel to extract them? When i try it gives me an error and doesnt extract anything
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-12-10T14:41:46+00:00
- Post Title: Star Wars First Assault Tech Demo models

> Reply from Chaotic1870 ↑Thu Dec 10, 2020 10:25 pm at Thu Dec 10, 2020 10:25 pm
>
> 
How do i get umodel to extract them? When i try it gives me an error and doesnt extract anything
read documentation or ask umodel author (gildor)
## Post #14
- Username: Chaotic1870
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Nov 30, 2020 2:14 pm
- Post datetime: 2020-12-10T15:20:24+00:00
- Post Title: Star Wars First Assault Tech Demo models

Alright, well thanks for the help!
## Post #15
- Username: Chaotic1870
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Nov 30, 2020 2:14 pm
- Post datetime: 2021-01-17T04:49:12+00:00
- Post Title: Star Wars First Assault Tech Demo models

Hi again, im a bit new to umodel, i cant figure out how to extract anything, i asked over in the umodel forums and they werent much help, could someone here walk me through it? Sorry for the inconvenience, if anyone wants to speak to me directly my discord is Surestsafe#1870
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-04-25T07:37:55+00:00
- Post Title: Re: Star Wars First Assault Tech Demo models

can you post a link to umodel forum where you asked?
## Post #17
- Username: Coldonne
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 27, 2021 4:03 pm
- Post datetime: 2021-06-27T10:46:30+00:00
- Post Title: Re: Star Wars First Assault Tech Demo models

Ok, I've been working at this for 6 hours straight, and I feel like I am just not winning anymore. 

I used umodel to pull a large amount of files, but it seems like character and weapon files are being skipped over. I also extracted the .xxx files and had a look in there, seems to be weapon attachments and some character models but not everything that should be there. I've been trying to use the .Texture2D file trick and reference the .TFC but quite frankly I don't know what I'm looking for, am I just looking for matching offsets? 

I also attempted to use BMS scripts to pull the texture files from the TFC, yet I keep getting an "Error: uncompressed data (-1) bigger than allocated buffer," then it goes on to say either the algorithm is wrong or the data isn't compressed, I was battin' a thousand when I got the tech demo to work on my PC but now I'm hitting one foul after another    Any help and/or thoughts would be appreciated.
