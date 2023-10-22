## Post #1
- Username: Peter49
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 10, 2014 11:22 pm
- Post datetime: 2016-05-29T14:15:06+00:00
- Post Title: Cultures 3-4 (.lib)

Can someone write a quick BMS script to Cultures 3(Northland) and Cultures 4(8th wonder of the world) lib file?
I want to translate the game
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-05-29T19:44:03+00:00
- Post Title: Cultures 3-4 (.lib)

wrong section - this needs to be posted here - [viewforum.php?f=35](http://forum.xentax.com/viewforum.php?f=35)

any sample files? will the demo do for research purposes?
## Post #3
- Username: Peter49
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 10, 2014 11:22 pm
- Post datetime: 2016-05-31T17:46:09+00:00
- Post Title: Cultures 3-4 (.lib)

> Reply from WRS
>
> wrong section - this needs to be posted here - viewforum.php?f=35

any sample files? will the demo do for research purposes?

Oops, that's my fault.
I will translate Cultures 2,3,4
I found a extractor program for Cultures 2 but i do not know how to reimport the files.
Cultures 2:data0001.lib,data0002.lib and t.dat
[https://www.dropbox.com/sh/cb72wr7hol6f ... p4Z2a?dl=0](https://www.dropbox.com/sh/cb72wr7hol6f3au/AAC9K_wySZ-bQzTG5cK7p4Z2a?dl=0)
Cultures 3:data0001.lib and t.dat
[https://www.dropbox.com/sh/bi227w29l5ys ... xqn3a?dl=0](https://www.dropbox.com/sh/bi227w29l5ysr3h/AACyqWZxBps7zEZ4RlwDxqn3a?dl=0)
Cultures 4:data0001.lib and t.dat
[https://www.dropbox.com/sh/ja3vqne27o6b ... T3wba?dl=0](https://www.dropbox.com/sh/ja3vqne27o6brzy/AACYuu4dkYfscC7U-oNXT3wba?dl=0)
The game text,pictures etc. files, it is in .lib file(s),however i uploaded .dat files too, this is in the same folder with the .lib file.
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-05-31T22:55:46+00:00
- Post Title: Cultures 3-4 (.lib)

i went ahead and made a start on the demo as the structure has a top-only file list at the start.

**not complete** just a 5-minute pseudocode

```
get COUNT long
for i = 0 to COUNT
get FILES long
get NLEN long
getdstring NAME NLEN
next i

# then actual files are referenced differently:
# 1387 is the first 'FILES' value
for i = 0 to 1387
get UNKNOWN long # offset?
get NLEN long
getdstring NAME NLEN
get UNKNOWN long # length?
next i


```


maybe this is enough for someone to take over?
## Post #5
- Username: Peter49
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 10, 2014 11:22 pm
- Post datetime: 2016-06-05T19:37:50+00:00
- Post Title: Cultures 3-4 (.lib)

Can somebody help ?
