## Post #1
- Username: liDante
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 17, 2013 9:12 pm
- Post datetime: 2013-09-18T12:22:08+00:00
- Post Title: [Question] Looking to learn...

Hi there!

My name is Dante, I'm 22 and from London, United Kingdom (The city of Rain and the colour grey).

Anywho, I'm here because I'm tired of the same thing, day in and day out, every day the same monotonous task(s) of life and doing boring crap to keep myself happy from time to time. Just last week, I spent over 250 hours on the frigging cookie clicker game... Just to keep myself from being bored out of my mind, which by the way, became extremely painful and boring in itself... Funny how the things we enjoy become boring and annoying over time. 

I want to do something new, something fresh, something that I won't look at and go "Meh... It's boring me" something that I can use in day to day life, something that others will look upon and actually note that it is good as opposed to saying "What did you do? What is that? Oh look, it's a pigeon" etc. See, I live in a house with two other people, who know nothing, and I mean, nothing, about computing or gaming or anything relating to computers whatsoever. I kid you not, they actually struggled to find the power button on my computer (Was hilarious by the way, kept me entertained for about 10 minutes); but that's not the point. 

I was looking at perhaps learning a new language (code) or something, and I asked a few friends who are rather savvy with the way code works and how to implement it into a project properly etc, and they have all suggested to me - learn C++ & LUA, to quote one of them, let's say Barry - "C++ will let you do anything you want to do, and LUA will work alongside it" which might not sound like much to anyone, but that - that line alone, made me almost ecstatic & giddy like a small child seeing chocolate for the first time... (Yeah, I get excitable about anything... Even food); so, what would you guys suggest?

Should I dive in and learn C++ & LUA? Should I take a jump here and move away from map making and textures? I'm bored of that, it's tedious now. I want a new challenge, something that won't take me 15 minutes to learn and get bored of. If so, where should I begin? Any recommendations on tutorials or classes to take? 

Sorry for the tyrannosaurus text, 

I like to type. 

Dante.
## Post #2
- Username: jaycenornin
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 28, 2007 7:07 am
- Post datetime: 2013-09-18T19:26:33+00:00
- Post Title: [Question] Looking to learn...

Hi Dante!

Welcome to Xentax 

I'm looking at starting a new learning project and so far I haven't advertised it anywhere but on facebook to my friends. If it's something that might interest you, then I could definitely use some help. Details follow  I think I'll need the most help with 3D texture art, scripting, and the game server. My typical development style is to design the interface first, and then build the back end off of that.

Mechwarrior 1 - Redux MMO

