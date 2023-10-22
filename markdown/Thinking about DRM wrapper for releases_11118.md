## Post #1
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-01-09T03:21:46+00:00
- Post Title: Thinking about: DRM wrapper for releases

Just a novel idea I had this afternoon: what if programs uploaded to Xentax are encased in a DRM wrapper at the discretion of the developer?

As you know, people tend to like to leech on the programs developed here. I'm actually fine with people redistributing my files, however I am not fine with the lack of attribution, back to the original link where they obtained it from. It basically encourages others to profit off of programs that people here had taken a tremendous amount of time developing, without so much as attempting to understand the theory behind the program and where the program actually came from.

I propose that programs be given a period of time where it's available exclusively to Xentax members, and enforced until a month or two after someone off-site complains. Yeah, I'm a bit of a sadist, but I just want to see the reaction.

This would be enforced by the program, requiring logging in to the forums through the wrapper around the program, which upon successful login, will download a forum attachment specific to the program (hence the need to log in) and use the information in it to decrypt the program. For .NET programs, this would be really easy to do (after writing the wrapper, that is), and the original executables won't even need to be extracted. It's completely doable too, since there's a builtin web browser control in .NET Framework that I can use to get the session cookies, and the rest of the encryption stuff is also built in.

I'm crazy, right?
## Post #2
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2014-01-09T10:45:17+00:00
- Post Title: Thinking about: DRM wrapper for releases

I actually think that open-sourcing everything (e.g. on github) would be better. It's really annoying to find a binary-only extractor in an age-old thread which doesn't work for a newer revision of the data file it's supposed to extract, and you have no way of updating or fixing it. Also, what would you do if you want to run a program but the forum is currently down? Or your internet is having trouble? And what's stopping people to take the downloaded "key" (or the decrypted binary itself) and post that somewhere else? 

Thus I propose the opposite: Every program posted here must be accompanied by its source code (maybe a few weeks/months later, as you suggest, as a "grace period"). That way the work done here will at least be future-proof and not lost when the original author leaves the board
## Post #3
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-01-09T15:41:55+00:00
- Post Title: Thinking about: DRM wrapper for releases

True, true. My intention is to give Xentax a period of exclusivity. I release source code for all my programs, and under the DRM system, once the grace period elapses, I'd update the downloads to contain a non-wrapped version with source code. As for stopping people from unwrapping, there'll be signature checks on the whole EXE to prevent modification, and the compiled wrapper will be run through an obfuscator. I doubt the people who rehost the files will bother to figure it out, and if anyone does, I won't mind (modding communities always need good reverse engineers).
## Post #4
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2014-01-09T19:19:00+00:00
- Post Title: Thinking about: DRM wrapper for releases

Seems hardly worth the trouble. All unpackers etc. I write/wrote are so small I don't even bother writing a GUI for them (people who can't use the command line shouldn't be allowed to call themselves "hacker" or "modder", let alone "reverse engineer"). So I definitely wouldn't bother pulling up a wrapper. Especially since command line tools are often called from batch files, and maybe even looping over 100s of files, and I don't want a user type a login every frickin time.

I think that a well-placed "coded by XXX" or "this is brought to you by XXX" printed by your program (maybe in a splash screen if needed) is attribution enough. People who edit the EXE to overwrite that will probably go to great lengths to rip out your DRM as well (and you could still use any stock EXE packer/encrypter to make it harder for them). And if they need their name in it for their ego then I don't really care, it's not as if nobody will ever find out that they can't code shit themselves if they pass it around as theirs 

Again, I ask you: What happens when after 2 years this forum is updated, all the URLs change, and now every single program doesn't work anymore? And probably the original developers have left as well. Someone else has to start back from square 1 (happened to me more than once already)
## Post #5
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-01-09T22:07:08+00:00
- Post Title: Thinking about: DRM wrapper for releases

