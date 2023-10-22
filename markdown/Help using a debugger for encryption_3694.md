## Post #1
- Username: qazmlpok
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 02, 2009 7:44 am
- Post datetime: 2009-09-02T22:53:11+00:00
- Post Title: Help using a debugger for encryption

For the past 6 months or so I've been interested in hacking games for the purpose of getting them ready for translation. I was able to find some guides and successfully used them on some simple games to extract all of the script and image files, modify them, and repack a working archive. The only games I've been able to succeed with have been incredibly simple, however. A lot of games use encryption on the archive index and/or the files themselves, and I can't simply "eyeball" these archive formats like I can when then index is just several entires of <Filename><4 byte filesize><4 byte filestart position> or something equally trivial. 

From what I've heard, the only reliable way to determine an encryption method is to use a debugger to figure out how the program decodes each file/the index and reproduce that with a tool to extract the files. However, while I was able to find a good deal of information on working with real simple archive formats, I haven't been so lucky finding any real tutorials on using a debugger. I was recommended OllyDbg by a friend, and I've tried playing around with it (which was the extent of his help), but haven't had much luck on any of the games I've turned it on. My knowledge of assembly is extremely limited (I am not a novice to other languages though), so I find it difficult to know what to look for. Most of the time I can't even find any memory blocks large enough to contain the files I'm looking for.

Any assistance in helping me figure out some encryption methods would be greatly appreciated. I could post a specific example if necessary, but I am looking for something I could use in general.
## Post #2
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2009-09-03T01:49:42+00:00
- Post Title: Help using a debugger for encryption

Why do you think people like me are writing extractors?

Every game tries to hide its content using special container files which contain all required ressources.
Mostly it is done because of enforcing of copyright laws. (But in my opinion NOBODY has the right of storing data on my computer which content I don't know!)

Almost every game uses its own method to compress/encrypt/spoof its content.
Sometimes it is easy to examine the file structure by some experience - recognizing offsets, data-sizes... or some simple encryption methods like XOR/NOT.

But nobody can give you a general help.

By the way, my first NOCD-hack on a WIN32-program some years ago was "TombRaider 2" which had simple CD-requests only, so despite my doubts about the Windows-32-OS hacking (at those days) was easier than I thought.

The first step is to analyze the data file itself.
In some cases it is easy to recognize the file structure (like Wolfenstein2).

But nowadays almost any game comes with a very heavy copy protection (like the evil "Starforce"-virus) which jackets and cripples the original EXE and a very sophisticated data-file encryption, so you (or anybody else) have to remove this EXE-file-encryption first (which is the most complicated step) to be able to examine it.

After that has been done the appropriate file handling EXE/DLL (which has to be found depending on the game development stage) has to be disassembled. This is the next complicated step which requires knowledge of assembly and high level parameter thunking.
## Post #3
- Username: qazmlpok
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 02, 2009 7:44 am
- Post datetime: 2009-09-03T02:54:30+00:00
- Post Title: Help using a debugger for encryption

The problem is that I really don't know how to analyze the data. For the game I'm currently interested in, the file is completely encrypted (or I'm just looking at it horribly wrong; I suppose that's also a possibility). I had noticed that with weak single-byte XOR encryption it's possible to search though the file for file headers for ogg, png, jpg, wav, etc file headers with every possible XOR permutation applied and occasionally get useful results. I just tried the program I wrote for that on a bgm file and only got 3 results for wav files, despite there being significantly more than 3 music files (plus, it's much more likely they used ogg). When I tried opening the exe up in a debugger, I didn't find any blocks of memory that were large enough to contain the archive files. According to Olly's Memory Map window, the largest block of memory is 0x0092E000, or just over 9 megabytes. I could simply be using Olly wrong, since I honestly don't know much about using it, but even if I am I can't use it to find any useful data. Viewing the memory blocks doesn't show any recognizable headers; music is playing, images are on the screen, so there must be files loaded somewhere into memory, but I'm not seeing it. The executable is 10 meg, so it's possible that some images are embedded, but there's no way that all of them are.

Also, the games I'm working on are small games made by groups of people, not companies. They're Japanese Doujin games, if you're familiar with the term. They certainly don't have any kind of advanced file protection, and they don't have any need to prevent hackers from cheating in online play or whatever, as there is no online play. That's actually why I'm focusing on them. When I decided to start trying to hack, I figured that doujin games would be very simple to deal with because they aren't commercial. I was honestly surprised when I started running into encrypted files.

