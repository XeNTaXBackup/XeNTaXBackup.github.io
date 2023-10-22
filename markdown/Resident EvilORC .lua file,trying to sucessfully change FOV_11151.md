## Post #1
- Username: passburger
- Rank: n00b
- Number of posts: 15
- Joined date: Mon May 21, 2012 6:42 am
- Post datetime: 2014-01-22T16:37:44+00:00
- Post Title: Resident Evil:ORC .lua file,trying to sucessfully change FOV

Hello all.

I've been trying to change the camera values in [globaltweaks.lua](http://www.4shared.com/archive/Wz1N3-2Sba/globaltweaks.html).
No matter how I edit the camera values [example:"/Y Fov", 45)" to "/Y Fov", 60 )"], none of the changes seem to take effect when I play the game.
What am I doing wrong? Any other lines I should be changing?
I'm not a .lua-pro at all.

Thanks in advance for any help.
## Post #2
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2014-01-22T17:06:10+00:00
- Post Title: Resident Evil:ORC .lua file,trying to sucessfully change FOV

The scripts and other assets you see there are just references for some reason. You won't see any changes even if you delete the files. The real ones are inside compress or uncompressed ssg archives.
There's a quickbms unpacker already here and a repacker by codeman somewhere.
## Post #3
- Username: passburger
- Rank: n00b
- Number of posts: 15
- Joined date: Mon May 21, 2012 6:42 am
- Post datetime: 2014-01-22T22:45:34+00:00
- Post Title: Resident Evil:ORC .lua file,trying to sucessfully change FOV

Thanks a whole bunch for the help so far, I've managed to find and use the unpacker, by still no luck finding the repacker. 
If you happen to know where to find it before I figure this out please let me know.
## Post #4
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2014-01-23T02:24:25+00:00
- Post Title: Resident Evil:ORC .lua file,trying to sucessfully change FOV

Here's the link, the filename is pretty obvious. [https://skydrive.live.com/?cid=aba6c499 ... 1B45%21172](https://skydrive.live.com/?cid=aba6c499ba561b45&id=ABA6C499BA561B45%21172)
I took it from Codemans public profile signature from the old RE forums, so I think he won't mind sharing it here. [http://z6.invisionfree.com/Resident_Evi ... wuser=7066](http://z6.invisionfree.com/Resident_Evil_4_PC/index.php?s=2f53cce2c07963275a8565a012071af1&showuser=7066)

One more thing, the ".plato" files are scripts too but with binary things, like the SWB2 for the characters, you might want to investigate there too.
