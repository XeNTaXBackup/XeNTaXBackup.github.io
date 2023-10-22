## Post #1
- Username: pharrell
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 26, 2017 12:35 am
- Post datetime: 2017-04-25T16:40:50+00:00
- Post Title: How would I go about getting the games code?

I've gone to the game directory file on my computer and all I see are some executable files and a bunch .dll files also one .ini file

Is there anyway I can get the code out of them? 

I'm trying to create a database for the items in the 'Store' and I don't want to log down every item in the store one by one so I was thinking of finding the code for it and writing a script to extract that information into a database.

Any tips on how I would start this?
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-04-25T23:15:50+00:00
- Post Title: How would I go about getting the games code?

does this game have any other files in the install directory?

most games are bundled with some bespoke file format which can be analysed.
## Post #3
- Username: willwill
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jun 11, 2017 10:11 am
- Post datetime: 2017-06-15T03:19:00+00:00
- Post Title: How would I go about getting the games code?

The only way to do this is to search for exe/dll decompilers or debuggers.

However if the program is binary executable you will eventually have to learn about assembly code, which is machine code. This is not a high level representation such as C or Java, it means that you simply won't see command statements (as in changeThis..., doThis) but only memory operations (mov EDX23423, EDX2242, JMP F22020).