> Why do you think people like me are writing extractors?
I wrote an extractor as well. If the archive isn't encrypted, I can just eyeball it usually to figure out how the files are arranged and slightly modify my extractor/repacker to get the files and rebuild the archive whenever. I just can't deal with encryption because I don't know how. If the index is encrypted I can't figure out how the files are arranged, or even where the index ends usually.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-09-03T04:05:31+00:00
- Post Title: Help using a debugger for encryption

I have seen some very weird file formats from japanese developers even when they do not need to prevent hacking they want to protect their assets from people reusing them in their own work.
you should post a sample file to look at.
have you tried offzip on the files?
## Post #5
- Username: qazmlpok
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 02, 2009 7:44 am
- Post datetime: 2009-09-03T04:34:58+00:00
- Post Title: Help using a debugger for encryption

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-09-03T14:13:48+00:00
- Post Title: Help using a debugger for encryption

Most games use large archives to contain the main game file in order to alleviate the need for the hard drive to seek so far to find files that would otherwise be in sequence in a directory.  When files are stored on the hard drive they are not guaranteed to be able to fit directly next to each other when stored, as the free space at that location on the disk may not be big enough so it chooses the next best location it can, which in turn may make another section of the disk not big enough to hold another file at that location later.  This occurs even when the files are supposed to be in the same directory.  I won't even go too deep into the fact that files are stored in even smaller chunks based on the formatting of the hard disk, which even further segments files, thus leading to what we all know as a fragmented hard drive.  OSes do their best to keep single files, and their sub-parts, as close together as possible on the drive so that read/write operations are for the most part close to each other without having to jump all over the drive since seek times are about the slowest part of accessing a hard drive.

Compression, for space concerns usually, but sometimes for protection as well depending on the method or modifications to a method used; and encryption for data protection.

The memory you are currently seeing is probably that of only the executable file data, in some cases about the same thing you will see should you open the executable in a hex editor.  A good portion of the data storage used by an executable will not be present until it is actually running, at which point it will begin to allocate data and memory storage as needed for any processing.  To see where files are being handled you will actually have to step through the code and watch the registers and memory access as it proceeds.

i have not personally used OllyDbg so i can really only tell my experiences from using Ida Pro, but i assume they should have similar features in some regard.  Your biggest helper here will be the imported function list should the debugger be able to determine the names of them from the executable.  Given that some function are not known until they are loaded by the executable during initialization, in the case of a dll being loaded dynamically you may have to wait until execution to actually have access to the relevant code in these modules, but this is usually not a problem as unless there is some other more advance method used, dynamic function importing is usually done by querying for the actual name of the function (which makes it easier to search for usually).  But overall most applications explicitly linked to a dll or even better statically link to the libraries which directly includes the code in the executable.

The search function for your chosen debugger is your greatest ally when starting out (next to hardware/software breakpoints), should things be done "simply" in the executable anyways.

I'll say this now before going further, if you find anything and it looks interesting or useful, put a break point there. If later you find it is no longer necessary, remove it, or preferably just disable it (this will probably happen a lot as you will find many useful, yet annoying spots where break points are necessary (annoying in that they may be hit every frame/loop iteration when you only needed to inspect it the first time)).  Since any debugger i know of keeps a list of all break points present these can be used as bookmarks in cases where the debugger may not allow you to add comments to the code or have some other location marking feature.

Your first searches should somewhat obviously be for the file extension of the file(s) you are trying to find out information for.  Most text strings used for identification, loading, comparison, etc. will often turn up in plain text form directly in the disassembled executable code, thus making this stand out and be readily findable in the code when searched for.  If you haven't looked at at least the hex level binary data of the file you are interested in, well you probably should have done that first to even see if it is necessary to have to dig through the code for the information you are looking for, then do so and see if there are any similarities or identifying patterns, bytes, and/or other values in the file that could possibly act as distinguishing marks for that type of data.  If you find any, search for those as well using the debugger, this can usually turn up many function where these values will be compared against data that will eventually come from the file in question, these functions may be of interest when stepping through the code later.  More break points.

Next, if possible, look through the imported function list or if necessary search through the function list and executable code for any file I/O related functions and/or OS api calls.  These are things like fopen, fread, fclose, CreateFile, ReadFile, WriteFile, etc.  On windows at least, even the basic standard library functions will usually at some point end up making API calls into the OS for file I/O related calls.  This may not always be the case, but you can be pretty confident that a good deal of people will be using these calls as they are usually the most efficient or easiest methods to handle them.  Searching for these calls and entry points and putting breakpoints on their access will greatly help in find where files are being accessed in the executable during runtime.

