## Post #1
- Username: Kung Fu Man
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Jul 14, 2011 1:34 pm
- Post datetime: 2012-03-20T20:54:44+00:00
- Post Title: Question regarding BNK files

This is going to sound odd given that most of the research done has involved taking them apart, but has any significant research been done on modifying or building them? Or at the very least, how the game calls them into play.

Reason I'm asking is because I've done some extensive work already modifying Splatterhouse 2010, and while I've had some preliminary success in restoring the game's removed photographs from its gallery, I've yet to isolate just how the sound files are being called. Closest I can figure I know the Xbox version uses XMA, while the PS3 uses OGG. A small part of each referenced file is included in the BNK, and a reference to the hexadecimal values for the files is included under the HIRC header. Trying to replace one file for another results in the game trying to play the data for the original file in the BNK but stopping quickly, while modifying the reference under HIRC to a non-existent file can remove the sound outright (as can just deleting the related sound file).

Any ideas?