Prerequisite
You must have played Mechwarrior 1.
[http://www.abandonia.com/en/games/471/Mechwarrior.html/](http://www.abandonia.com/en/games/471/Mechwarrior.html/)

Purpose
A proof of concept game, designed to demonstrate not only the feasibility but also the popularity of role-playing in a multiplayer Battletech universe.

The idea here is to produce a battletech universe game that incorporates more than just the combat simulation. One of the best parts about MW1 was that there was more to do in the game than just blow stuff up (as much fun as that is). I'd like to make a MW game with a whole inner sphere to explore. Where a player can actually make a character and play that character inside a vast and wonderful universe.

Platform
The game client will be designed for PC using the Unity game engine. 3D modelling will be done in Blender. Game dynamics will be largely Javascript within Unity.
We can also use CryEngine 3 SDK, but that's a bit higher of a learning curve. It would, however, make better use of skills in C++ and LUA if you're interested in developing those.
The game server will have to be built entirely from scratch using C++ or C# and LUA. It will need to handle player-player communications and transactions, player-computer transactions, game saving, etc etc - a lot.

Game content - mechs, worlds, etc, will have descriptive data stored in XML (or LUA) files for easy modification and adjustment.

Design
The game will be designed with an interface like Mechwarrior 1, adapted for MMO multiplayer. Combat simulator will be left out (or developed last).

The "Command Center" will be the icon in the upper left of the main screen. From here the player will be able to view vital personal and unit statistics, receive news information (fed by developers), manage unit members/mechs, and send/receive messages from unit members (both in Private Messages and group chat with all online members).

The "Marketplace" will be the middle left icon. From here the player can purchase supplies and commodities. Links from here will lead to a mech lab for reloading/repairing mechs, a market place for buying/selling mechs and ammo, and a marketplace for buying/selling commodities (for trading simulation).

The "Contracts" icon will be the lower left icon. From here a player can bid on contracts for attack/defense, trading, transportation etc - whatever we can think of. There will be two options here - to view local contracts offered by political and economic organizations on this particular world, and contracts offered globally by the different houses, large merc units, or larger interstellar companies. Negotiation will likely operate in a manner similar to the contracts negotiation in MW1, but may involve more of an auction style where players actually compete for specific contracts.

The options screen will be accessible from the lower right icon; graphics settings etc will be available here.

The "Lounge" will be the middle right icon. This will be a "Zoned" chat room for all players currently active on the same planet as the player. This is a good place to spend time, be social, negotiate player-player transactions, or recruit for your unit. New players will want to start out here and will probably have to join another unit before earning enough money to set out on their own.

The "Travel" screen will be accessible from the upper right icon. This will present the player with a 3d map of the inner sphere. Players can select a star/world and view pertinent information on that world - economics, politics, defenses, etc. The player can then travel to a selected world by clicking the "travel" button available on this screen. Travel will be instantaneous, to avoid messing with synchronizing multiplayer calendars. Each world will have a unique background for its starport, an independent chat room (bar), and unique local contracts.

If development progresses rapidly and successfully, we may incorporate role-playing beyond each world's starport - including exploring the local town and meeting NPCs with interesting side quests.

All quests will be dynamically generated, just like the contracts were in MW1, though with a bit more variety.

In order to simplify development, there will be no advanced 3D animation and graphics - such as combat simulation comparable to MechWarrior Online. This is primarily proof of concept, not a full on game. Prove that people will like it and we can get IGP to do it. Or maybe, if we're lucky, get Topps to license us to develop a full game.

If we do get as far as combat simulation, we'll start with instant action style combat on Solaris 7. From there we'll program contract matchups where players' units with defense contracts meet up against players' units with attack contracts on specific worlds. The results of these matches will affect political borders, economics, and available future contracts. Combat graphics and gameplay will not be advanced to compare with MW:O or MW:Tactics - we don't want to compete with these other MW games. I'm currently postulating a turn-based strategy system similar to The Crescent Hawks: Inception, built on 3025 rules. 

If we get licensed by Topps (the Battletech IP owners) to produce a full game, we'll make money by having a dual free to play paradigm coupled with a subscription paradigm. There will be multiple kinds of subscriptions. Essentially, the subscription will work as the character purchasing a type of license. A "Davion Mercenary" license, for example, will cost say $2 a month and give the player access to better Davion contracts and combat salvage etc. A "Davion Merchant" license will give the player bonuses in the marketplaces on Federated Suns worlds. A "Davion Military" license contracts the character as a member of the FedSuns military - requiring the unit to only take FedSuns contracts, but opening up advanced R&D equipment and unique contracts/quests and possibly also making repairs/reloads free (military issue).

Last night I was considering redoing the licensing structure - so F2P players can only take local (single world) contracts, most of which will be garrison duty and minor skirmishes, or arena matches on Solaris. A house merc license would be required to get house contracts.

But for now, this is not a money-making venture. It's purely educational and proof-of-concept. Development builds will be downloadable from a web site I'll host and I'll probably set up the game server locally. Because this game would use an existing IP without a license, there's potentially some legal mumbo jumbo, but I'll deal with that. I'll be contacting Topps' legal department this week to talk about licensing the IP.

So... Interested?

:Edit:
My post is bigger than your post
## Post #3
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2013-09-18T20:59:56+00:00
- Post Title: [Question] Looking to learn...

I'd recommend learning C, then C++. C++ will seem less esoteric if you already know C. I'd also recommend choosing whatever scripting language you like; I recommend Python, Ruby, or LUA. Personally I use Python and C primarily. It may also be beneficial to learn the scripting language first, they tend to be pretty forgiving and there are large communities that can help you. Also make yourself familiar with StackExchange. Those folks will likely help you more than anywhere in the world.
## Post #4
- Username: jaycenornin
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 28, 2007 7:07 am
- Post datetime: 2013-09-18T23:28:24+00:00
- Post Title: [Question] Looking to learn...

When it comes to learning programming and scripting languages, what you choose to learn will depend greatly upon what you intend to do with it. C++ and LUA are great for game design and modding. C#, VB and VB#, and a few others are great for designing desktop applications (specifically for Windows - Linux and Mac are still largely in the C++ stone age). If you're going to be an IT guy, like I am, you'll want to know Batch, VBS, and PowerShell for Windows.

Since this is a game-centric forum, I assume you're probably looking for stuffy to do that's related to games. C++ is still the de facto standard for game development, even though there are much newer, more efficient, higher level languages out there to code in. LUA is a newer standard for game extensibility, but so far I think CryEngine is the only major game engine to fully support it (I haven't looked at Unreal Engine in a while). C# is gaining a foothold in game development and is fully supported by Unity.

One skill that I think could get you VERY far is shader coding. It's almost entirely math - lots of calculus. But it's so necessary.
## Post #5
- Username: jaycenornin
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-09-19T00:13:33+00:00
- Post Title: [Question] Looking to learn...

In order of preference, I would say:

1) Run far away, use your time on a woman or something.
2) Learn the intricacies of the Commodore 64 and write something amazing in 6502.
3) Pick an existing game engine+framework and let that dictate which language(s) you start with, to get the biggest immediate bang for your buck. (being able to immediately implement and tinker with things as opposed to going down a long road before you reach that point) I would go back and make pornographic mods for Quake, personally.
4) Learn C/C++, become amazing at low-level optimization and systems engineering, get a high-paying job, and work your life away for faceless consumers and/or corporations until you realize you put all that effort in just so you could come up with the same cookie-cutter engineering solutions as everyone else with a bit of altogether meaningless variation. Then go back to 1.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-09-20T04:08:43+00:00
- Post Title: [Question] Looking to learn...