In some instances the debugger will be able to determine the intended parameter usage of known functions.  In the case of file I/O you are usually most interested in the file name that is trying to be accessed. If it is not know which register holds this value, your breakpoint should stop execution before the function is even called in order for you to be able to inspect the values being passed beforehand so that you will know if you are even interested in this particular call.  This can also sometimes narrow down the locations you do not need to be wary of, i.e. if this location only  seems to load configuration files or only gets call during the start of the executable and you are interested in other data not touched here you can disable this spot's break point so as to not be bothered by it stopping there.

If you are able to figure things out in a section of code it will be extremely helpful if your debugger allows you to label/comment things so that you don't have to remember them yourself.  If need be keep separate notes in notepad, on paper, etc. so that you can track where things are occurring in the code.  Functions, variables, parameters, etc. the more you know about what things are being used for the easier it will be to determine what is going on.  If you are actually in a function that is processing data you are interested in, leave notes on how a particular location or process related to the information you know so far on the data you are investigation (i.e. reads animation count, etc.)

If your debugger supports it the ability to track back references to a function will be extremely useful and can in some cases allow you to avoid a lot of needless searching should your intuitions about previously found information be correct.  To use the aforementioned file I/O case, if you can find the CreateFile function address of even function code and find all the locations in the executable that make a references to call this function, you have just located at least good stating points for tracking down places where attempt are made at opening files.  The same will go for ReadFile as well since knowing when and where data is read into will allow you to find the memory location that is used to store the data you are interested in and compare it to the file(s) you are interested in as well as allow you to put the debugger's hardware breakpoint functionality to good use by placing Read/Write breakpoints at the memory locations you are interested in to tell when things are read into the computer's registers for processing.

Other function and methods that are good candidates to be on the look out for are malloc and free.  These are not function you would generally want to search for, but while you are stepping through the code you want to track the memory location these return should the be useful to you.  This you will not know so much yet unless you have alread determined what the code does that is surrounding the memory allocation call, or that eventually ends up using the memory that was allocated.

Unfortunately with this type of debugging you will not get away without knowing at least some basics about assembly language calls.  You don't really need to know that much as a good deal of the instructions are self explanatory given their name add and mov (Add and Move) for example, so in some way you can learn as you go if you are observant and catch on quickly.  But the more you know about what is going on and how it affects the registers the easier it will be to go from seeing things as a random string of assembly instructions to interpreting it as say a matrix multiplication function, etc.  Though even then, unless you are an assembly guru++ or possibly a computer yourself, and can memorize register changes and computations in your head, you will not be able to figure everything out until you are actually running and stepping through the code with actual data pumping through the electronic veins of the processor.  Use the register and memory views provided by the debugger to watch and analyze how data is being moved from location to location and processed into the resulting information.

If your debugger of choice supports adding comments to disassembled code, Use It!  When i first got started i didn't even think to look for this feature as i was still getting used to working the break points and registers and jumps and crashes and anti-debugging functions/exceptions (anti-debug methods, is a whole topic in itself, but hopefully you won't run into this much and i am not that experienced with it still).

All in all everything you are looking for or at, will in some way break down into a series of computations performed by the computer on the data in question.  Once you find it, either through searching and finding the right location, or stepping function by function, line by line, and/or instruction by instruction, keep at it until you can make out what the heck is going on.

Not sure if i missed anything, i may come back and make some edits and/or respond to other comments.  I am fairly new at this as well, but being accustomed to debugging my c/c++ programs has greatly helped in working through these things, so getting to a point where debugging is an enjoyable experience can be beneficial.

Hope that helps.

- revel8n
## Post #7
- Username: qazmlpok
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 02, 2009 7:44 am
- Post datetime: 2009-09-03T21:25:55+00:00
- Post Title: Help using a debugger for encryption

File fragmentation shouldn't be an issue because the OS handles it and unfragments the files as they are accessed. Memory fragmentation shouldn't occur, because IIRC malloc or whatever will return an error if it cannot allocate a continuous block of memory.

I've run into compression before, and I doubt these are compressed (or maybe they're both. I can't say for sure). Looking at all of the archive files together for the first time, I just noticed that the first four bytes are always the same, then 4 different bytes, then 4 bytes that are the same. I assume that the first four bytes are the archive signature, possibly the second set is 0x00000000, refering to the beginning of the first file after the end of the index. Well, if nothing else that means the all of the archives should be encrypted the same way, with no seeding done to the index.

I did start running the game in the debugger when I mentioned the memory blocks I was seeing. I started it with no breakpoints set, load it go to the main menu, loaded a savegame, paused execution and looked at the memory map. At the time there was music playing and several images on the screen; they should have been opened and their contents loaded into memory, but I was not able to find anything.

