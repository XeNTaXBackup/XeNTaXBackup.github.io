## Post #1
- Username: cheyrn
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 02, 2014 2:24 am
- Post datetime: 2016-05-13T01:14:51+00:00
- Post Title: bms variable length strings

I've went through only one mrmouse youtube video so far, the one for etherlords.

Trying to do something similar with another file format, the file seems to be a sequence of null terminated 16-bit (utf-16le) characters, preceded and followed by other data that I haven't figured out. Can I use bms language to handle that?

I see I can set a variable to a string read from the current position in a file, but how do I then write that into an output file? Log/CLog want an explicit length. Is there a way to log the contents of a variable?
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-05-14T13:21:38+00:00
- Post Title: bms variable length strings

Create a memory file, write the variable to that memory file then log it to a text file.
## Post #3
- Username: cheyrn
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 02, 2014 2:24 am
- Post datetime: 2016-05-28T03:20:15+00:00
- Post Title: bms variable length strings

Ah. I see memory files in quickbms syntax. I was first trying multiex syntax. Quickbms has strlen and the unicode type reads the text without needing to specify the length. So, I don't think I need the memory file. But, thanks for leading me to quickbms.