Ya I'd start with a game engine or pick up one of those game modding packs and start picking up some skills from there.
The most important thing is not to have fun, but to be able to give yourself results. To measure your growth. To be able to say you put in 250 hours of your life and got something to show.

If you got some badges for that cookie clicking, it may still be a good 250 hours spent.
## Post #7
- Username: liDante
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 17, 2013 9:12 pm
- Post datetime: 2013-09-21T11:17:08+00:00
- Post Title: [Question] Looking to learn...

Well, 

I've enjoyed reading some of the comments and feedback, especially the ones that hold cookie clicker in regard. I know it was time well spent wasted and I could have put it to better use. I have nothing to show for the hours I put into that game. Basically I was running through a real bad patch in terms of everything (Life, Job, Relationship(s)) etc. But now, I've had enough of the same crap every single day and wanted to do something better with my time. 

C++ is something I'd like to learn, but again - I wouldn't know where to begin and some of the tutorials on YouTube and other places alike do not really explain much in terms of what the functions do, or how they work, or why they are using them, they only tell me to put "This command here to make this say 'Hello World'" which is all well and good, but that would not really teach me much in terms of using the code for myself, it would only teach me how to copy a code as opposed to creating and tinkering with my own. (I know how that sounded)

So in all honest opinion, which would be the best for me to begin with? Would you recommend C++ as a starting language, or perhaps something a little more basic and eventually work my way up?

So you can see the extent of wasted time, here is an image cap I just took of Raptr.
## Post #8
- Username: jaycenornin
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 28, 2007 7:07 am
- Post datetime: 2013-09-21T19:10:16+00:00
- Post Title: [Question] Looking to learn...

> Reply from liDante
>
> 
So in all honest opinion, which would be the best for me to begin with? Would you recommend C++ as a starting language, or perhaps something a little more basic and eventually work my way up?

So you can see the extent of wasted time, here is an image cap I just took of Raptr.

I played Cookie Clicker and got addicted to it and finally quit after about 30 hours; I've been clean now for several weeks. There is no benefit to it, it's purely a Pavlovian dopamine dispenser.

Java is a great starting language. It's simple and its syntax and structure are fairly common in C based languages. It's a great way to learn programming concepts and principles without getting too deep into the low-level nonsense that is C++, but still give you enough familiarity to be able to transition to C++ without getting lost. Java is frequently the "starter language" taught in CS 100 classes at universities.

I also recommend Visual Basic. It's structure and syntax are wildly different from Java and C++, which is a great thing to help you learn about programming concepts without attaching those concepts to specific languages. Lot's of scripting languages have similarities to VB as well, so it will help round out your abilities. I actually started VB by programming in MS Office with the built in "Visual Basic for Applications" scripting functionality, which has LOADS of instructions, help, reference, and samples built into the Office help system.

I suggest that you actually buy a book. A college text book wouldn't be bad. Read it and do the assignments in it. Yes, your first several projects are only going to be "put this code here to make it say 'Hello World'," but later when the projects get more detailed, you'll start to see how it all fits together and you'll look at the author and say "Oh, I see what you did there." It's learning by doing rather than rote lecture; create a simple program first, then the book tears it down to explain what you just did.

