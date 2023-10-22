## Post #1
- Username: OmniDo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 11, 2004 2:50 pm
- Post datetime: 2004-10-11T07:01:51+00:00
- Post Title: m4b Files from Myst 4 Revelation

Hello all. 
I am somewhat new here, but being a fan of Mr. Mouse's work, I decided to join up and post a few Q's. 

First off, Id like to congradulate Mr. Mouse on all his work thus far, as well as anyone who participated in assistance for the development of MultiEx commander. Specifically, the TREArchiver for Starwars Galaxies. 

Now for my next question. 
Is there any chance that a similar program can be developed / modified for Myst 4 Game files? They all appear to be extremely large. 
The only clue I had was the zlib.dll in one of the data folders, as well as hints from other coders who claim they extracted .ogg files from the Myst 4 Demo. 

Anyone got any ideas? 
Mr. Mouse?
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-10-12T20:56:06+00:00
- Post Title: m4b Files from Myst 4 Revelation

Well, thanks for joining!  Be welcome!

We could examine the files, sure. But is there any demo or another way of obtaining examples of the files? Perhaps some small ones?
## Post #3
- Username: OmniDo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 11, 2004 2:50 pm
- Post datetime: 2004-10-13T07:03:10+00:00
- Post Title: m4b Files from Myst 4 Revelation

The only file thats sendable is one that is 469K.
The rest are incredibly huge, i.e the next smallest is 86MB, which would be one heck of an excessive attachment.

Im interested in accessing all the data in the files (if possible) but sending them all would be impossible.

I will attach the smallest one here, and perhaps we can cross our fingers and hope the rest use the same packing formatÂ¿ 