> Reply from Darkstar
>
> Again, I ask you: What happens when after 2 years this forum is updated, all the URLs change, and now every single program doesn't work anymore? And probably the original developers have left as well. Someone else has to start back from square 1 (happened to me more than once already)

The non-wrapped version will be uploaded before then. I only intend it to be an experiment, not anything long term (actually, just to piss off a few guys at another forum full of noobs who just want tools).
## Post #6
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2014-01-09T22:24:27+00:00
- Post Title: Thinking about: DRM wrapper for releases

> Reply from GMMan
>
> The non-wrapped version will be uploaded before then. I only intend it to be an experiment, not anything long term (actually, just to piss off a few guys at another forum full of noobs who just want tools).
Ah, so you want to use Xentax as a way of getting your personal revenge; or maybe for proving to someone that you're "better" than them? Well, nobody is keeping you from coding your own tools in such a way (e.g. limited runtime or feature set without proper unlock-code which can be gotten from you via PM here, for example) but I think pulling the community in your personal vendetta against other forums is not the way to go.

Instead, why not provide source code ONLY so that they at least have to compile it themselves? Maybe lock the unpacker to only a subset of the files (via fixed offsets or something which work only for some files and not for others) and then tell them (abstractly) how to code around that?That would be much more educating in the long term...
## Post #7
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-01-09T23:07:59+00:00
- Post Title: Thinking about: DRM wrapper for releases

An observation I've made: isn't MultiEx Commander using a similar system, sans encryption, by withholding program data without valid login?
## Post #8
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2014-01-11T01:06:09+00:00
- Post Title: Thinking about: DRM wrapper for releases

IMO using DRM in a reversing site is kinda ironic. 
If leechers don't give credit or reference the original source, that's bad for them/their forum, since many tools are updated on a regular basis, and they can't give feedback/report bugs. A google search would be enough to bring the interested people here if the tool name is distinctive enough or have an "about" with info and author name, right? 
Scripts on the other hand can be easily modified, but what they would do that?


I agree with darkstar in making xentax more open too, so also people could learn, and maybe some exclusivity for people who contribute with actual research and tools (1% maybe?), but that might be offtopic.
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2014-01-11T04:21:47+00:00
- Post Title: Thinking about: DRM wrapper for releases

No one would adhere to it, getting developer cooperation in this kind of environment is worse than herding cats. It also overlooks the real problem. The real problem being that people are pieces of shit.

When I see someone abusing Noesis or posting ripped model batches for their own idiot manchild life-wasted glory, I yell at them. But the simple fact of the matter is, I don't witness 99% of it firsthand, and people have 0 respect when it comes to respecting me for the thing I've spent hundreds of hours making and subsequently given away for free. Over the years of Noesis work, I've gotten $0 from any kind of attached publicity or ad revenue others have made on it, and maybe $300 or so total in random donations, from a total of 3 different people that have continued donating small sums over time just to show their appreciation, and their sentiment means more to me than the money.

That's 3 out of, oh, probably around 10,000 or so total users. If the volume of unique crash reports that I get from old versions of Noesis alone is any indication, thousands more are passing it around in unofficial channels and idiotically submitting crashes that I fixed months ago. People are fucking dicks. But I digress.

Practically speaking, I don't think a forum-based DRM is a good solution, and it just leaves a bad taste in my mouth.
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-01-11T09:10:57+00:00
- Post Title: Thinking about: DRM wrapper for releases

> Reply from GMMan
>
> An observation I've made: isn't MultiEx Commander using a similar system, sans encryption, by withholding program data without valid login?

Interesting observation, how did you make it ? 

As for the topic, I agree that it goes against the vision to DRMify tools posted. And it is development hell to get any system to work properly integrated. I'm not going to spend any time on that, and I'm sure no other at XeNTaX would. 

MrAdults raises a good point, people are being cowardly dogs by pretending to be cool, while all they do is rip other people's work without properly giving credit where credit is due. That is the real issue, but one that is not easily handled, as humanity has shown time and again to produce an overwhelming stream of bastards on a hourly basis.  

