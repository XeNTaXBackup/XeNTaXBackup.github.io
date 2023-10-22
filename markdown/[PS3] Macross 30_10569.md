## Post #1
- Username: Rygdea
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Aug 16, 2010 7:27 pm
- Post datetime: 2013-07-02T00:00:22+00:00
- Post Title: [PS3] Macross 30

[http://en.wikipedia.org/wiki/Macross_30 ... the_Galaxy](http://en.wikipedia.org/wiki/Macross_30:_The_Voice_that_Connects_the_Galaxy)

 


Trying to view this game's archives. Both for the Models and Images as a Macross fan myself, plus text if possible on the chance it may be useful to get a translation project running.

The packed files are all .dat (and a single small "pack.idx" file) with all of them having the header PIDX0.


Now this is what I managed to do myself looking into it with my very limited knowledge:

Using [offzip](http://aluigi.altervista.org/mytoolz.htm) with the parameters of -a -z -15 0x0 it did manage to extract files (meanwhile spewing out a TON of error messages) but they were all in 64KB chunks... this gets very confusing for me, personally wouldn't know where to start on joining these up.

So I went the other path of using offzip again but -1 -a -z -15 0x0 so it spits out just one huge file, then I used a scanner (Ravioli game tools in this case which I found on google, not sure if better exist) it works but I'm limited to what the scanner supports in this method... which in this game's case just bundles of DDS textures.


[Helpful?](https://dl.dropboxusercontent.com/u/12804628/Macross/dat%20files%20hex.jpg) or [1](https://dl.dropboxusercontent.com/u/12804628/Macross/fileset0.dat.chunk001), [2](https://dl.dropboxusercontent.com/u/12804628/Macross/pack.idx),  [3](https://dl.dropboxusercontent.com/u/12804628/Macross/data.dat.chunk001), [4](https://dl.dropboxusercontent.com/u/12804628/Macross/lua.dat)?

Many thanks to anyone who can help me with this in any way.



Edit: I found out howfie started working on a ripper a while back but didn't finish: [http://code.google.com/p/sticklove/sour ... ross30.cpp](http://code.google.com/p/sticklove/source/browse/trunk/source/xentax/ripper/ps3_macross30.cpp)
## Post #2
- Username: Chthonic
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 23, 2012 4:08 am
- Post datetime: 2013-07-03T04:09:05+00:00
- Post Title: [PS3] Macross 30

I've already spoken to aluigi and he explained that the data files are done with LZS compression. He mentioned "the best solution in this case is having a script that handles the whole format correctly"
