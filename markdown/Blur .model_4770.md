## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-07-19T18:43:33+00:00
- Post Title: Blur .model

Can anyone convert .model files with 3d model of the Blur racing game?

I attached as sample [audi r8v10](http://www.sendspace.com/file/wfgu9z)

p.s.: also about textures from Blur [here](http://forum.xentax.com/viewtopic.php?f=18&t=4769)
## Post #2
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2010-09-12T02:40:43+00:00
- Post Title: Blur .model

I started to research this format and now I've got some problems.
While the header and the list of parts are quite understood, the rest of file is a complete mess.
Also there can be DDS data inside the file.
in the end of the model file there's some text data (debug maybe) like XML.
Here's a picture of the data I can't understand as yet.
[](http://radikal.ru/F/s47.radikal.ru/i116/1009/d7/3932a8572324.jpg.html)

I hope anyone has ideas what it is.
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-09-12T02:55:14+00:00
- Post Title: Blur .model

> Reply from RoadTrain
>
> I started to research this format and now I've got some problems.
While the header and the list of parts are quite understood, the rest of file is a complete mess.
Also there can be DDS data inside the file.
in the end of the model file there's some text data (debug maybe) like XML.
Here's a picture of the data I can't understand as yet.


I hope anyone has ideas what it is.
Thanks for starting. Maybe someone get interest in this models.
## Post #4
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2010-09-12T04:51:45+00:00
- Post Title: Blur .model

I suppose the model files have hierarchical structure.

```
{
   char element_name[8];
   DWORD element_size; // size of the whole element including data
   DWORD flag; // I saw 2 types of flag: 04004300 and 00004100
   char data; //data may not to present, I dont understand how to recognize what to do: read the data or the next element?
}
```

'data' can be the child element.

Also I looked through the level files. They have the same hierarchical structure as models.
I need someone to help me with the models particularly with vertex/normal/face data.
I haven't dealt with 3D formats before.
## Post #5
- Username: vagos21
- Rank: veteran
- Number of posts: 128
- Joined date: Thu Feb 10, 2011 5:48 pm
- Post datetime: 2011-02-28T01:34:03+00:00
- Post Title: Blur .model

I was just asked to make a little research on the blur .model format, i'm stuck at exactly the same point! textures are a walk in the park in there, but vertices are the only thing messed up, even index buffers show up ok... no idea what's going on in there!

i fear it has to do with this [http://http.developer.nvidia.com/GPUGem ... _ch36.html](http://http.developer.nvidia.com/GPUGems3/gpugems3_ch36.html) and we're all doomed!
## Post #6
- Username: JGZinv
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 06, 2011 11:44 am
- Post datetime: 2011-04-06T05:32:55+00:00
- Post Title: Blur .model

You can capture models from Blur with 3d Ripper DX 1.8.0 and later. 

So far I can get a about a 90% complete model, but all the other data about the
car is of course lost. Not sure if that would help anyone here to take a look at the output
and compare it with the original file format. It can also grab about 98% of the textures with
correct color & size. Note that version 1.8 seems to do a better job than 1.8.1

Made a tut here, with Blur's Ford GT as the source: [http://www.youtube.com/watch?v=67HV5TfRrQg](http://www.youtube.com/watch?v=67HV5TfRrQg)

Also, if you look back at some of Bizarre's development videos, you can see some interesting
discussions. 

[http://www.slideshare.net/nonchaotic/a- ... e-lighting](http://www.slideshare.net/nonchaotic/a-bizarre-way-to-do-realtime-lighting)
A technical lighting and rendering heavy slideshow. 

[http://www.gametrailers.com/video/bizar ... blur/62635](http://www.gametrailers.com/video/bizarre-creations-blur/62635)
Around 1:23 you can see the damage mapping contact points for the cars.
## Post #7
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2011-04-09T01:31:56+00:00
- Post Title: Blur .model

> Reply from vagos21
>
> I was just asked to make a little research on the blur .model format, i'm stuck at exactly the same point! textures are a walk in the park in there, but vertices are the only thing messed up, even index buffers show up ok... no idea what's going on in there!

i fear it has to do with this http://http.developer.nvidia.com/GPUGem ... _ch36.html and we're all doomed!
I had the same problem. I could clearly see a lot of blocks of floats in .model files, but when I tried to load them into a 3D editor I always had a mess. I abandoned since the game seemed not to be worth researching.
## Post #8
- Username: JGZinv
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 06, 2011 11:44 am
- Post datetime: 2011-04-09T02:20:28+00:00
- Post Title: Blur .model

Well I can give you a 3DRDX ripped model file if you want to take a look.

If you're not interested any longer RoadTrain, would you mind passing the information on?
I did attempt to send you an e-mail on this a few days ago.

I have been contacting the developers (ex Bizarre) - but haven't yielded anyone
that has been interested in talking at length yet.
## Post #9
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2011-04-10T01:19:20+00:00
- Post Title: Blur .model

> Reply from JGZinv
>
> Well I can give you a 3DRDX ripped model file if you want to take a look.

If you're not interested any longer RoadTrain, would you mind passing the information on?
I did attempt to send you an e-mail on this a few days ago.

I have been contacting the developers (ex Bizarre) - but haven't yielded anyone
that has been interested in talking at length yet.
I'll think about it. I'll likely try to look at the models once again and then provide you all the info about them that's in my brain. But I can't claim when since there are uncertainties with my free time.
## Post #10
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2011-04-11T08:01:29+00:00
- Post Title: Blur .model

With Blur, only 3D Ripper DX is the solution. And, JGZinv, I claim that you rip them uncorrect. Taking huge-load of captures on one place will cause messed up textures and parameters. 

Also, from that view, you can easily receive screwed mesh.
## Post #11
- Username: JGZinv
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 06, 2011 11:44 am
- Post datetime: 2011-04-11T13:53:13+00:00
- Post Title: Blur .model

Well RF, I question if you have used 3DRDX before, as I've not stated I've taken a "huge load" before.
I've attempted to take several captures in the interest of seeing how well the output would come out.
Textures are exported with different file names each time you shut down and reload 3DRDX, so I find no issue
there. Besides the boss and legend cars, the others are using what appears to be a shine map, and RGB value
for the paint jobs.

What view would you suggest? Blur's showroom does not have a stationary camera, it moves around the
car in an oval pattern. In map captures are not any better than the showroom, short of the driver being included.
3DRDX 1.8 appears to keep more of the textures aligned to the correct UV's and captures some of the dummy helper
objects for lights on the car mesh.
## Post #12
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2011-04-12T08:39:57+00:00
- Post Title: Blur .model

I`ve been using 3D Ripper DX for years. Best view to capture is usually when you`re on starting grid, from the back view of car. Now depends on how the game`s physics are, for example if they`re 'wooden' like in 'GT Pro Series', just do capture on starting grid and you can easily receive it without problem. I haven`t tested with Blur right now, but suppose taking a capture from that way (with 1.8.1) you will be able to have it, unscrewed. I never take captures from rotated car view. I mostly use to rip from GameCube and Wii games, running on Dolphin, and collecting the 3D carmodels.

Also doing single capture will cause you have everything as must be, that`s my advise
## Post #13
- Username: JGZinv
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 06, 2011 11:44 am
- Post datetime: 2011-04-12T14:33:05+00:00
- Post Title: Blur .model

It's been my experience thus far with Blur that 3DR will rip a "complete" model, but miss 
sub objects or details on the opposite side of whatever you are looking at. Usually car lights,
tires, or windows. It seems to create a lot of duplicate objects due to reflections.

The showroom models give you about 97% of the complete car, as individual sub objects. Which should
be how the model file is composed, due to the damage system.

The in game race captures, may be missing half a car, tires, and large chunks of opponent cars. The cars
are also one mesh instead of pieces.

The in game map only captures the local part of the map that you are on.

The textures rip out fine, but are not applied properly/at all to the view in Max, although I've seen
some tutorials where this can be fixed.

As a side question RT, have you performed any DirectX 6 rips during your time with 3DR?
## Post #14
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2011-04-12T17:14:56+00:00
- Post Title: Blur .model

I did DirectX6 captures a lot of times usually on ePSXe (receive flat capture, pretty useless but fine for model recreation, thus far perfect for PSX textures) and Test Drive 5 (receive crappy meshes, but again it`s fine).

As for your problems, it`s fine, just leave ONLY the 'Remove degenerate faces' option checked. Ripping opponent`s car is always useless, better rip your carmodel only. And if possible for some games, rip better from the 'Photo mode', and rotate it to correct position 

Actually my site isn`t complete yet, but it will later include a lot of model rips (done with 3D Ripper DX) and tutorials at how to use it correctly.
## Post #15
- Username: JGZinv
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 06, 2011 11:44 am
- Post datetime: 2011-04-12T21:30:00+00:00
- Post Title: Blur .model

That'd be much appreciated cause documentation is poor at best, with max scripts scattered
across the 3DRDX forum which is about to collapse.

My DX6 question was in regard to this: [http://www.deep-shadows.com/hax/forum2/ ... f=2&t=7202](http://www.deep-shadows.com/hax/forum2/viewtopic.php?f=2&t=7202)

But let's not clutter the Blur thread with it.
## Post #16
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2023-02-04T16:38:38+00:00
- Post Title: Re: Blur .model

I'm bumping this topic. I tried hex2obj but the car model looks garbage. Are there plugins that can import .model files from Blur (2010) and fix this problem? Textures are bundled in here.



bandicam 2023-02-04 03-26-29-020.jpg (114.09 KiB) Viewed 118 times



Samples:
[https://mega.nz/folder/ZfJFVYxY#3zlYGVzBRSTGbIRW4o9Xaw](https://mega.nz/folder/ZfJFVYxY#3zlYGVzBRSTGbIRW4o9Xaw)
