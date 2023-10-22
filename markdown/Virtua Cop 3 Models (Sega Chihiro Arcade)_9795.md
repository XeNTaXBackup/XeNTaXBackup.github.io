## Post #1
- Username: themonkeyman
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Nov 27, 2009 8:49 am
- Post datetime: 2012-10-28T02:20:24+00:00
- Post Title: Virtua Cop 3 Models (Sega Chihiro Arcade)

I have the model files for the game Virtua Cop 3 and was wondering if anyone out there could take a look at them. Any help on converting these files to a more standard format (such as .obj ) would be greatly appreciated.

[http://www.sendspace.com/file/oxorxg](http://www.sendspace.com/file/oxorxg)

Virtua Cop 3 was released on the sega chihiro arcade platform, which has very similar hardware to the Xbox 1.


Unrelated, this game uses .adx audio files, same as dreamcast, and .sfd video files, same as xbox, both types of file already have tools created to convert them.
## Post #2
- Username: themonkeyman
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-10-28T03:10:54+00:00
- Post Title: Virtua Cop 3 Models (Sega Chihiro Arcade)

the 3d models are very simple.
there is a table of offsets to the start of each mesh at the start of the file.
then you just go to each of those offsets and read some information about the mesh then its faces as shorts followed by common vertex format vertices.
## Post #3
- Username: themonkeyman
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Nov 27, 2009 8:49 am
- Post datetime: 2012-10-28T04:46:15+00:00
- Post Title: Virtua Cop 3 Models (Sega Chihiro Arcade)

Would anyone out there be kind enough to write a noesis script for this format, or am I left on my own?
## Post #4
- Username: luffytam
- Rank: n00b
- Number of posts: 10
- Joined date: Sun May 06, 2012 10:35 am
- Post datetime: 2012-11-08T07:29:19+00:00
- Post Title: Virtua Cop 3 Models (Sega Chihiro Arcade)

SFD file can easily encode to OGV format include sound,with Theora Converter .NET
but I don't know how to decode a model file
