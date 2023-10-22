## Post #1
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-10-30T01:44:42+00:00
- Post Title: Can someone compile this for me?

Hello fellows. I was hoping someone could quickly compile a source file for me, as I have no idea how to do it properly. There is a readme included.

[http://www.sendspace.com/file/6k2n1w](http://www.sendspace.com/file/6k2n1w)
## Post #2
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-11-05T16:15:01+00:00
- Post Title: Can someone compile this for me?

Sorry to double post, but I forgot to mention that this is a fully-functional Paper Mario: The Thousand Year Door and Super Paper Mario model and animation viewer. It is written in C++, but is supposedly to be used for MingW + MingSYS, and contains a Makefile
## Post #3
- Username: shakotay
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 29, 2010 5:43 am
- Post datetime: 2010-11-09T02:05:55+00:00
- Post Title: Can someone compile this for me?

There is a 3DTest.exe in the win32 subfolder. So why compile the project?

You have to call the exe at the command prompt with 3DTest ModelFileName.

I don't owe the games; so don't know what ModelFileName is like. That's on your own...

edit: c_gonbaba is a name; can be found in the sample input subfolder.
[http://www.pic-upload.de/view-7695320/gonbaba.jpg.html](http://www.pic-upload.de/view-7695320/gonbaba.jpg.html)

And for all those who are versed in 3D modelling: there are infos about the vertex coordinates

(c_gonbaba.info.txt) Block 4, 5: Vertex Coordinates

```
      ID|   VertID|->                Vertex Coordinates|
------------------------------------------------------------------------------------------------------------------------

       0:        7 -> (   -34.080,    12.425,     0.000)
       1:        4 -> (   -49.281,    20.000,     0.000)
       2:        3 -> (   -34.080,    20.000,     0.000)
       3:        5 -> (   -49.373,   -20.000,     5.000)
       4:        0 -> (   -62.746,   -20.000,     0.000)
       5:        8 -> (   -62.746,    12.287,     0.000)
       6:        6 -> (   -49.327,    -0.118,    10.000)
       7:        1 -> (   -34.080,   -20.000,     0.000)
       8:        5 -> (   -49.373,   -20.000,     5.000)
       9:        6 -> (   -49.327,    -0.118,    10.000)
      10:        7 -> (   -34.080,    12.425,     0.000)
      11:        8 -> (   -62.746,    12.287,     0.000)
      12:        4 -> (   -49.281,    20.000,     0.000)
      13:        6 -> (   -49.327,    -0.118,    10.000)
      14:        8 -> (   -62.746,    12.287,     0.000)
      15:        2 -> (   -62.746,    20.000,     0.000)
      16:        4 -> (   -49.281,    20.000,     0.000)
      17:        7 -> (   -34.080,    12.425,     0.000)
      18:        6 -> (   -49.327,    -0.118,    10.000)
      19:        4 -> (   -49.281,    20.000,     0.000)
```


Could not figure out where/how the faces can be found.
## Post #4
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-11-11T17:40:50+00:00
- Post Title: Can someone compile this for me?

I hadn't noticed that! Thank you.

But still, I'd like this project compiled properly so i can view the animations as well...
## Post #5
- Username: shakotay
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 29, 2010 5:43 am
- Post datetime: 2010-11-13T22:56:05+00:00
- Post Title: Can someone compile this for me?

Did not find a hint that animations can be played with this project without doing additional coding but ok:

the pm model viewer project should be compiled like this (gcc)

make -fmakefile

or with codeblocks/mingw:
mingw32-make -fmakefile

Did not test this because you'll have to install SFML-1.5 before.

From the Readme:

```
Download the SFML-1.5 SDK and set the include and library paths as appropriate to your system.
```

[http://www.sfml-dev.org/tutorials/1.5/start-cb.php](http://www.sfml-dev.org/tutorials/1.5/start-cb.php)

You can download the minimal package (libraries + headers) here:
[http://www.sfml-dev.org/download.php](http://www.sfml-dev.org/download.php)

Hope this helps.