I also recommend that you find a couple of open source projects to look at. You can find open source projects on SourceForge and download the source code and rip into it with your IDE (integrated development environment) of choice. If you do this first, however, you'll probably not understand what you're looking at, so wait until after you've done a few basic projects and understand the differences between - and purposes for - classes, methods, functions etc.

Lastly, if you are a student enrolled at a college or university (and/or have a .edu e-mail address you can use), register for Microsoft DreamSpark. It's Microsoft giving away a whole bunch of their products (including the full version of Visual Studio Professional, Windows Server, SQL Server and so much more) to students for free. And yes, you can use these products for commercial purposes (with a few caveats, read the EULA).

:EDIT:
I should append.
There are high level programming languages and low level programming languages. Low level languages are a lot more esoteric, barely a step above machine code. Actually, Machine Code is a perfect example of a low level language - it has no instructions or utilities except what the hardware directly understands and operates with. The advantage of low level languages is that you can program very efficiently. There is almost no wasted space in your programs, they have virtually no processing overhead, and they run extremely quickly. The disadvantages of low level languages are that they are incredibly difficult to write and that they are often very hardware dependent - programs written on one hardware platform may not run on a different hardware platform.

High level languages, on the other hand, are very easy to read and understand. The syntax and instructions are often written in plain enough English that a lay-person can read a block of code and get a basic idea of what it's supposed to do (this concept is called abstraction). The advantage is that these languages are much easier to learn and use and a program written on one hardware platform can be compiled to run on nearly any other platform. The disadvantage is that your program has to be converted into machine code by an interpreter before it can run on any given computer, which uses up resources and slows down the operation of the computer and your program.

Java is a high level language. It's easy to learn, understand, and code. So are C#, Perl, and Python. C++ is kind of in the middle with some abstraction, but also a lot of difficult to understand lower-level junk. C++ has been evolving for decades and it's still a useful language (and more importantly, a widely used language), but there are many features and concepts that it simply can not support.

It will be much easier for you to cut your teeth on a high level language. The down side is that if you learn Java or C# and then go back to do C++ you're going to get really frustrated that C++ can't do all of these things you learned how to do in Java and C#. What, no garbage collector? Seriously?
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-09-23T00:17:09+00:00
- Post Title: [Question] Looking to learn...

I recommend thinking about why you want to learn to code.
You should have goals in mind before going out and figuring out how to achieve your goal.

Randomly looking at things might work, but most structured teaching courses use exercises and assignments as a way of measuring learning progress as well as to force you to think about how to use the things you're learning.

Being able to print "Hello world" means nothing if you are unable to figure out when that might be useful.
## Post #10
- Username: Dchaps
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 22, 2013 12:44 pm
- Post datetime: 2013-09-23T02:23:59+00:00
- Post Title: [Question] Looking to learn...

Hey Dante, I am very new here myself, and your will to learn reminds me of myself, for over a year now I've been pretty much in the same boat, trying to figure out what programming languages to delve into and what to spend my time on. I've also had a lot of interest in tearing apart video games with modifications and stretching a game to its limit of possibility's. I started pecking away at C first because C++ is a derivative of C and i was told to go this route. I started learning very basic stuff like writing C calculators, file re namers, dumping strings to text files, understanding loops, arrays, pointers and just very basic concepts like that.The beauty of programming is alot of concepts learned in one language are universal so you can carry over your knowledge when its time to partake in another but I recommend sticking with one and pushing hard at it, even when things get tough.  I have a thirst for knowledge like a lot of people in this world, I even went around in my city, hitting every library, book store, thrift stores looking for used books on computing and various programming languages. Some of the elite coders here will probably laugh at me but I started practicing with visual basic 6 a tad to since creating a GUI is so easy and you literally just punch the code in after. I've tried my hand at 3d modeling and the more artsy stuff at one point but its to much focus on mundane detail for me, I personally would rather stick to coding. My interest/motivation for learning coding is primarily to write tool sets and applications for my own personal video game modification purposes. Everyone has a reason behind why they want to get into this stuff so just like others here have suggested you have to find a goal to pursue so you can take steps at advancing towards it. Anyways you remind me very much of myself but if you want to start basic I really would suggest C, its fun & easy in its basic form and with the right attitude and will power to move forward good things will happen.

- Derek


*edit* this is my 1st post here haha
