## Post #1
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-05-26T23:24:24+00:00
- Post Title: Advanced C++: How to read DVD sectors

Hi guys 
This is related to my earlier [kengo thread](http://forum.xentax.com/viewtopic.php?f=13&t=11511). I have figured out a fool proof way to seperating models from animation files as they are currently using similar representations.
I played the game in pcsx2 and dumped out the logs from the dvd read. I was able to enter a mode that showed only animation of certain moves (move select mode) and the dvd consistently read the exact same sector when ever an animation is triggered.

If i know how to read dvd sectors in c++ i would be able to identify the files read and use it as a method to eliminate doubt.
## Post #2
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-05-31T01:33:13+00:00
- Post Title: Advanced C++: How to read DVD sectors

Figured it out.

Some Hex Editors can read by sector but they often have fixed sizes 512, 1024 and 2048 . The size I seek is 2064 .
Manual labour
## Post #3
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-06-02T22:08:37+00:00
- Post Title: Advanced C++: How to read DVD sectors

Just a guess: on Windows you may need to use DeviceIoControl() to send data directly to the DVD-ROM driver. Similarly on UNIX based systems, ioctl().
