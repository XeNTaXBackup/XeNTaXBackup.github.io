## Post #1
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2015-03-30T14:32:15+00:00
- Post Title: Spider-Man FoE .DATA

So I've got Spider-Man Friend Or Foe for PC, and while it might be an old game I'm stuck on trying to figure out how to convert the DATA to a useable 3D format. I tried to search here before I posted this to see if anyone else has dealt with this before but no luck. If anyone can help here's a few sample files. Or should I just try to use 3D Ripper DX or Ninja Ripper on the game?
[http://www.uploadmb.com/dw.php?id=1427725904](http://www.uploadmb.com/dw.php?id=1427725904)
## Post #2
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2015-04-04T22:40:28+00:00
- Post Title: Spider-Man FoE .DATA

I only had time for a quick look, but the file format seems pretty straightforward. Just a stream of data.



The first value show the block size, plus terminated by 8byte and comes the next file. Found a few suspicious byte/float, which i think could be vertex/uv/skin data, but it requires further investigation 

That's it for now. When I have more time I'll look into it
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-05T06:32:26+00:00
- Post Title: Spider-Man FoE .DATA

GreenGoblin_pointCloud.JPG (155.62 KiB) Viewed 90 times


(face indices count not exact)
## Post #4
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2015-05-05T03:17:32+00:00
- Post Title: Spider-Man FoE .DATA

i just used 3d ripper to pull all of these game models, works perfectly fine.
