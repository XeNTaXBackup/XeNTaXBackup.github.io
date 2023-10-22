## Post #1
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-06-06T18:52:50+00:00
- Post Title: Teach me something quick (File names extraction eg MGSV)

I remember looking at a few games in the past where I could easily decrpyt and extract nameless data. But since i did not know the file names  was frustrated into submission
I recently found out people where making dictionariies for MGSV by extracting the file names from exe
I think MGS turned out to be simple hash tables 
If anyone else has experienced this and are willing to share some info on how to match the binary to their hidden names I would be very pleased
## Post #2
- Username: willwill
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jun 11, 2017 10:11 am
- Post datetime: 2017-06-15T03:31:46+00:00
- Post Title: Teach me something quick (File names extraction eg MGSV)

I have never tried something like this. My gut is telling me that you could do a process dump while the game is running (perhaps a good opportunity might arise at the loading screens) and then searching the output, you would expect to see some id strings that refer to the actual assets. Perhaps then if you try to get the list of all encrypted names, then try some brute force techniques to reveal file names that make sense. However this is only guessing, but might be a clue.
## Post #3
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2018-05-29T21:13:22+00:00
- Post Title: Teach me something quick (File names extraction eg MGSV)

The solution was simple. The files all had hash ids in place of names
so i made a dictionary MGS style with the had and the string section of the exe
