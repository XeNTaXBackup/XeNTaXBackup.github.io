## Post #1
- Username: ibeckman671
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 16, 2014 10:16 am
- Post datetime: 2014-04-22T06:27:57+00:00
- Post Title: Heroes of the Storm

Has anyone delved into this yet? Trying to get access to some of the new models, but like all Blizzard games, there's been a major format shift.

Using this tool, you can get some stuff, but other models simply don't work:
[http://www.sc2mapster.com/assets/m3-exp ... n-3ds-max/](http://www.sc2mapster.com/assets/m3-export-plugin-3ds-max/)
[raynor.jpg](https://xentaxbackup.github.io/file/7241_raynor.jpg)
## Post #2
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-01-08T21:03:02+00:00
- Post Title: Heroes of the Storm

Hey, Ive been diving into this, with many hours and lots of success, and some not so much

I created a script that imports the HotS and S2 models into Max, unfortunately without animation

I posted something here : [viewtopic.php?f=10&t=11209&hilit=Heroes ... m&start=15](http://forum.xentax.com/viewtopic.php?f=10&t=11209&hilit=Heroes+of+the+Storm&start=15)

So please give me a hand, hope the scripts work 

T.
## Post #3
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-01-31T21:39:45+00:00
- Post Title: Heroes of the Storm

Here is a working script to import SC2 models (m3) and animations (m3a) and Heroes of the storm, requires 3DS MAX 2011


Files can be found on my Dev Blog or SC2 Mapster files ( links in my signature)

T.
## Post #4
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2015-02-01T07:24:00+00:00
- Post Title: Heroes of the Storm

> Reply from TaylorMouse
>
> Here is a working script to import SC2 models (m3) and animations (m3a) and Heroes of the storm, requires 3DS MAX 2011

T.Hi TaylorMouse my friend, thank you very much for the great work, I tested the script, but I had no luck, script errors can not be imported model, I use win7 3dsmax2011 64bit and 3dsmax2012 64bit, here is a test file [https://onedrive.live.com/redir?resid=6 ... =file%2c7z](https://onedrive.live.com/redir?resid=6A28B826BE5F1236!190&authkey=!AOK1p7bNjjrXboE&ithint=file%2C7z)
## Post #5
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-02-01T21:25:57+00:00
- Post Title: Heroes of the Storm

> 2 things, I was aware there was an error, so you need to download the one with the bug fix:
>
> 
>
> http://www.sc2mapster.com/media/files/8 ... m_v1.1.zip
>
> 
>
> but I already made another one, same script but for those that do not have MAX 2011, but a newer version:
>
> 
>
> http://www.sc2mapster.com/media/files/8 ... tTools.zip
>
> 
>
> Be aware that the SC2ArtTools only support MAX 2011 for exporting, and no newer version is available.

IGNORE, new script is available !!

T.
## Post #6
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2015-02-02T17:25:51+00:00
- Post Title: Heroes of the Storm

> Reply from TaylorMouse
>
> 2 things, I was aware there was an error, so you need to download the one with the bug fix:

http://www.sc2mapster.com/media/files/8 ... m_v1.1.zip

but I already made another one, same script but for those that do not have MAX 2011, but a newer version:

http://www.sc2mapster.com/media/files/8 ... tTools.zip

Be aware that the SC2ArtTools only support MAX 2011 for exporting, and no newer version is available.

T.Hi TaylorMouse My friend, thank you very much for your help, I tested the script runs perfectly. Thank you very much for the great work
## Post #7
- Username: clairegrube
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Feb 14, 2011 6:35 am
- Post datetime: 2015-02-02T21:53:09+00:00
- Post Title: Heroes of the Storm

Love it! 
Just a question though, Starcraft2 used different UV sets for decal textures on the same meshes, but i found only one UV set when i imported Raynor with your script. Any idea how the storm_hero_raynor_dec.dds is applied properly?
## Post #8
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-02-03T12:02:58+00:00
- Post Title: Heroes of the Storm

YES !

in my script there is no support for the decal, yet, I know there are different uv map layers in the m3 files, and I know where they are, I just haven't scripted it yet so that it is immediatly applied to the model.

anyway, this is very clearly documented in the Star 2 Art Tool documentation under tutorials and can be found on their official site: 

[http://us.battle.net/sc2/en/blog/124444 ... -1-21-2014](http://us.battle.net/sc2/en/blog/12444476/patch-21-art-tools-1-21-2014)

There is also a way to do this without the Art Tools, but I think you than need composite materials and apply another material id to that layer of uv's ( or something like that)

It is probably not going to be covered in my script though :/

T.
## Post #9
- Username: clairegrube
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Feb 14, 2011 6:35 am
- Post datetime: 2015-02-03T14:36:34+00:00
- Post Title: Heroes of the Storm

Thanks for the headsup.
I have no problem setting up the materials , it's just a matter of getting the UVs in the first place (for me that is). 
Again, great script!
## Post #10
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-02-04T07:43:32+00:00
- Post Title: Heroes of the Storm

New script coming this evening, 
* bug on the weird skinning after applying animation from a m3a animation file is fixed
* animation split body is fixed into one decent animation

Small preview 

[Dancing Illidan](https://www.youtube.com/watch?feature=player_embedded&v=AYqJFeFCDfk)

T.
## Post #11
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2015-02-04T09:23:08+00:00
- Post Title: Heroes of the Storm

cool，That's good
## Post #12
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-02-04T22:46:55+00:00
- Post Title: Heroes of the Storm

Here is the latest version with the animation (m3a) supported 

[Import m3 & m3a script v1.5](http://www.sc2mapster.com/assets/sc1-raynor-vulture/files/73-script-m3-import-script-by-tm-v-1-5/)

For those that do not have MAX 2011 with the Art Tools installed, here is an additional script that allows you to browse the imported animations

[Download AnimProps Script](http://www.sc2mapster.com/assets/sc1-raynor-vulture/files/75-script-anim-props/)

It shows you a popup list with the available animations, and changes the start and end frame if you like



How this is installed:
* Open Max
* Go to MaxScript menu
* Select Run Script...
* Select my script (TM_AnimProps.mse)
* Then go to Customize menu
* Select Customize User Interface...
* Select in Category "Taylor Mouse's Tools" ( like in the screenshot)



* Drag the "AnimationProperies" Action to one of your application bars, or make a new one
* You can assign an image to the button in stead of keeping the text

So after you imported the model and animation, click the button 

T.
## Post #13
- Username: clairegrube
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Feb 14, 2011 6:35 am
- Post datetime: 2015-02-06T13:27:44+00:00
- Post Title: Heroes of the Storm

I can only repeat myself: Once again, great work!
At least the SC2 art tools version works nicely, can't comment on the other one. 
Some of the HotS animations (Uther for example) have very long loading times, to the point i had to restart 3ds max. I don't know if that's a fault or if they just have to load very long due to their complexity.

EDIT: I've waited a few minutes, it seems some of the animations do indeed need considerably more time to load than others. So, no fault in the script!
## Post #14
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-02-06T19:41:07+00:00
- Post Title: Heroes of the Storm

[out]
## Post #15
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-02-08T10:48:34+00:00
- Post Title: Heroes of the Storm

Yes it does, but it uses a more complex version or newer version that was not supported up till now 

T.
## Post #16
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-02-16T19:11:01+00:00
- Post Title: Re: Heroes of the Storm

[out]
## Post #17
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-02-16T21:36:48+00:00
- Post Title: Re: Heroes of the Storm

Thx Wobble, I already tried the approach, but failed, for some newer models, it is no longer the case..

T.
## Post #18
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-02-17T23:33:55+00:00
- Post Title: Re: Heroes of the Storm

[out]
## Post #19
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-02-18T21:13:55+00:00
- Post Title: Re: Heroes of the Storm

mmmm cool, I need to verify that! cause with the alpha models it kinda screwed up :/

thnx

T.
## Post #20
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-02-22T11:25:04+00:00
- Post Title: Re: Heroes of the Storm

Hey Wobble, what are the other bits you are assigning?

#define HAS_POSITION_AND_UV   0x00020000
#define HAS_EXTRA_UVSET1   0x00040000
#define HAS_EXTRA_UVSET2   0x00080000
#define HAS_EXTRA_UVSET3   0x00100000

but what for 
HAS_WEIGHTS
HAS_NORMAL
HAS_TANGENT

?

Thnx
T.
## Post #21
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-06-05T19:59:22+00:00
- Post Title: Re: Heroes of the Storm

New script to Import Heroes of the Storm

[http://www.sc2mapster.com/assets/sc1-ra ... port-v2-0/](http://www.sc2mapster.com/assets/sc1-raynor-vulture/files/89-script-m3-import-v2-0/)

It supports the latest Build ( Release from 2.06.2015 )

You should be able to run this in 3DS Max 2011 ( which is supported by the SC2ArtTools ) and above

Enjoy

T.
## Post #22
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-06-10T09:44:54+00:00
- Post Title: Re: Heroes of the Storm

Problem found for importing the Materials when not using MAX 2011
Fixed a memory leak


Download here

[m3 import v 2.1](http://www.sc2mapster.com/assets/sc1-raynor-vulture/files/90-script-m3-import-v2-1/)


T.
## Post #23
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2015-06-10T10:00:51+00:00
- Post Title: Re: Heroes of the Storm

> Reply from TaylorMouse
>
> Problem found for importing the Materials when not using MAX 2011
Fixed a memory leak


Download here

m3 import v 2.1


T.
TaylorMouse My friend, the script works perfectly, thanks to your great job
## Post #24
- Username: pgw00k
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 28, 2014 7:42 am
- Post datetime: 2015-06-13T00:34:55+00:00
- Post Title: Re: Heroes of the Storm

> Reply from TaylorMouse
>
> Problem found for importing the Materials when not using MAX 2011
Fixed a memory leak


Download here

m3 import v 2.1


T.

Hi,TayLor,I could't get .m3 files,it is data.000 such files and I use zlib offzip to unpack but it do not work.
## Post #25
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-06-15T17:19:53+00:00
- Post Title: Re: Heroes of the Storm

Just download the CASC Viewer, it will browse the content of Heroes of the Storm 

[http://www.zezula.net/en/casc/main.html](http://www.zezula.net/en/casc/main.html)

T.
## Post #26
- Username: okami29
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Mar 09, 2017 8:57 pm
- Post datetime: 2019-05-10T17:25:22+00:00
- Post Title: Re: Heroes of the Storm

Hi Thank you Taylormouse for this script, it works wonderfully to import characters like Tyrael.
However I couldn't manage to import Tyrael wings, do you think it would be possible to find a way to import the wings mesh (those are animated planes) and animations ?
Thank you
