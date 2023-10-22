## Post #1
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2020-05-27T22:31:36+00:00
- Post Title: [PS2] 007 Nightfire .crp files

Hey all,

I've been working on having a look through the files of 007 Nightfire model files lately and I've come across a stumbling block that I need more help with.

I have the files extracted and there is some patterns I am seeing but I am struggling to figure how to parse the data out.

The file magic is PRAC along side that in the header is the following data:

PRAC (CARP) 90 4 1
itrA (Arti) 26 12 6
rahS (Shar) 26 0 17
dFLE (ELFd) 2101274 0 976
rFLE (ELFr) 401602 0 9664
tceS (Sect) 32962 0 11216
  ns (sn  ) 3323 0 11680
esaB (Base) 24586 0 400
emaN (Name) 2082 0 9344

The first string (PRAC) is the way the data shows in the file, the second in brackets is my inversion of the string (after Edness on the discord pointed out the emaN was just Name backwards, not my proudest moment).

The other values I have just pulled out as UInt32s but this is possibly (likely) wrong...

There is ELF data in the file (starting at 0x400, which can be found via the ELFd part of the header) and after that, lots of instances and small variations on this: __GPRenderMethod_bazooka::{as  0000}::Model[0].00_0_name (usually the zero between the two _'s is increasing).

Further down the file are references to image files (.ssh) and some EAGL microcode bits.

If anyone has info on how I can actually parse this file it would be a life saver as I've tried loads and loads of things and I'm kinda at a loss now...

File link in case you wanna have a play / gander at it.

[.crp file](https://cdn.discordapp.com/attachments/493152982293282816/715158439600455710/bazooka.crp)

Thank you and have a brilliant day!

~ r
## Post #2
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-05-28T13:32:11+00:00
- Post Title: [PS2] 007 Nightfire .crp files

It's about time someone looked into the old EA games formats honestly. I've been trying myself to rip models from Nightfire and Agent Under Fire console as well, seriously hope someone can finally figure out a way to do so after all these years. I got close with someone helping me unpack some .dat files from Agent Under Fire but I didn't know where to go from there.
## Post #3
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2020-05-28T16:38:54+00:00
- Post Title: [PS2] 007 Nightfire .crp files

Hell yes! How far did you get and with what tools ? I've been stuck on those .dat files too. I'm also in the progress of trying to crack the .BIN file I have in the root of the ISO... It's odd cause it's not structured like a normal file with a typical header.

If you are on the Discord, drop me a message, would be good to try work through some of these files, see if we can figure something out!
## Post #4
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-05-28T17:05:50+00:00
- Post Title: [PS2] 007 Nightfire .crp files

> Reply from hidinginthevoid ↑Fri May 29, 2020 12:38 am at Fri May 29, 2020 12:38 am
>
> 
Hell yes! How far did you get and with what tools ? I've been stuck on those .dat files too. I'm also in the progress of trying to crack the .BIN file I have in the root of the ISO... It's odd cause it's not structured like a normal file with a typical header.

If you are on the Discord, drop me a message, would be good to try work through some of these files, see if we can figure something out!

Lol sorry, I just saw this message in regards to your PM. At this time I don't have Nightfire's iso downloaded on my pc but I didn't look much into it, just some stuff from Agent Under Fire that's it. I tried to rip models using Ninja Ripper but it didn't work out well and looked bad. I have little experience with hex editing for this stuff too
## Post #5
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2020-05-29T01:48:58+00:00
- Post Title: [PS2] 007 Nightfire .crp files

Great to see more interest about this game, i did a bunch of attempts to extract the data ( especially models/anims ), i mainly worked with the gamecube build because it has all assets split per level which gives you various chunks that are easier to navigate.

One of the hardest things to figure out was the initial file compression, (this is all based on gamecube version ) the archives/chunks were compressed with EDL, Eurocom used this in other titles too.


A sample compressed/decompressed plus the EDL tool, incase you want to check:

[https://mega.nz/file/iFg0FY7Z#WQQubp11H ... ouMPkjiQXk](https://mega.nz/file/iFg0FY7Z#WQQubp11HG7V-9GYKzcdAC9RW6Nw1DBFIouMPkjiQXk)

Another thing i can recommend is getting the following game on steam:

[https://store.steampowered.com/app/6067 ... sed_Mummy/](https://store.steampowered.com/app/606710/Sphinx_and_the_Cursed_Mummy/)

It ships with the engine tools/data that was also used for Nightfire in some variant before.

Really hoping to see support for Meshes/anims, i did not have much time to actually decipher the formats after initial decompression, but would be great to chime in so feel free to pm regarding discord.
## Post #6
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2020-05-29T10:21:13+00:00
- Post Title: [PS2] 007 Nightfire .crp files

Woo, glad to hear I am not alone in trying to get these files out.

Worked with DKDave on the Discord last night to extract stuff from the .bin file successfully (though formats are the next challenge), will try see if I can get the decompression working on the files.

I will pick up that game and try use any of the tools I find to extract stuff, thank you!

I actually have a massive markdown file I'm updating with every new discovery, so when I end up cracking most the file formats etc I will be writing it all up  (And crediting anyone who helped me, it's a big team effort now!)
## Post #7
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2020-05-29T11:51:28+00:00
- Post Title: [PS2] 007 Nightfire .crp files

This is all great stuff! if you guys' do come across getting the models out n such, should post em here too for other people to download em! i'd love to have all the agent under fire NPC models too, those were great
## Post #8
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-05-30T01:53:41+00:00
- Post Title: [PS2] 007 Nightfire .crp files

> Reply from Reddance ↑Fri May 29, 2020 7:51 pm at Fri May 29, 2020 7:51 pm
>
> 
This is all great stuff! if you guys' do come across getting the models out n such, should post em here too for other people to download em! i'd love to have all the agent under fire NPC models too, those were great

Agreed, been trying to crack this format and get the models myself for years lol. The only one I got through was Everything or Nothing for the gamecube, with Ninja Ripper I could get an A pose for the meshes but Nightfire and AuF, even Goldeneye Rogue Agent don't do that, no clue why.
## Post #9
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2020-05-30T10:02:42+00:00
- Post Title: [PS2] 007 Nightfire .crp files

> Agreed, been trying to crack this format and get the models myself for years lol. The only one I got through was Everything or Nothing for the gamecube, with Ninja Ripper I could get an A pose for the meshes but Nightfire and AuF, even Goldeneye Rogue Agent don't do that, no clue why.

damn! Lol yeah!! it'd be awesome to get those models from agent under fire cause alota them had some great detail, not to mention the 1990s / early to mid 2000s vibe they gave off aswell, i'd just love to use em for stuff, if you guy's do come across some kinda work around for em, please, share it! and post any models / animations you might get from it on this thread too!! ;D
## Post #10
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2020-06-08T19:04:27+00:00
- Post Title: [PS2] 007 Nightfire .crp files

any progress fam?
## Post #11
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2020-06-11T18:27:21+00:00
- Post Title: [PS2] 007 Nightfire .crp files

Some, we have been able to crack the BIN file a bit more and are currently working on a suite of tools to be able to parse the geometry, models, textures etc from files found within the FILES.BIN file...

Annoyingly they are rather complex and trying to actually parse them / understand them is complex as hell.

Will try update here as and when we can, but it could be a while!

If you are able to help out, drop me a message!
## Post #12
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-06-11T19:48:52+00:00
- Post Title: [PS2] 007 Nightfire .crp files

I don't know if you've managed to get a look at any of the models but I hear that the console models are higher quality than the crap pc version. Is that true?
## Post #13
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2020-06-11T20:15:07+00:00
- Post Title: [PS2] 007 Nightfire .crp files

No clue at the moment, I'd imagine so cause the PC version made their own models from what I know.

It's going to possibly a while until we get any models cause trying to understand how they attempt to load the model data or even finding patterns in the Hex editors is proving to be a giant pain, until we really know how these files with no extensions are formatted, models are but a distant hope!
## Post #14
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2020-06-12T06:32:21+00:00
- Post Title: [PS2] 007 Nightfire .crp files

> Reply from hidinginthevoid ↑Fri Jun 12, 2020 2:27 am at Fri Jun 12, 2020 2:27 am
>
> 
Some, we have been able to crack the BIN file a bit more and are currently working on a suite of tools to be able to parse the geometry, models, textures etc from files found within the FILES.BIN file...

Annoyingly they are rather complex and trying to actually parse them / understand them is complex as hell.

Will try update here as and when we can, but it could be a while!

If you are able to help out, drop me a message!

i see! also unfortunately i'm not ENTIRELY skilled on any sort of hex editing or reverse engineering but i'll still stick around for any future progress! heheh, the 007 Agent Under Fire formats aswell, Did anyone get a chance to look at those too?
## Post #15
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-06-12T10:16:29+00:00
- Post Title: [PS2] 007 Nightfire .crp files

I don't think Agent Under Fire should be terribly hard to crack if Nightfire can be cracked. What's weird is that AuF uses a modified Quake 3 engine so you'd think it'd be easier to crack that but no one has yet for whatever reason.
## Post #16
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2020-06-12T13:50:49+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

AuF might use Quake 3 but the underlying engine of 007 is something from Eurocom and is really strange...

We have vague understanding of how the model data is setup but it's getting the lengths and understanding their Hashtables really!
## Post #17
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2020-06-12T17:52:31+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

damn! well hopefully it can be figured out, I know that hex editing and reverse engineering ain't exactly a picnic Lol
## Post #18
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-06-12T23:09:17+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

> Reply from hidinginthevoid ↑Fri Jun 12, 2020 9:50 pm at Fri Jun 12, 2020 9:50 pm
>
> 
AuF might use Quake 3 but the underlying engine of 007 is something from Eurocom and is really strange...

We have vague understanding of how the model data is setup but it's getting the lengths and understanding their Hashtables really!

Yeah that is a fairpoint, like I said it's a Quake 3 engine but it's "modified" so I wasn't suggesting that quake 3 tools would automatically work on it or anything of course, but I get your point. Strangely enough the only game I've had luck ripping using Ninja ripper is Everything or Nothing, the models came out in A pose. With Nighfire, AuF and FRWL all of them rip in their pose they were captured in so I'm not entirely sure what's going on there either. Personally if I were you I'd actually try to crack Agent Under Fire and Goldeneye Rogue Agent instead of console Nightire, but that's just my personal preference. Perhaps any info coming out of this will lead to an easier foundation for the other games.
## Post #19
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2020-07-01T04:41:07+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

any progress or more attempts on the agent under fire models?
## Post #20
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2020-07-01T09:32:51+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

Not yet and we are really only focusing on the Nightfire game, not any others, sorry.

If there is no resource out there for understanding the model formatting / how to extract, could be a good chance to jump into the world of reverse engineering!
## Post #21
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2020-07-01T09:54:20+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

> Reply from hidinginthevoid ↑Wed Jul 01, 2020 5:32 pm at Wed Jul 01, 2020 5:32 pm
>
> 
Not yet and we are really only focusing on the Nightfire game, not any others, sorry.

If there is no resource out there for understanding the model formatting / how to extract, could be a good chance to jump into the world of reverse engineering!

Ahh that's okay! heheh I'll patiently see what comes up and the progress made! I'll leave all the reverse engineering to the pros n what not xP but as far as nightfire goes, any progress on THOSE models?? Is this also the PC version of nightfire? Or the Console variant?
## Post #22
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-07-01T14:11:40+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

> Reply from Reddance ↑Wed Jul 01, 2020 5:54 pm at Wed Jul 01, 2020 5:54 pm
>
> 
hidinginthevoid wrote: ↑Wed Jul 01, 2020 5:32 pm
Not yet and we are really only focusing on the Nightfire game, not any others, sorry.

If there is no resource out there for understanding the model formatting / how to extract, could be a good chance to jump into the world of reverse engineering!


Ahh that's okay! heheh I'll patiently see what comes up and the progress made! I'll leave all the reverse engineering to the pros n what not xP but as far as nightfire goes, any progress on THOSE models?? Is this also the PC version of nightfire? Or the Console variant?

PC version uses GoldSrc engine, that's easy to rip from using Dragon Unpacker and a decompiler. The console variant uses an id-tech 3 engine or something like that, so clearly that's where the trouble lies.
## Post #23
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2020-07-01T20:50:40+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

> Reply from Assasinge ↑Wed Jul 01, 2020 10:11 pm at Wed Jul 01, 2020 10:11 pm
>
> 
PC version uses GoldSrc engine, that's easy to rip from using Dragon Unpacker and a decompiler. The console variant uses an id-tech 3 engine or something like that, so clearly that's where the trouble lies.

Console version does not use id-tech 3, this is an old misconception, I remember for a while that was the leading idea, but the console version uses an engine called EngineX created by Eurocom, the driving parts of the game use EAGL (EA Game Library) code.

We could rip the PC version but... we don't talk about the PC version... It was made by Gearbox (yes, using GoldSrc) but uses different everything, for some reason Gearbox didn't use Eurocoms assets, so it's not something that we really are interested in ripping and reverse engineering.
## Post #24
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2020-07-01T20:54:10+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

> Reply from Reddance ↑Wed Jul 01, 2020 5:54 pm at Wed Jul 01, 2020 5:54 pm
>
> 
Ahh that's okay! heheh I'll patiently see what comes up and the progress made! I'll leave all the reverse engineering to the pros n what not xP but as far as nightfire goes, any progress on THOSE models?? Is this also the PC version of nightfire? Or the Console variant?

As far as Nightfire goes, we have a small team slowly working on things as free time / health etc permits.

We are down inside the FILES.BIN file and have found the raw data behind the models / textures / maps... But reading them is proving to be something of a challenge, hoping with some more digging and processing that we will be able to fully understand the data.
## Post #25
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2020-07-02T16:27:02+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

> Reply from hidinginthevoid ↑Thu Jul 02, 2020 4:54 am at Thu Jul 02, 2020 4:54 am
>
> 
Reddance wrote: ↑Wed Jul 01, 2020 5:54 pm
Ahh that's okay! heheh I'll patiently see what comes up and the progress made! I'll leave all the reverse engineering to the pros n what not xP but as far as nightfire goes, any progress on THOSE models?? Is this also the PC version of nightfire? Or the Console variant?


As far as Nightfire goes, we have a small team slowly working on things as free time / health etc permits.

We are down inside the FILES.BIN file and have found the raw data behind the models / textures / maps... But reading them is proving to be something of a challenge, hoping with some more digging and processing that we will be able to fully understand the data.

that sounds awesome! if you guy's do come across cracking the procedures n stuff i'd love to see some pictures of how everything turns out x)
## Post #26
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2020-07-15T19:45:33+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

The Nightfire Research Team have been hard at work these last few weeks, we have cracked a lot more of the formats and keeping on with the processing of them.

We are currently in the process of writing a custom tool to grab everything nice and easily, we have some bits like images, sounds, some text files and a few other bits semi-understood but there is still a lot of work to go!
## Post #27
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2020-07-17T06:58:50+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

> Reply from hidinginthevoid ↑Thu Jul 16, 2020 3:45 am at Thu Jul 16, 2020 3:45 am
>
> 
The Nightfire Research Team have been hard at work these last few weeks, we have cracked a lot more of the formats and keeping on with the processing of them.

We are currently in the process of writing a custom tool to grab everything nice and easily, we have some bits like images, sounds, some text files and a few other bits semi-understood but there is still a lot of work to go!

Sounds awesome, I'd love to also have the sounds from that game aswell! x) keep it up!!
## Post #28
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2020-08-04T23:20:46+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

how's it all going!
## Post #29
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-11-02T20:32:52+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

Whatever happened to this thread?
## Post #30
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2020-11-21T16:28:25+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

Hey!

The team and I are slowly working on things, sadly real life stuff has been going on so less time has been dedicated to the work we are trying to do.

Hopefully with the winter break coming up a little more work can be done, but it's deffo not been an easy task in general parsing files and trying to get everything up and running!

When we have an update on either our tooling or similar, we will make sure to post an update, but for now it's just a lot of development and trying to understand file formats.
## Post #31
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-01-17T17:51:27+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

Any update?
## Post #32
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2022-02-18T23:18:56+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

Yes!

Still going, have written a lot of code to get this all up and running and have to do all the file research.

It's basically down to me and another dev who have free time to work on this. But even that is highly limited so we do what we can, when we can.

We have managed to get loaders and extractors running for all three platforms and currently working on deeper handling of all the files
## Post #33
- Username: callmeliam
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 14, 2022 10:01 pm
- Post datetime: 2022-03-14T14:04:07+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

Hi, My name is Liam, I am a speedrunner of 007 Nightfire and I have been attempting to crack this game open for many years, good to see progress on this thing. I would reccomend you guys join the nightfire speedrunning discord. I can provide a link via a dm if necessary as we have another coder/person trying to decompile this stuff too.

Thanks
## Post #34
- Username: Galap
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 03, 2022 2:12 pm
- Post datetime: 2022-04-03T06:25:49+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

I too am interested in getting these models out, and am glad to see that others are trying to do this as well.

It looks like someone was able to get models and textures out of the GCN version. They only posted a couple of them, though.

[https://www.models-resource.com/gamecub ... nightfire/](https://www.models-resource.com/gamecube/jamesbond007nightfire/)

Unfortunately, it doesn't seem like there's any way to contact him there and ask him about his methods.
## Post #35
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2022-04-03T13:42:40+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

> Reply from Galap ↑Sun Apr 03, 2022 2:25 pm at Sun Apr 03, 2022 2:25 pm
>
> Unfortunately, it doesn't seem like there's any way to contact him there and ask him about his methods.It's nothing special, looks like it was just NinjaRipper that was used.
## Post #36
- Username: GeekOutGamer
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 04, 2022 12:56 am
- Post datetime: 2022-05-03T16:58:25+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

Hey,

Just joined this board as I'm looking to rip the game. Any chance you'd like some help with your project? I have lots of coding experience and some reverse engineering experience.
## Post #37
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-07-10T12:33:17+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

Has there been any update/progress on this?
## Post #38
- Username: GeekOutGamer
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 04, 2022 12:56 am
- Post datetime: 2022-07-14T10:27:44+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

I didn't really get a response if they wanted some help so I doubt it.
## Post #39
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-08-18T15:45:09+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

Damn that's such a shame. The old EA games always seem to get the shaft when it comes to research
## Post #40
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-18T17:57:01+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

Concerning results this thread purely leads to nothing.  

Only interesting thing I found is this:

> Reply from Highflex ↑Fri May 29, 2020 9:48 am at Fri May 29, 2020 9:48 am
>
> Another thing i can recommend is getting the following game on steam:

https://store.steampowered.com/app/6067 ... sed_Mummy/

It ships with the engine tools/data that was also used for Nightfire in some variant before.Comes with a funny map editor, indeed. But it seems you can't save single meshes - complete maps only.

(Guess no one has a backup of the EDL tool? Mega-link in above mentioned post is dead.)
## Post #41
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-08-19T17:32:59+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

> Reply from Highflex ↑Fri May 29, 2020 9:48 am at Fri May 29, 2020 9:48 am
>
> 
Another thing i can recommend is getting the following game on steam:

https://store.steampowered.com/app/6067 ... sed_Mummy/

It ships with the engine tools/data that was also used for Nightfire in some variant before.

Really hoping to see support for Meshes/anims, i did not have much time to actually decipher the formats after initial decompression, but would be great to chime in so feel free to pm regarding discord.

I'm assuming the authoring tools included in that game, do they work with the gamecube version of Nightfire by any chance? Can anyone who owns the game or the authoring tools try fiddling with it and see what results you get with Nightfire's files? Pretty interesting stuff.
## Post #42
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2022-09-04T21:28:42+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

Hello!

Yes there is still progress on this, time for me is limited because of work! But I am working on this on a fairly regular basis.

There is a hell of a lot of work to do and I've been slowly chipping away at things.

Consdiering we are having to build an entire framework for the project that can support the multitude of ISOs we've had access to, each with their own complications, including but not limited to file compression, image data header changes and a number of other things.

Whilst EDL is something we hope to get working with the Nightfire files, there is no (known) direct way to translate what is in the Nightfire files back into EDL files, as the version that was used for the project has been long since lost to time. We might have to convert whatever we found within the files into a new instance and formatting.

We do have access to a version of the EuroLand Editor (this is included with the Sphinx and the Cursed Mummy Authoring files that can be found via Steam) but again, this isn't the version used for Nightfire.
## Post #43
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2022-09-04T21:33:31+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

> Reply from AxelNoir ↑Sat Aug 20, 2022 1:32 am at Sat Aug 20, 2022 1:32 am
>
> 
Highflex wrote: ↑Fri May 29, 2020 9:48 am
Another thing i can recommend is getting the following game on steam:

https://store.steampowered.com/app/6067 ... sed_Mummy/

It ships with the engine tools/data that was also used for Nightfire in some variant before.

Really hoping to see support for Meshes/anims, i did not have much time to actually decipher the formats after initial decompression, but would be great to chime in so feel free to pm regarding discord.


I'm assuming the authoring tools included in that game, do they work with the gamecube version of Nightfire by any chance? Can anyone who owns the game or the authoring tools try fiddling with it and see what results you get with Nightfire's files? Pretty interesting stuff.

Having a look at the files, I can confirm this wouldn't work.

Unlike later Eurocom games, the levels are compiled into .bin files, with a custom layout.

I've done some private write-ups for my own tracking, but it's a true challenge as every file requires a lot of care and attention for it to be understood and a custom parser to be written.

Then often we have to make three instances of the parser to support each platform!
## Post #44
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2022-09-04T21:37:12+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

> Reply from AxelNoir ↑Thu Aug 18, 2022 11:45 pm at Thu Aug 18, 2022 11:45 pm
>
> 
Damn that's such a shame. The old EA games always seem to get the shaft when it comes to research

The challenge actually lays on the Eurocom side! EA's stuff is pretty open already, with little work you can get things from the action side e.g. the .asf files (audio) and a lot of the data is presented in .ini files or other files that can be read by things like notepad!

However things deeper, like skeleton files and model files take a little more poking!

We also have a researcher who will write things into BMS scripts for us, which we have to convert into C# code!

This is a project I will not let die, even if I have to take breaks from it! I'm only mortal and have a full time job!
## Post #45
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2022-09-04T21:37:33+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

> Reply from GeekOutGamer ↑Thu Jul 14, 2022 6:27 pm at Thu Jul 14, 2022 6:27 pm
>
> 
I didn't really get a response if they wanted some help so I doubt it.

Sorry! I need to turn on email notifications for this thread!
## Post #46
- Username: swanbiff
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 09, 2022 1:35 am
- Post datetime: 2022-11-08T17:47:55+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

Hi, any update for the sounds part? I'm looking to extract all of the audios from the game (specifically dialogues and sound effects, rather than music and such). So far i've managed to extract all (presumably) from STREAMS.BIN and most from the DRIVING folder in English, even though around 70 audio files there are corrupted/unrecognizable for some reason sadly. But at least 132 of those work.

So which sounds can be located in FILES.BIN ? I know for sure i'm missing pain sounds and screams from NPC's and Bond anyway lol. I'd love to have everything available to upload videos of the sounds and use in other videos.
## Post #47
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2022-11-08T18:19:41+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

> Reply from swanbiff ↑Wed Nov 09, 2022 1:47 am at Wed Nov 09, 2022 1:47 am
>
> 
Hi, any update for the sounds part? I'm looking to extract all of the audios from the game (specifically dialogues and sound effects, rather than music and such). So far i've managed to extract all (presumably) from STREAMS.BIN and most from the DRIVING folder in English, even though around 70 audio files there are corrupted/unrecognizable for some reason sadly. But at least 132 of those work.

So which sounds can be located in FILES.BIN ? I know for sure i'm missing pain sounds and screams from NPC's and Bond anyway lol. I'd love to have everything available to upload videos of the sounds and use in other videos.

Would you be up for sharing how you did your extraction work from STREAMS.BIN? We've only been looking into music and parsing my other of the files so far instead of dialouge! What files have you found to be corrupted ? I can see against the versions of the game I have how they differ and might be able to help you!

I am actually not sure what audio is files are located in the FILES.BIN setup, it's a complex system once you break it open, mostly though it's art, model files and the levels!
## Post #48
- Username: swanbiff
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 09, 2022 1:35 am
- Post datetime: 2022-11-08T18:55:12+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

> Reply from hidinginthevoid ↑Wed Nov 09, 2022 2:19 am at Wed Nov 09, 2022 2:19 am
>
> 
swanbiff wrote: ↑Wed Nov 09, 2022 1:47 am
Hi, any update for the sounds part? I'm looking to extract all of the audios from the game (specifically dialogues and sound effects, rather than music and such). So far i've managed to extract all (presumably) from STREAMS.BIN and most from the DRIVING folder in English, even though around 70 audio files there are corrupted/unrecognizable for some reason sadly. But at least 132 of those work.

So which sounds can be located in FILES.BIN ? I know for sure i'm missing pain sounds and screams from NPC's and Bond anyway lol. I'd love to have everything available to upload videos of the sounds and use in other videos.


Would you be up for sharing how you did your extraction work from STREAMS.BIN? We've only been looking into music and parsing my other of the files so far instead of dialouge! What files have you found to be corrupted ? I can see against the versions of the game I have how they differ and might be able to help you!

I am actually not sure what audio is files are located in the FILES.BIN setup, it's a complex system once you break it open, mostly though it's art, model files and the levels!

Yes. For STREAMS.BIN i used the program PSound and it brought up pretty much all of the dialogues and jingles used in the main missions of the game (not driving missions). PSound was also able to find audio files in the .SBF files in PS2>English and the SB folders. the SB folders contains sound effects like weapons, gadgets, explosions, impacts, materials, some soundtracks etc. I also found that there seemed to be lots of the same repeated audios for some reason.

in the DRIVING folder, there's a lot of different audios that don't work. Including dialogues for Bond, Car Computer, M, Q, various ambience sounds and one or two for Alura, Dominique, Zoe and a Guard. But there's a lot that do work too. I can give specific file names if needed. Also in some cases i found that the French version of the same dialogues worked where the English did not, and other cases both did not work.
## Post #49
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2022-11-09T00:34:00+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

> Reply from swanbiff ↑Wed Nov 09, 2022 2:55 am at Wed Nov 09, 2022 2:55 am
>
> 
hidinginthevoid wrote: ↑Wed Nov 09, 2022 2:19 am
swanbiff wrote: ↑Wed Nov 09, 2022 1:47 am
Hi, any update for the sounds part? I'm looking to extract all of the audios from the game (specifically dialogues and sound effects, rather than music and such). So far i've managed to extract all (presumably) from STREAMS.BIN and most from the DRIVING folder in English, even though around 70 audio files there are corrupted/unrecognizable for some reason sadly. But at least 132 of those work.

So which sounds can be located in FILES.BIN ? I know for sure i'm missing pain sounds and screams from NPC's and Bond anyway lol. I'd love to have everything available to upload videos of the sounds and use in other videos.


Would you be up for sharing how you did your extraction work from STREAMS.BIN? We've only been looking into music and parsing my other of the files so far instead of dialouge! What files have you found to be corrupted ? I can see against the versions of the game I have how they differ and might be able to help you!

I am actually not sure what audio is files are located in the FILES.BIN setup, it's a complex system once you break it open, mostly though it's art, model files and the levels!


Yes. For STREAMS.BIN i used the program PSound and it brought up pretty much all of the dialogues and jingles used in the main missions of the game (not driving missions). PSound was also able to find audio files in the .SBF files in PS2>English and the SB folders. the SB folders contains sound effects like weapons, gadgets, explosions, impacts, materials, some soundtracks etc. I also found that there seemed to be lots of the same repeated audios for some reason.

in the DRIVING folder, there's a lot of different audios that don't work. Including dialogues for Bond, Car Computer, M, Q, various ambience sounds and one or two for Alura, Dominique, Zoe and a Guard. But there's a lot that do work too. I can give specific file names if needed. Also in some cases i found that the French version of the same dialogues worked where the English did not, and other cases both did not work.

Amazing! Never heard of PSound actually, so having a play with that now and trying to see if there are any things we don't know about and also get a viewer / handler built up in my code base. It wouldn't shock me that there is a lot of duped audio because of avoiding random seeks!

Hrmmm, okay, let me have a look and see what I can find, I'll drop you a DM with a link to the Discord we have running to keep you up to date with the progress we make!
## Post #50
- Username: swanbiff
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 09, 2022 1:35 am
- Post datetime: 2022-11-09T00:55:48+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

Ok, great!
## Post #51
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-12-27T16:19:11+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

> Reply from hidinginthevoid ↑Wed Nov 09, 2022 8:34 am at Wed Nov 09, 2022 8:34 am
>
> 
Hrmmm, okay, let me have a look and see what I can find, I'll drop you a DM with a link to the Discord we have running to keep you up to date with the progress we make!

Hi, can I get a link to the discord as well?
## Post #52
- Username: bugsimtasdesimt
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 02, 2022 11:02 pm
- Post datetime: 2023-01-04T21:47:54+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

This game uses the same engine as NFS: Porsche Unleashed, you can try using resources from that game.
Link for some stuff that might help: 
[https://mega.nz/file/No43Dbpa#rWjxAv-Wr ... SM5el616R4](https://mega.nz/file/No43Dbpa#rWjxAv-WrwyMFKzykXlWTP-3TLIKvbvrOSM5el616R4)
Keep in mind the files from the original NFS5 are compressed, so you will have to use a decompressor to get them "to look like" these CRP files.
The version of CRP in this game and NFS5 is different of course, but i think it would still help at least a bit
## Post #53
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2023-01-04T21:52:32+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

> Reply from bugsimtasdesimt ↑Thu Jan 05, 2023 5:47 am at Thu Jan 05, 2023 5:47 am
>
> 
This game uses the same engine as NFS: Porsche Unleashed, you can try using resources from that game.
Link for some stuff that might help: 
https://mega.nz/file/No43Dbpa#rWjxAv-Wr ... SM5el616R4
Keep in mind the files from the original NFS5 are compressed, so you will have to use a decompressor to get them "to look like" these CRP files.
The version of CRP in this game and NFS5 is different of course, but i think it would still help at least a bit

Appreciate the file format information! The driving side did use a version of the NFS engine but everything else was entirely a custom

Added all the data to our research notes and hopefully can get some parsing going on the files, we've got some understanding already of them but more always helps
## Post #54
- Username: bugsimtasdesimt
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 02, 2022 11:02 pm
- Post datetime: 2023-01-04T22:54:02+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

Very interesting, the only reason i even found this thread was because NFS5 also uses .crp files, so when searching for info about that game it lead me here 
Anyway, glad to help
## Post #55
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-08-06T14:49:47+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

This thread hasn't had much activity in a while, is there any progress on it?
## Post #56
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2023-08-06T15:57:15+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

> Reply from AxelNoir ↑Sun Aug 06, 2023 10:49 pm at Sun Aug 06, 2023 10:49 pm
>
> 
This thread hasn't had much activity in a while, is there any progress on it?

Had some set backs with some of the formatting of files.

I've had some life stuff going on meaning I can't work on this as often as I want (I also work full time). So the project is worked on as much as I can phsyically and mentally do so.

There is a lot of code involved in this, not only that, we have to triplicate things and whilst some things are similar on platforms, there is a lot that has changed. Whilst we don't exactly need to do so, it can makes reverse engineering other parts easier.

If you are up for helping we do have a discord you can join if you want to give us a hand on the dev work!
## Post #57
- Username: charliebruce
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 09, 2023 12:01 am
- Post datetime: 2023-08-08T16:07:29+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

> Reply from hidinginthevoid ↑Sun Aug 06, 2023 11:57 pm at Sun Aug 06, 2023 11:57 pm
>
> 
If you are up for helping we do have a discord you can join if you want to give us a hand on the dev work!

Are you able to share a link to the Discord, or share any of the tools you've been developing on Github? No idea if my skillset would be useful (general coding / embedded development including pipelines to embed art/data in compiled binaries, but no game reverse engineering experience and not much time spare!) but I'd love to take a look at least.
## Post #58
- Username: dibugr
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 23, 2021 12:24 pm
- Post datetime: 2023-08-15T02:28:18+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

Hi. I also want to know if anyone has links to parsers, structures or a Discord server for this game.
## Post #59
- Username: hidinginthevoid
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 25, 2020 6:38 am
- Post datetime: 2023-08-15T02:39:14+00:00
- Post Title: Re: [PS2] 007 Nightfire .crp files

> Reply from dibugr ↑Tue Aug 15, 2023 10:28 am at Tue Aug 15, 2023 10:28 am
>
> 
Hi. I also want to know if anyone has links to parsers, structures or a Discord server for this game.

Check ya DMs! But yes we have some parsers written up for the game
