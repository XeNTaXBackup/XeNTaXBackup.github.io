## Post #1
- Username: lumis
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Dec 01, 2013 4:32 am
- Post datetime: 2013-12-09T03:44:26+00:00
- Post Title: Gujian2 models .rawxac .xac .xsm

As the title says i've recently discovered this game and managed to unpack it


Preview video, this game looks epic ^^
[http://www.youtube.com/watch?v=8N9bIXT4BEA](http://www.youtube.com/watch?v=8N9bIXT4BEA)

Below there are some file examples to play with ;d
[http://www65.zippyshare.com/v/6563369/file.html](http://www65.zippyshare.com/v/6563369/file.html)
[http://www63.zippyshare.com/v/31900746/file.html](http://www63.zippyshare.com/v/31900746/file.html)

Have fun, I guess ^^
## Post #2
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2013-12-13T04:02:39+00:00
- Post Title: Gujian2 models .rawxac .xac .xsm

Would you mind sharing method how to unpack zpkg, the Gujian2 Archive File ?
## Post #3
- Username: lumis
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Dec 01, 2013 4:32 am
- Post datetime: 2013-12-13T10:42:40+00:00
- Post Title: Gujian2 models .rawxac .xac .xsm

Sure, but as you can see, no1 is interested to mess with game files ^^ I'll wait some days.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-15T00:15:29+00:00
- Post Title: Gujian2 models .rawxac .xac .xsm

I made two versions of 101y_Box01.xac

little endian version
# 0x187b: verts= 8
v -9.721093 -0.000000 -9.614623 
v -9.721093 -0.000000 9.614623 
v -9.721093 25.948864 -9.614623 
v 9.721093 25.948864 -9.614623 
v -9.721093 -0.000000 -9.614623 
v 9.721093 0.000000 -9.614623 
v 9.721093 0.000000 -9.614623 
v 9.721093 0.000000 9.614623 
f 2 4 2 
f 6 5 1 
f 1 4 3 
f 2 5 8 
f 6 7 1 
f 6 2 5 
f 2 8 4 
f 6 4 7 
f 3 8 3 
f 5 1 7 


big endian version
# 0x187e: verts= 8
v -19.316946 -0.000000 -19.191946 
v -19.316946 -0.000000 19.191946 
v -12.412063 15.989526 -19.191946 
v 12.412063 15.989526 -19.191946 
v -19.316946 -0.000000 -19.191946 
v 19.316946 0.000000 -19.191946 
v 19.316946 0.000000 -19.191946 
v 19.316946 0.000000 19.191946 
f 2 4 2 
f 6 5 1 
f 1 4 3 
f 2 5 8 
f 6 7 1 
f 6 2 5 
f 2 8 4 
f 6 4 7 
f 3 8 3 
f 5 1 7 

and as you can see: that's no box, so that's no fun...

edit: ok, that's better, but still no box at all:
# 0x187b: verts= 8
v -9.721093 -0.000000 -9.614623 
v -9.721093 -0.000000 9.614623 
v -9.721093 25.948864 -9.614623 
v 9.721093 25.948864 -9.614623 
v -9.721093 -0.000000 -9.614623 
v 9.721093 0.000000 -9.614623 
v 9.721093 0.000000 -9.614623 
v 9.721093 0.000000 9.614623 
f 4 2 6
f 2 5 6
f 6 5 1
f 1 1 4
f 1 3 4
f 4 3 2
f 3 5 2
f 2 5 8
f 5 6 8
f 8 6 7
f 6 1 7
f 7 1 6
f 1 2 6
f 6 2 5
f 5 2 8
f 2 4 8
f 8 4 6
f 6 4 7
f 4 3 7
f 7 3 8
f 8 3 5
f 3 1 5
f 5 1 7

H2O file:
0x17F7 30
VB1
24 16
0x187B 8
0410
