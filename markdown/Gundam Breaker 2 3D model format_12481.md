## Post #1
- Username: johndman
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 19, 2014 2:23 am
- Post datetime: 2015-01-07T19:42:19+00:00
- Post Title: Gundam Breaker 2 3D model format

Anyone willing to help out with this?

Sample file for a 3D model: [https://mega.co.nz/#!kdZy2bSJ!vYq-gvTQG ... ysWDo8obWc](https://mega.co.nz/#!kdZy2bSJ!vYq-gvTQGWq2TguBPKF9djATNZqZneR8qysWDo8obWc)

Format of the file:

SHORT: Number of vertices
SHORT: Number of entries in the polygon list
INT: 0xFFFFFFFF

Then follows the polygon definitions. Followed by 8 bytes set to zero and then the vertices. And some unknown stuff at the end.

The problem I'm having is the faces seems messed up. When viewing the extracted model the shape is right and makes sense so I assume I got the vertices right. I've tried outputting the faces in different orders (e.g <1 2 3> <2 1 3> etc) but can't make it work.

I can provide a larger sample file with multiple models in it if needed.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-07T21:48:35+00:00
- Post Title: Gundam Breaker 2 3D model format

using hex2obj (view link in my sig):



breaker3D.JPG (43.51 KiB) Viewed 251 times
## Post #3
- Username: johndman
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 19, 2014 2:23 am
- Post datetime: 2015-01-08T12:01:36+00:00
- Post Title: Gundam Breaker 2 3D model format

Thanks. Turns out I made an error in my own OBJ exporter. Forgot vertex indexes start at 1 and not 0 in OBJ files.
## Post #4
- Username: cosmos28
- Rank: n00b
- Number of posts: 10
- Joined date: Tue May 08, 2012 1:56 am
- Post datetime: 2015-09-13T21:24:21+00:00
- Post Title: Gundam Breaker 2 3D model format

Hi!
any chance of getting the models please?? I'm really interested.
Thanks!!