Here goes. 
[video_1.rar](https://xentaxbackup.github.io/file/75_video_1.rar)
## Post #4
- Username: OmniDo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 11, 2004 2:50 pm
- Post datetime: 2004-10-13T07:15:27+00:00
- Post Title: m4b Files from Myst 4 Revelation

Another thing that is of great intrest to me is the coding tools / software you utilize to accomplish most of your data analysis.
I noticed on your public profile that you admit to an interest in philsophy, politics, and music.

I, too, am a philosopher, musician, and creative writer.
Ive always wanted to delve into the world of assembly language and attempt to understand coding and data analysis at its core, but ive found scarce reference material or competant instructors that could simplify the process of syntax and computer systems, as well as data systems.
Would it be asking too much Mr. Mouse for a point in the right direction?
Ive already looked around for any Idiots Guides to Assembly or programming, and none have sufficed for dismantling other program information or disassembling other data representation(s).

Any ideas would be greatly appreciated. 
I like to get my hands dirty, or my fingertips dusty, as it were, whenever possible.
## Post #5
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-10-14T05:20:44+00:00
- Post Title: m4b Files from Myst 4 Revelation

I don't think Mr. Mouse, has done much assembly, well other than with the commodore chipsets .  And then it depends on what CPU you are assembling for.  As for programming, there are hundreds of tutorials on hundreds of different programming languages.  Pascal, Object Pascal, C, C++, Java, PHP, Perl, Cobol, Ada, Cold fusion, Basica, GW-Basic, QBasic, Visual Basic, Business Basics (TBred, BBx), C#.  And this is just a small handful of languages.  Where would you like to start?  Mr Mouse, is mainly a hobby coder and is experienced in Visual Basic, as where myself, I use Object Pascal/C/C++, the most, although it depends on what i need to accomplish.

As for Mexcom, the user interface and scriptor, is done by Mr Mouse in Visual Basic (5? i think).  As where i'm designing the plugin interface which is in Delphi, but will interface with his application.

I've always felt the best way to learn was to jump in.  I'm sure your welcome to ask questions, and either Mr Mouse or myself will respond.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-10-14T07:42:27+00:00
- Post Title: m4b Files from Myst 4 Revelation

As you can see from my programming CV, 
[http://www.xentax.com/html/zuurmancv.html](http://www.xentax.com/html/zuurmancv.html) 
I have programmed in assembly on the Commodore machines and on the IBM PC's, Rahly , get your facts straight. 
I have created a number of graphic demos and utilities, with routines completely in assembly. I also adressed EMS in assembly (to store large amounts of images), as well as mouse routines etc...etc... 

Here's a small graphical example, I did it for the guys of our LAN party group, the NWP crew. [http://www.xentax.com/downloads/oldcode ... WPDemo.zip](http://www.xentax.com/downloads/oldcode/mr.mouse/NWPDemo.zip)

As for MultiEx Commander, the DOS version I wrote in Turbo C/Assembly. 

The win32 version I wrote in Visual Basic 6, and created support programs in Visual C++ when necessary (when VB lacked in ability, yet again). 

The current version however does not rely on those support programs in VC++ anymore, as they were mainly used to solidly work with the old 16-bit multiex.exe from the DOS days. After the conversion of all old scripts, the 16-bit multiex became obsolete and with it, these support programs. 

Finally, I agree with Rahly that you just have to dive in. There are a lot of tutorials on the net, you just have to decide which programming language you want to use. I chose to recreate MultiEx Commander for Windows in VB6, as that was probably the easiest way for me to quickly have a Windows version. The language is pretty easy, yet not that powerful as VC++, Delphi, Python or others. For a beginner, to understand the way programming works, I would recommend it, but also look at Delphi. 

I would not recommend assembly at all, especially not when you're just starting. Today, the compilers of the best languages have been heavily optimized to create solid and fast assembly code from the scripts people write. Consequently, few still write in assembly.
## Post #7
- Username: OmniDo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 11, 2004 2:50 pm
- Post datetime: 2004-10-16T01:21:27+00:00
- Post Title: m4b Files from Myst 4 Revelation

Hrmm...interesting, as I was always under the impression from my brief experience with assembly that it was considered "God's Language" because if you are coding for x86 architecture, you can literally tell the processor what to do, instruction by instruction.
While this may seem tedious and boring (what coding isnt?) it still is nonetheless the most direct method to controlling a PC.

However, where to begin?
Umm... ok let me ask this:
Suppose I wanted to start coding for a Win32 enviornment, say Windows XP. 
I want a language that can do ANYTHING, and I do mean anything. 
No exceptions.
I dont want to have to switch languges or coding formats or syntaxes just because so-and-so programming languge doesnt offer support for X.

I want a coding language that, bar none, has no limits to what you want to do with it, all the way down to a bootloader for my PC (should I feel so inclined or bored to code one) if I want to control every aspect of my PC.

Ive been told there are various coding languages for various applications. Quite simply, Id like to start with one that can do it all. Thus far, to the best of my knowledge, there is nothing that assembly cannot do.
Granted, you'd have to translate it to be compatible with multiple platforms, but if Im just sticking to x86 architecture, then a PC is just a PC.

Anyway, thanks for all the suggesstions and Im open to more. =)

By the way, any luck with that Myst 4 data file? Im anxious to see what you can turn up by way of developing a method to extract its resource files. 

In case it might have been missed, I included an attachment with one of the previous posts.
## Post #8
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-10-16T04:33:39+00:00
- Post Title: m4b Files from Myst 4 Revelation

> Reply from Mr.Mouse
>
> As you can see from my programming CV, 
http://www.xentax.com/html/zuurmancv.html 
I have programmed in assembly on the Commodore machines and on the IBM PC's, Rahly , get your facts straight. 
I have created a number of graphic demos and utilities, with routines completely in assembly. I also adressed EMS in assembly (to store large amounts of images), as well as mouse routines etc...etc...

Like i said "I think" not "I know" 

> Reply from Mr.Mouse
>
> Finally, I agree with Rahly that you just have to dive in. There are a lot of tutorials on the net, you just have to decide which programming language you want to use. I chose to recreate MultiEx Commander for Windows in VB6, as that was probably the easiest way for me to quickly have a Windows version. The language is pretty easy, yet not that powerful as VC++, Delphi, Python or others. For a beginner, to understand the way programming works, I would recommend it, but also look at Delphi.

I would not recommend assembly at all, especially not when you're just starting. Today, the compilers of the best languages have been heavily optimized to create solid and fast assembly code from the scripts people write. Consequently, few still write in assembly.

Actually, a lot of people still write in assembly, they just don't write an entire program in assembly.  Most of the people who do end up writing assembly, write it inline with their c/c++/delphi code.  For the most part, Mr Mouse is right, most compilers are very highly optimized in the code they output, except in certain circumstances.  Which is why a lot of languages allow inlining assembly.  BASIC and Pascal are called by many a beginners language, but both can be expanded well beyond those boundaries.  Choosing a compiler is important as they all have their own little qwirks for the language they are compiling too.

> Reply from Omnido
>
> I dont want to have to switch languges or coding formats or syntaxes just because so-and-so programming languge doesnt offer support for X.

This isn't really an issue anymore, support is a vague term.  As some support one thing, others support another thing.  It depends on what you mean by "support".  In terms of new software, then if you don't have it, write it.  As to like syntax support, each language has its features.  C# has a foreach construct that C++ doesn't support.  C++ allows for pointer variables, C# doesn't.  Perl has built in Regex support, other languages don't.  Delphi has is/as/with operators that other languages don't have. VB allows you easy to create com objects, in C++/delphi they have wizards but can be very ugly and/or hard to read.

Bootloaders have not much to do with the compiler itself, as to where to load it on the hard drive.  Those the best to use is a C compiler, but with a C compiler, you'll spend forever making a windows application.  Right about assembly, but here is the kicker, but you also have to look for portability between OSs, not only that, with linux/windows you are not running in ring 0, so there are a lot of assembly statements that you can't use because you must be in ring 0 to run those statements(this is where the kernels run).  Assembly is very ugly too.  You sound like someone who doesn't hardly know anything about programming and wants to jump right into expert mode.  Writing a windows application in assembly is one of the most tedious things you could EVER do.  Writing just a hello world program will take you forever and a day.
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-10-16T08:29:57+00:00
- Post Title: m4b Files from Myst 4 Revelation

> Reply from OmniDo
>
> Hrmm...interesting, as I was always under the impression from my brief experience with assembly that it was considered "God's Language" because if you are coding for x86 architecture, you can literally tell the processor what to do, instruction by instruction.
While this may seem tedious and boring (what coding isnt?) it still is nonetheless the most direct method to controlling a PC.

Well, yes, Assembly is the Divine Language perhaps, but it is also the most difficult to start off with, and as Rahly said, it will take ages for you to create a simple program that pops up a window that says "Hello World". Programming soley in assembly in W32 can be a nasty thing, recommended for fetish addicts only.  

Using higher languages gives a much more readable source code, that will take care of many basic, but nevertheless important, instructions for you, that would be utter hell to recreate yourself in assembly. You can't imagine how tedious it is to write routines that just print a line on screen. You have to in assembly. This is what you are looking at with the language. You will have to create each and every function yourself. 

The DOS version of MultiEx Commander uses assembly for specific routines, and for some printing as well. But it also featured a "windows"-like approach, such that I could just open new "windows" wherever on screen and whenever I needed and use them to show whatever I needed them to show. That was probably the biggest task in the creation process of the program, not the actual functionality of the program. It goes to illustrate the boring and tedious proces of having to recreate every basic thing before you can get to the good part: the actual functionality.   Luckily I did most of this in C. Imagine the time lost if I had chosen to do all that in assembly as well.   

> Reply from OmniDo
>
> By the way, any luck with that Myst 4 data file? Im anxious to see what you can turn up by way of developing a method to extract its resource files.

I have figured out the format of the one file, but had to compare to other m4b files. So I downloaded the demos, to look at the big m4b files, they are in a different format however. This may be due to the version being a demo. Is it possible for you to save the first, say, 512 KB of the bigger files you have and zip them so you can attach them here?
Any good hexeditor will let you open a file and select/copy-paste content into a new file, which you can then post here. Try Hex Workshop from Breakpoint Software, if you need to know a good editor. 

> Reply from Rahly
>
> Actually, a lot of people still write in assembly, they just don't write an entire program in assembly. Most of the people who do end up writing assembly, write it inline with their c/c++/delphi code. For the most part, Mr Mouse is right, most compilers are very highly optimized in the code they output, except in certain circumstances. Which is why a lot of languages allow inlining assembly. BASIC and Pascal are called by many a beginners language, but both can be expanded well beyond those boundaries. Choosing a compiler is important as they all have their own little qwirks for the language they are compiling too.

I agree, and what I meant was that few write complete programs in assembly. The inline feature is indeed the way to go to optimize custom routines.
## Post #10
- Username: OmniDo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 11, 2004 2:50 pm
- Post datetime: 2004-10-16T10:12:39+00:00
- Post Title: m4b Files from Myst 4 Revelation

Thank you for all your suggesstions.

By "Support" I generally mean, any programming language that can "do it all" without any limitations, other than those imposed by x86 architecture, or specific restrictions on the OS, such as the kernel issue of 0 that you mentioned.

Ok Mr. Mouse, I used that Hex Workshop program you mentioned and I cut & pasted 1MB of one of the files in the Myst 4 Data folder. 
Subsequently, the original file is 1.4GB in size. The file I am about to attach is only the first 1MB of that original File.
It has been rar'd to around 93K.
Hope this helps.

Also, if you require, I can use this process on all the remaining files, but other than one named data.m4b, they are all "Video" files, such as Video_1.m4b, Video_2.m4b, etc. I presume they are using the Bink format, though I could be wrong. I make this assumption due to the presence of the binkw32.dll file inside the "bin" folder.
Acessing these would also be nice, but Im primarily after the Data and the Sound at the moment, as the data.m4b file could contain still images, etc..

Well, I hope this helps. Lemme know. 
[Partial-sound.rar](https://xentaxbackup.github.io/file/78_Partial-sound.rar)
## Post #11
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-10-16T19:30:48+00:00
- Post Title: m4b Files from Myst 4 Revelation

> Reply from OmniDo
>
> By "Support" I generally mean, any programming language that can "do it all" without any limitations, other than those imposed by x86 architecture, or specific restrictions on the OS, such as the kernel issue of 0 that you mentioned.

The only thing close is the C language. NOT C++ but straight C, as just about every OS has at least a C compiler, and they themselves have been written in C.  But to say C does it all, is a little far fetched.
## Post #12
- Username: OmniDo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 11, 2004 2:50 pm
- Post datetime: 2004-10-17T03:14:28+00:00
- Post Title: m4b Files from Myst 4 Revelation

C hrmm... Well, I'll consider that.
Ive been reccomended Perl by many, along with Java, C++, etc...
I dove into perl for a while, it was interesting.
I also did some scripting in mIRC for a while.

Syntax has been my problem mostly. When it comes to basic coding directives, my main problem has been one not of layout, but of proper syntax usage with respect to the coding language I am using.

I hope that file helps.
Let me know if you need additional beginning fragments from the other files.
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-10-17T07:51:12+00:00
- Post Title: m4b Files from Myst 4 Revelation

Yes, if you can send one or two more, I'd be happy. I noticed a catch, and I have to see if that is always so in this files.
## Post #14
- Username: OmniDo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 11, 2004 2:50 pm
- Post datetime: 2004-10-18T02:10:01+00:00
- Post Title: m4b Files from Myst 4 Revelation

Great!
Ok here goes.
Ive rar'd 2 files in this attachment. One is the first 1MB of the data.m4b file, I presume contains all the scripts for the game, possibly resources like still images, although Ive no evidence of this so far.
The second file contains a couple hundred K of what I presume to be Bink format video, as it didnt compress very well.

Heads up, Mr. Mouse. This should be all you need. Although, I could quite possibly rar the .dll files too (there are alot of them) if that would expedite the process.

*Eagerly awaits your discovery*
[Partial-m4b.rar](https://xentaxbackup.github.io/file/81_Partial-m4b.rar)
## Post #15
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-10-18T03:04:55+00:00
- Post Title: m4b Files from Myst 4 Revelation

> Reply from OmniDo
>
> C hrmm... Well, I'll consider that.
Ive been reccomended Perl by many, along with Java, C++, etc...
I dove into perl for a while, it was interesting.
I also did some scripting in mIRC for a while.

Syntax has been my problem mostly. When it comes to basic coding directives, my main problem has been one not of layout, but of proper syntax usage with respect to the coding language I am using.

I hope that file helps.
Let me know if you need additional beginning fragments from the other files.

The thing about perl (which i LOVE) or Java (which i don't love as much), is that the source code is written in C, so it can compile whereever there is a C compiler, which is just about EVERYWHERE.  Perl is open source, so it has been compiled for every system, every os imaginable.  Java on the other hand, is not opensource, and only runs on machines that there is a JavaVM for.

I would personally recommend to choose, the BEST tool for the JOB.  I use delphi for most windows programming, because, at least in my opinion, its as powerful as C, but still as easy to use as VB.  If i need to do some text processing(web page ripping or text file report processing) I use perl, because some of the stuff you can do in perl is like in one line, that would be HUNDREDS upon HUNDREDS of lines in C.  If you need a gui interface that needs to reach as many people as possible with minimal fuss, pick java.  If you only wanna support windows, VB, VC++, C#, Delphi will work for you.
## Post #16
- Username: Raho
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-10-18T13:38:09+00:00
- Post Title: Myst IV

hi
go to below site for extractor m4b

[http://www.elberethzone.net/index.php?p ... anguage=en](http://www.elberethzone.net/index.php?page=dup5&language=en)
## Post #17
- Username: OmniDo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 11, 2004 2:50 pm
- Post datetime: 2004-10-19T06:42:24+00:00
- Post Title: Myst IV

Hrmm, well that link did indeed direct me to the correct file extractor. The problem is, the files are unrecognizable. 

They are all sequenced with names, etc.. but the file extension is .ss0 and .sb0, which is not readable by either my mp3 player or a conventional wav player.

Any chance of determining their file format Mr. Mouse?
## Post #18
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-10-19T07:07:29+00:00
- Post Title: Myst IV

Yes, I will look at it, I will first enable you to extract the files (I have figured out the format). This might however need a plugin. If so, it will take some time before it is complete, as Rahly and I are doing an overhaul of the pluginsystem in MultiEx Commander. The Pluginmanager is about ready, MultiEx Commander however still hasn't been introduced to its latest partner . I will see if I can do it first with standard script.
## Post #19
- Username: OmniDo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 11, 2004 2:50 pm
- Post datetime: 2004-10-19T08:37:46+00:00
- Post Title: Myst IV

/cheer Mr. Mouse and Rahly 

Oh by the way, I was directed to a link that created a java program which was able to extract the files (some of them), however accessing all the resources is still something Id like to have available.

No rush now, as the primary music files have been successfully extracted.
Apparently, they are in deed all .ogg files, which after using the java program located here: [http://homepage.mac.com/rshayter/Revelator.html](http://homepage.mac.com/rshayter/Revelator.html)
they all extracted without a hitch.

This particular program did the job quite well, amazingly enough. 
However, the author elected not to include "some" files. Dialogue, Sound Effects, etc... which one day I would like to access.

However, all your efforts are greatly appreciated. 
Now if only I could find an Idiots guide to understanding programming languages....
## Post #20
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-10-19T08:45:49+00:00
- Post Title: Myst IV

By the way, MultiEx Commander also plays .ogg files. Courtesy of BASS, the sound library it uses (by the lads at [http://www.un4seen.com](http://www.un4seen.com) ). So when we include support for Myst, you'll hear them in MultiEx Commander as well.
## Post #21
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-10-19T11:10:41+00:00
- Post Title: Myst IV

Great! I look forward to it.
