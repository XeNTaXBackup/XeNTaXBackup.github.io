## Post #1
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-10-21T21:11:09+00:00
- Post Title: Winter X-Games: Snocross (.GR2 - File)

Hey Guys,
I'm a little better prepared this time! Since Granny 3D (.GR2) is way more common than the file types I usually request to open, I was able to come up with this:

Link to the high poly file here: [https://cdn.discordapp.com/attachments/ ... Punk_H.zip](https://cdn.discordapp.com/attachments/553220665692651542/635945647765454898/Punk_H.zip)

I used this tool to convert the mesh inside the .GR2 - file to .obj:
[http://dl.eve-files.com/media/0801/evegr2toobj.2.zip](http://dl.eve-files.com/media/0801/evegr2toobj.2.zip)

With "Granny Viewer" I could view the textures within the .GR2 - file:
[https://forums.civfanatics.com/resource ... 5-0.21206/](https://forums.civfanatics.com/resources/granny-viewer-2-8-45-0.21206/)

I ripped the displayed textures in "Granny Viewer" with this program:
[https://glxtractor.software.informer.com/download/](https://glxtractor.software.informer.com/download/)

One of the textures came out half transparent:

it displays correctly on the model though.
My question now is;
Does anybody know of a more straight forward workflow? I want to export the sleds and characters, so everybody can use them. In best case theres a noesis import script for both the models and the textures already.........i hope.....
in any other case, take this thread as a "guide" to convert Winter X-Games: Snocross .GR2 files
## Post #2
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2019-12-06T03:14:49+00:00
- Post Title: Winter X-Games: Snocross (.GR2 - File)

Im getting an error.
[](https://ibb.co/RjB07Rj)

All it finds is the tires.
[](https://imgbb.com/)

Model
[](https://imgbb.com/)

Sample File
[https://drive.google.com/file/d/12ZmHn4 ... sp=sharing](https://drive.google.com/file/d/12ZmHn4neKIrWU7cJLftL4UUCEoRf5i17/view?usp=sharing)
## Post #3
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-12-07T13:19:13+00:00
- Post Title: Winter X-Games: Snocross (.GR2 - File)

Did you use Evergreen to convert? Sometimes a model consists out of Multiple submeshes...the tires in your case. Is the used .gr2 file for the whole car?
## Post #4
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2020-03-04T19:47:26+00:00
- Post Title: Winter X-Games: Snocross (.GR2 - File)

Based on many others ALMOST correct code I've adjusted and built new exporters over the years.
My programs don't require command line and rip complete models.
Given some people want textures also exported?
I'll do a newer version if needed.
## Post #5
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-03-06T23:57:27+00:00
- Post Title: Winter X-Games: Snocross (.GR2 - File)

> Reply from 05SpeedMaster ↑Thu Mar 05, 2020 3:47 am at Thu Mar 05, 2020 3:47 am
>
> 
Given some people want textures also exported?
I'll do a newer version if needed.

Please hit me up as soon as you have an update
## Post #6
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-03-09T08:30:32+00:00
- Post Title: Winter X-Games: Snocross (.GR2 - File)

Im trying to get my hands on the sled models seen in this Video at 01:06
[https://youtu.be/tjqOg4px8LA](https://youtu.be/tjqOg4px8LA)


They seem to be .gr2 files within a Single .rez
Would this be a common method to pack granny models like that?

Heres a Link to the CARZ.rez file:
[https://we.tl/t-YALKQhCcZc](https://we.tl/t-YALKQhCcZc)
(Let me know if dead)
## Post #7
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2020-03-16T08:27:36+00:00
- Post Title: Winter X-Games: Snocross (.GR2 - File)

No that is not a GR2 file in anyway.
I see textures and meshes but have not looked hard at it.
## Post #8
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-03-17T11:23:42+00:00
- Post Title: Winter X-Games: Snocross (.GR2 - File)

> Reply from 05SpeedMaster ↑Mon Mar 16, 2020 4:27 pm at Mon Mar 16, 2020 4:27 pm
>
> 
No that is not a GR2 file in anyway.
I see textures and meshes but have not looked hard at it.

So .rez is a Archive for models and textures, right?
## Post #9
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2020-03-18T09:49:56+00:00
- Post Title: Winter X-Games: Snocross (.GR2 - File)

It looks that way to me.
I see IMG which I figure is image and M3D which I figure is the 3d mesh.
Do a hex search for EOF. (End of File)
## Post #10
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-03-18T21:17:05+00:00
- Post Title: Winter X-Games: Snocross (.GR2 - File)

> Reply from 05SpeedMaster ↑Wed Mar 18, 2020 5:49 pm at Wed Mar 18, 2020 5:49 pm
>
> 
I see IMG which I figure is image and M3D which I figure is the 3d mesh.

So is the model structure like the .gr2 file?
why would it make sense to use different model formats if its not terrain or physic based suff?
## Post #11
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2020-03-19T06:59:48+00:00
- Post Title: Winter X-Games: Snocross (.GR2 - File)

This is the Game that runs on Apple correct?
Released in 2010 by ESPN?
## Post #12
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-03-19T08:33:26+00:00
- Post Title: Winter X-Games: Snocross (.GR2 - File)

> Reply from 05SpeedMaster ↑Thu Mar 19, 2020 2:59 pm at Thu Mar 19, 2020 2:59 pm
>
> 
This is the Game that runs on Apple correct?

Oofff....good question man.


ESPN licensed it for sure!
All i know is that its been released 2012 and comes with a hard drive that you can order seperatly.
Heres a Link to the operators manual:
[https://manualzz.com/doc/9494975/winter ... --snocross](https://manualzz.com/doc/9494975/winter-x-games--snocross)

I Found this on wikipedia:

> X Games Snocross is a snocross racing video game from ESPN and 2XL Games that was released on January 18, 2010 for iOS. It was the first game demoed on the Apple iPad on stage January 27, 2010 by Scott Forstall.[1]
[https://en.m.wikipedia.org/wiki/X_Games_SnoCross](https://en.m.wikipedia.org/wiki/X_Games_SnoCross)
This seems to be a different game though.

This is the one i am refering to:
[https://rawthrills.com/games/snocross/](https://rawthrills.com/games/snocross/)
So i guess it must be pc-based the, right?
## Post #13
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-04-05T14:06:40+00:00
- Post Title: Winter X-Games: Snocross (.GR2 - File)

Just found this in the games manual:

"The computer contains sensitive components, including a hard drive. Do not handle it roughly. Call your distributor
before servicing its internal components. Ask about warranty information as it relates to the PC.  
Do not turn the PC power switch on or off. It should remain permanently in the ON position.  
Cycle AC power on or off with the cabinet power switch.
A dongle has been inserted into one of the USB ports. This is required for game play.  
Do not remove the dongle except for troubleshooting purposes."

So it is actually pc-based!
I heard that most of these run on Windows XP.
## Post #14
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-04-11T08:13:05+00:00
- Post Title: Winter X-Games: Snocross (.GR2 - File)

> Reply from 05SpeedMaster ↑Thu Mar 05, 2020 3:47 am at Thu Mar 05, 2020 3:47 am
>
> 
I'll do a newer version if needed.

Where are you man? :-/
## Post #15
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2020-04-11T20:32:06+00:00
- Post Title: Winter X-Games: Snocross (.GR2 - File)

> Reply from Henchman800 ↑Sat Apr 11, 2020 4:13 pm at Sat Apr 11, 2020 4:13 pm
>
> 
05SpeedMaster wrote: ↑Thu Mar 05, 2020 3:47 am
I'll do a newer version if needed.


Where are you man? :-/
Alive and well here. 
Just busy in the times we are going through right now.
## Post #16
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-04-13T11:12:28+00:00
- Post Title: Re: Winter X-Games: Snocross (.GR2 - File)

> Reply from 05SpeedMaster ↑Sun Apr 12, 2020 4:32 am at Sun Apr 12, 2020 4:32 am
>
> 
Alive and well here. 
Just busy in the times we are going through right now.

Glad to hear that!
Yeah...Times are insane...having alot of spare time without actually having it :-/
## Post #17
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-04-23T10:46:33+00:00
- Post Title: Re: Winter X-Games: Snocross (.GR2 - File)

Yeah!
[https://www.models-resource.com/arcade/ ... ssnocross/](https://www.models-resource.com/arcade/winterxgamessnocross/)

They've accepted the first model
## Post #18
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-06-13T20:20:31+00:00
- Post Title: Re: Winter X-Games: Snocross (.GR2 - File)

Jayn23 created a noesis script that is able to read the games .gr2 files 
[viewtopic.php?f=16&t=22277](https://forum.xentax.com/viewtopic.php?f=16&t=22277)
