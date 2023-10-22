## Post #1
- Username: Kung Fu Man
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Jul 14, 2011 1:34 pm
- Post datetime: 2012-03-31T06:50:43+00:00
- Post Title: Console-based HKX vs PC

To be direct, has any work been done with console-based havok-engine HKX files vs. their PC counterparts? Reason I ask is I've gone round robin with hkxcmd at this point, only to find it doesn't support these files due to being based off the PC components of the SDK. Looking over the files I have in front of me, it looks like both the PS3 and 360 use big endian with a switch at 0x11 to determine which it is (1 = little, 0 = big).

I'm guessing given this is a widely-used format that doesn't change consistency too much someone else must have done research on the files. There are a few Sonic modding groups online that have dipped into the subject, but all they ascertain is that it "can't be done without the 360 SDK", which seems doubtable. One idea seems to be if you compare the compression done between a PC little-endian file and its 360 counterpart, you should be able to reverse-engineer it, no?
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-03-31T11:14:35+00:00
- Post Title: Console-based HKX vs PC

I have had some .hkx files for some time, can anyone tell me what tools can do atleast something to this file? I'd like to convert Xbox ones to PC is it possible? They just look the opposite endian that's all.

```
WààW.ÀÀ.............................Ý...Havok-5.5.0-r1.ÿÿÿÿÿÿÿÿÿ__classnames__.....ÿÐ...Ð...Ð...Ð...Ð...Ð...Ð...__types__..........ÿ ...........................__data__...........ÿ ...0}..€}..à}..@~..@~..@~..Ž.w8.hkClass.W.$¥.hkClassMember.Ï.6Š.hkClassEnum.lŠoÎ.hkClassEnumItem..Þ.ª.hkpPhantom..‹”J.hkAabb.Ád#ë.hkpEntitySmallArraySerializeOverrideType.äa¤Â.hkpPhysicsData.´ö...hkWorldMemoryAvailableWatchDog.ïðX..hkpPhysicsSystem.pWN..hkSweptTransform..Špà.hkpShapeContainer.Ã¢yX.hkpCollidable.Üi.”.hkpBroadPhaseHandle.7…yú.hkpEntity.e2.›.hkpShapeCollection.d¢…..hkpMaterial.º×@..hkpSimpleMeshShape.¿-.
```
## Post #3
- Username: Kung Fu Man
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Jul 14, 2011 1:34 pm
- Post datetime: 2012-04-01T21:35:34+00:00
- Post Title: Console-based HKX vs PC

Well doing some research and comparing I've figured out some of the following for the header:
0x00-07: Eight bytes, always the same for any of these files (57 E0 E0 57 10 C0 C0 10)
0x08-0B: "User settable tags". Unknown purpose at this time, always 00 00 00 00 in the files checked
0x0C-0F: Binary file version.
0x10-13: Layout rules for the file
*0x10: Always seems to be 04 regardless of file checked
*0x11: Flag, determines endianness (1 = little, 0 = big)
*0x12: Flag, set to 1 if on PS3, 0 for Xbox or PC.*
*0x13: Always 1?
0x14-17: Number of Packfile sections following this header
0x18-1B: Section index
0x1C-1F: Section offset
0x20-23: Classnames Section
0x24-27: Classfiles offset

Currently only have a limited number of havok files to check through for any format, so I'll post more after I dig through a few more games in my library.

*This does nothing as far as Splatterhouse goes apparently. Both the PS3 and Xbox games are the same with the exception of this one byte.
## Post #4
- Username: Kung Fu Man
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Jul 14, 2011 1:34 pm
- Post datetime: 2012-04-05T10:24:21+00:00
- Post Title: Console-based HKX vs PC

Well made some headway here, and quite possibly talking to myself but could use a hand with some raw files to look through. A good chunk of the bytes swapped are straightforward enough and just integers, which makes converting not as painful and thus far I've managed to swap over collision-only files easily.

Skeletons are proving a bit more of a hassle though, due to the fact they implement shorts that need to be mirrored inside the file. If anyone happens to have a PC game using Havok installed and preferably using version 5.5.0 (though really any version will work, opening the file in a hex editor will show this info in the header), I could use some hkx skeleton files for test samples. The SDK's own outputs tend to be bloated, making that route that much harder...
## Post #5
- Username: Kung Fu Man
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Jul 14, 2011 1:34 pm
- Post datetime: 2012-04-07T02:16:27+00:00
- Post Title: Console-based HKX vs PC

Skeletons are still a pain in the butt, but even complex collision files are not a problem any longer...still need files to research the other parts though.

Trying BioShock to see if I can use resources from it for study.
## Post #6
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2012-04-07T05:44:32+00:00
- Post Title: Console-based HKX vs PC

This is very interesting since I wanted something like this to happen for a while now. Nice to see something like this to come to fruition. You plan to release it when you are done? Since the Sonic Community who are porting would like to make good usage of it for porting.
## Post #7
- Username: Kung Fu Man
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Jul 14, 2011 1:34 pm
- Post datetime: 2012-04-07T07:04:12+00:00
- Post Title: Console-based HKX vs PC

