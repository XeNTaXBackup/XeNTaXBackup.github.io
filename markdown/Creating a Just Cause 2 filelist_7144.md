## Post #1
- Username: Kstolen
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 08, 2011 8:39 am
- Post datetime: 2011-08-08T08:02:32+00:00
- Post Title: Creating a Just Cause 2 filelist

Hi guys, I'd like to do some modding on Just Cause 2. 

Gibbed/Rick has made some nice tools for viewing the archives that come with the game and the files inside them.
Unfortunately, the filenames are hashed, so his tool uses a list of known file names to identify files in the archives. 
However, only something like ~10% of filenames are known. I'd like to improve on this, but I'm not really sure where to start.

How do people tend to go about discovering filenames/paths to create a filelist?
## Post #2
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-08T23:03:55+00:00
- Post Title: Creating a Just Cause 2 filelist

The typical way is to hook the hashing function in the game so you can log all calls, IIRC, Just Cause 2 doesn't use precomputed hashes for anything aside from property names.
## Post #3
- Username: Kstolen
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 08, 2011 8:39 am
- Post datetime: 2011-09-03T02:29:23+00:00
- Post Title: Creating a Just Cause 2 filelist

I'd put this off for a little while, back on it now. 

> The typical way is to hook the hashing function in the game

Is that what you did, yeah? Any tips to share about the process? Maybe the address of the hashing function? I can't seem to find it. It would probably have a load of bitwise shifts and xors in it, yeah?