I do see the point that it is very annoying if you miss the source code when a binary is no longer available, but it really is at the discretion of the developer to release it or not. So whenever you see a tool posted, and would like to have the souce code, you can always ask the developer. Perhaps he or she agrees. 

So, XeNTaX is already very OPEN, and we are not going to make it obligatory to release source code, though we may give people a hard time when to come in here to boast about their skills to work with a certain game but refuse to share their information on how they did it. Sharing is key, as long as other people can then at least build their own tools.
## Post #11
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-01-11T21:18:28+00:00
- Post Title: Thinking about: DRM wrapper for releases

To add another note: [blog/](http://forum.xentax.com/blog/)

That is the blog where forum members can post their (or other) tools of interest. I created that blog to store the tools in one place, not to be lost.
## Post #12
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2014-01-11T22:53:27+00:00
- Post Title: Thinking about: DRM wrapper for releases

When I first started contributing compression/format/etc. specs, I came in with the mentality of "What's wrong with you people? Why doesn't anyone share their findings instead of just throwing up a binary?" So I went out of my way to write spec docs, put full source up for all of my reversed formats, and so on. Then I saw people using my work and not throwing so much as a "hey thanks" in my direction, and the whole strange and screwed up secretive nature of the community made a lot more sense. People don't release their code because the ego isn't fed when someone else takes the code and does something with it without proper attribution, and the person that steals the code thanklessly doesn't get their ego stroked as much if they correctly attribute and acknowledge that someone else did 99% of the work. It's an issue of ego on both sides, with the weak taking from the strong, leading to a basic hostility in what would otherwise be a flourishing community.

My policy these days is, if I have a reason to respect you, I'll give you code, specs, and help and expect nothing in return. If I don't have a reason to respect you, it's probably because you haven't done anything to impress me in the context of this community, which means you're probably the type to take a lot and give little to nothing back, therefore you deserve nothing from me. It's a haphazard system, but it works. Unfortunately, it's still a closed system in its nature, but people have shown that they just can't play nicely in an open environment.

The up side to all of this in terms of preservation of data/knowledge is, we're making all these tools for x86. (or at least x64) Someone with some decent knowledge and experience can reverse-engineer our work if they want, a lot more easily than having to do it in the native environment and code for whatever game/app/etc. it is that they're interested in, without worrying that the hardware is gone forever or was never properly documented itself due to some commercial entity keeping a tight hold on the information. x86 isn't going anywhere, and it will be a debuggable architecture for the common man for longer than C is likely to be a common language. So in this way, there's no danger of our work being lost to time, as long as the work is significant enough for someone to want it enough to do a little bit of disassembly down the line. And if someone is willing to go at least that far, they probably know what it is to work hard to make something, and aren't the kind of thoughtless wankbags that would just steal source code and compile it as something slightly changed to stroke their egos. So it kind of naturally filters the benefactors of the work down to the people that actually deserve it.
## Post #13
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2014-01-11T23:44:27+00:00
- Post Title: Thinking about: DRM wrapper for releases

> Reply from MrAdults
>
> ...Someone with some decent knowledge and experience can reverse-engineer our work if they want, a lot more easily than having to do it in the native environment and code for whatever game/app/etc. it is that they're interested in, without worrying that the hardware is gone forever or was never properly documented itself due to some commercial entity keeping a tight hold on the information.
Heh, this is the most backward argument in the whole thread. Reversing a program that someone else wrote to reverse a file format? Yeah, because with every layer you put on top the reversing gets easier and easier, right? Normally this is not about running an old binary on some other system (Linux or ARM or whatever), but rather to extend it because some slightly new/different file format made some subtle changes that make the tool crash/not work. While you are theoretically right that you can still fix that in a binary, it is infinitely more complex than having a file format description in the first place and fixing just that...

Also, the whole notion of other people grabbing source code from somewhere and passing it off as their own is not really new. If everyone thought like you we wouldn't have any Open Source software today. Licenses exist for a reason. If you put it under a (L)GPL license (or any other open source license), people will STILL steal your code but now you have legal grounds to go against them if you want. Open Source relies on trust, for 100 users who obey and respect your choice of license, there's maybe 5 or 10 who don't. Or maybe even 20, I don't know. Still you "punish" all 100 of them just to get those 20. That's the same as with DRM, you punish the many "good guys" with crippleware while the few "bad guys" just crack your program and be done with it.

It took the game industry many many years to realize that (see gog.com, desura, humblebundle, etc.), I thought that at least the reverse engineering community would understand that as well by now.

So in your case of noesis, if you want/need revenue from it, why not make it (feature-limited) Shareware? Or keep it free but sell the source code for 2 bucks? I for one would gladly pay for the specs to so many 3D formats (even if my own 3D experience is still rather small), and even though I couldn't use it directly in any of my programs (because I tend to give away the source for free) I could still create clean-room documentation from it (and that would be a bliss because so many of the formats noesis supports are still not documented at all...) and preserve at least that...
## Post #14
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2014-01-12T04:09:34+00:00
- Post Title: Thinking about: DRM wrapper for releases

It's not an argument. It's a simple statement. The code and data is there in a way that guarantees preservation, and allows extension if someone perseveres enough to bother. How easy/complex it is has no relevance to the statement, although I do think saying it's "infinitely more complex" is silly and subjective.

I wouldn't be arrogant enough to try to put the license of my choice on code that's derived from disassembled binary. That's in itself ridiculous and just asking for legal problems of your own. It's all about pettiness and ego, and how we deal with it outside of typical open source constructs. That's the whole reason this community and reverse engineering is different and has to exist under different rules. An actual GPL zealot wouldn't consider touching RE'd code with a 10 foot pole.

Selling Noesis is a ridiculous notion for he same reasons, I never implied money was the goal either. Terrible inference.
## Post #15
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-01-12T05:17:07+00:00
- Post Title: Thinking about: DRM wrapper for releases

Neat idea but I don't see it working
## Post #16
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2014-01-12T05:50:25+00:00
- Post Title: Re: Thinking about: DRM wrapper for releases

Now that I'm not posting from my phone, I'd also like to address this as a tangent:

> Reply from Darkstar
>
> Reversing a program that someone else wrote to reverse a file format? Yeah, because with every layer you put on top the reversing gets easier and easier, right?I suspect you don't do much actual reverse engineering yourself, or if you do you live the sheltered life of one who only disassembles native code, or worse yet, strictly guesses based on nothing but binary observations.  When you're talking about shoveling together tools to reverse engineer something on a proprietary embedded system for a different CPU than your tool target, you probably aren't going to have debugging capabilities anywhere near as nice as the ones you have under a desktop OS. And even if you do have a very nice debugging and disassembling solution for the platform you're reversing from, you're still translating it to a different architecture. If you're just disassembling and targeting x86, you can tear the routines straight out of the app, plop them into your own, and you're tentatively done. From there you can step through them, take your time, easily put them through any kind of unit/sandbox test you want, and translate them way more easily with the aid of experimentation and observation in your own isolated framework. That's a far cry from translating blindly from raw disassembly because you can't debug on the platform, and even from translating to a different architecture using a likely limited (in comparison to the x86 debugging tools available) debugging environment.

So, yeah, unless the reverse engineer made a complete mess of things, it is a hell of a lot easier to reverse their work instead of the original in pretty much every case when we're talking about things like gaming console platforms. I can't name a single instance where I've chosen non-x86 over x86 for ease of reversing.
## Post #17
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2014-01-12T10:28:03+00:00
- Post Title: Re: Thinking about: DRM wrapper for releases

Now I see that we're talking about different things. You're mostly talking about reversing from different architectures, I'm talking about figuring out file formats regardless of architecture (and you're right in that I mostly work with x86 stuff)
Also I see that we have different goals, my goal for reversing a file format is to help as many people as possible to extract or change the contents, to enable mods, cheats, fantranslations etc., while your goal seems to be recognition, ego, and having others praise you for your work.

