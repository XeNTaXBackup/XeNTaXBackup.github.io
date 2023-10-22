## Post #1
- Username: cornal
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Oct 25, 2014 10:31 am
- Post datetime: 2017-04-18T18:28:54+00:00
- Post Title: Monster Jam Path Of Destruction .bin models

Hi, I'm trying to handle with H2O this type of files, these contain sub meshes and begin with 0000 0100 0200 0200 0300, but I don't know find the end   , yes i know this require "experience", but I'm trying to learn.

Some examples:
[https://drive.google.com/open?id=0B2n9Q ... U0wdHhxTWc](https://drive.google.com/open?id=0B2n9QIK-r-NjN1Z6WU0wdHhxTWc)


If someone can help with a script it would be very nice.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-04-18T18:52:27+00:00
- Post Title: Monster Jam Path Of Destruction .bin models

it's not only "experience", often it's a matter of patience or some efficient proceeding.
I wouldn't start with a 1 MB file for example.

The Wheel appears doable, you even don't need to know where the face indices end for a good start.
(Guess you didn't use big endian?)



Wheel_I_R-bin.JPG (82.98 KiB) Viewed 60 times

(unsure about uvs)

@cornal: as for the endianess: as you stated, iirc, for PS4 it's little endian
## Post #3
- Username: cornal
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Oct 25, 2014 10:31 am
- Post datetime: 2017-04-19T04:37:38+00:00
- Post Title: Monster Jam Path Of Destruction .bin models

Need take more attention to little details about Little and Big Endian, big endian is usable in PS3, X360 games?
