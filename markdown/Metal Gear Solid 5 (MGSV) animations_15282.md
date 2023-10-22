## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-09-27T19:49:22+00:00
- Post Title: Metal Gear Solid 5 (MGSV) animations

Metal Gear Solid 5 animations.

200 extracted animations in one non-stop video. As for strange effects in transitions between animations, ignore them, it happens because they're not supposed to work in one go. 

[https://youtu.be/oUofIF7u1bQ](https://youtu.be/oUofIF7u1bQ)

Also here's an interesting video recorded during quat research. Changing one component sign made snake (and everyone else) walk in a strange way. I also have a video of finding Paz in this way, its pathetic.

[https://youtu.be/7pOoO4rhimY](https://youtu.be/7pOoO4rhimY)

Human MTAR tools. Works on all human (Ground Zero & Phantom Pain) skeletal animations now, but soon I plan to make support for all kinds.

Usage: drop animation file on the tool. Or run with 1 command line parameter (animation filename).
Snake model from Ground Zeroes (sna2_main0_def.fmdl) must be in the same dir. The tool needs it for skeleton initial position and bone names. For Phantom Pain also use the same GZ model, because the skeleton is the same, and it has bone names.

For example, if you use it on TppGzPlayer_layers.mtar package, it will extract all 2405 animations in SMD format files. If you use it on one of snake's .GANI animations, it will unpack it.

After unpacking, load the model and apply it.
Then connect arms to palms and legs to feet with IK constraints.

Example: connect IK_LARM -----> SKL_013_LHAND, and use pole vector IK_POLEARM_L
You will also need to do something with twist bones, this is not done automatically yet.

TPP Cutscene tool
You will need corresponding .sand and .fsm file for the cutscene, also .fmdl files. SAND (scene animation description) files are all over the FPK packages. FSM files are in "demo" folders.

Usage:
mgs5_pp_cutscene [sand] [n] [fmdl]

[sand] - required .sand file name. If you only use this parameter, will list character cast and not extract anything.
[n] - number or character to extract, according to the cast. In theory, you can extract any character, camera, thing, whatever.
[fmdl] - model file that the animation will be put on. In case of model swap, will produce model swapping results, but it will also work.

For your convenience, this is the description of all cutscene files I have: [http://pastebin.com/i81gAGNp](http://pastebin.com/i81gAGNp)

DDog MTAR tools Supports only Diamond Dogs! Normal dogs have a little different skeleton.

Usage is similar to human MTAR, but no IK actions needed. Model file for it is ddg0_main0_def.fmdl
[mgsv_anim_tools.rar](https://xentaxbackup.github.io/file/23909_mgsv_anim_tools.rar)
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-09-27T20:30:19+00:00
- Post Title: Metal Gear Solid 5 (MGSV) animations

Excellent work!
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-09-28T19:11:21+00:00
- Post Title: Metal Gear Solid 5 (MGSV) animations

Tool beta published here: [http://zenhax.com/viewtopic.php?f=5&t=3172](http://zenhax.com/viewtopic.php?f=5&t=3172)

It only works on snake (Ground Zero format) skeletal animations now, but soon there will be support for all kinds.
## Post #4
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2016-10-01T18:49:39+00:00
- Post Title: Metal Gear Solid 5 (MGSV) animations

This looks like an excellent work. Some questions about the research:

1- How much time did it take you to figure out the format?
2- Are you going to release the format spec?

I always wanted to research animation formats, it always seemed to me like the most difficult, so any info on your workflow is appreciated.
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-10-02T06:04:20+00:00
- Post Title: Metal Gear Solid 5 (MGSV) animations

Animation research in "normal" games usually takes 1-2 weeks. That meaning they're using normal data types like ints, floats or half-floats. But recently I reversed Morpheme engine. This look about a month. They had mixed global/local rotations, variable bit-length packed data, specially packed quaternions, and so on.

Now to MGSV. The research is not complete yet. It took 2 weeks already, and probably may take another month. Just yesterday I found them sometimes using 16-bit float numbers, and not usual half-float format, but their own type. They also had variable bit-length packed data, and quaternions packed in another weird way. There are still facial, cutscene animations to do, maybe including some more non-standard types.

I will describe most of the special things they use when I have time.

So that's right. Animation research may be most difficult, because for that you need to know models and rigging with all their details and tricks, and above that, you have to understand quaternions and all those geometry calculations needed to build skeletons and animate models.
## Post #6
- Username: Bastien
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-10-03T02:04:54+00:00
- Post Title: Metal Gear Solid 5 (MGSV) animations

> Reply from Bastien
>
> This looks like an excellent work. Some questions about the research:

1- How much time did it take you to figure out the format?
2- Are you going to release the format spec?

I always wanted to research animation formats, it always seemed to me like the most difficult, so any info on your workflow is appreciated.
Since you messaged me looking for info, here's some relevant free tidbits:

- Animation data can be trivial at times, but often if there's any kind of interesting compression or packing, disassembly becomes vital or at least very useful.
- PC games are way easier to deal with when figuring out any kind of complex data, like elaborate animation packing/encoding, compression, and encryption. Faster turnaround for debugging sessions, and faster turnaround for modifying data in-place, or even in memory, to observe the outcome. Additionally, capabilities like hardware read/write and conditional breakpoints can be hard to come by for some non-PC platforms.
- Start by learning how to debug and read through disassembly, using breakpoints and system hooks effectively to get at the routines you care about, where the data you care about is being utilized. Spend a lot of time with IDA just learning how to target data and understand the disassembly dealing with it. It will usually take you longer than just staring at binary for simple formats, but the practice will be very valuable for you for when you want to do something complicated.
- In-memory asset data like animation can be even easier to discern in this manner than something that's quickly flushed or copied multiple times at load time. For this type of data, just search for the data in-memory, set a read breakpoint on it, and you'll end up somewhere directly relevant to the data you care about.
- Even if you're dealing with an easier platform, still be prepared to lose plenty of hours of your life. Make sure you're married and have a nice family before you commit to flushing your days down the drain.
- For PC x86/x64 games, once you narrow down the range of disassembly you're dealing with, you can pull it out and compile it into your own program locally. This isn't terribly difficult, and it'll be a pretty obvious step once you've spent some time debugging your way through some disassembly. From here, all you have to figure out is what to feed in (e.g. what register and stack states are expected to be as you enter your initial function), and you can replicate the behavior (whatever it may be, such as decoding a frame of animation) in your own program. Once you have this happening, it's much easier to begin picking apart the isolated code, and test it on different assets in a more controlled environment. Translating it back to some other language is a simple matter of time at this point.
- If you're clueless about a certain type of data to begin with, it will be harder for you to reverse engineer it. Sometimes, broadening your knowledge in the related field is the right way to spend your time before you continue tackling a certain type of data.

People are petty and secretive with their findings, but other people are also dicks and steal things immediately, so it goes both ways. Often times, though, there aren't too many big global secrets that are going to help you across all games/platforms. If you can figure out the workflow above, you're pretty much set to accomplish anything on the Windows/PC side. Consoles are another matter. If you can get a debugger going on the target platform, great. If not, you're limited to offline disassembly and analysis, which can be much more time-consuming, but still viable if you're willing to put forth the extra effort.
## Post #7
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2016-10-05T01:00:04+00:00
- Post Title: Metal Gear Solid 5 (MGSV) animations

Thanks daemon1 and Mradults for your comments on your workflow. I don't want to pollute the thread with unrelated things to MGSV, so I'll post questions in other threads.

> and above that, you have to understand quaternions and all those geometry calculations needed to build skeletons and animate models.
Yeah, I remember that when you talked about IK. I thought most games used FK data since they come from motion capture, but it makes sense to calculate data on the fly.

> Spend a lot of time with IDA (...) It will usually take you longer than just staring at binary for simple formats, but the practice will be very valuable for you for when you want to do something complicated.
I've been using the Free version of IDA for some time, and reading a [book](https://www.nostarch.com/idapro2.htm), and it's been a little frustrating, specially the "using breakpoints and system hooks effectively to get at the routines you care about" I could identify where interesting strings where used (e.g. the name of a model file), but not where the actual parsing happens. Probably I didn't dedicate enough time to it, same with ollydb (seems to fail frequently in many games, probably an anti-debug system)

> For PC x86/x64 games, once you narrow down the range of disassembly you're dealing with, you can pull it out and compile it into your own program locally. This isn't terribly difficult,
wow, amazing

> Sometimes, broadening your knowledge in the related field is the right way to spend your time before you continue tackling a certain type of data.
I thought the same thing! I started learning a little directx.

> People are petty and secretive with their findings 
In many threads (but from many years ago) I saw that working in collaboration makes the process of figuring out 100% something much faster, but usually is the work on only one person that happens to be interested in the game. I understand the shitty experiences with people stealing stuff and not giving credit.
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-10-05T18:44:43+00:00
- Post Title: Metal Gear Solid 5 (MGSV) animations

> Reply from Bastien
>
> and above that, you have to understand quaternions and all those geometry calculations needed to build skeletons and animate models.
Yeah, I remember that when you talked about IK. I thought most games used FK data since they come from motion capture, but it makes sense to calculate data on the fly.

Yes, most games use FK data. But what I said was about most games. You need to understand quaternions and geometry calculations even for simple animations.
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-10-05T18:48:32+00:00
- Post Title: Metal Gear Solid 5 (MGSV) animations

> Reply from Bastien
>
> For PC x86/x64 games, once you narrow down the range of disassembly you're dealing with, you can pull it out and compile it into your own program locally. This isn't terribly difficult,
wow, amazing

I'm doing this very rarely. Only if its absolutely needed, for some very complex procedures. Actually I never needed that for animations, only once for complex audio codec. Most of the time, its possible and easier for me to just analyze the data. And if it's something really complex, debug it for a while, but once I understand what it does, make my own code for it.
## Post #10
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-10-05T19:27:53+00:00
- Post Title: Metal Gear Solid 5 (MGSV) animations

> Reply from daemon1
>
> I'm doing this very rarely. Only if its absolutely needed, for some very complex procedures. Actually I never needed that for animations, only once for complex audio codec. Most of the time, its possible and easier for me to just analyze the data. And if it's something really complex, debug it for a while, but once I understand what it does, make my own code for it.
It's often easier/faster to just stare at data and try to intuit it. I've done this with complicated animation formats that use variable adaptive delta compression, but I don't recommend it. I suggest not giving into the temptation to avoid understanding and analyzing the associated code/disassembly given any real opportunity to do so, you're going to get better and faster the more you do it.

On the other hand, guessing at someone else's approach to something is based on your broad-spanning knowledge and intuition, and you're always going to run into walls when someone decides to deviate from all the norms or hasn't based their work on anything that's well-documented/researched already. So when you run into something like this and you need your disassembly muscle, it'll be weaker than it should be if you haven't been using it. This is also the difference between a problem taking 3 days and taking a month. If I need to spend more than 2 days of solid effort on something, that usually means it's time to disassemble. Every time I've violated that rule myself, I've regretted the amount of time wasted in the end. On console games, I'm always weighing the options because debugging and disassembling can be a huge pain in the ass for certain platforms. But on PC, it's a no-brainer.

And of course, when it comes to analyzing large amounts of disassembly, you're naturally going to save a lot of time by isolating the relevant code to be able to run more tests and interactively debug it without worrying about the state of the rest of the program. You always want to do this right away when disassembling with a purpose, and it takes virtually no time at all once you've worked out how it fits into your workflow.

TL;DR - Even if it's easy enough to guess at, missing the opportunity to strengthen yourself puts you in a self-perpetuating rut. If you find yourself spending too much time banging your head against the wall, you can probably be doing something smarter to get the answer you're after. I'll stop semi-hijacking this thread now.
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-10-05T19:43:19+00:00
- Post Title: Metal Gear Solid 5 (MGSV) animations

> Reply from MrAdults
>
> ...when you run into something like this and you need your disassembly muscle, it'll be weaker than it should be

But then when you run into something not like this and you need your analyzing muscle, it'll be weaker than it should be.
## Post #12
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-10-05T20:20:48+00:00
- Post Title: Metal Gear Solid 5 (MGSV) animations

> Reply from daemon1
>
> MrAdults wrote:...when you run into something like this and you need your disassembly muscle, it'll be weaker than it should be

But then when you run into something not like this and you need your analyzing muscle, it'll be weaker than it should be.
This is untrue. Understanding happens whether you do it the easy way or the hard way. Ease of analysis improves with understanding and knowledge. Wasting time with wrong guesses isn't actually helping you, because you aren't excluding possibilities for anything else you'll ever work on, just for the particular thing you're working on right at that moment.

So the "analyzing muscle" is actually going to grow more effectively if you're churning through problems efficiently to get to the root of the data and how it's intended to work, instead of wasting time banging your head against the wall for one thing. Not to mention, you may be making false assumptions about that data that you never catch or notice, because you weren't looking at the true source of its implementation.
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-10-06T16:34:54+00:00
- Post Title: Metal Gear Solid 5 (MGSV) animations

> Reply from MrAdults
>
> This is untrue.
I disagree. I'm looking at this from a different angle. Let me just mention that my first assembler was a PDP system in late 1980's. Then 8080. I had to write my own disassembler for that, because there was no one on a particular platform, and I wanted to disassemble games for that. Then was 8086 and so on. I have almost 30 years of experience in both data analyzing and disassembling.

> Reply from MrAdults
>
> Wasting time with wrong guesses isn't actually helping you
If you're good in analyzing, you don't have to make wrong guesses. All your guesses will be right. Have you heard about nonograms? Its very similar to it. You start from one corner, and one by one make it all out. There's no waste of time.

> Reply from MrAdults
>
> you aren't excluding possibilities for anything else you'll ever work on, just for the particular thing you're working on right at that moment.
There are lots of tricks and methods in data analyzing. If you only disassemble, you'll never know these techniques, and will have no experience in using them. So analyzing does actually help. And not only for one case. And it doesn't depend on knowing common norms or well-documented things. When I first analyzed game archive, I had no idea how they're usually made, and that's why it was interesting to me. When I first analyzed sound files, I had no idea about adpcm codecs or usual segmenting/frame types. And that's why it was again very interesting to analyze.

Its a fact, that some people perceive visual data better than audio and vise versa. Can you admit that for some people, analyzing ability will grow more effectively when analyzing, rather than disassembling? I mean, in most cases reading the code will only confuse you and slow you down, but looking at the data will get you right to the point. So in most cases, disassembling will be a waste of time.

Not to mention that personally for me, disassembling is like instead of solving the puzzle, you're trying to find the answer in a big and badly organized book. That's not interesting. No fun. Every time I'm forced to use disassembly I feel disappointed.
## Post #14
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-10-06T18:21:37+00:00
- Post Title: Metal Gear Solid 5 (MGSV) animations

> Reply from daemon1
>
> If you're good in analyzing, you don't have to make wrong guesses
How can you say this, when you've just spent weeks on an animation format?  You know as well as I do, you will make guesses, and they will be wrong. Even if you have a limited set of possibilities, it's like using A* to pathfind - you can make good steps based on heuristics but you're still going to end up traversing nodes that you didn't need to because you didn't understand how to get where you were going when you started out. You've wasted time because you didn't collect the necessary data to start efficiently.

> Reply from daemon1
>
> I disagree. I'm looking at this from a different angle. Let me just mention that my first assembler was a PDP system in late 1980's. Then 8080. I had to write my own disassembler for that, because there was no one on a particular platform, and I wanted to disassemble games for that. Then was 8086 and so on. I have almost 30 years of experience in both data analyzing and disassembling.
You've been at this for even longer than I have. I got my first gamedev contract about 20 years ago, but have only been active in reverse engineering for maybe 10-15 years. But you could say that after 30 years, if relatively simple things still take weeks or months, it could be a problem with the methodology, or you just don't care about utilizing your time effectively. Sorry, I do respect the aspect of "fun", because there isn't much other reason to do this crap if it isn't fun for you in some way, but I also don't find it fun to have to tackle a single problem for weeks at a time unless the complexity or scale of that problem truly warrants it. When a format has many different facets that are taking that time justifiably, or I'm exploring something for new hardware that I'm not familiar with, then sure, great, that will take more time and give me new knowledge in the process. But instead of getting caught up on details like "which bit is signifying which packing format, how many bits are used in this mode, how many fraction/exponent bits are used for this custom floating point encoding, blah blah blah", save yourself all that time guessing and narrowing down your search potentials and just read the disassembly. Once you get into actual decryption or more elaborate forms of compression, this holds 200 times stronger.

Disassembling anything modern is certainly a lot different than it was 10, and I can only imagine 30, years ago. The difference in volume alone is staggering, and it requires many different methodologies to achieve efficiency.

Rather than solving a puzzle versus using a badly-organized book, at this level, it's blindly throwing A* at a nice uniform node grid when you have a starting node right in front of you that begins a perfectly visible linked list leading straight to your destination. The difference between being good or bad at reading through and understanding disassembly is the difference between going from one node to the next instantly or getting stuck at each node examining lots of useless pointers. It's a skill on its own that gets you faster, less frustrating results once honed properly.

> Reply from daemon1
>
> There are lots of tricks and methods in data analyzing. If you only disassemble, you'll never know these techniques, and will have no experience in using them. So analyzing does actually help. And not only for one case. And it doesn't depend on knowing common norms or well-documented things. When I first analyzed game archive, I had no idea how they're usually made, and that's why it was interesting to me. When I first analyzed sound files, I had no idea about adpcm codecs or usual segmenting/frame types. And that's why it was again very interesting to analyze.
Once you have the answer through either approach, maybe you've learned something new. But probably not. I haven't learned something new in reversing games in many, many years. I tend to learn all the new approaches and techniques that relate to game data through actual development instead. But it's certainly interesting to learn new things when you come across them. Using disassembly doesn't detract from this in the slightest, and it gives you better insight into otherwise-flawed assumptions you're going to make when you're first understanding data. Traditional "analysis" in the sense that you mean it leaves the door wide open for misinterpretation that happens to line up with your dataset. I think what you're missing here is that in the context of videogame data, you typically can't do anything very meaningful with reverse engineered data without understanding it anyway. Because you already have so much of this knowledge that your analysis and intuition is entirely contingent upon, maybe you've lost sight of how you acquired a lot of it, or made the mistake of thinking the way you acquired it was the only way to acquire it.

> Reply from daemon1
>
> Not to mention that personally for me, disassembling is like instead of solving the puzzle, you're trying to find the answer in a big and badly organized book. That's not interesting. No fun. Every time I'm forced to use disassembly I feel disappointed.
The book is very well organized, but if you aren't practiced in understanding how to effectively parse it to get the information you want, it will appear badly organized. This is rather speaking to my point. Again, if time/efficiency isn't important to you, then sure, take whatever approach you want. But when you start out, it's really undeniably easier to just stare at your hex editor and step through your process of elimination than it is to get down in the dirt and learn how to navigate a big sea of disassembled code.

I'm carrying on here because I think it's pretty important for beginners to take that step. Most of the people here don't take it, which prevents them from expanding into more areas of reverse engineering. I don't see a point to limiting yourself to a little puzzle-solving sandbox. It might provide you with some sense of fun and reward for a while, but keep it up for 5 or 10 years, and after a while it will just be depressing when you look back and realize you could've been building other useful skills alongside your efforts that entire time. You're advocating a methodology that will have that very result for beginners because they'll just stare at and "analyze" data as you're advocating, until they hit their fateful wall, and retreat back into the sandbox.

This is probably central to our disagreement, where you're looking at the methodology you "like" and that works for you, I'm looking at the methodology that provides the greatest extra-activity benefit and time efficacy. In practice, I rarely need to take the debugging & disassembly route, but it's pretty nice to have the option, and have it actually be a time-effective one at that. To me you sound like one of those people that says "I hate debuggers, I only use printf" because they haven't learned how to use a debugger. 

Good talk! I wonder if anyone will ever find any of this useful.
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-10-06T20:06:13+00:00
- Post Title: Metal Gear Solid 5 (MGSV) animations

> Reply from daemon1
>
> 
Not to mention that personally for me, disassembling is like instead of solving the puzzle, you're trying to find the answer in a big and badly organized book. That's not interesting. No fun. Every time I'm forced to use disassembly I feel disappointed.

Disassembling is not having to solve any puzzle. If you're adept at disassembly, you skip to the answer. Hell, in case of opening an archive of sorts, you might even just use native code if you're good at it. Example, I stared for hours at Painkiller's encryption method using just a hex editor and a piece of paper. I got it in the end, and felt real good about my power of deduction. If I had just opened up the damn executable and looked at the code, it might have been a lot faster. Silly me. Since we're all doomed to eternal darkness anyway, those wasted hours I could have used to get drunk and be merry.
## Post #16
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-10-06T20:09:34+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from Mr.Mouse
>
> Since we're all doomed to eternal darkness anyway, those wasted hours I could have used to get drunk and be merry.
## Post #17
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-10-07T17:07:54+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from MrAdults
>
> How can you say this, when you've just spent weeks on an animation format
A week is not that much time. I usually only have a couple of hours in the evening for research, and not every day. So if we count the actual time spent it will be about 10 hours for a normal game. This including research of a model format, because it will be needed for animation, writing a tool, correcting all bugs, exporting some models and testing how it all work together. Do you say it all can be done in 1-2 hours?

> Reply from MrAdults
>
> You know as well as I do, you will make guesses, and they will be wrong.
No I will not. This may sound strange, but it's true. In most cases the format can be solved without wrong guesses. If this happens, I call it a flawless solve.

For example we have a model file I recently did - Hellboy Science of Evil PS3. In the beginning I can see a list of some offsets. This will probably be offsets to file segments with different model data, such as bones, geometry, etc. And this guess was right. I'm checking them. Some of them I can't identify yet, but this is not a wrong guess. I'm just leaving them for later.

Now one of the data arrays definitely look like bone matrices. They are easy to detect. I'm checking them and counting them. Looking at the float numbers, I detect where the global bone coordinates are. Later we'll know this was also right guess. Now I have bone count and coordinates. Checking this count and I found it in both model and animation file. This means now I know where it is written in the header. Another right guess.

Now when I know the total bone count it looks like another array I've seen before is bone remapping, because it consist of a number of lists having all numbers from 0 to total bone count minus 1. And later I'll see that this was again the right guess.

This way, one thing after another, I can solve the whole format. Of course, there may be some parts unknown for me left, but this will only happen in case I don't need them. But as soon as I'll realize I need something else, these will be easy to identify, because with each step, the amount of unknown data decreases. Just like in solving a nonogram.

So as you can see, no time wasted, everything is solved, no mistakes, no wrong guesses.

> Reply from MrAdults
>
> I got my first gamedev contract about 20 years ago
Well, I didn't say I was WORKING in this for 30 years. Most of the time it was for fun. And I never worked in gamedev. Actually I returned to this game-analyzing stuff only recently, about 3 years ago, and it was like a fresh air to me. I actually discovered what quaternions are only this spring. The time for learning what they are is also included in those 10 hours mentioned before. And I can't say they are something intuitively understandable 

Also I never said I don't use disassembly. I actually said I never decompile the whole anim engine to put it into my tool. Once I've seen that quats in morpheme are packed some unusual way, I ran the debugger, found a place where it's done, and very soon I knew it and returned back to analyze.

> Reply from MrAdults
>
> The book is very well organized
Maybe you could say that 5 or 10 years ago. But now with all this multi-threading, FPU and SSE mixed up in one line for optimization, I can actually SEE when looking at the data and the code that reads this very data, how much easier it is to understand it by data, rather then code. I've seen how they read sets of ints for 4 bones from memory, converting them to float and making SSE calculations all messed up one with another. No matter if you look at assembly or decompiled c++ it's hard to understand what it does. I think you saw it too.

The simple xor-decrypt loop optimized for 8 threads looks like a monster, and I don't know of a tool that is able to decompile it into normal human-readable code.

> Reply from MrAdults
>
> You're advocating a methodology that will have that very result for beginners because they'll just stare at and "analyze" data as you're advocating, until they hit their fateful wall, and retreat back into the sandbox.
If they take your advice and try assembly only, there's a big chance they will find it too difficult and give up for good. Again, I'm not against disassembly, I was just disagree that only this method should be used always as it seemed to me from your previous quotes. But now it looks like you don't actually mean that:

> Reply from MrAdults
>
> In practice, I rarely need to take the debugging & disassembly route

So now I think we can summarize that beginners should learn both methods and use what suits them most.
## Post #18
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-10-07T18:16:18+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from daemon1
>
> A week is not that much time. I usually only have a couple of hours in the evening for research, and not every day. So if we count the actual time spent it will be about 10 hours for a normal game. This including research of a model format, because it will be needed for animation, writing a tool, correcting all bugs, exporting some models and testing how it all work together. Do you say it all can be done in 1-2 hours?
When you account for normal human scheduling and needs, for me, an animation format like this that has a lot of nasty variations on packing that utilizes multiple spaces (which typically will only happen if IK is employed) should take something in the area of 10-20 hours with effective use of disassembly. Unfortunately, I rarely get that much time to spend in a month myself. Something simple like the Space Channel 5 animations I looked at the other night took about an hour from start to finish, including writing up the new Noesis import logic to handle it, tying it to the models, and remembering how the Ninja model format was set up. So it's very subjective. Models will generally take no time at all unless there is something very new and crazy, like the first time I ran into Edge index compression. But this has nothing to do with disassembly being inefficient, it's just because my knowledge/intuition has become vast after years of working with this data. That will happen whether you've been employing disassembly or not. This intuition in many cases is built upon prior use of disassembly to get me over a hurdle more effectively.

> Reply from daemon1
>
> No I will not. This may sound strange, but it's true. In most cases the format can be solved without wrong guesses. If this happens, I call it a flawless solve.
Sure, if your data is perfectly intuitive (like so many model formats), you're not going to waste time trying things that don't work. Your example is many worlds apart from a format that uses a proprietary means of tightly packing data through, for example, some form of variable delta compression. I'm not advocating people use disassembly to solve things that are stupidly obvious, but I'm advocating that they be able to do so if they need to. If you can't understand a quaternion or a unit-length vector when you spot it in hex, you have a lot of growing to do before any approach will be effective for you in the realm of models/animation. But you probably understand these things already if you've figured out just about any modern game + skeleton through analysis, as most people on these forums already have. Quaternions are extremely common, although I'll give you that inverse matrix transforms tend to be more popular for representing the base skeleton, for the purpose of transforming modelspace transforms for the bind pose. (with the exception of those rare games that still choose to store vertices in local space)

> Reply from daemon1
>
> I actually discovered what quaternions are only this spring. The time for learning what they are is also included in those 10 hours mentioned before. And I can't say they are something intuitively understandable
Once you understand that a quaternion is just a rotation about an axis, it's pretty intuitive. But a lot of people can never seem to wrap their brain around it. This is why I included "sometimes it's best to broaden your knowledge in the field instead of continuing to reverse engineer data you don't understand" in my initial list of suggestions.

> Reply from daemon1
>
> Again, I'm not against disassembly, I was just disagree that only this method should be used always as it seemed to me from your previous quotes.
Yeah, it's silly to use disassembly when you can look at something for an hour and have it all mapped out. Your methodology of mapping a file out I think is very common between beginners of veterans alike, the problem is when you come upon some part of that data that you spend too many hours trying to understand and there is nothing to "eliminate" to make it easier. That's when it's smarter to use disassembly. If you say you immediately intuited all of the packing types used for MGS5, I won't believe you. But if you can't use disassembly when you hit a wall, then you're just stuck. If you haven't been using it, it will take you hours or days (and I don't mean 1-2 hour days) of time to figure out how to get where you need to be. This will discourage you from switching to it, meaning you'll just keep hitting your head on the wall. Maybe eventually you'll get lucky, but you'll have wasted more time than if you had the confidence to go right over to disassembly.

> Reply from daemon1
>
> Also I never said I don't use disassembly. I actually said I never decompile the whole anim engine to put it into my tool. Once I've seen that quats in morpheme are packed some unusual way, I ran the debugger, found a place where it's done, and very soon I knew it and returned back to analyze.
Well, where you cut the line is up to you, but it's very effective either way. For example, if you have many pages of disassembly with a targeted purpose, like decoding tightly packed data with many different conditional branches, there is no reason not to isolate that code. Not to mention, if you need to go back to it to validate results, you already have it right there in front of you. No need to fire up the game and debugger all over again.

> Reply from daemon1
>
> Maybe you could say that 5 or 10 years ago. But now with all this multi-threading, FPU and SSE mixed up in one line for optimization, I can actually SEE when looking at the data and the code that reads this very data, how much easier it is to understand it by data, rather then code. I've seen how they read sets of ints for 4 bones from memory, converting them to float and making SSE calculations all messed up one with another. No matter if you look at assembly or decompiled c++ it's hard to understand what it does. I think you saw it too.

The simple xor-decrypt loop optimized for 8 threads looks like a monster, and I don't know of a tool that is able to decompile it into normal human-readable code.
You can still say it.  That is why "practice makes something resembling perfect". Compiler optimizations (particularly with SSE, I'll agree to that) and the types of job systems developers like to employ these days make it a greater kind of hell, but that's another thing where understanding what to look for, your "disassembly intuition", is very helpful. You can see where a kernel is being pushed to a job system, for example, and that actually makes your life even easier. You have that kernel right there nice and isolated to show you exactly how your data is being processed, and better yet, you probably have a structure that kernel is using that points to all the data you care about. With so many developers switching to fiber-based job systems, or otherwise a system that simply pushes some job structure to a queue, you just have to understand how that system is working. Knowing how to recognize that you're in a kernel/fiber in a lot of ways makes the job even easier and it makes it easier to isolate parts of the system.

And yeah, there is a learning curve to understanding code with compiler-generated SSE/SSE2/NEON/etc. in the mix. But you get used to it, especially if you've spent a lot of time debugging problems in this same optimized disassembly like me. You start to develop a greater intuition of what that optimized code came from or the kinds of initially-confusing decisions the compiler makes to optimize for SIMD or utilizing separate SIMD registers.

> Reply from daemon1
>
> So now I think we can summarize that beginners should learn both methods and use what suits them most.
I can generally agree on that.

I'm pretty sure the vast majority of people doing work here on Xentax, especially with 3D models and animation, have little to no disassembly experience. Hence the emphasis on learning this upfront as a tool to overcome imminent hurdles. Disassembly is a different discipline with a different type of intuition associated with it, and it will help you along the way. Of course, there are also ways to help that disassembly intuition that doesn't involve just disassembling in itself. I got a lot of free practice from debugging "impossible" crashes in multi-threaded scenarios with optimized and sometimes even intermingling of managed code in the mix. Maybe "never give up on a crash" is also good advice to accidentally becoming better at parsing disassembly.

Our workflows are probably very similar, in the end, except I view switching over to disassembly as a time-saving measure instead of a disappointment.
## Post #19
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-10-08T20:42:04+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from MrAdults
>
> utilizes multiple spaces (which typically will only happen if IK is employed)
Do you mean local/global space or something else? I may be not too good in terms, I'm no animator  How would you do exporting in this case, I mean MGSV? Does noesis have some kind of IK-solver, or you would try to isolate their IK-solving code and directly putting it into your program? How many games have you seen utilizing this kind of FK/IK mix, because another professional animator told me this is really exotic.

> Reply from MrAdults
>
> Your example is many worlds apart from a format that uses a proprietary means of tightly packing data
Yes. But still, I think 90% games are not using any tight packing. Packed quats and half-floats best case. Nothing more complex.

> Reply from MrAdults
>
> For example, if you have many pages of disassembly with a targeted purpose, like decoding tightly packed data with many different conditional branches, there is no reason not to isolate that code
I actually saw how these "many pages of disassembly for tightly packed data" can be replaced with only a few lines in C after a quick research in debugger. From what I've seen, "code isolation" is only needed in case of complex math, like audio codecs. Yes, I've seen not too many cases, and maybe there are harder ones, like maybe MGSV, but this is probably very rare.
## Post #20
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-10-09T22:45:51+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

Yeah, I was referring to local and model space. It's pretty rare these days to see animations stored completely in model space, although frequently certain hierarchies are "flattened" so they're effectively in model space in order to reduce transform overhead. Most commonly, everything is in local space. But if you're going to animate IK effectors, it makes sense to do it in model space, to make it easy to modify those effectors as-needed at runtime.

Animating IK joints and/or effectors is something I hadn't seen much of since the PS2 days. I have a 2-bone and an analytic IK solver buried in the noesis_misc module, but haven't exposed it in the public API, as animation interest hasn't been too high until, strangely, very recently. The problem is that games like to store relevant data in very different ways, especially constraints. I don't know why it was so popular specifically on PS2 titles, I think this is either a Japanese developer thing or perhaps Sony provided some common VU code/libs that hinted in this direction.

I've never seen a reason to approach IK in that way, it generally makes more sense to perform FK animation transforms, take those modelspace transforms and use them to apply IK with constraints, and optionally blend the IK in on a given hierarchy. This is the way I've always implemented it myself, and have no plans to switch over. Animating IK effectors is also basically ensuring you always have to solve for IK on a given hierarchy, which is kind of a pointless overhead, but it makes ok sense to have it only done on a per-sequence basis. (and the plus side is that this gives the animator better visibility as they're creating the animation, instead of only having the IK solver applied at runtime, and messing their animation up in a way they didn't realize would happen)

How to preserve the data is up to you - it mostly depends on how complicated it is. If you need to preserve some detailed constraint information, you might be best off dumping it out in a paired file, or a .qc file has plenty of support for constraints if you can make the data conform, since you're already exporting to .smd from the looks of it. Then you just dump the anims as FK transforms. When you export .smd back to MGS5 anims, pull the same constraint data back in (probably based on joint names), and take the modelspace transforms of the effector joints to automatically convert them back into IK sequences where needed. (you'll probably need some data preserved to also determine which animations need which joints/hierarchies IK-driven, you might just adopt a joint naming convention to make this easier) Depending on how the IK joints are animated, those might restrict the allowable techniques animators can use to change those animations (like a lot of PS2 games will animate nothing but a simple effector position for some joints, making it impossible to control custom rotations outside of the solver), but that's Just Life.
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-10-11T19:43:16+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from MrAdults
>
> Animating IK joints and/or effectors is something I hadn't seen much of since the PS2 days
Thanks for all the info. If even you say it, then what they did is really rare.

> Reply from MrAdults
>
> If you need to preserve some detailed constraint information
I'd be happy if I can do it without constraints, but now I don't see any other way to export data.

> Reply from MrAdults
>
> Then you just dump the anims as FK transforms.
Unfortunately I can't do this. There are just no FK transforms for IK bones in game files.

> Reply from MrAdults
>
> you'll probably need some data preserved to also determine which animations need which joints/hierarchies IK-driven, you might just adopt a joint naming convention to make this easier
I can't do this either. This is already defined in game for the whole character model, not individual animations.

So this game is probably the hardest game in the whole world to export animations.
## Post #22
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-10-12T00:36:19+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from daemon1
>
> Unfortunately I can't do this. There are just no FK transforms for IK bones in game files.
I meant, when you want to convert back into the game format from a limited FK-only format, you can convert your FK transforms (that you've generated by solving the IK transforms and exporting to SMD as FK) back into IK, by transforming your FK joints to modelspace, and deriving the IK transform from the modelspace transform for the joint. 

> Reply from daemon1
>
> 
I can't do this either. This is already defined in game for the whole character model, not individual animations.

So this game is probably the hardest game in the whole world to export animations.
At least, in a way, that makes it easier, since you know something is or isn't an IK joint globally. That's surprising though, that they would just have IK always active for all sequences.

But yeah, sounds like a pain in the ass format.
## Post #23
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-10-12T17:01:23+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from MrAdults
>
> At least, in a way, that makes it easier, since you know something is or isn't an IK joint globally. That's surprising though, that they would just have IK always active for all sequences.

Yes, another strange japanese thing. And they have different IK node types hardcoded in their engine. I mean they have different sets of parameters, and processed differently. I already exported human leg and human arm types, now working on robot leg. And there is also some other type in horses. Also there are types I can't find used anywhere yet, but maybe they are for some weird types of monsters/animals.
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-06T09:51:07+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

New cutscene tool. Phantom Pain cutscene support! All characters (including dogs, horses, etc)


[None](https://xentaxbackup.github.io/file/11987_None)
## Post #25
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-06T12:56:07+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

Update. Forgot to remove some debug constants. Should be fine now.
## Post #26
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-01-12T08:12:37+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

i cannot believe you did this omg THIS WAS SO NICE!. really nice!!

One question regarding other games. we have tools / script for importing exporting meshes + skels in resident evil 5 and 6, do you think that would help in the process to get the animations from the games?

Animations from re5 and re6 (specially melees and biped interactions) are very cool in those games.

i wouldnt mind to donate if you could do this.
## Post #27
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-12T15:34:18+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from rubening
>
> do you think that would help in the process to get the animations from the games?

Models are needed to get animations, yes. Main question is what type of anim engine they use, some third party, or their own.
## Post #28
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-01-12T22:33:28+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from daemon1
>
> rubening wrote:do you think that would help in the process to get the animations from the games?

Models are needed to get animations, yes. Main question is what type of anim engine they use, some third party, or their own.

to be honest i think their own, but i'm not sure. I have Lmt files(re5format animation files) from the game and i've the script to export the models too.

probably GhostBlade knows about this answer...would be nice if he could answer this question he knows a lot about this games file format.

probably the animations are the same format in devil may cry 4... Because at least the models are on the same format.

by the way could i get the.. snakes running animation without downloading the game? if you could share with me. That animation looks really good.
## Post #29
- Username: tpcrew
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jan 08, 2012 7:36 pm
- Post datetime: 2017-01-13T11:33:39+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from daemon1
>
> New cutscene tool. Phantom Pain cutscene support! All characters (including dogs, horses, etc)

Hi,
this is great! But I have a question, is there a tool to extract and import the models in 3dsmax?
thanks.

ps. I apologize if my question does not go in this thread.
## Post #30
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-17T20:04:40+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from rubening
>
> probably the animations are the same format in devil may cry 4... Because at least the models are on the same format.

I checked animations, and they are not too complex. I can even export them, but the problem is, the bone numbers don't correspond to the bones in model. So I need information why model is exported that way. I can't apply animation to bones without it.

You said its like devil may cry 4? devil may cry 4 anims can be exported?

> Reply from rubening
>
> by the way could i get the.. snakes running animation without downloading the game? if you could share with me. That animation looks really good.

No, because I don't know where is running animation, there are about 2000 of them there.
## Post #31
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-01-19T10:40:58+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from daemon1
>
> rubening wrote:probably the animations are the same format in devil may cry 4... Because at least the models are on the same format.

I checked animations, and they are not too complex. I can even export them, but the problem is, the bone numbers don't correspond to the bones in model. So I need information why model is exported that way. I can't apply animation to bones without it.

You said its like devil may cry 4? devil may cry 4 anims can be exported?
rubening wrote:by the way could i get the.. snakes running animation without downloading the game? if you could share with me. That animation looks really good.

No, because I don't know where is running animation, there are about 2000 of them there.

wow great.. maybe if i give you the 3dmax script for re5/dvmaycry and re6 ? could that help?


( I SENT YOU THE LINK in your profile/ check your message box)

must be one of both, since both are versions for re5 i think. i added a "mod" file which is a re5 character, and i added a lmt(pack of animations, unpacked) so any motion file there is an animation.
## Post #32
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-19T15:23:13+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from rubening
>
> You said its like devil may cry 4? devil may cry 4 anims can be exported?

maybe if i give you the 3dmax script for re5/dvmaycry and re6 ? could that help?

No it wont help. You better send me model converted to some format that I can read in blender.

Also I still dont have a clear picture, if devil may cry 4 animations CAN be imported now?
## Post #33
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-01-19T16:39:00+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

[https://github.com/Brachi/albam/releases/tag/v0.2.0](https://github.com/Brachi/albam/releases/tag/v0.2.0)

[https://mega.nz/#!uoNGDLCZ!eq0-cyxKZKDN ... _7sQOhJ71I](https://mega.nz/#!uoNGDLCZ!eq0-cyxKZKDNAXscJNGh7LAy51_CuZ_Pd_7sQOhJ71I)

the model and the script to import in blender the ARC files;)
## Post #34
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-19T16:48:42+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

I'm asking for the 3rd time:

can devil may cry 4 animations be exported or not?
## Post #35
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-01-19T17:32:44+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from daemon1
>
> I'm asking for the 3rd time:

can devil may cry 4 animations be exported or not?
lol sorry
 i never heared of that, i also dontg play that game to know about its resources, but i searched now in google and i couldn find anything

maximum i found is this : [viewtopic.php?f=10&t=3057&start=285](http://forum.xentax.com/viewtopic.php?f=10&t=3057&start=285)
## Post #36
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-19T18:10:44+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

Ok thanks. You just said the format was similar, so I wanted to be sure that animations are not yet supported.

Well, bone numbers I'm getting from this script are the same as I got from noesis. So I'm afraid, to get the animations applied to bones, I need to research the whole ARC format again to find where this information may be.

I will notify you if I find anything.
## Post #37
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-01-19T18:14:48+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from daemon1
>
> Ok thanks. You just said the format was similar, so I wanted to be sure that animations are not yet supported.

Well, bone numbers I'm getting from this script are the same as I got from noesis. So I'm afraid, to get the animations applied to bones, I need to research the whole ARC format again to find where this information may be.

I will notify you if I find anything.

well similar because , seems to work with the importer/exporter that is used for re5 and re6...
or at least thats what i read.

in the personal message i sent you one of the files is "MOD" file this is the model file, maybe its easier to find for you there instead the arc.
## Post #38
- Username: rubening
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-01-19T20:04:19+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from daemon1
>
> Ok thanks. You just said the format was similar, so I wanted to be sure that animations are not yet supported.

Well, bone numbers I'm getting from this script are the same as I got from noesis. So I'm afraid, to get the animations applied to bones, I need to research the whole ARC format again to find where this information may be.

I will notify you if I find anything.
How are you reading the data? For RE5 animations, The joint number is stored as an unsigned char followed by a float which is the weight. If you mean that the joint numbers do not remap correctly to the ones from exported skeletal files. That's really weird, perhaps you're reading the file incorrectly? Here is the "official struct" with joint info:

```
{
    unsigned char type;
    unsigned char usage;
    unsigned char jointType;
    unsigned char jointNumber;
    float weight;
    unsigned int parameterSize;
    unsigned int parameterOffset;
    MTFloat4 value;
};

```


Cheers.
## Post #39
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-19T20:10:57+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from Gh0stBlade
>
> perhaps you're reading the file incorrectly?

I'm reading the files correctly. The format was easy to reverse, but the joint numbers do not remap correctly to the exported skeletal model files.
## Post #40
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-19T20:22:58+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

I will need to study all the files inside ARC archive, including MOD files, to find some kind of remapping table.
## Post #41
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-19T20:46:34+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

From what I can see in files sent by rubening, somebody already tried to reverse the animation format, and split the basic structure. But probably faced the problem of bone numbers...
## Post #42
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-01-19T21:04:41+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from daemon1
>
> From what I can see in files sent by rubening, somebody already tried to reverse the animation format, and split the basic structure. But probably faced the problem of bone numbers...
The purpose of almost all files are known in the MTFramework. I do doubt there is some file storing bone remap information. The info might be in .JEX files though, that's the only suggestion I can make. Sending a sample via PM

Edit: IIRC Bones from the PC version are different. I would suggest trying X360 models.
## Post #43
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2017-01-20T03:11:33+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

Probably it would be better to create another thread for Capcom's animations, it's been a while and no research was ever completed AFAIK.
There was a tool to export Devil May Cry 4 animations to a text file to be used in 3ds max.

> Reply from daemon1
>
> I will need to study all the files inside ARC archive, including MOD files, to find some kind of remapping table.
[Here](http://residentevilmodding.boards.net/thread/6320/capcoms-mtframework-mod-format-research) I posted the mod structure (the mod version for RE5 is 156, Devil May cry 154 I think), there are still a few unknowns.
Every mesh has a 'bone_map_id'. A bone_map_id has its size(int) and then up to 32 values (bytes). The indices in the skeleton are mapped to those values, 255 means no value.
[Here](https://github.com/Brachi/albam/blob/develop/albam/mtframework/blender_import.py#L345) is how I parse it.
There's also an array of 256 values I called unk_13. What I found is that it maps to groups of bones for each model. E.g. from indices 0 to 32 will map to arms and legs. Probably to swap animations easily in any model (as shown [here](https://www.youtube.com/watch?v=JV4MOTf9N1k), animations go pretty smoothly with different models in cutscenes).
## Post #44
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-20T04:24:23+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from Bastien
>
> There's also an array of 256 values I called unk_13. What I found is that it maps to groups of bones for each model. E.g. from indices 0 to 32 will map to arms and legs. Probably to swap animations easily in any model

That must be it, I will check. Because bone indices are different in all models, and in animations they are the same.
## Post #45
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-20T15:16:18+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

I checked. Yes, thats it! So that "unk_13" in MOD file is actually a bone remap table for animations.
## Post #46
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-20T18:09:19+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

RE5 discussion goes to this new thread:

[viewtopic.php?f=16&t=15765](http://forum.xentax.com/viewtopic.php?f=16&t=15765)
## Post #47
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-26T17:37:14+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

Horse test
[https://www.youtube.com/watch?v=ss3wNYDdYEc](https://www.youtube.com/watch?v=ss3wNYDdYEc)
[https://www.youtube.com/watch?v=spE0lItzgUI](https://www.youtube.com/watch?v=spE0lItzgUI)
## Post #48
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-27T15:31:50+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

Horse animations tool
[https://www.youtube.com/watch?v=PZolKsvWH1M](https://www.youtube.com/watch?v=PZolKsvWH1M)
IK pole vectors are not applied on this video, so you can see some improper positions



hrs0_main0_def.fmdl  model must be in the same dir, tool needs it for bones.
fmdl_dictionary.txt has all known horse bones, 2 bone names are still used as hashes

leg IK:
- IK_TARGET_ ... bones are targets for nails (position+rotation)
- IK_pole_ ... (pole vectors) must be applied somehow

There is one additional rotation for each leg, thats supposed to set feet rotation, these are not extracted, because I don't know how to apply them.
[mgs5_horse.rar](https://xentaxbackup.github.io/file/23908_mgs5_horse.rar)
## Post #49
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-05-29T07:21:04+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

is it possible to convert models itself?
## Post #50
- Username: leus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 22, 2020 1:00 am
- Post datetime: 2020-10-21T19:41:52+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

Hello - I know this is an old topic, but I wonder if the code for the .GANI file format is available anywhere. I want to get one or two animations (in .gani format) from PES2020 (Fox engine) just for testing models vertex weights (all face models in the game use the same skeleton).

Cheers!
## Post #51
- Username: Bungdrtyu
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jan 13, 2023 1:04 am
- Post datetime: 2023-01-12T17:07:59+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

Is there any chance the tool could be re-uploaded? The latest link is dead unfortunately.

Thank you
## Post #52
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-01-12T19:18:32+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

its still up on zenhax (link in 2nd post here)
## Post #53
- Username: Bungdrtyu
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jan 13, 2023 1:04 am
- Post datetime: 2023-01-26T22:04:35+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

Hi Daemon,

The tool is working great for the majority of the cutscenes, however I can't seem to get it to work for cutscene p81_000010.

The sand and fsm files are named the same and the scene contains the camera, and 2 snake skeleton performances. I think it's the scene where he punches the mirror.

I've used every snake fmdl file to convert the scenes into smd but it's just not working. I've used snakes skeleton from ground zeroes too. The error is

Unhandled exception: System IO end of stream exception. Unable to read beyond end of stream.

There's also another error that says
"Unhandled exception: System.ArgumentException: An item with the same key value has already been added. At systems collection.generic.dictionary`2.insert(Tkey key, Tvalue value, Boolean add) at mgs5_anims.mgs5_anims.Main(string[] args)

I can only imagine I don't have the right skeleton but I've tried 9 different snake skeletons now and it refuses. Is the cutscene broken or something?

Do you have any ideas what's happening?
## Post #54
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-01-27T15:56:53+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from Bungdrtyu ↑Fri Jan 27, 2023 6:04 am at Fri Jan 27, 2023 6:04 am
>
> 
Do you have any ideas what's happening?
i think its because of the mirror
as a result, one animation has 2 snake skeletons, and probably tool does not expect that so it crashes
## Post #55
- Username: Bungdrtyu
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jan 13, 2023 1:04 am
- Post datetime: 2023-01-27T19:21:19+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from daemon1 ↑Fri Jan 27, 2023 11:56 pm at Fri Jan 27, 2023 11:56 pm
>
> 
Bungdrtyu wrote: ↑Fri Jan 27, 2023 6:04 am
Do you have any ideas what's happening?

i think its because of the mirror
as a result, one animation has 2 snake skeletons, and probably tool does not expect that so it crashes

Hi Daemon, thanks for the reply.

Is there a way to add to the missing hashes in the tool? I'm happy to add them where I find out what they relate to.

Also, may I ask how I get the smd body meshes into blender? I only have the skeleton animation when I import into blender.

P.s I accidently reported your reply (I thought I was replying to you) apologies for the error.
## Post #56
- Username: sepinood
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 26, 2019 5:32 pm
- Post datetime: 2023-06-11T13:17:56+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from daemon1 ↑Sun May 27, 2018 11:31 pm at Sun May 27, 2018 11:31 pm
>
> 
Horse animations tool
https://www.youtube.com/watch?v=PZolKsvWH1M
IK pole vectors are not applied on this video, so you can see some improper positions



hrs0_main0_def.fmdl  model must be in the same dir, tool needs it for bones.
fmdl_dictionary.txt has all known horse bones, 2 bone names are still used as hashes

leg IK:
- IK_TARGET_ ... bones are targets for nails (position+rotation)
- IK_pole_ ... (pole vectors) must be applied somehow

There is one additional rotation for each leg, thats supposed to set feet rotation, these are not extracted, because I don't know how to apply them.
would you please reupload the tools all the link is dead. thanks
## Post #57
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-06-11T15:52:28+00:00
- Post Title: Re: Metal Gear Solid 5 (MGSV) animations

> Reply from sepinood ↑Sun Jun 11, 2023 9:17 pm at Sun Jun 11, 2023 9:17 pm
>
> 
would you please reupload the tools all the link is dead. thanks
zenhax is down. Probably forever. But you can always use wayback machine to get saved pages:

[web.archive.org](https://web.archive.org/web/20230514014102/http://zenhax.com/viewtopic.php?f=5&t=3172)

Also updated links here.