Which is fine, I won't judge people over that, it just helps me understand their motivations for sharing/not sharing source code and detail documentation.

Also, if money never was the issue, why did you bring it into the discussion?
## Post #18
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2014-01-12T18:32:03+00:00
- Post Title: Re: Thinking about: DRM wrapper for releases

Reverse engineering does not necessarily mean figuring out file formats. Figuring out file formats is just a possible side effect of reverse engineering. Reverse engineering is the thing that causes all of the interesting/unique issues here.

The desires of your ego are rationalized by your goals. You aren't feeding starving children and saving the world, and your abilities aren't unique enough to matter in terms of overall advancement. You can rationalize what you do as "making people happy" like any member of any entertainment industry, but it's really about you and your desire to feel whatever it is that you feel as a result of doing what you do. Unless you're some kind of sad Entertainment Jesus martyr figure, in which case I'm sure we'll all be lamenting your crucifixion one day.

I work on Noesis because I enjoy working on Noesis, and I enjoy the puzzles in reverse engineering. It's like sitting around and doing Sudoku puzzles, except in this case other people happen to be interested in looking at the solved puzzles. And in some cases, I enjoy sharing and explaining those puzzles to others, with the same sort of egotism a teacher indulges in sharing the culmination of their knowledge to their students. Those are the people that I respect on the basis of their character and the constructive uses of their talent that they've demonstrated. I enjoy it when someone uses Noesis to creative ends, to create something new, to refactor or process their own content, to learn and experiment. Unfortunately, those people are an extreme minority here.

