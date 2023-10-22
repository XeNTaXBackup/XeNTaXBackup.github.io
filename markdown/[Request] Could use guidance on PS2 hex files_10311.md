## Post #1
- Username: Meow
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 06, 2013 12:13 pm
- Post datetime: 2013-04-06T18:24:31+00:00
- Post Title: [Request] Could use guidance on PS2 hex files

Hello, and thank you in advance to anyone who lends their assistance. Long story short, I've extracted the multiplayer level files from a PS2 disc and have located the model (which is the map itself). I'm very new to hexadecimal files, but I think I understand the basics of it... I'm just looking for someone to help point me in the right direction so that the project can move forward. Here's a [screenshot](http://i.imgur.com/qMx9eKM.png) of where the map seems to begin. I'm not entirely sure if the float values include the 0xFFFFFFFF portions, or if those are meant to be "stops". Any help would be greatly appreciated, thanks.
## Post #2
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-04-09T01:17:49+00:00
- Post Title: [Request] Could use guidance on PS2 hex files

I'm not sure what to make of that.
Those numbers between the Fs look like 1 byte values, but I'm not sure.
It doesn't look like a geometry data though. Also it looks like the file pointer is at 0x17.
The values should be aligned to 4 byte boundaries,i.e., 0x18.
## Post #3
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2013-04-12T22:06:17+00:00
- Post Title: [Request] Could use guidance on PS2 hex files

Those look like 32-bit pointers. I'm not as familiar with PS2, but on PSX memory is mapped to start at 0x80000000 and I'd guess the PS2 is the same(same CPU architecture). It's not unusual to store direct memory offsets in a file that you know you will be loading into a specific place in RAM every time. Saves you having to calculate them at runtime; though some games do this too and then store the offset in the place of whatever offset/index is already in the file. You can probably get offsets to the real map data by subtracting some value from the pointer in the file. Without seeing the whole file I couldn't say for sure and I can't guess what value to subtract by either. You'll have to figure it out
## Post #4
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-04-13T19:15:08+00:00
- Post Title: [Request] Could use guidance on PS2 hex files

Yeah, even though that 8.7MB file has some textures in it, there's 1,987 (good year) references to tif files
and references to a bunch of other files as well. If there's geometry in there, I'm still too much of a newb to figure it out.
## Post #5
- Username: Meow
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 06, 2013 12:13 pm
- Post datetime: 2013-04-13T19:26:17+00:00
- Post Title: [Request] Could use guidance on PS2 hex files

Hey, I appreciate both of you taking the time to look/reply. Turns out (as TheDude just said), there are .tiffs in the file... the area that's labeled as "Basemap" actually contains something else. I found a few sections of the file that had the proper x,y,z vert || x,y,z normals || u,v data. Learning something new every day it seems. Thanks again!
## Post #6
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2013-04-14T03:35:00+00:00
- Post Title: [Request] Could use guidance on PS2 hex files

see if theres any obvious data after the Basemap block, like a TIF header, and do some quick math to see if you can find the offsets. That'd be helpful if it makes sense... Like find one, see how long it is and see if you can find that difference in the Basemap block(sub the 2nd pointer from the 1st and compare to your found size, etc). Or see if the actual offset of the TIF header is present somewhere in the file you're looking at.