Olly does assign names to function, stuff like <exename>.7C09AB56C. Some functions, e.g. CreateFileW, Olly does know the name of.

I did a search for all text strings. I was not able to find any mention of the archive files in the list. Not the full name of any of the files, the extension (*.dxa), or "bgm" "img", etc. I was able to find img.dxa being opened after setting a breakpoint at CreateFile. But now what do I do with it? I set a breakpoint at ReadFile and ran until it stopped there, then skipped to the end of the function. I still don't see any useful files in the memory mapper. Shouldn't the program open the archive file and then read the entire file into memory? I had tried messing around with other games in the past and was able to find the entire archive loaded into memory - which should then get decrypted by the program so it can read the contents, allowing me to see the unencrypted index and giving me somewhat of a hint as to where the decryption is done. But that just isn't happening this time.


And offzip did not bring up anything useful when I ran it on one of the archive files with the -S parameter.
## Post #8
- Username: xhugox
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 29, 2009 5:50 am
- Post datetime: 2009-09-03T22:52:43+00:00
- Post Title: Help using a debugger for encryption

( [http://msdn.microsoft.com/en-us/library ... S.85).aspx](http://msdn.microsoft.com/en-us/library/aa365467%28VS.85%29.aspx) )

BOOL WINAPI ReadFile(
  __in         HANDLE hFile,
__out        LPVOID lpBuffer,
  __in         DWORD nNumberOfBytesToRead,
  __out_opt    LPDWORD lpNumberOfBytesRead,
  __inout_opt  LPOVERLAPPED lpOverlapped
);

meaning if you have instructions like these;

push EAX
push EBX
push ECX
push EDX
push ESI
Call ReadFile

This will be the content of the registers.

ESI =  __in         HANDLE hFile,
EDX = __out        LPVOID lpBuffer,
ECX =  __in         DWORD nNumberOfBytesToRead,
EBX =  __out_opt    LPDWORD lpNumberOfBytesRead,
EAX =  __inout_opt  LPOVERLAPPED lpOverlapped

FIFO, RRRRRING? 

p.s. If anyone has a look at my thread ( [viewtopic.php?f=21&t=3679](http://forum.xentax.com/viewtopic.php?f=21&t=3679) ) atm please contact me, I would like to have a chat with you.
## Post #9
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-09-04T09:33:43+00:00
- Post Title: Help using a debugger for encryption

ok, to expand, once you have found the CreateFile call you are interested in you will want to track where its return value (eax) is stored.  This value is the file handle that will be used in future calls to ReadFile, etc.  At this point you can either put conditional breakpoints on calls to ReadFile that will only stop when the file handle matches, or even better place a read/write breakpoint on the data location where the file handle was stored.  The latter allows you to track all accesses to the file handle for any reason; if it  is being moved to a register just befor being used in a ReadFile call, you know data is about to be read that you may be interested in investigating; if it is being copied to another location in memory, you may now need to track this new location in addition to previous ones.

Once you have found a read call you are interested in, as has been mentioned, you will more than likely be interested in tracking the future usage of the destination buffer address and any accesses and computations performed on the data that resides there.  At this poit the memory at this location should match all or at least part of the file you are looking into depending on how much the application decided to read in.  Use this to decide where you want to place your breakpoints in memory.
## Post #10
- Username: qazmlpok
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 02, 2009 7:44 am
- Post datetime: 2009-09-07T04:06:55+00:00
- Post Title: Help using a debugger for encryption

ok, I just managed to watch the debugger read in the index and decode it. Decryption seems to be done in 12 byte chunks, but with the same 12 bytes being applied repeatedly. Not too much more complicated technically than single byte XOR encryption. I should be able to find the exact part where the decryption is done, but I'm not positive I'll be able to understand it by myself. 

Two more questions though
First, when I try setting a breakpoint in much of the code involved in decryption, Olly warns me that I am trying to set an INT3 breakpoint outside of a code region. Since it's definitely being executed as code, it's perfectly safe to set a breakpoint, and I can safely ignore such warnins in the future. Correct?
Second, when I got the file handle for img.dxa from revelation's method, I got '433C'. I then set a breakpoint at ReadFile, the first call used handle '434C'. From looking at the memory dump after ReadFile returned, it appeared to be img.dxa. Setting a conditional breakpoint for a 433C filehandle never paused. Every time I reset the program the filehandle was different by the same amount. Is it normal for the return value (taken from the value of EAX at the RET statement in the end of ReadFile) to be 0x10 lower than the later used file handle?

Thanks again for all the help.