I mentioned that 3 in 10,000 people have donated as a way of pointing out that 3 out of 10,000 people have said thanks in a way that actually inconvenienced them to some degree. Even when we set the bar for saying thanks down to merely saying "thanks", far fewer people have said thanks than have abused Noesis and disrespected me by going against my wishes and against regional copyright law. We can't rely on source code licenses to protect us, because we aren't in a place to try to enforce a license on source code that's derived from disassembled binary. We could certainly lie about it entirely and say that all of our code is "clean room" engineered, but everyone would know that was bullshit, and it would not stand up to any sort of scrutiny. And do you know what open source development is without enforceable licensing? It's disgusting. Because people are horrible and disrespectful, and if there were no legally enforced consequences a shockingly high percentage of the global populace would be happy to rape your mother.
## Post #19
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2014-01-12T23:31:53+00:00
- Post Title: Re: Thinking about: DRM wrapper for releases

> Reply from MrAdults
>
> 0
My policy these days is, if I have a reason to respect you, I'll give you code, specs, and help and expect nothing in return. If I don't have a reason to respect you, it's probably because you haven't done anything to impress me in the context of this community, which means you're probably the type to take a lot and give little to nothing back, therefore you deserve nothing from me. It's a haphazard system, but it works. Unfortunately, it's still a closed system in its nature, but people have shown that they just can't play nicely in an open environment.

This is interesting, I think many veteran members have that policy too. I'm thankful that many users have helped me with lots of questions even when I did no contributions.

One thing I observe is that there's not enough information about disassembling games so one could save time in learning it elsewhere (like [this site](http://thelegendofrandom.com/blog/sample-page), which is focused on cracking)
I'd appreciate a lot more to have a video/doc on how you did disassemble x game to find out x format than the file spec per se. 
So maybe that lack of information prevents new users to reach your level and make significant contributions (and impress you?).
Making documentation/tutorials is a lot of work, but at least you're not giving anything for free, they'll have to read/practice a lot to get any value from it.
Anyways, I just realized I could actually do some tutorials, so I'll start by that.
## Post #20
- Username: Bastien
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2014-01-13T04:24:57+00:00
- Post Title: Re: Thinking about: DRM wrapper for releases