Just to clarify...that's Havok's own tool, Standalone Filter Manager. The collision's easy enough to open in a hex editor like 010 and just tear through it with the integer swap function. As long as the version of havok used to make the file is the same as the version of SFM, it'll open a little endian HKX just fine after you're done modifying.

Kicker is the same issue comes up for more heavily complex collision files compared to complex *shapes*. Some functions only use shorts rather than ints such as the aforementioned skeleton data or say Sonic Unleashed collision files. While a lot of the data can just be simply reversed and then you get the results, without knowing for sure how the endianness affects functions of those kinds you end up with a broken file instead.

In a nutshell, simple files are easy to tackle at least but it still has a long way to go.
## Post #8
- Username: Kung Fu Man
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Jul 14, 2011 1:34 pm
- Post datetime: 2012-04-09T02:51:18+00:00
- Post Title: Console-based HKX vs PC

I am officially the only person that got Skyrim just to research how its files worked. And yeah that's Dr. West's skeleton from Splatterhouse for those curious.
## Post #9
- Username: xpliskin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 11, 2009 8:29 pm
- Post datetime: 2012-04-29T17:26:36+00:00
- Post Title: Console-based HKX vs PC

Do you swap the data by hand (for small files) or have you written anything that does it automatically ?
Like, how did you get the collision model to actually load on the PC platform tools ?
## Post #10
- Username: Dario ff
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 01, 2012 6:48 am
- Post datetime: 2012-04-30T23:03:00+00:00
- Post Title: Console-based HKX vs PC

I gave this a try myself. I went for the approach of reading the types section of the HKX, and the assumption that the data is identical to what it would be on PC with different endianness.

The file gives enough of a description of every single structure in the file and the linking to parent structures and such. Or to what structure each type member referenced. In short, I had to do some assumptions on some data blocks at how it was supposed to be swapped since there isn't much documentation for it from the Havok SDK.

hkxconverter source.hkx out.hkx
Or just drag and drop a 360 HKX to the exe and it'll work.
[Editted link out because I want to keep the tool private until my Mod's release, sorry]

Example, Sonic's Unleashed drift animation previewed in Havok after a successful conversion:
[http://www.youtube.com/watch?v=cuPFw4yUqJE](http://www.youtube.com/watch?v=cuPFw4yUqJE)
## Post #11
- Username: xpliskin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 11, 2009 8:29 pm
- Post datetime: 2012-05-01T00:59:35+00:00
- Post Title: Console-based HKX vs PC

Ah, seems there's some progress for the X360 files.

The bad thing about HKX files  is that they're just serialized havok scene data, which means they can store a lot of different things.

I'm focusing more on the WII/GC platform. Some game engines divide their data, for example Darkside Chronicles hkx files contain only references and pointer patches while the actual data is stored in another file entirely.
The odd thing is that there's no way the PC tools will read it, you'd have to patch the pointers up yourself and merge to the two files, which is a super cumbersome approach. Anyway, I got it figured out, here's a top view of the Darkside Chronicles RPD front hall havok collision file:


I'd release a tool but it'd be useless since I can only count a few games who uses this approach.
For anyone out there who wants to progress further I think the best way is to learn the layout of the different "classnames" sections, they're always the same regardless of platform.
What you could do is use the PC tools to write to the target format you want to reverse engineer and map out how each classname type is laid out in the file, then write a converter that parses each section and swaps the relevant bytes. That's what I did.
## Post #12
- Username: BrucieK
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 25, 2012 3:10 am
- Post datetime: 2012-06-25T14:14:07+00:00
- Post Title: Console-based HKX vs PC

> Reply from Dario ff
>
> I gave this a try myself. I went for the approach of reading the types section of the HKX, and the assumption that the data is identical to what it would be on PC with different endianness.

The file gives enough of a description of every single structure in the file and the linking to parent structures and such. Or to what structure each type member referenced. In short, I had to do some assumptions on some data blocks at how it was supposed to be swapped since there isn't much documentation for it from the Havok SDK.

hkxconverter source.hkx out.hkx
Or just drag and drop a 360 HKX to the exe and it'll work.
Download: http://filebeam.com/14f99127c5f7252d19c7cc3c665d5f12

Example, Sonic's Unleashed drift animation previewed in Havok after a successful conversion:
http://www.youtube.com/watch?v=cuPFw4yUqJE

Can you reupload hkxconverter?

Can textures be stored in havok file?
## Post #13
- Username: Kung Fu Man
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Jul 14, 2011 1:34 pm
- Post datetime: 2013-01-16T22:56:22+00:00
- Post Title: Console-based HKX vs PC

Textures tend to be stored in the model files themselves, like nifs and whatnot. Havok works more for collision, bones and animation.

With that said if anyone has the above tool I'm also interested in it, if only to see if it can do the trick here for Splatterhouse. Sorry for the bump, but I'm presuming someone got it before it went down...and manually editing these is a trial and error way of doing it.
