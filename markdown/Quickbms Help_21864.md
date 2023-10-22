## Post #1
- Username: theclub654
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Oct 14, 2015 8:57 am
- Post datetime: 2020-03-11T01:37:35+00:00
- Post Title: Quickbms Help

Im new to reverse engineering file formats but im trying to write a quickbms script to extract fles from a afs but its not working can someone help me out here.


endian little
idstring "AFS\x00"
get FILENUM long

for i = 0 < FILENUM
get pointer long
get SIZE long
next i
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-11T18:40:42+00:00
- Post Title: Quickbms Help

> Reply from theclub654 ↑Wed Mar 11, 2020 9:37 am at Wed Mar 11, 2020 9:37 am
>
> im trying to write a quickbms script to extract fles from a afs but its not working can someone help me out here.What do you think it should do? In fact it works on an afs sample (but doesn't extract yet):

  offset   filesize   filename (?)
--------------------------------------
files 5
addr: 2048, size: 2343936
addr: 2347008, size: 2132888
addr: 4481024, size: 288
addr: 4483072, size: 1461936
addr: 5945344, size: 1174168

I'd suggest to insert (debug) print lines such like:
print "files %FILENUM%"

The third found file params (addr: 4481024, size: 288) lead to this:
.



extract_AFS.png (25.2 KiB) Viewed 40 times


.
Now you gonna have to insert a log line to get/log the files.
Good luck. 

btw: I assume chr_dat2 is not part of the file contents (not sure). You may read it and use it to name the file to be logged.
## Post #3
- Username: theclub654
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Oct 14, 2015 8:57 am
- Post datetime: 2020-03-12T01:26:30+00:00
- Post Title: Quickbms Help

I really couldn't understand what you are saying so what do I have to edit in my bms script in order to extract the afs file
## Post #4
- Username: theclub654
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Oct 14, 2015 8:57 am
- Post datetime: 2020-03-12T01:36:47+00:00
- Post Title: Quickbms Help

the afs im tryna extract doesn't have filenames either