I did exactly that a couple of years back for FX Fighter:

[http://richwhitehouse.com/index.php?postid=63](http://richwhitehouse.com/index.php?postid=63)

It covers my whole process from start to finish, using IDA as my disassembler and DosBox as my debugger. You can use the latest freeware IDA for everything I cover there. For learning how to use IDA, there is a ton of material on Google and YouTube. It just takes practice to be able to do things quickly and effectively, and you develop a sense for things as you go. There is no real hidden knowledge barrier to entry.
## Post #21
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-01-14T00:26:46+00:00
- Post Title: Re: Thinking about: DRM wrapper for releases

> Reply from Mr.Mouse
>
> GMMan wrote:An observation I've made: isn't MultiEx Commander using a similar system, sans encryption, by withholding program data without valid login?Interesting observation, how did you make it ?
I install Privoxy on all my machines for basic blanket filtering for anything that uses HTTP (and respects proxy settings on Windows). One of its features is logging HTTP requests, complete with url-encoded parameters if the request is a GET request. I just stuck in each URL requested by MultiEx to download whatever files it serves up. There was something in the registration mail about if someone redistributes MultiEx login details the login would be invalidated and the person would get a corrupted MultiEx. So I assumed that's what happens with an invalid login (which serves up a zero-length page).

As for the thread: It's nice to provoke some discussion. I release all my programs with source code, since I'm too lazy to write proper documentation, and it would be easy for others to update things if necessary. As I said in the first post, I don't mind distribution, but it would be nice if they'd at least include a link to the original download page so people can get updates. For those who do distribute without linking, it's a loss to themselves and their community. For one of my tools, the other site was months late into updating, and when they ask questions, they won't get answered because the person who rehosted doesn't (or can't) care, and I'm not considering joining their forum any time soon. My DRM idea isn't anything permanent. I only really want to try it once to get a reaction (I doubt anyone here are avid Gameloft modders; their games are a bit on the cheap side, both monetarily and graphically), plus it'd be nice to do something that's different than a packer/unpacker. I wouldn't be miffed if someone cracked the DRM. In fact, I'd encourage people to crack it. It's all in fun, just as I'm not actually serious in trying to limit the program to Xentax members. As I said, I'm a bit of a sadist, and would like to see those only use tools and not do any research whine, even if to just stoke my ego.
## Post #22
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2014-01-14T01:35:56+00:00
- Post Title: Re: Thinking about: DRM wrapper for releases

Well, it's good to be honest about it, at least.

In all candor, I might make the effort to do a proper Noesis source release one day. But I'd have to remove/rewrite all the data processing code and math routines that I've contractually obligated myself into not releasing. I'm certainly not motivated to go that far, mostly because I hate 99% of the people who want the code, and the other 1% I just help and offer code/info to directly. That's also why I usually just throw up a .cpp file without all the dependencies and watch people whine about not being able to compile it directly when all it would take is 10 minutes of effort to plop it into another working framework. Unless I wrote it in Python. In which case, it's Python, you lazy fucks. Usually people just rip that off directly and make a few changes so it works in blender. Heaven forbid they do anything to assist or support the Noesis framework in the process.
## Post #23
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2014-01-15T14:57:22+00:00
- Post Title: Re: Thinking about: DRM wrapper for releases

This has nothing to do with the current topic, but I just want to say I love you mr.Adults for the support on mld and valve files. They make my life a lot easier to create 3d models/items for dota 2.
## Post #24
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2014-02-16T17:55:28+00:00
- Post Title: Re: Thinking about: DRM wrapper for releases

GMMan
yes, you ARE crazy 

DRM makes people HATE you. Want proper credits - add CAboutDlg  Want your program to live - make it opensource.
