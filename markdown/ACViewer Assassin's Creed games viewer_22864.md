## Post #1
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-10-19T21:20:47+00:00
- Post Title: ACViewer: Assassin's Creed games viewer

This is a little thing I started working on years ago, around the time of AC2 Revelations and AC3. Over the years I added support for more recent games, sometimes breaking older games in the process.
I the last couple years I went back this project, with the idea of a more general release. Things are not as good as I wanted them to be, but it's good enough for a first release.

Supports all main AC games from the original to Odyssey, with the exception of 3HD and Liberation HD (mostly because I didn't look into them yet). PC only version (although some xbox360 work was done, but the mesh will not load properly yet).
Most maps should load, with the caveat that Origins and Odyssey are very taxing to load/display, and will be missing the ground. Of course, not everything will work properly, the lighting is broken, and a lot of materials are slightly wrong/missing. This is a work in progress.

I've removed a few broken/incomplete features to not confuse people, so this should be a considered a preview version of what the tool can do. Some features that were removed for now is the ability to look at characters (was functional in AC3, but got broken since), animations (also worked on AC3), data properties, stuff like gameplay entities,...

[Update 5/17/2023]:
Much has changed since this post was made.
For latest version and link to discord:
[https://github.com/forge-master/ACViewer/wiki](https://github.com/forge-master/ACViewer/wiki)
## Post #2
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-10-19T21:25:56+00:00
- Post Title: ACViewer: Assassin's Creed games viewer

acviewer4.jpg (204.88 KiB) Viewed 1248 times
## Post #3
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-10-19T21:26:14+00:00
- Post Title: ACViewer: Assassin's Creed games viewer

acviewer2.jpg (244.04 KiB) Viewed 1248 times
## Post #4
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-10-20T01:30:10+00:00
- Post Title: ACViewer: Assassin's Creed games viewer

A very ambitious project, thank you for sharing.
To those of you wanting to try this, make sure you have plenty of RAM as it eats up lots of it, trying on ACUnity it filled up my 24GB of ram in less than 35 seconds, i wonder if possible to use the GPU as an acceleration hardware for loading/preview and all, if that makes sense.
I got very excited seeing this type of project, hoping in the future we can actually export full maps as in-game.
Also on my end, just trying to navigate is not easy, and as soon as i try to zoom out even as little as possible, all goes light dray and nothing else is shown even after long minutes of waiting, so i have to kill the process and start over.

WIP or not this is still amazing, looking forward to try new features if and when they become available if planned, thank you once again.
## Post #5
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-10-20T02:09:09+00:00
- Post Title: ACViewer: Assassin's Creed games viewer

Camera speed is controlled by mouse-wheel, but isn't capped. So it can happened that move speed gets very large and you end up lost in the map. I will look at capping the speed properly. When that happen, you can use the menu World>Transition portals to choose a portal and teleport the camera back there (this is player spawn points). No need to reload the map.
## Post #6
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-10-20T02:12:21+00:00
- Post Title: ACViewer: Assassin's Creed games viewer

Also forgot to say, camera controls are AWSD, and mouse right click for orientation
## Post #7
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2020-10-22T18:31:21+00:00
- Post Title: ACViewer: Assassin's Creed games viewer

I love you  
Great project, sadly I don't have 24 GB of memory to view big map in AC Unity, but medieval map loaded fine.
## Post #8
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-10-22T19:12:40+00:00
- Post Title: ACViewer: Assassin's Creed games viewer

I have on-going memory optimizations that should reduce the memory footprint, but that's going to take a bit of time. But for now, Unity or later game are definitively pretty expensive on large maps.
I should have an update later today or tomorrow fixing AC Rogue and Syndicate that broke at some point in recent changes, as well as texture improvements.
## Post #9
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-10-22T19:18:02+00:00
- Post Title: ACViewer: Assassin's Creed games viewer

Some of the interesting maps in ACU includes the Prologue, Rebirth Ritual (I used that map a lot for early ACU implementations). The maps labelled LGS are a bit less interesting in my opinion.
For Rebirth Ritual, make sure you enable all the data layers in World>Data Layers as part of the maps are loaded as extra layers on top of the base map.
## Post #10
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-10-22T19:21:01+00:00
- Post Title: ACViewer: Assassin's Creed games viewer

Really need to get the lighting back into a functional state



ACU.jpg (220.39 KiB) Viewed 1169 times
## Post #11
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-10-22T19:25:24+00:00
- Post Title: ACViewer: Assassin's Creed games viewer

ACU2.jpg (246.98 KiB) Viewed 1169 times
## Post #12
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-10-22T19:43:00+00:00
- Post Title: ACViewer: Assassin's Creed games viewer

This looks so good and so tempting, but we cant use any of it, for, literally anything at all, no export no nothing, sadly, but please continue to work on it for what ever purpose it may be, curious to see what that is moving forward.
## Post #13
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-10-22T20:19:06+00:00
- Post Title: ACViewer: Assassin's Creed games viewer

Exporing meshes would not be a giant issue. But exporting a complete city would be tricky. I don't think blender or any other program would load the full high poly map of say Greece
## Post #14
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-10-22T20:20:47+00:00
- Post Title: ACViewer: Assassin's Creed games viewer

I think the best I could do would be to make ue4 plugin and import the maps inside of UE4. But not even sure it would be able to cope with it nicely. But might be worth a try.
## Post #15
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-10-22T20:24:40+00:00
- Post Title: ACViewer: Assassin's Creed games viewer

Everything would export/import by sectors/areas/zones or what ever the game has, not all at once in one giant file, that's not productive obviously.
The map can then be easily worked on by its sections in your desired 3D Editor or even in a game engine. 
The ONLY main thing would be to make sure we are able to export/import in their in-game coordinates, every single asset.
Quite a few of us are interested in this and the AC games, because as you've noticed by now, i assume, many tools have surfaced, yet neither have been ever finished or actually usable in any proper way.
## Post #16
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2020-10-22T20:36:13+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

> Reply from forgeMaster ↑Fri Oct 23, 2020 3:12 am at Fri Oct 23, 2020 3:12 am
>
> 
I have on-going memory optimizations that should reduce the memory footprint, but that's going to take a bit of time. But for now, Unity or later game are definitively pretty expensive on large maps.
I should have an update later today or tomorrow fixing AC Rogue and Syndicate that broke at some point in recent changes, as well as texture improvements.

I actually impressed that your program load maps just fine.
I tested only ACU as this is the only game I have installed right now and interested in, my spec are 2GB of video RAM and 8 GB of RAM,
with those specs I can load and fly through Paris map with stutters, but it loads! You did a big work with managing game LODs and draw distance
## Post #17
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2020-10-22T20:42:03+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

For export, there is a program called ACExplorer, it able to export a small parts of game in a form of chunks.

[viewtopic.php?t=20061](https://forum.xentax.com/viewtopic.php?t=20061)
In general, it export successfully Notre-Dame and few streets near it, giving errors on other maps or streets far away from Notre-Dame even within single map.
P.S. But yeah, as it was said previously, that exporter is still wip and maybe abandoned at all
## Post #18
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-10-22T20:54:56+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

> Reply from fullinu ↑Fri Oct 23, 2020 4:42 am at Fri Oct 23, 2020 4:42 am
>
> 
For export, there is a program called ACExplorer, it able to export a small parts of game in a form of chunks.

viewtopic.php?t=20061
In general, it export successfully Notre-Dame and few streets near it, giving errors on other maps or streets far away from Notre-Dame even within single map.
Unfortunately is unfinished and lots of missing assets due to un-reversed/unknown formats.
And yes that is a good example how its exported in its cell_blocks sections as its loaded incrementally during game play, this project could easily do the exact same thing
## Post #19
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-10-22T21:06:33+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

Stutter are due to loading more data in a single threader way. This should improve over time. On very demanding games (syndicate and later due to the way they handled some stuff differently compared to earlier games), it's better to toggle "Freeze Camera" as it stops all loading and keeps LODs as they were when you froze the camera. Just unfreeze it when you reached where you wanted to go.

I'm aware of some of the other projects yes, and I was surprised anyone else bother with the chunked format of ACU. It's pretty good work!

> Unfortunately is unfinished and lots of missing assets due to un-reversed/unknown formats.
The format is annoying, I try to do the same guesswork approach early-on, but it's just too much stuff. ACViewer actually support a lot of things behind the hood that are not displayed yet, gameplay entities, triggers, animations, cutscene data,... My interest goes a bit beyond the graphical stuff.

Regarding the export, my current thinking is to write an USD exporter, as it's meant for very large dataset, seems flexible enough and is supported by multiple editor.
## Post #20
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2020-10-22T21:17:56+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

> Reply from forgeMaster ↑Fri Oct 23, 2020 5:06 am at Fri Oct 23, 2020 5:06 am
>
> 
On very demanding games (syndicate and later due to the way they handled some stuff differently compared to earlier games), it's better to toggle "Freeze Camera" as it stops all loading and keeps LODs as they were when you froze the camera. Just unfreeze it when you reached where you wanted to go.

Thanks, I will give it a try and try to load further regions of Paris now!
## Post #21
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-10-22T23:34:36+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

> Reply from forgeMaster ↑Fri Oct 23, 2020 5:06 am at Fri Oct 23, 2020 5:06 am
>
> 
...Regarding the export, my current thinking is to write an USD exporter, as it's meant for very large dataset, seems flexible enough and is supported by multiple editor.
I like the fact your considering a option to export as it is in-game, nice. Not only that this USD is relatively new to the public though, no native support to any of the editors we currently use, such as:
3ds Max, Maya, Cinema4D even the horrible Blender (and others), neither of them support this format currently, i hope it will be a good decision in the end.
## Post #22
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-10-23T00:18:29+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

Mmm, I'm pretty sure there is USD plugin for Maya and Max. Blender support is in development. Unit and UE4 already support it. Might not be full support, but what I need is pretty simple mesh/material/texture.
The advantage of USD is that you can load on demand the assets, so you could have a whole city, and only load the bits you care about, while still sharing all the instances.
## Post #23
- Username: cire992
- Rank: beginner
- Number of posts: 31
- Joined date: Sun May 02, 2010 11:39 am
- Post datetime: 2020-10-28T09:04:48+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

If you add USD support for bringing chunks of AC maps into Unreal then I'll build a temple in your honor that puts the parthenon, pantheon, notre dame and all the others we've scrambled up top of in these game to shame. Or... I'll throw some generous tips toward your patreon for your efforts. Playing these games is fun, but making stuff with them is a blast. If nothing else, I want you to know how much I appreciate what you've done with this program. I especially love the widget you put on there that shows the id of whatever entity is under the mouse. Having spent all this time rooting around the game files in blacksmith, it's nice to finally be able to clearly see how these worlds were assembled together.
## Post #24
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-28T09:39:03+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

Do you plan support characters (bones, skin) e.t.c?
## Post #25
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-10-28T18:55:30+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

> Reply from erik945 ↑Wed Oct 28, 2020 5:39 pm at Wed Oct 28, 2020 5:39 pm
>
> 
Do you plan support characters (bones, skin) e.t.c?

Correct. It's actually already in there, but in a broken state right now.
Here is a screenshot of the tool when character loading was working (this is early 2013). I've been working at restoring character loading so hopefully sometime soon.
[connor.jpg](https://xentaxbackup.github.io/file/18921_connor.jpg)
## Post #26
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-10-28T18:55:56+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

I also had animation working around the same time, albeit with busted skinning in this screenshot.
[anim.jpg](https://xentaxbackup.github.io/file/18922_anim.jpg)
## Post #27
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-29T03:16:16+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

Ok, thanks, Do you plan support last games - Origins, Odyssey?
## Post #28
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-10-29T04:57:00+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

It already does support them, although it's a bit broken, and map only. Haven't looked at characters in those, but there is nothing that would prevent me from implementing it given time.
## Post #29
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-29T07:06:32+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

Thanks for answers. Will waitt.
## Post #30
- Username: cire992
- Rank: beginner
- Number of posts: 31
- Joined date: Sun May 02, 2010 11:39 am
- Post datetime: 2020-10-29T07:42:37+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

Damn, you're an absolute madman.
## Post #31
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-10-29T13:20:27+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

Keeping a watch on this thread 

Liking what I see so far~
## Post #32
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-10-29T21:55:54+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

This pulled me into the rabbit hole of fixing characters, and made some good progress.
[character.jpg](https://xentaxbackup.github.io/file/18926_character.jpg)
## Post #33
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-11-02T08:07:17+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

Sorry for the lack of update/release, I went very deep in the rabbit hole of supporting characters. Scimitar allows designers to override pretty-much any properties when spawning characters. Supporting this ended up requiring major changes to fundamental pieces of code. This is for example used in AC Revelation to swap Desmond hoodie from white to black while in the Animus, toggling the player's hood, or replacing player head texture depending if the hood is up or not.
Also added ACU characters while I was at it. I implemented hair with a complete hack, but that will do for now.
There is still some issues that need work, but it's getting there.
[characters.jpg](https://xentaxbackup.github.io/file/18942_characters.jpg)
## Post #34
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-11-02T10:06:04+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

It looks very interesting.
How difficult do you think it is to support the Odyssey and Origins characters?
Are you planning to support Valhalla?
## Post #35
- Username: cire992
- Rank: beginner
- Number of posts: 31
- Joined date: Sun May 02, 2010 11:39 am
- Post datetime: 2020-11-02T13:52:26+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

Man, that's awesome. Wish I had more to say, but to a peon like me you're basically a wizard doing magic.
## Post #36
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-11-02T18:55:00+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

> Reply from erik945 ↑Mon Nov 02, 2020 6:06 pm at Mon Nov 02, 2020 6:06 pm
>
> 
How difficult do you think it is to support the Odyssey and Origins characters?

Actually got Bayek loading just after I made the previous post. Odyssey needs a bit more work, but nothing impossible.



Bayek.jpg (162.03 KiB) Viewed 249 times



> Reply from erik945 ↑Mon Nov 02, 2020 6:06 pm at Mon Nov 02, 2020 6:06 pm
>
> 
Are you planning to support Valhalla?

Whenever it's released I will take a look, but I expect it to be fairly close to Odyssey.
## Post #37
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-11-02T23:50:24+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

Quick bugfix release 0.1a: [https://mega.nz/file/VKZHQaYb#OM7MDzVnX ... s1eh0RmSS4](https://mega.nz/file/VKZHQaYb#OM7MDzVnXLuD5Fcr1-Rofz_w5xX5y-C7fs1eh0RmSS4)

Changelog:
* Stuff, lots of it
* Proper camera speed capping
* Mipmaps!
* Fixes to Syndicate and Rogue that were crashing on load
* Spawn character: super early and buggy, vaguely supported on ACRevelations, AC3, ACUnity, ACOrigins and ACOdyssey.

Characters are spawned from the World>EntityBuilder menu. This will only list entities that are global or in the current loaded world. Characters spawn at the origin of the world, but that's not always easy to find as the camera spawn at the player default spawn point. I will fix that up. In the meantime, I recommend loading the whiteroom (or titlescreen in ACU) to spawn characters.
## Post #38
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2020-11-03T00:41:41+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

Hello, forgeMaster! Surprise about your tool, can i'm wait a Prince of Persia 2008 support in future updates? 
Try use it on the title but empty boxes and black\gray window only.
Export Characters with Animations will be possible in your plans?
## Post #39
- Username: cire992
- Rank: beginner
- Number of posts: 31
- Joined date: Sun May 02, 2010 11:39 am
- Post datetime: 2020-11-03T16:21:29+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

Cool. I noticed that the terrain is rendering in a few places. Honestly, I feel like more stuff is rendering properly in general. Big thumbs up. Also, with the entity spawning, maybe a function that snaps the camera to the world origin would do in a pinch. I'm thinking you have more elaborate plans there, though.

Also, not sure if anyone else is having trouble, but I'm getting a crash with Odyssey when loading any of the worlds other than the whiteroom.

Otherwise, great work on all of this. I'm really blown away that this just works with basically the entire franchise.
## Post #40
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-11-03T16:48:45+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

> Reply from JakeMiles ↑Tue Nov 03, 2020 8:41 am at Tue Nov 03, 2020 8:41 am
>
> 
can i'm wait a Prince of Persia 2008 support in future updates?

I looked at it a while back. Will probably re-evaluate at some point, but it's not at the top of my list. The format is similar to AC, but with enough custom tweaks that it's going to be a bit of work.

> Reply from cire992 ↑Wed Nov 04, 2020 12:21 am at Wed Nov 04, 2020 12:21 am
>
> 
maybe a function that snaps the camera to the world origin would do in a pinch
Yeah thought about it, but since most games where it "works" have a white room close to the origin I decided to not fuss with it and do something better later. I want to do character loading in a separate 3d window.

> Reply from cire992 ↑Wed Nov 04, 2020 12:21 am at Wed Nov 04, 2020 12:21 am
>
> 
Also, not sure if anyone else is having trouble, but I'm getting a crash with Odyssey when loading any of the worlds other than the whiteroom.
Yeah, sorry about that, I realize after the fact that I broke some texture loading stuff in Odyssey. I already fixed it locally, but decided to not do another update as I want to spend some time fixing Odyssey/Origins sluggish speed first. But let me know if you'd rather have a fixed build for loading now.
## Post #41
- Username: cire992
- Rank: beginner
- Number of posts: 31
- Joined date: Sun May 02, 2010 11:39 am
- Post datetime: 2020-11-03T17:08:45+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

No rush. I just wanted to make sure I wasn't doing something wrong.
## Post #42
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-11-03T17:25:54+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

When I run the program, I only see this.

Did I do something wrong (Odyssey)?

This is just viewer or exporter too?
[Безымянный.jpg](https://xentaxbackup.github.io/file/18949_Безымянный.jpg)
## Post #43
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-11-03T17:52:27+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

> Reply from erik945 ↑Wed Nov 04, 2020 1:25 am at Wed Nov 04, 2020 1:25 am
>
> 
When I run the program, I only see this.

Did I do something wrong (Odyssey)?

This is just viewer or exporter too?

This is the throne room, you can move the camera with WASD, and mouse with right click.
Just a viewer for now, will look at exporting later.
## Post #44
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-11-03T17:54:52+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

Just created a discord server in case you want to chat about the tool and have questions.
[https://discord.gg/hs9qrhYHyX](https://discord.gg/hs9qrhYHyX)
## Post #45
- Username: cire992
- Rank: beginner
- Number of posts: 31
- Joined date: Sun May 02, 2010 11:39 am
- Post datetime: 2020-11-04T22:32:38+00:00
- Post Title: Re: ACViewer 0.1: Assassin's Creed games map viewer

Invite's invalid?
## Post #46
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-11-05T00:29:41+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

> Reply from cire992 ↑Thu Nov 05, 2020 6:32 am at Thu Nov 05, 2020 6:32 am
>
> 
Invite's invalid?

Forgot to make the invite not expired. Updated the link.
## Post #47
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-11-10T16:46:17+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

A quick update here, been hard at work rewritting the mesh/material/texture code and clean things up. Supporting this many revisions of the same engine over such a long time period has created quite a tangled mess. This new code is much more flexible and allow me to isolate each game to limit a fix to one game to break another. It's done for AC3/ACUnity/ACSyndicate/Origins/Odyssey and mostly done for the rest.
I will take a look at Valhalla soon.
## Post #48
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-11-10T20:43:14+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

Preliminary AC Valhalla world loaded:
[norway.jpg](https://xentaxbackup.github.io/file/19007_norway.jpg)
## Post #49
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-11-11T02:03:52+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

Progress
[hall.jpg](https://xentaxbackup.github.io/file/19013_hall.jpg)
## Post #50
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2020-11-11T02:56:49+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

Are all of these environment meshes also fully exportable to OBJ/FBX or any other format.
I saw a lot of mention about characters but didn't spot anything much about environments just yet.
## Post #51
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-11-11T16:36:05+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

No export yet, but will look at it soonish now.
## Post #52
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-11-11T16:38:58+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

Some update from last night
[valhalla.jpg](https://xentaxbackup.github.io/file/19017_valhalla.jpg)
## Post #53
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2020-11-17T22:18:28+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

released 0.1b: [https://mega.nz/file/VGoVBKKA#MM44q_Agr ... 8aKnlWqoDA](https://mega.nz/file/VGoVBKKA#MM44q_Agrgta3cc7eloyoitpnyjsuSFcl8aKnlWqoDA)
Add preliminary Valhalla an fbx exporter.
## Post #54
- Username: bellyache
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 09, 2011 4:43 am
- Post datetime: 2020-11-25T10:39:40+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

This is nice! Keep up the great work.
## Post #55
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2020-11-27T00:57:17+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

The program closes a second after I run it. What am I doing wrong? I run the program from the same directory where the game files are located.
## Post #56
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2020-11-27T09:20:00+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

> Reply from Lord Vaako ↑Fri Nov 27, 2020 8:57 am at Fri Nov 27, 2020 8:57 am
>
> 
The program closes a second after I run it. What am I doing wrong? I run the program from the same directory where the game files are located.

You need oo2core_7_win64.dll in the same folder
## Post #57
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2020-11-27T09:42:13+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

> Reply from fil1969 ↑Fri Nov 27, 2020 5:20 pm at Fri Nov 27, 2020 5:20 pm
>
> 
You need oo2core_7_win64.dll in the same folder

thank you
## Post #58
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2020-11-27T09:47:17+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

any idea how they could extract / create such maps (backgrounds)? 

[https://www.ign.com/maps/assassins-cree ... lla/asgard](https://www.ign.com/maps/assassins-creed-valhalla/asgard)
[https://www.ign.com/maps/assassins-cree ... la/england](https://www.ign.com/maps/assassins-creed-valhalla/england)
etc.
## Post #59
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-11-27T15:39:48+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

> Reply from Lord Vaako ↑Fri Nov 27, 2020 5:47 pm at Fri Nov 27, 2020 5:47 pm
>
> 
any idea how they could extract / create such maps (backgrounds)?
Those seem 2D renders of actual map from high above, then added in Photoshop rest of details you see there.
## Post #60
- Username: Farrarie
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Mar 19, 2017 6:00 pm
- Post datetime: 2021-01-24T23:38:23+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

can someone plz share the discord link ?
## Post #61
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2021-01-25T06:42:12+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

> Reply from Farrarie ↑Mon Jan 25, 2021 7:38 am at Mon Jan 25, 2021 7:38 am
>
> 
can someone plz share the discord link ?

read first post
## Post #62
- Username: Tholwin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 06, 2021 7:02 pm
- Post datetime: 2021-05-06T11:13:51+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

> Reply from fil1969 ↑Fri Nov 27, 2020 5:20 pm at Fri Nov 27, 2020 5:20 pm
>
> 
Lord Vaako wrote: ↑Fri Nov 27, 2020 8:57 am
The program closes a second after I run it. What am I doing wrong? I run the program from the same directory where the game files are located.


You need oo2core_7_win64.dll in the same folder

Hello,
I have a similar issue. The program crashes when I start it. (Version 0.1b)
ACViewer.exe, ACValhalla.exe and oo2core_7_win64.dll are all in "C:\Program Files (x86)\Ubisoft\Ubisoft Game Launcher\games\Assassin's Creed Valhalla\"

I get the following in the Event Viewer :

```
Faulting module name: ntdll.dll, version: 10.0.19041.928, time stamp: 0x9bed63d6
Exception code: 0xc00000fd
Fault offset: 0x0000000000032223
Faulting process id: 0x22c4
Faulting application start time: 0x01d742650c4b1a11
Faulting application path: C:\Program Files (x86)\Ubisoft\Ubisoft Game Launcher\games\Assassin's Creed Valhalla\ACViewer.exe
Faulting module path: C:\Windows\SYSTEM32\ntdll.dll
Report Id: 7cabb504-3e3b-4aa2-bf27-31bbcf743fa1
Faulting package full name: 
Faulting package-relative application ID: 
```


Any idea how to fix this?

(I had the reckless idea to replace "ntdll.dll" with an older version and my PC wouldn't start anymore. With luck, I managed to restore the original DLL.)

I also tried versions 0.1a and 0.1. They also crash, but with a different Exception and offset. (Exception code: 0xc0000005  Fault offset: 0x0000000000051d1e)
## Post #63
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2021-10-24T23:33:35+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

> Reply from Tholwin ↑Thu May 06, 2021 7:13 pm at Thu May 06, 2021 7:13 pm
>
> 
fil1969 wrote: ↑Fri Nov 27, 2020 5:20 pm
Lord Vaako wrote: ↑Fri Nov 27, 2020 8:57 am
The program closes a second after I run it. What am I doing wrong? I run the program from the same directory where the game files are located.


You need oo2core_7_win64.dll in the same folder


Hello,
I have a similar issue. The program crashes when I start it. (Version 0.1b)
ACViewer.exe, ACValhalla.exe and oo2core_7_win64.dll are all in "C:\Program Files (x86)\Ubisoft\Ubisoft Game Launcher\games\Assassin's Creed Valhalla\"

I get the following in the Event Viewer :
Code: Select allFaulting application name: ACViewer.exe, version: 0.0.0.0, time stamp: 0x5fb43464
Faulting module name: ntdll.dll, version: 10.0.19041.928, time stamp: 0x9bed63d6
Exception code: 0xc00000fd
Fault offset: 0x0000000000032223
Faulting process id: 0x22c4
Faulting application start time: 0x01d742650c4b1a11
Faulting application path: C:\Program Files (x86)\Ubisoft\Ubisoft Game Launcher\games\Assassin's Creed Valhalla\ACViewer.exe
Faulting module path: C:\Windows\SYSTEM32\ntdll.dll
Report Id: 7cabb504-3e3b-4aa2-bf27-31bbcf743fa1
Faulting package full name: 
Faulting package-relative application ID: 

Any idea how to fix this?

(I had the reckless idea to replace "ntdll.dll" with an older version and my PC wouldn't start anymore. With luck, I managed to restore the original DLL.)

I also tried versions 0.1a and 0.1. They also crash, but with a different Exception and offset. (Exception code: 0xc0000005  Fault offset: 0x0000000000051d1e)

did you manage to solve an issue? i am having the same trouble..
## Post #64
- Username: urao
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 29, 2016 9:14 pm
- Post datetime: 2022-01-19T08:09:43+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

Thank you very much for your work.
 Is there an update for Valhalla? 
I'm trying Valhalla, but it doesn't load the  map correctly, and the few models I can see are in LOD2, am I doing something wrong?
thanks regards
## Post #65
- Username: Tholwin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 06, 2021 7:02 pm
- Post datetime: 2022-02-15T09:44:10+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

> Reply from probe88 ↑Mon Oct 25, 2021 7:33 am at Mon Oct 25, 2021 7:33 am
>
> 
Tholwin wrote: ↑Thu May 06, 2021 7:13 pm
fil1969 wrote: ↑Fri Nov 27, 2020 5:20 pm


You need oo2core_7_win64.dll in the same folder


Hello,
I have a similar issue. The program crashes when I start it. (Version 0.1b)
ACViewer.exe, ACValhalla.exe and oo2core_7_win64.dll are all in "C:\Program Files (x86)\Ubisoft\Ubisoft Game Launcher\games\Assassin's Creed Valhalla\"

I get the following in the Event Viewer :
Code: Select allFaulting application name: ACViewer.exe, version: 0.0.0.0, time stamp: 0x5fb43464
Faulting module name: ntdll.dll, version: 10.0.19041.928, time stamp: 0x9bed63d6
Exception code: 0xc00000fd
Fault offset: 0x0000000000032223
Faulting process id: 0x22c4
Faulting application start time: 0x01d742650c4b1a11
Faulting application path: C:\Program Files (x86)\Ubisoft\Ubisoft Game Launcher\games\Assassin's Creed Valhalla\ACViewer.exe
Faulting module path: C:\Windows\SYSTEM32\ntdll.dll
Report Id: 7cabb504-3e3b-4aa2-bf27-31bbcf743fa1
Faulting package full name: 
Faulting package-relative application ID: 

Any idea how to fix this?

(I had the reckless idea to replace "ntdll.dll" with an older version and my PC wouldn't start anymore. With luck, I managed to restore the original DLL.)

I also tried versions 0.1a and 0.1. They also crash, but with a different Exception and offset. (Exception code: 0xc0000005  Fault offset: 0x0000000000051d1e)


did you manage to solve an issue? i am having the same trouble..

Yes, I solved the issue by downloading the latest version from the Discord server. (link inside the first post of this thread)
Sorry for the ultra late reply.
## Post #66
- Username: ElHabto
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 30, 2022 5:43 am
- Post datetime: 2023-01-01T11:46:54+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

> Reply from forgeMaster ↑Tue Oct 20, 2020 5:20 am at Tue Oct 20, 2020 5:20 am
>
> 
This is a little thing I started working on years ago, around the time of AC2 Revelations and AC3. Over the years I added support for more recent games, sometimes breaking older games in the process.
I the last couple years I went back this project, with the idea of a more general release. Things are not as good as I wanted them to be, but it's good enough for a first release.

Supports all main AC games from the original to Odyssey, with the exception of 3HD and Liberation HD (mostly because I didn't look into them yet). PC only version (although some xbox360 work was done, but the mesh will not load properly yet).
Most maps should load, with the caveat that Origins and Odyssey are very taxing to load/display, and will be missing the ground. Of course, not everything will work properly, the lighting is broken, and a lot of materials are slightly wrong/missing. This is a work in progress.

I've removed a few broken/incomplete features to not confuse people, so this should be a considered a preview version of what the tool can do. Some features that were removed for now is the ability to look at characters (was functional in AC3, but got broken since), animations (also worked on AC3), data properties, stuff like gameplay entities,...

Conversion on discord:
https://discord.gg/ JeTKGKVSf7
(You need to remove the space in the url)

Current
0.1b: https://mega.nz/file/VGoVBKKA#MM44q_Agr ... 8aKnlWqoDA
Add preliminary Valhalla an fbx exporter.

Older versions:
0.1a: https://mega.nz/file/VKZHQaYb#OM7MDzVnX ... s1eh0RmSS4
0.1: https://mega.nz/file/FaBEmZoT#pS-fkq58- ... ISHFd-uL7s

Just put the ACViewer.exe in the game folder and launch it from there.

I placed the exe in the Unity files, opened it and nothing happened. Am I doing it right?
## Post #67
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-01-01T16:09:48+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

> Reply from ElHabto ↑Sun Jan 01, 2023 7:46 pm at Sun Jan 01, 2023 7:46 pm
>
> I placed the exe in the Unity files, opened it and nothing happened. Am I doing it right?
Yeah, your using the old version, join discord to use latest build and its updates.
## Post #68
- Username: lzanlorenzi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 09, 2023 7:09 am
- Post datetime: 2023-01-08T23:22:02+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

hello guys! Can i use the ACViewer to extract AC: Origins models? Like pyramids, etc? the app close when i start it.
Thanks
## Post #69
- Username: ElHabto
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 30, 2022 5:43 am
- Post datetime: 2023-01-10T04:11:58+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

How do I go about navigating the viewport? The WASD keys are fairly slow, and they don't exactly facilitate exporting
## Post #70
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2023-05-17T21:22:15+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

Will update the opening post, but you can now go to [https://github.com/forge-master/ACViewer/wiki](https://github.com/forge-master/ACViewer/wiki) for updates and link to the discord for support
## Post #71
- Username: pepapoha
- Rank: n00b
- Number of posts: 16
- Joined date: Wed May 20, 2020 9:49 pm
- Post datetime: 2023-06-01T01:36:42+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

Hey guys this is tool dont support assasins creed origin models ?
## Post #72
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2023-10-20T05:26:40+00:00
- Post Title: Re: ACViewer: Assassin's Creed games viewer

> Reply from forgeMaster ↑Thu May 18, 2023 5:22 am at Thu May 18, 2023 5:22 am
>
> 
Will update the opening post, but you can now go to https://github.com/forge-master/ACViewer/wiki for updates and link to the discord for support

Any plans to do repack ?
