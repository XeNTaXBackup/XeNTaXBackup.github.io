## Post #1
- Username: Scarabay
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Oct 12, 2014 6:04 pm
- Post datetime: 2014-10-13T06:09:08+00:00
- Post Title: You Are Empty .ds2md 3d-models

Hello everybody! My name is Alexander.
I am noob in coding, so I'd like to ask you for some help. I need to "crack" a format of .ds2md 3d-model from game "You Are Empty". Models can contain mesh, bones and animations data. There are only static mesh converters\importers, but I need skin\anims too, so I can load them all into 3ds Max and use in my mod.

Here are some links about file format:
[http://3d-orange.com.ua/reversing-game- ... are-empty/](http://3d-orange.com.ua/reversing-game-resources-in-you-are-empty/)
[http://code.google.com/p/yae-tools/](http://code.google.com/p/yae-tools/)
[Samples of models](http://rghost.ru/58495254)
If you need, I can upload one more source code of converter. 

I hope for your help. Thank you.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-13T10:48:58+00:00
- Post Title: You Are Empty .ds2md 3d-models

> Reply from Scarabay
>
> There are only static mesh converters\importers,The model format is very simple:



madman.JPG (175.37 KiB) Viewed 179 times



that's the reason why there are tools for the static mesh.


> but I need skin\anims too,that's a little bit harder/time consuming to get them.

(I will look for the skeleton as soon as I've some spare time.)
## Post #3
- Username: Scarabay
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Oct 12, 2014 6:04 pm
- Post datetime: 2014-10-14T04:10:00+00:00
- Post Title: You Are Empty .ds2md 3d-models

shakotay2, the model on your screenshot has no mesh with alpha-channel, just take a look at my screenshot.
[Here is the correct model](http://rghost.ru/58512440)

> I will look for the skeleton as soon as I've some spare time
That's great!
[madman.JPG](https://xentaxbackup.github.io/file/7934_madman.JPG)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-14T04:40:49+00:00
- Post Title: You Are Empty .ds2md 3d-models

> Reply from Scarabay
>
> shakotay2, the model on your screenshot has no mesh with alpha-channel, just take a look at my screenshot.yes. I don't have the time to check ALL submeshes of every model posted in this forum. So what?

here's the skeleton:



madman_skel.JPG (71.57 KiB) Viewed 159 times
## Post #5
- Username: Scarabay
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Oct 12, 2014 6:04 pm
- Post datetime: 2014-10-15T04:21:32+00:00
- Post Title: You Are Empty .ds2md 3d-models

> Reply from shakotay2
>
> here's the skeleton


[Here is the source code of converter](http://rghost.ru/58530152)
## Post #6
- Username: Scarabay
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Oct 12, 2014 6:04 pm
- Post datetime: 2014-10-17T14:36:49+00:00
- Post Title: You Are Empty .ds2md 3d-models

shakotay2, are there any news?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-17T19:34:49+00:00
- Post Title: You Are Empty .ds2md 3d-models

I think I'll look for the animation frames but that's not a 15-minutes-job. So may take some time.

If you don't want to wait and have some scripting skills (3dsmax or Noesis) you could start investigations in the format,
for example in madman.ds2md. There's a whole bunch of floats (litttle endian) between

(0x80DE1 Bip01 Pelvis) 0x80DF2 and 0x823C1 Bip01 Spine
such as
-0.026461 0.706611 -0.026461  -0.706612
 -2.694851 2.266191  73.805649 1.000000 
...
## Post #8
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-10-18T14:42:24+00:00
- Post Title: You Are Empty .ds2md 3d-models

Scarabay,

I added the  DS2 Engine (You Are Empty) .DS2MD loader module to the 3D Object Converter v5.339.
It loads the fully textured/materialized object.

[http://www.i3dconverter.com/3doc/downlo ... rtable.zip](http://www.i3dconverter.com/3doc/downloads/3doc_v5.339_portable.zip)

(See the file_id.diz files for the changes from v5.30.)
## Post #9
- Username: Scarabay
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Oct 12, 2014 6:04 pm
- Post datetime: 2014-10-19T11:33:38+00:00
- Post Title: You Are Empty .ds2md 3d-models

Karpati, thank you, but I already have two other converters   

shakotay2, as I said, I'm almost a noob in coding and I don't know maxscript, only Lua. I'll wait.
## Post #10
- Username: Scarabay
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Oct 12, 2014 6:04 pm
- Post datetime: 2014-10-30T04:38:30+00:00
- Post Title: You Are Empty .ds2md 3d-models

> Reply from Scarabay
>
> shakotay2, are there any news?
Hi. And what's now? 
You do not have enough time? When about ready?
