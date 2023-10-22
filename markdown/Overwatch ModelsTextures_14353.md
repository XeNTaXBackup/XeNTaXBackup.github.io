## Post #1
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2016-05-16T22:58:21+00:00
- Post Title: Overwatch Models/Textures

--redacted--
## Post #2
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2016-05-16T23:33:00+00:00
- Post Title: Overwatch Models/Textures

coulda asked myself too. didn't need to. tfa asked for it. so... wtf.

for the heck have a normal map too. doesn't belong to that model either. just got some lil more header. that doesn't help decoding either tho. 

[https://drive.google.com/file/d/0B_pQQ7 ... hSdlk/view](https://drive.google.com/file/d/0B_pQQ7YfZgJxRUF6eDBYdkhSdlk/view)
## Post #3
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-05-17T18:18:29+00:00
- Post Title: Overwatch Models/Textures

[out]
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-05-17T19:02:41+00:00
- Post Title: Overwatch Models/Textures

> Reply from TFA
>
> Currently available information ...

That would be good to summarize the current standing, so people don't need to write 9 pages of that thread:

Most of the archive format is already researched, I have a list of all character packages with all the corresponding stuff, the model format is almost fully reseached (except maybe some details about bones and weights) and the first version of a model converter is already working:
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-05-17T19:15:33+00:00
- Post Title: Overwatch Models/Textures

It even worked with the mech, the huge thing with only the main (of 50) submeshes having 34k+ vertices:
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-05-18T17:50:19+00:00
- Post Title: Overwatch Models/Textures

The tool is here: [http://zenhax.com/viewtopic.php?f=5&t=2472](http://zenhax.com/viewtopic.php?f=5&t=2472)
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-05-18T20:40:48+00:00
- Post Title: Overwatch Models/Textures

News. Textures are ready too.
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-05-21T13:35:32+00:00
- Post Title: Overwatch Models/Textures

Overwatch mass texture convertor released! [http://zenhax.com/viewtopic.php?f=5&...p=13592#p13595](http://zenhax.com/viewtopic.php?f=5&...p=13592#p13595)

Converts almost every shuffled texture in the game! Diffuse, specular, normal maps, masks.

First run cascexplorer and extract files from folders "004" and "04D". If you want to save space, extract only second half of "04D" folder, where all files have 0001 flag, like "000100000155" etc. These files are biggest MIPS, and they are only needed, so convertion tool will not use small MIPS anyway.

Then place "Overwatch_texture.exe" next to those 2 folders and run it

You don't have to convert all files at one time, just put the files you want in the corresponding "004" and "04D" folders.

In the end you must have about 13k from 18k files converted, because the remaining 5k files are NOT shuffled.
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-05-25T15:56:25+00:00
- Post Title: Overwatch Models/Textures

Looks like we got bones & weights.
## Post #10
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2016-05-31T20:35:20+00:00
- Post Title: Overwatch Models/Textures

Been following this A LOT !!

This is what I did with the all this knowledge in my model viewer
I cleaned it up a bit so it supports multiple meshes in one obj file.




T.
[multiplemeshesloaded.png](https://xentaxbackup.github.io/file/10986_multiplemeshesloaded.png)
## Post #11
- Username: tathannibal
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 16, 2015 7:05 am
- Post datetime: 2016-06-01T20:20:02+00:00
- Post Title: Overwatch Models/Textures

Wait to Download 

> Reply from TaylorMouse
>
> Been following this A LOT !!

This is what I did with the all this knowledge in my model viewer
I cleaned it up a bit so it supports multiple meshes in one obj file.




T.
## Post #12
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2016-06-01T21:37:03+00:00
- Post Title: Overwatch Models/Textures

Working on a script in 3D Studio Max

seems to be working too 

I can post that faster than the rebuild of the model viewer.

I also went over (almost all) the models and renamed them to something usefull ( like in the screenschot )

I'll post that list here as well once it is done.

T.
[wip.jpg](https://xentaxbackup.github.io/file/10990_wip.jpg)
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-02T15:08:48+00:00
- Post Title: Overwatch Models/Textures

> Reply from TaylorMouse
>
> I'll post that list here as well once it is done.
I already made a list of all characters/weapons with textures including premium model names. How your list will be different?

> Reply from TaylorMouse
>
> I cleaned it up a bit so it supports multiple meshes in one obj file.
Obj format is obsolete. It doesn't support bones, multiple UVs and other features that are needed.
## Post #14
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2016-06-02T19:43:55+00:00
- Post Title: Overwatch Models/Textures

Ho, my list has all the files renamed, also the other object, like pipes, buildings, decoration, pots, wall, ark, doorway, airplane.... etc
but, if you list does that as well, I don't need to finish mine 


Obj is obsolete, I don't think that is the case for my viewer, since it does not support materials or bones, so in my case it does the job perfectly

The viewer is only for quick browsing through all the models.

T.
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-02T19:59:11+00:00
- Post Title: Overwatch Models/Textures

> Reply from TaylorMouse
>
> but, if you list does that as well, I don't need to finish mine

No, I only marked characters and their stuff.
## Post #16
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2016-06-03T22:31:10+00:00
- Post Title: Re: Overwatch Models/Textures

I've used it to pin point the heroes, which was an awesome help, 
I really like this model, the drop ship and all the obj's combined look just awesome, I did this via a script I wrote in max



T.
## Post #17
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-04T05:29:13+00:00
- Post Title: Re: Overwatch Models/Textures

Yeah, this ship is the biggest model in the game. Number 00002DDC if anyone wants to extract it now. My skeleton tool that I posted a week ago does it in one Xnalara file. Though this ship has no bones.



While this bus does. (model 00001946)
## Post #18
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2016-06-04T09:35:15+00:00
- Post Title: Re: Overwatch Models/Textures

Yeah, Blizzard really did a good one on these 


Btw, I extracted all of the models, but noticed that my files nbrs are longer, for example

```
0000000009F8
```
 -> Hero Genji First Person Arms

How can that be ?

T.
## Post #19
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-04T10:49:47+00:00
- Post Title: Re: Overwatch Models/Textures

> Reply from TaylorMouse
>
> Btw, I extracted all of the models, but noticed that my files nbrs are longer

That doesn't matter. I Just removed first 0000's. You can also remove 00000000, because they never go up 4 digits.
## Post #20
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2016-06-04T11:12:11+00:00
- Post Title: Re: Overwatch Models/Textures

Btw, I have a couple of files where there is not "physical" meshes, any idea what they are ?

a few examples:

000000000213
000000000322
00000000085D
00000000085E
0000000008CE
0000000009B8

Just wondering, don't break your head on it

T.
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-04T11:18:07+00:00
- Post Title: Re: Overwatch Models/Textures

> Reply from TaylorMouse
>
> Btw, I have a couple of files where there is not "physical" meshes, any idea what they are ?

What do you mean? They are no different than others. This is for example your 0322:
## Post #22
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2016-06-04T12:49:37+00:00
- Post Title: Re: Overwatch Models/Textures

Damn, you are right, the model viewer draw distance was not set far enough so I did not see it !!

THnx ( again :p )

T.
## Post #23
- Username: tathannibal
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 16, 2015 7:05 am
- Post datetime: 2016-06-22T08:10:52+00:00
- Post Title: Re: Overwatch Models/Textures

Anny News?
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-22T15:14:41+00:00
- Post Title: Re: Overwatch Models/Textures

What news you expect? All models and textures are extracted.
## Post #25
- Username: tathannibal
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 16, 2015 7:05 am
- Post datetime: 2016-06-23T07:13:07+00:00
- Post Title: Re: Overwatch Models/Textures

Okey.
Pls share to extracter or viewer/converter program.
Thx 

> Reply from daemon1
>
> What news you expect? All models and textures are extracted.
## Post #26
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-23T15:12:23+00:00
- Post Title: Re: Overwatch Models/Textures

> Reply from tathannibal
>
> Okey.
Pls share to extracter or viewer/converter program.
Thx 
daemon1 wrote:What news you expect? All models and textures are extracted.

Scroll up to the start of this thread. In my first messages i posted all the links! It was a month ago
## Post #27
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-07-14T07:49:16+00:00
- Post Title: Re: Overwatch Models/Textures

Animations extracted

[https://youtu.be/koX8695_ry0](https://youtu.be/koX8695_ry0)

[https://youtu.be/9CMajorRE7Y](https://youtu.be/9CMajorRE7Y)
## Post #28
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-07-15T15:47:50+00:00
- Post Title: Re: Overwatch Models/Textures

Experimental version of animation tool released:

[http://zenhax.com/viewtopic.php?p=13517#p13517](http://zenhax.com/viewtopic.php?p=13517#p13517)
## Post #29
- Username: Emissaryofwind
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 18, 2016 6:00 am
- Post datetime: 2016-10-14T16:56:05+00:00
- Post Title: Re: Overwatch Models/Textures

Any chance someone can grab the models for the Halloween skins and put them up in fbx?
## Post #30
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2017-05-18T18:15:58+00:00
- Post Title: Re: Overwatch Models/Textures

A long time has passed, but it payed up!!

Here you go

Model AND animation import for 3D Studio Max 


[https://www.youtube.com/watch?v=ljOBb1ggLDE](https://www.youtube.com/watch?v=ljOBb1ggLDE)




Hope you like it!

T.
## Post #31
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2018-07-18T22:57:54+00:00
- Post Title: Re: Overwatch Models/Textures

Is it possible for me to ask for vehicle meshes? I don't need them rigged I don't need them textured I just want the meshes prefferably in a .obj. Thanks for your time.
## Post #32
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2018-07-19T07:25:19+00:00
- Post Title: Re: Overwatch Models/Textures

You will probably need to do that yourself

you need the game, the casc explorer and my viewer.

Extract the raw models with the casc explorer and browse through the models with my viewer, the names are just a sequence of bytes like 000000004EF.0CC

Casc explorer: [https://ci.appveyor.com/api/buildjobs/x ... plorer.zip](https://ci.appveyor.com/api/buildjobs/xnvppukqk0any6re/artifacts/CASCExplorer%2FCASCExplorer%2Fbin%2FCASCExplorer.zip)

My viewer: [https://www.dropbox.com/s/g19lul4r359eo ... 2.zip?dl=0](https://www.dropbox.com/s/g19lul4r359eo3t/3D%20Model%20Viewer%203.2.zip?dl=0)

With my viewer you can export the model to .obj

More on my blog here: [https://taylormousegamedev.blogspot.com/](https://taylormousegamedev.blogspot.com/)

Hope this helps.
## Post #33
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2018-07-19T14:04:42+00:00
- Post Title: Re: Overwatch Models/Textures

> Reply from TaylorMouse
>
> You will probably need to do that yourself

you need the game, the casc explorer and my viewer.

Extract the raw models with the casc explorer and browse through the models with my viewer, the names are just a sequence of bytes like 000000004EF.0CC

Casc explorer: https://ci.appveyor.com/api/buildjobs/x ... plorer.zip

My viewer: https://www.dropbox.com/s/g19lul4r359eo ... 2.zip?dl=0

With my viewer you can export the model to .obj

More on my blog here: https://taylormousegamedev.blogspot.com/

Hope this helps.

 Okay, thanks I shall work with all this but while I have you I have ment to ask about making an addition to you 3d model viewer tool here. When I rip most pc games I can see the gemetry even if it's been flipped (mercinaries 2 world of flames seems to rip the model inside out) But when I ripping models from android games using ninja ripper I can never see the geometry at all and have to go rip by rip in 3D max to get to the geometry I want out of the all the files. Your viewer,  usuaully cuts down my rip sorting time to a 1/4 of the time it takes me in 3D MAX going one by one.  is there a way or can you make a way to make android ninja ripper rip files show geometry with your tool?  cause that's been my biggest and only issue with your awesome 3d viewer.
## Post #34
- Username: Tabris
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Jan 27, 2011 9:56 am
- Post datetime: 2019-11-28T09:03:35+00:00
- Post Title: Re: Overwatch Models/Textures

Hi everyone,

I tried to export models from Overwatch.

My overwatch version is the 1.42. I tried to use CASCExplorer.exe v1.0.123 but I got an error message.

Is there another way to extract the models ? What am I doing wrong ?

Thanks.
## Post #35
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-11-28T13:49:43+00:00
- Post Title: Re: Overwatch Models/Textures

> Reply from Tabris ↑Thu Nov 28, 2019 5:03 pm at Thu Nov 28, 2019 5:03 pm
>
> 
...
Is there another way to extract the models ? What am I doing wrong ?

there is only [this way](https://github.com/overtools/OWLib) afaik. i can't tell the version status tho. i'm not on it rn.
## Post #36
- Username: Tabris
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Jan 27, 2011 9:56 am
- Post datetime: 2019-12-03T11:29:57+00:00
- Post Title: Re: Overwatch Models/Textures

humm.. sorry but I'm a 3d artist I don't even know what to do with your link.

I tried to use Datatool, it says "base not correct".

I just need the gun of zarya. Could maybe someone send me the model ?

[https://i.pinimg.com/originals/29/fc/24 ... 20506.jpg
](https://i.pinimg.com/originals/29/fc/24/29fc24500711f0629afef2dc42720506.jpg)
Best
## Post #37
- Username: rensole
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Feb 26, 2013 4:34 am
- Post datetime: 2019-12-08T17:32:19+00:00
- Post Title: Re: Overwatch Models/Textures

Ive recently also been getting errors and I'm no longer able to extract anything.
Would anyone have any idea on how I could resolve this?

Datatool v1.42.0.855
Overwatch build  1.42.0.0.63869

I always get this:

Time now: 8-12-2019 18:30:18
Cmdline: DataTool.exe --language=enUS --cache --cache-data --convert-textures-type=tif "F:\hots\2\Overwatch" extract-unlocks ".\\" "ana"
Output: .\
[Core] DataTool v1.42.0.855-git-75497e17c0afb455b9aee19c9748faa43c08aa35
[Core] CommandLine: ["--language=enUS", "--cache", "--cache-data", "--convert-textures-type=tif", "F:\hots\2\Overwatch", "extract-unlocks", ".\", "ana"]
[Core] CommandLineFile: C:\Users\****\Downloads\toolchain-release (4)\DataTool.exe.args
[CASC] Set language to enUS
[CASC] Overwatch build 1.42.0.0.63869
[CASC] Initializing...
[CMF] Using CMF procedure 63869
[CMF] Using CMF procedure 63869
System.Reflection.TargetInvocationException: Exception has been thrown by the target of an invocation. ---> System.AggregateException: One or more errors occurred. ---> System.IO.EndOfStreamException: Unable to read beyond the end of the stream.
   at System.IO.__Error.EndOfFile()
   at System.IO.BinaryReader.FillBuffer(Int32 numBytes)
   at System.IO.BinaryReader.ReadInt32()
   at TACTLib.Container.ContainerHandler.OpenIndexEntry(IndexEntry indexEntry)
   at TACTLib.Container.ContainerHandler.OpenEKey(EKey key)
   at TACTLib.Client.ClientHandler.OpenEKey(CKey key)
   at TACTLib.Client.ClientHandler.OpenCKey(CKey key)
   at TACTLib.Core.Product.Tank.ApplicationPackageManifest.LoadPackage(Int32 i, ClientHandler client, ContentManifestFile cmf)
   at TACTLib.Core.Product.Tank.ApplicationPackageManifest.<>c__DisplayClass12_2.<.ctor>b__0(Int32 i)
   at System.Threading.Tasks.Parallel.<>c__DisplayClass17_0`1.<ForWorker>b__1()
   at System.Threading.Tasks.Task.InnerInvokeWithArg(Task childTask)
   at System.Threading.Tasks.Task.<>c__DisplayClass176_0.<ExecuteSelfReplicating>b__0(Object )
   --- End of inner exception stack trace ---
   at System.Threading.Tasks.Task.ThrowIfExceptional(Boolean includeTaskCanceledExceptions)
   at System.Threading.Tasks.Task.Wait(Int32 millisecondsTimeout, CancellationToken cancellationToken)
   at System.Threading.Tasks.Parallel.ForWorker[TLocal](Int32 fromInclusive, Int32 toExclusive, ParallelOptions parallelOptions, Action`1 body, Action`2 bodyWithState, Func`4 bodyWithLocal, Func`1 localInit, Action`1 localFinally)
   at System.Threading.Tasks.Parallel.For(Int32 fromInclusive, Int32 toExclusive, ParallelOptions parallelOptions, Action`1 body)
   at TACTLib.Core.Product.Tank.ApplicationPackageManifest..ctor(ClientHandler client, ProductHandler_Tank tankHandler, Stream stream, String name)
   at TACTLib.Core.Product.Tank.ProductHandler_Tank..ctor(ClientHandler client, Stream stream)
   --- End of inner exception stack trace ---
   at System.RuntimeMethodHandle.InvokeMethod(Object target, Object[] arguments, Signature sig, Boolean constructor)
   at System.Reflection.RuntimeConstructorInfo.Invoke(BindingFlags invokeAttr, Binder binder, Object[] parameters, CultureInfo culture)
   at System.RuntimeType.CreateInstanceImpl(BindingFlags bindingAttr, Binder binder, Object[] args, CultureInfo culture, Object[] activationAttributes, StackCrawlMark& stackMark)
   at System.Activator.CreateInstance(Type type, BindingFlags bindingAttr, Binder binder, Object[] args, CultureInfo culture, Object[] activationAttributes)
   at System.Activator.CreateInstance(Type type, Object[] args)
   at TACTLib.Core.Product.ProductHandlerFactory.GetHandler(TACTProduct product, ClientHandler client, Stream root)
   at TACTLib.Client.ClientHandler..ctor(String basePath, ClientCreateArgs createArgs)
   at DataTool.Program.InitStorage(Boolean online)
   at DataTool.Program.Main()
