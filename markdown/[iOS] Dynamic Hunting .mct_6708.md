## Post #1
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2011-06-01T17:44:40+00:00
- Post Title: [iOS] Dynamic Hunting *.mct

Hey all,

I'd like to play around with the textures from iOS game Dynamic Hunting.
The textures do not seem to be encrypted from what I can tell, but I cannot analyze/convert them.
I would be very grateful for a format analysis/tool to convert them to a common image format and eventually back.

Example files: [http://vuvu.bplaced.net/mct.zip](http://vuvu.bplaced.net/mct.zip)
Maybe this code helps, I found it in the game: [http://vuvu.bplaced.net/GraphicsMC.cpp](http://vuvu.bplaced.net/GraphicsMC.cpp)

Thanks in advance and kind regards!
## Post #2
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2011-06-03T17:42:49+00:00
- Post Title: [iOS] Dynamic Hunting *.mct

The code isn`t really necessary as those images are in a pretty obvious format:

They are just RGBA8888 direct color, little endian images; some examples you posted:









There...
