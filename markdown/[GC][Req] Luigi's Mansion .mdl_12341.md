## Post #1
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2014-12-07T05:25:32+00:00
- Post Title: [GC][Req] Luigi's Mansion .mdl?

Hello, i'm beginner in model, i unpacked .szp files due to [viewtopic.php?f=16&t=3485&view=next](http://forum.xentax.com/viewtopic.php?f=16&t=3485&view=next)
And i have some .mdl, but i can't do anything to open it  and then i tried google, and they said mdl2obj is a suitable tool, but i don't know how to use mdl2obj.py @@ it got an error: module numpy not found. So can we have another choice to open .mdl of LM?
Sample .mdl: [http://www.mediafire.com/download/340h2 ... t/baby.mdl](http://www.mediafire.com/download/340h23ht1w0lelt/baby.mdl)
mdl2obj.py : [http://www.romhacking.net/utilities/1025/](http://www.romhacking.net/utilities/1025/)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-07T10:22:01+00:00
- Post Title: [GC][Req] Luigi's Mansion .mdl?

> Reply from onelove1210
>
> Hello, i'm beginner in model[...]
use mdl2obj.py @@ it got an error: module numpy not found.
Hi,
python is not the very best way to get 3D models being a beginner (imho).

Download numpy
[https://pypi.python.org/pypi/numpy](https://pypi.python.org/pypi/numpy)
and try to get it working with your python installation.
(Python package distutils is required, too.
I didn't use numpy so far so there might be other caveats.)

> So can we have another choice to open .mdl of LM?
Yep, analyzing from scratch using hex2obj for example 
- but it doesn't make sense here having an existing python solution.
## Post #3
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2014-12-07T12:37:12+00:00
- Post Title: [GC][Req] Luigi's Mansion .mdl?

> Reply from shakotay2
>
> 
Hi,
python is not the very best way to get 3D models being a beginner (imho).

Download numpy
https://pypi.python.org/pypi/numpy
and try to get it working with your python installation.
(Python package distutils is required, too.
I didn't use numpy so far so there might be other caveats.)

OMG, SF is maintenanced at the moment, and no alternative link
Would you mind helping me with hex2obj to open the sample file? i don't know much about it
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-07T13:43:02+00:00
- Post Title: [GC][Req] Luigi's Mansion .mdl?

reinventing the wheel is a waste of time. A solution exists - you should wait.

Anyway - you'll need to exercise the tutorial sample (tut button) to understand hex2obj.
(It's a helper tool for simple models only, not a one-click-solution.)

Here's a point cloud (no face indices) from baby.mdl:



babe_PtCloud.jpg (71.33 KiB) Viewed 79 times
## Post #5
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2014-12-10T04:44:29+00:00
- Post Title: [GC][Req] Luigi's Mansion .mdl?

sorry for my late, i tried mdl2obj.py, and got an error : 
"  File "C:\texdump.py", line 1, in <module>
    from PyQt4 import QtGui
ImportError: cannot import name QtGui" 
Although i had downloaded PyQt4, any solutions?
