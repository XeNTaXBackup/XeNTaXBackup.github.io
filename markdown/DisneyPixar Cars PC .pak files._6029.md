## Post #1
- Username: Eradicon
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Feb 11, 2011 1:20 am
- Post datetime: 2011-02-10T19:10:29+00:00
- Post Title: Disney/Pixar Cars PC .pak files.

I've tried so hard to unlock the files for Cars the Video Game, but to no prevail. The files I'm trying to unlock are Audio.pak,Global.pak, and UI.pak. Can somebody plese help he out?
## Post #2
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-02-10T20:47:10+00:00
- Post Title: Disney/Pixar Cars PC .pak files.

You must post some file samples
## Post #3
- Username: Eradicon
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Feb 11, 2011 1:20 am
- Post datetime: 2011-02-17T12:48:33+00:00
- Post Title: Disney/Pixar Cars PC .pak files.

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-02-17T17:21:19+00:00
- Post Title: Disney/Pixar Cars PC .pak files.

no other header info except name, position and size - so no compression with PAK files at least   

here's a script for global pak (warning: will take time to run due to large file sizes) it should work on others too

```
# quickbms script for Cars PAK

get FCOUNT long

set DATAPOS long FCOUNT
math DATAPOS *= 108
math DATAPOS += 4

for F = 1 to FCOUNT
  getdstring FNAME 100
  get FPOS long
  get FSIZE long
  math FPOS += DATAPOS
  log FNAME FPOS FSIZE
next F

```
## Post #5
- Username: Eradicon
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Feb 11, 2011 1:20 am
- Post datetime: 2011-02-19T15:48:48+00:00
- Post Title: Disney/Pixar Cars PC .pak files.

so how do i run the script?
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-02-19T19:37:45+00:00
- Post Title: Disney/Pixar Cars PC .pak files.

> Reply from Eradicon
>
> so how do i run the script?

i commented its a quickbms script. you could look that up next time, or just spent a little more time on this forum    

multiex now has a quickbms script option - [http://multiex.xentax.com/](http://multiex.xentax.com/)
or
[http://aluigi.altervista.org/papers.htm#quickbms](http://aluigi.altervista.org/papers.htm#quickbms) (minimal gui)
