## Post #1
- Username: adroduke
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 16, 2019 7:46 pm
- Post datetime: 2019-01-17T09:36:56+00:00
- Post Title: Burnout series models

hello,

I was wondering if there was someone that knows about using 3d model researcher and extracts games model. I'm not really familiar with hex code, and there are some models from the burnout games that I would like to obtain (xbox version). 

you'll find one of the models i'm after attached to this topic.

I'll offer to pay for your time and would very much appreciate the help

Thanks
[Car1.rar](https://xentaxbackup.github.io/file/15512_Car1.rar)
## Post #2
- Username: adroduke
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 16, 2019 7:46 pm
- Post datetime: 2019-01-18T12:59:45+00:00
- Post Title: Burnout series models

Forgot to mention that I am prepared to pay for your time.

would really appreciate the help.

Thanks
## Post #3
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-01-18T21:28:54+00:00
- Post Title: Burnout series models

The whole model is divided into several small meshes with 30-50 vertices. To get it using the program is hardly possible.



Car1.bgv_01-19-19_04-24-46.png (69.9 KiB) Viewed 633 times
## Post #4
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2019-01-19T00:50:21+00:00
- Post Title: Burnout series models

PS2 versions of games are not really the best to get models from in my experience.

The Xbox version you'll have a much easier time with.
## Post #5
- Username: adroduke
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 16, 2019 7:46 pm
- Post datetime: 2019-01-19T02:30:54+00:00
- Post Title: Burnout series models

> Reply from Nega
>
> PS2 versions of games are not really the best to get models from in my experience.

The Xbox version you'll have a much easier time with.
Thanks for getting back to me

Thats awesome, i'm happy with the xbox version, i'll attach the xbox version of car, is it hard getting the uvs and normals aswell?

i have no idea what i'm doing when it comes to hexadecimal, so really appreciate the help

Thanks
[Car1.rar](https://xentaxbackup.github.io/file/15511_Car1.rar)
## Post #6
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2019-01-19T10:03:46+00:00
- Post Title: Burnout series models

With the file you given, the highest level of detail model starts at 0x54B5C, with faces starting at 0x51640



The UVs are not a problem either, it's only the normals i'm not sure where they are, but I suspect they might be the 4 bytes before each UV.



=====================================

With each sub mesh, there's a set number of faces before a new one. You can tell with a 00 00 separating the next set of faces.



If there isn't any, keep adding more faces until you see an outstretched polygon, then reduce until it's gone. The vertices and UVs should be the same offset and count each sub mesh.
## Post #7
- Username: adroduke
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 16, 2019 7:46 pm
- Post datetime: 2019-01-19T11:01:42+00:00
- Post Title: Burnout series models

> Reply from Nega
>
> With the file you given, the highest level of detail model starts at 0x54B5C, with faces starting at 0x51640



The UVs are not a problem either, it's only the normals i'm not sure where they are, but I suspect they might be the 4 bytes before each UV.



=====================================

With each sub mesh, there's a set number of faces before a new one. You can tell with a 00 00 separating the next set of faces.



If there isn't any, keep adding more faces until you see an outstretched polygon, then reduce until it's gone. The vertices and UVs should be the same offset and count each sub mesh.
This is awesome but, I don't know how to use this program nor understand hexadecimal, so was kinda hoping if you could extract the whole model for me? like i said i will offer to pay for your time
## Post #8
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2019-01-19T14:50:18+00:00
- Post Title: Burnout series models

Give me a little bit, and i'll see what I can whip up for you.

I'll get an obj up if you like?
## Post #9
- Username: adroduke
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 16, 2019 7:46 pm
- Post datetime: 2019-01-19T17:07:52+00:00
- Post Title: Burnout series models

> Reply from Nega
>
> Give me a little bit, and i'll see what I can whip up for you.

I'll get an obj up if you like?
that would be great, thanks really appreciate it, there are couple more models i'm after as well if its not too much trouble, when u got free time
## Post #10
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2019-01-19T18:03:26+00:00
- Post Title: Burnout series models

There we go, here's the car all ripped and all meshes positioned correctly


[Car1.rar](https://xentaxbackup.github.io/file/15523_Car1.rar)
## Post #11
- Username: adroduke
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 16, 2019 7:46 pm
- Post datetime: 2019-01-20T00:00:31+00:00
- Post Title: Burnout series models

> Reply from Nega
>
> There we go, here's the car all ripped and all meshes positioned correctly
This is absolutely outstanding! thank you so much! do you want something in return for your time? was it a pain to do?
## Post #12
- Username: adroduke
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 16, 2019 7:46 pm
- Post datetime: 2019-01-20T03:39:10+00:00
- Post Title: Burnout series models

> Reply from Nega
>
> There we go, here's the car all ripped and all meshes positioned correctly
I've got just have 3 more that I'm after if you don't mind obtaining for me? 1 of them is attached to this post, i'll send the other 2 in other posts 

These models are from burnout revenge where as the one you just did is from burnout 3 but, same file format, so shouldn't be that much different. i hope these are the right models I want cause, its a little harder to tell in the revenge folders. Like i said in the past, i'll pay you for your time and you can do this whenever you are free, you just did a really good job on that last model.

appreciate your time, it really means a lot for me getting these models

cheers
[Car1S1.rar](https://xentaxbackup.github.io/file/15527_Car1S1.rar)
## Post #13
- Username: adroduke
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 16, 2019 7:46 pm
- Post datetime: 2019-01-20T03:40:10+00:00
- Post Title: Burnout series models

> Reply from adroduke
>
> Nega wrote:There we go, here's the car all ripped and all meshes positioned correctly


I've got just have 3 more that I'm after if you don't mind obtaining for me? 1 of them is attached to this post, i'll send the other 2 in other posts 

These models are from burnout revenge where as the one you just did is from burnout 3 but, same file format, so shouldn't be that much different. i hope these are the right models I want cause, its a little harder to tell in the revenge folders. Like i said in the past, i'll pay you for your time and you can do this whenever you are free, you just did a really good job on that last model.

appreciate your time, it really means a lot for me getting these models

cheers
Car number 2
[Car1W1.rar](https://xentaxbackup.github.io/file/15528_Car1W1.rar)
## Post #14
- Username: adroduke
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 16, 2019 7:46 pm
- Post datetime: 2019-01-20T03:42:03+00:00
- Post Title: Burnout series models

> Reply from adroduke
>
> Nega wrote:There we go, here's the car all ripped and all meshes positioned correctly


I've got just have 3 more that I'm after if you don't mind obtaining for me? 1 of them is attached to this post, i'll send the other 2 in other posts 

These models are from burnout revenge where as the one you just did is from burnout 3 but, same file format, so shouldn't be that much different. i hope these are the right models I want cause, its a little harder to tell in the revenge folders. Like i said in the past, i'll pay you for your time and you can do this whenever you are free, you just did a really good job on that last model.

appreciate your time, it really means a lot for me getting these models

cheers
Car number 3
[Car1S11.rar](https://xentaxbackup.github.io/file/15529_Car1S11.rar)
## Post #15
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2019-01-20T15:58:16+00:00
- Post Title: Burnout series models

My apologies, I was sleeping when you posted those. I'll take a look at these now, and i'll get back to you on them.

As for the meshes, they weren't that difficult to do, just more time consuming if anything due to the game using multiple instances of one object for the tires. The model data only has one type of mesh/sub mesh for the tires, idle, fast, fastest and only uses the front right tire.

================================================

For Car1S1.bgv, just want to confirm if this is the right car you're wanting me to look at?
## Post #16
- Username: adroduke
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 16, 2019 7:46 pm
- Post datetime: 2019-01-20T23:19:30+00:00
- Post Title: Re: Burnout series models

> Reply from Nega
>
> My apologies, I was sleeping when you posted those. I'll take a look at these now, and i'll get back to you on them.

As for the meshes, they weren't that difficult to do, just more time consuming if anything due to the game using multiple instances of one object for the tires. The model data only has one type of mesh/sub mesh for the tires, idle, fast, fastest and only uses the front right tire.

================================================

For Car1S1.bgv, just want to confirm if this is the right car you're wanting me to look at?
Nah thats alright, i was asleep when you sent this message, haha. your a legend and yes thats definitely the one I'm after and the other 2 are definitely the ones I'm also after, thanks
## Post #17
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2019-01-21T11:18:13+00:00
- Post Title: Re: Burnout series models

Car1S1 has been done.


[Car1S1.rar](https://xentaxbackup.github.io/file/15540_Car1S1.rar)
## Post #18
- Username: adroduke
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 16, 2019 7:46 pm
- Post datetime: 2019-01-21T12:54:52+00:00
- Post Title: Re: Burnout series models

> Reply from Nega
>
> Car1S1 has been done.
Yes!!! I'm so freaking happy, been trying to get these models for so long, thank you! glad this was the right one too, there is the same car in the game but, with different texture. But, this was the one I really wanted, great work! 

Also, I see what you mean by the wheels having different instances. If it makes it any easier for you, you don't need to export all the wheels instances, only just the idle version.
## Post #19
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2019-01-23T00:31:29+00:00
- Post Title: Re: Burnout series models

Here's Car1W1.



I tend to include everything, just in case it can be utilized by something else, but if you're okay with that i'll just add the idle ones.
[Car1W1.rar](https://xentaxbackup.github.io/file/15546_Car1W1.rar)
## Post #20
- Username: adroduke
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 16, 2019 7:46 pm
- Post datetime: 2019-01-23T06:49:31+00:00
- Post Title: Re: Burnout series models

> Reply from Nega
>
> Here's Car1W1.



I tend to include everything, just in case it can be utilized by something else, but if you're okay with that i'll just add the idle ones.
Awesome work, loving these models  

Yeah cool, whatever is best for you, i thought it would be less hassle that way
## Post #21
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2019-01-23T12:48:59+00:00
- Post Title: Re: Burnout series models

And here's the last car done.


[Car1S1.rar](https://xentaxbackup.github.io/file/15551_Car1S1.rar)
## Post #22
- Username: adroduke
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 16, 2019 7:46 pm
- Post datetime: 2019-01-23T13:44:52+00:00
- Post Title: Re: Burnout series models

> Reply from Nega
>
> And here's the last car done.
Thank you so much Nega, really appreciate your time on getting these. Now, do you want anything for your time? because, you said they were time consuming to get. so I would like to return the favor.

Also, I do have some more models that I am after as well, they're not that urgent or anything so they can be done whenever. but, i don't want to annoy you with these requests. So, just wanted to see if you are ok with doing some more? Like i've said in the past, I'll pay you for your time and I really like the models you've given me, you've been a big help.

let me know what you think

Cheers
## Post #23
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2019-01-24T08:51:50+00:00
- Post Title: Re: Burnout series models

> Reply from adroduke
>
> Nega wrote:And here's the last car done.


Thank you so much Nega, really appreciate your time on getting these. Now, do you want anything for your time? because, you said they were time consuming to get. so I would like to return the favor.

Also, I do have some more models that I am after as well, they're not that urgent or anything so they can be done whenever. but, i don't want to annoy you with these requests. So, just wanted to see if you are ok with doing some more? Like i've said in the past, I'll pay you for your time and I really like the models you've given me, you've been a big help.

let me know what you think

Cheers

Sure, if you have any more Burnout models you'd like, I can give them a shot.

I would much prefer to get everything sorted out before getting anything in return, that's my take on it though.
## Post #24
- Username: adroduke
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 16, 2019 7:46 pm
- Post datetime: 2019-01-24T11:34:31+00:00
- Post Title: Re: Burnout series models

Awesome, we can do that if you like. Well in that case then, here is the first batch of cars, link below:

[http://www.mediafire.com/file/ffr383g3e ... s.rar/file](http://www.mediafire.com/file/ffr383g3eipndqh/burnout_cars.rar/file)

if you have any dramas with the link let me know. For future reference, did you want me to send these through to a personal messenger/email or prefer it to do it this way? let me know

Thanks Nega, you're a champion!
## Post #25
- Username: adroduke
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 16, 2019 7:46 pm
- Post datetime: 2019-01-26T16:29:05+00:00
- Post Title: Re: Burnout series models

Hey nega,

I couldn't reply to your personal message cause, it's been disabled.

but was gonna say that it's Awesome to hear, hopefully they are not too much trouble. 

thanks again for doing these.
## Post #26
- Username: MatiTheMudkip
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jan 23, 2018 4:35 am
- Post datetime: 2019-05-20T04:37:54+00:00
- Post Title: Re: Burnout series models

can someone explain me how to do all of this stuff or like example of how all of this works?

the hex stuff and how to get every part of a car of the game and all of that
## Post #27
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-01-26T15:14:34+00:00
- Post Title: Re: Burnout series models

Hi,

I'm here to try to open .bgv file 3d too! Someone can explain to me how did you do it?

...

Yes, idk where to him my head
## Post #28
- Username: tempaccount555
- Rank: beginner
- Number of posts: 27
- Joined date: Sun May 12, 2019 8:14 pm
- Post datetime: 2020-07-10T20:11:17+00:00
- Post Title: Re: Burnout series models

Hey I'm tryna convert the Factory GT from Burnout Revenge/Dominator, can anyone help out with the model pieces?
## Post #29
- Username: MatiTheMudkip
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jan 23, 2018 4:35 am
- Post datetime: 2020-12-03T18:33:42+00:00
- Post Title: Re: Burnout series models

i have come to give random contribution to the post



[http://www.mediafire.com/file/fliwu8l69 ... B.rar/file](http://www.mediafire.com/file/fliwu8l69fg76l8/Car2B.rar/file)
[Limited M-Type DX.png](https://xentaxbackup.github.io/file/19124_Limited M-Type DX.png)
## Post #30
- Username: MatiTheMudkip
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jan 23, 2018 4:35 am
- Post datetime: 2020-12-03T18:39:29+00:00
- Post Title: Re: Burnout series models

Also this too but Wip
[WipAngelValley.PNG](https://xentaxbackup.github.io/file/19125_WipAngelValley.PNG)
## Post #31
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-12-07T18:06:20+00:00
- Post Title: Re: Burnout series models

> Reply from Ness ↑Fri Dec 04, 2020 2:39 am at Fri Dec 04, 2020 2:39 am
>
> 
Also this too but Wip

Cant wait!!!
Nice man!
## Post #32
- Username: MatiTheMudkip
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jan 23, 2018 4:35 am
- Post datetime: 2020-12-07T20:47:28+00:00
- Post Title: Re: Burnout series models

> Reply from Henchman800 ↑Tue Dec 08, 2020 2:06 am at Tue Dec 08, 2020 2:06 am
>
> 
Ness wrote: ↑Fri Dec 04, 2020 2:39 am
Also this too but Wip


Cant wait!!!
Nice man!

Thanks! quite been busy with other projects in hand doe but at least i can guarantee that i will get this exported!
## Post #33
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-12-30T14:29:53+00:00
- Post Title: Re: Burnout series models

> Reply from Ness ↑Tue Dec 08, 2020 4:47 am at Tue Dec 08, 2020 4:47 am
>
> 
Thanks! quite been busy with other projects in hand doe but at least i can guarantee that i will get this exported!

Do you have another Screenshot of your progress? Im really curious
## Post #34
- Username: DGIorio
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 11, 2016 6:12 am
- Post datetime: 2020-12-30T22:51:16+00:00
- Post Title: Re: Burnout series models

A while ago I made an importer addon for Blender that supports importing models from Burnout Takedown, Dominator, Legends and Revenge (it also can open nfs shift psp models). UVs from PS2 version aren't supported.

Here is the download link
[DGI_Burnout_BGV_BlenderAddon](https://drive.google.com/file/d/1hQs4pyPhzNBdbGFuBmb_5mEn9K7GJGn2/view?usp=sharing)

For installing it on Blender, use the option "Install from File" on the Add-ons tab and choose each .zip files (it's not necessary to extract the files). Then, active the addon on "User Preferences" at Add-ons tab. There are tutorials about it on Youtube and Blender wiki.
## Post #35
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-01-01T03:57:07+00:00
- Post Title: Re: Burnout series models

> Reply from DGIorio ↑Thu Dec 31, 2020 6:51 am at Thu Dec 31, 2020 6:51 am
>
> ...(it also can open nfs shift psp models)...
Interesting, how where you able to extract the Data.fxp/Data1.fxp ?

This is only FXP script i found, and it does NOT work: [http://aluigi.org/bms/harry_potter_fxp.bms](http://aluigi.org/bms/harry_potter_fxp.bms)
## Post #36
- Username: DGIorio
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 11, 2016 6:12 am
- Post datetime: 2021-01-02T17:46:23+00:00
- Post Title: Re: Burnout series models

> Reply from mono24 ↑Fri Jan 01, 2021 11:57 am at Fri Jan 01, 2021 11:57 am
>
> 
DGIorio wrote: ↑Thu Dec 31, 2020 6:51 am...(it also can open nfs shift psp models)...
Interesting, how where you able to extract the Data.fxp/Data1.fxp ?

This is only FXP script i found, and it does NOT work: http://aluigi.org/bms/harry_potter_fxp.bms

I friend (KabutoKun) sent me an unpacked file from nfs shift (PSP), he said that he extract it manually.
## Post #37
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2021-01-04T19:16:30+00:00
- Post Title: Re: Burnout series models

> Reply from DGIorio ↑Thu Dec 31, 2020 6:51 am at Thu Dec 31, 2020 6:51 am
>
> 
A while ago I made an importer addon for Blender that supports importing models from Burnout Takedown, Dominator, Legends and Revenge

Hi, I've got issues about UV mapping in Blender (I've tried Blender 2.79 and Blender 2,83), when I try to open Burnout Dominator's PS2 vehicle files (.bgv), they has got a messed up UV mapping like this in attachment. is a common issue?
[UVmessedup.jpg](https://xentaxbackup.github.io/file/19270_UVmessedup.jpg)
## Post #38
- Username: DGIorio
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 11, 2016 6:12 am
- Post datetime: 2021-01-04T21:16:15+00:00
- Post Title: Re: Burnout series models

> Reply from Fiammanera628 ↑Tue Jan 05, 2021 3:16 am at Tue Jan 05, 2021 3:16 am
>
> 
DGIorio wrote: ↑Thu Dec 31, 2020 6:51 am
A while ago I made an importer addon for Blender that supports importing models from Burnout Takedown, Dominator, Legends and Revenge


Hi, I've got issues about UV mapping in Blender (I've tried Blender 2.79 and Blender 2,83), when I try to open Burnout Dominator's PS2 vehicle files (.bgv), they has got a messed up UV mapping like this in attachment. is a common issue?

Oh, I forgot to mention that the UVs from PS2 versions aren't supported, because I didn't understand them well. UVs from PSP, Xbox and X360 are supported.
## Post #39
- Username: adroduke
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 16, 2019 7:46 pm
- Post datetime: 2021-01-18T16:14:12+00:00
- Post Title: Re: Burnout series models

> Reply from DGIorio ↑Thu Dec 31, 2020 6:51 am at Thu Dec 31, 2020 6:51 am
>
> 
A while ago I made an importer addon for Blender that supports importing models from Burnout Takedown, Dominator, Legends and Revenge (it also can open nfs shift psp models). UVs from PS2 version aren't supported.

Here is the download link
DGI_Burnout_BGV_BlenderAddon

For installing it on Blender, use the option "Install from File" on the Add-ons tab and choose each .zip files (it's not necessary to extract the files). Then, active the addon on "User Preferences" at Add-ons tab. There are tutorials about it on Youtube and Blender wiki.

My prayers have been answered, thank you so much for this, works a treat with xbox models. I was wondering if you were able to do an add-on for the burnout 2 cars by any chance? think they are in an .RCF format?
## Post #40
- Username: CDTH06
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 16, 2021 3:00 am
- Post datetime: 2021-09-15T19:13:17+00:00
- Post Title: Re: Burnout series models

When Import car to the blender, there's nothing. Can someone help this shit?
## Post #41
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2021-10-19T17:26:53+00:00
- Post Title: Re: Burnout series models

Hey guys, is a while since I posted something here.

I wonder if there is any progress about Burnout Dominator PS2's UVs issues...?
## Post #42
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-11-24T18:37:48+00:00
- Post Title: Re: Burnout series models

> Reply from DGIorio ↑Sun Jan 03, 2021 1:46 am at Sun Jan 03, 2021 1:46 am
>
> ...
I friend (KabutoKun) sent me an unpacked file from nfs shift (PSP), he said that he extract it manually.is it possible to upload fxp unpacker somewhere?
Data1.fxp can't be extracted
## Post #43
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-11-27T14:20:19+00:00
- Post Title: Re: Burnout series models

> Reply from DGIorio ↑Thu Dec 31, 2020 6:51 am at Thu Dec 31, 2020 6:51 am
>
> 
Here is the download link
DGI_Burnout_BGV_BlenderAddon

thanks for the script! can't get this model tho (dominator psp):


p.s.: actually most of the traffic models doesn't work

EDIT: okay, I found that just some models doesn't work with Automatic game version detection. So I have to choose Burnout Dominator version in importer before the import.
[Car1.zip](https://xentaxbackup.github.io/file/21296_Car1.zip)
## Post #44
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-11-28T12:34:32+00:00
- Post Title: Re: Burnout series models

These models doesn't work with currect plugin
Burnout Dominator psp
[BDom_Traffic.zip](https://xentaxbackup.github.io/file/21302_BDom_Traffic.zip)
## Post #45
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2022-06-13T05:16:44+00:00
- Post Title: Re: Burnout series models

> Reply from Tosyk ↑Thu Nov 25, 2021 2:37 am at Thu Nov 25, 2021 2:37 am
>
> is it possible to upload fxp unpacker somewhere?
Data1.fxp can't be extracted

sorry to necro-post, but I just wrote a script for fxp files: [https://zenhax.com/viewtopic.php?f=17&t ... 014#p72014](https://zenhax.com/viewtopic.php?f=17&t=7982&p=72014#p72014)
## Post #46
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2022-06-13T08:56:18+00:00
- Post Title: Re: Burnout series models

> Reply from AlphaTwentyThree ↑Mon Jun 13, 2022 1:16 pm at Mon Jun 13, 2022 1:16 pm
>
> 
Tosyk wrote: ↑Thu Nov 25, 2021 2:37 amis it possible to upload fxp unpacker somewhere?
Data1.fxp can't be extracted

sorry to necro-post, but I just wrote a script for fxp files: https://zenhax.com/viewtopic.php?f=17&t ... 014#p72014please necro-posting more often, love your work!
## Post #47
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2022-08-20T06:08:40+00:00
- Post Title: Re: Burnout series models

> Reply from DGIorio ↑Thu Dec 31, 2020 6:51 am at Thu Dec 31, 2020 6:51 am
>
> 
A while ago I made an importer addon for Blender that supports importing models from Burnout Takedown, Dominator, Legends and Revenge (it also can open nfs shift psp models). UVs from PS2 version aren't supported.

Here is the download link
DGI_Burnout_BGV_BlenderAddon

For installing it on Blender, use the option "Install from File" on the Add-ons tab and choose each .zip files (it's not necessary to extract the files). Then, active the addon on "User Preferences" at Add-ons tab. There are tutorials about it on Youtube and Blender wiki.

I have a problem in importing only the Burnout 3 model in 3d program, but I don't have any issues in Revenge X360 model. After I have a Xbox version of B3, and imported a bgv file into blender, some parts of a model normals are fucked up. Is it related to the model itself or the UV Mapping? because I want each model to be imported in smooth normals. and also pls update this blender addon for latest version of Blender and fix the model normal bug
