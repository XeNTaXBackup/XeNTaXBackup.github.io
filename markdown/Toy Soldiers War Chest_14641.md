## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-07-17T19:52:04+00:00
- Post Title: Toy Soldiers War Chest

Toy Soldiers War Chest model tool. The game has really weird way to remap bones, you'll need 3 files for each model to convert:

- mesh description file (.mshb)
- geometry file (.geob)
- skeleton file (sklb)

Command line to run it: ToySoldiers <mshb> <geob> [sklb]

If you don't provide a skeleton (or if the model doesn't have it) it will be exported without bones. Also I was lazy and didn't read the full buffers & submeshes descriptions, so the tool only assumes that they all go sequentially, like 0,1,2,3... . So if anything goes wrong, let me know.

Texture noesis plugin by AceWell here: [viewtopic.php?p=117125#p117125](http://forum.xentax.com/viewtopic.php?p=117125#p117125)

They are toy soldiers, but still can move their fingers and bend their spine & feet.


[ToySoldiers.rar](https://xentaxbackup.github.io/file/11300_ToySoldiers.rar)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-07-18T10:35:57+00:00
- Post Title: Toy Soldiers War Chest

Vehicles are also ok. This is Cobra Rattler, and bones are all working, turbines rotate, wings modifies etc. I only need to support static models now and its done.
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-07-18T12:13:32+00:00
- Post Title: Toy Soldiers War Chest

ok tested and ready:



Must support all models from the game with UVs, bones & weigths.
## Post #4
- Username: sixxstreeter
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Sep 15, 2016 2:38 pm
- Post datetime: 2019-03-25T17:25:16+00:00
- Post Title: Toy Soldiers War Chest

can you relup the file its not working when try to download please thanks
## Post #5
- Username: sixxstreeter
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Sep 15, 2016 2:38 pm
- Post datetime: 2019-03-25T18:50:45+00:00
- Post Title: Toy Soldiers War Chest

sorry i got the download but how does it work..i open cdm and type commands are just drag drop it over ive tryed bothe ways and nothing happens?im on windows 10 so if i click the program it open cmd fast and close it..i dont know if im messing something here are not lol so a little help and what progrham do you open the models in are does it just turn it to an obj file? thanks for your help
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-03-26T15:12:09+00:00
- Post Title: Toy Soldiers War Chest

> Reply from sixxstreeter ↑Tue Mar 26, 2019 2:50 am at Tue Mar 26, 2019 2:50 am
>
> 
sorry i got the download but how does it work..i open cdm and type commands are just drag drop it over ive tryed bothe ways and nothing happens?im on windows 10 so if i click the program it open cmd fast and close it..i dont know if im messing something here are not lol so a little help and what progrham do you open the models in are does it just turn it to an obj file? thanks for your help

google how to use command line
## Post #7
- Username: sixxstreeter
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Sep 15, 2016 2:38 pm
- Post datetime: 2019-03-26T16:48:34+00:00
- Post Title: Toy Soldiers War Chest

ok i look at how to run cmd  and typed in  c:\>program files ToySoldiers.exe then it displayed i need mshb geob sklb so then i typed in the command as you have  Command line to run it: ToySoldiers <mshb> <geob> [sklb]

i tryed several ways one way  not ready are somthing but heres the commands i put in

c:\>program files ToySoldiers <cobra_aa_tinroof.mshb> <cobra_aa_tinroof.0.geob> [cobra_aa_tinroof.Sklb] enter is that correct or not and can you fix this command line if it isnt using the data i have here please so i can see how the line is wrote

like say i go search open pc cmd and the go find the exe if progrham files and then it tells me i need  mshb geob sklb

thanks for taking the time to help me so now i understand a bit about cmd
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-26T23:04:30+00:00
- Post Title: Toy Soldiers War Chest

> Reply from sixxstreeter ↑Wed Mar 27, 2019 12:48 am at Wed Mar 27, 2019 12:48 am
>
> c:\>program files ToySoldiers <cobra_aa_tinroof.mshb> <cobra_aa_tinroof.0.geob> [cobra_aa_tinroof.Sklb]
open a cmd prompt in the location of your ToySoldiers.exe and mshb/geob/sklb files and type this:

```
ToySoldiers cobra_aa_tinroof.mshb cobra_aa_tinroof.0.geob cobra_aa_tinroof.Sklb
```
## Post #9
- Username: sixxstreeter
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Sep 15, 2016 2:38 pm
- Post datetime: 2019-03-27T10:19:34+00:00
- Post Title: Toy Soldiers War Chest

hey thanks acewell i know from facepunch for sw modles from battle front ..i tryed it and get errors saying not found and diffrent things  if you could do me a fav pull the mods for heman and joe and cobra ill own you one..i know alot of people want tor models i know easy way to take them straight out of jedipedia i look at fp and see people still ask but its a real simple way i can exsplain it how to get any of the models from that site..if you dont know all ready..i worked on tor for along time lol why everybody worked on bf so if you could help me out i owe you a big fav
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-27T19:12:03+00:00
- Post Title: Toy Soldiers War Chest

> Reply from sixxstreeter ↑Wed Mar 27, 2019 6:19 pm at Wed Mar 27, 2019 6:19 pm
>
> .... if you could do me a fav pull the mods for heman and joe and cobra ill own you one..
no can do, i don't have the files or the game.   

> Reply from sixxstreeter ↑Wed Mar 27, 2019 6:19 pm at Wed Mar 27, 2019 6:19 pm
>
> i know alot of people want tor models i know easy way to take them straight out of jedipedia....
so do i, for almost 3 years exist my Noesis script here for jedipedia models:   
[https://forum.xentax.com/viewtopic.php?f=16&t=15623](https://forum.xentax.com/viewtopic.php?f=16&t=15623)
## Post #11
- Username: sixxstreeter
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Sep 15, 2016 2:38 pm
- Post datetime: 2019-03-28T08:19:29+00:00
- Post Title: Toy Soldiers War Chest

thanks if need i can put a package togother for files just send a pm
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-31T01:06:16+00:00
- Post Title: Toy Soldiers War Chest

> Reply from sixxstreeter ↑Thu Mar 28, 2019 4:19 pm at Thu Mar 28, 2019 4:19 pm
>
> 
thanks if need i can put a package togother for files just send a pm
no need, you have everything you need to extract all the things you want,
i have faith in you!
## Post #13
- Username: sixxstreeter
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Sep 15, 2016 2:38 pm
- Post datetime: 2019-03-31T07:31:57+00:00
- Post Title: Toy Soldiers War Chest

yea i figured out was so stupid what i was doing wrong hahaha but im ok now thanks
## Post #14
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2019-05-04T23:52:07+00:00
- Post Title: Toy Soldiers War Chest

Hello Acewell, could you please add a printscreen of the cmd prompt of how would the command line be inside the cmd prompt to extract the 3d models? And what format are they extracted, obj, 3ds?
I have toy soldiers war chest of fame edition of this
game, Acewell, could you tell me if I need to buy the dlc from g.i.joe so I can find the 3 files necessary for the extraction of each 3d model, or this version I have is it possible to find the files and extract without problem?
Thank you, success
## Post #15
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-05-05T02:31:48+00:00
- Post Title: Toy Soldiers War Chest

i don't know anything about this game, i just looked at some samples.
i gave an example of what to type in cmd prompt in my post here:
[https://forum.xentax.com/viewtopic.php? ... 41#p150208](https://forum.xentax.com/viewtopic.php?f=16&t=14641#p150208)
## Post #16
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2019-05-07T22:26:50+00:00
- Post Title: Re: Toy Soldiers War Chest

hello, daemon1 could you please add a printscreen of the cmd prompt, with an example of how the name of ToySoldiers.exe and name of the 3 files have to be written inside the cmd prompt before pressing enter? thanks
## Post #17
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-05-08T14:35:58+00:00
- Post Title: Re: Toy Soldiers War Chest

acewell posted an example already
## Post #18
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2019-05-09T00:28:28+00:00
- Post Title: Re: Toy Soldiers War Chest

daemon1 which version of the toy soldiers war chest game you used to extract the 3d models, the version PC, PS4 or XBOX ONE?
If it is the pc version, did you buy any dlc separately for the game?
## Post #19
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2019-05-09T01:37:41+00:00
- Post Title: Re: Toy Soldiers War Chest

hello, sixxstreeter could you please add a PRINTSCREEN of the cmd prompt, with an example of how the name of ToySoldiers.exe and name of the 3 files have to be written inside the cmd prompt before pressing enter? Thanks
this would help me a lot, because I do not know what is going wrong in the 3d model extraction
I've tried it in several ways, and I still can not
## Post #20
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-05-09T05:47:47+00:00
- Post Title: Re: Toy Soldiers War Chest

> Reply from vanilla1 ↑Thu May 09, 2019 8:28 am at Thu May 09, 2019 8:28 am
>
> 
daemon1 which version of the toy soldiers war chest game you used to extract the 3d models, the version PC, PS4 or XBOX ONE?
If it is the pc version, did you buy any dlc separately for the game?

PC
i dont remember anything about DLCs
## Post #21
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2019-05-10T01:47:16+00:00
- Post Title: Re: Toy Soldiers War Chest

daemon1, I managed to extract the file, but the program that opens it shows the following error:
CAN NOT OPEN, object reference not defined for an instance of an object.
I used xnalara xps, which program do you use to open the mesh.ascii,thank you very much
## Post #22
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2019-05-10T02:32:15+00:00
- Post Title: Re: Toy Soldiers War Chest

daemon1, these are the files I unzipped:
heman_heman_classic.mshb
heman_heman_classic.0.geob
heman_classic.sklb
And created this:heman_heman_classic.mesh.ascii
## Post #23
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-05-10T13:20:32+00:00
- Post Title: Re: Toy Soldiers War Chest

use noesis, blender or 3dmax
you need plugins for them to load mesh.ascii
i used "johnzero" plugin for blender
## Post #24
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2019-05-12T01:07:08+00:00
- Post Title: Re: Toy Soldiers War Chest

daemon1, did you apply texture in he-man open in blender? or do you use other software to apply the textures? I found the plugin for blender and noesis, but I did not find it for 3ds max
## Post #25
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2019-05-12T01:11:29+00:00
- Post Title: Re: Toy Soldiers War Chest

Do you have the 3ds max plugin? Could you pass me where you got it? I downloaded some here, but I only opened .mesh files
## Post #26
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-05-12T05:43:52+00:00
- Post Title: Re: Toy Soldiers War Chest

i did not work with textures, only models
## Post #27
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2019-05-13T03:22:14+00:00
- Post Title: Re: Toy Soldiers War Chest

3d model opened in 3ds max. the bone file (sklb) of this 3d model I can not find in the game
[modelo.png](https://xentaxbackup.github.io/file/16245_modelo.png)
## Post #28
- Username: mdelafe
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 08, 2022 1:21 am
- Post datetime: 2022-07-07T22:50:07+00:00
- Post Title: Re: Toy Soldiers War Chest

Hi! I'm new here and I want to find a way to extract all those G.I.Joe and He-Man Models for 3D print.

I downloaded a repack with all, and there was no problem in find the bones... I'll try to find the way to extract all and I will post something here.
