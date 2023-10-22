## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-24T04:30:54+00:00
- Post Title: A simple file unpacker

So I want to write an archive unpacker with a simple GUI interface for a simple format but am not sure about some things.

By simple format, it is just one of those things where you have the file table with offsets sizes and names, and then the data.

Is it better to read the file table and store all of the values in memory and then just grab these values to unpack files? Or is it better to just store offsets to each file entry and read the file entries to grab the necessary info?

Even with really large archives with like, say 20000 files would it still be fine to just store all the values I need in memory?
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-24T13:12:18+00:00
- Post Title: A simple file unpacker

Storing 20,000 offsets is nothing. Each number is what? 4 bytes? So 80,000 bytes. That's less than 80 KB. Drop in the bucket. Biggest thing you need to watch out for is when extracting these files you encounter a very large file, like several hundred MB+ (archives within archives). In fact, I would set a 32 MB threshold where any data between two offsets is greater than 32 MB then save them in 16 MB chunks at a time. But don't let mr. 30-60 minutes give you advice ha ha ha . I do batch stuff mainly cuz I am a minimal work type of guy and I want everything, and I just want to rip the whole thing and be done with it.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-24T14:17:39+00:00
- Post Title: A simple file unpacker

Pretty sure you just need to write a GUI once lol
