## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-01-11T21:28:51+00:00
- Post Title: calculating sample count

I'm working on a script to add a working RSTM header but I'm having problems to calculate the sample count. The variables I have are:

frequency
file size
channels
data rate (kbps)
How does the sample count calculate from these? I thought it's just (file size * freq) / data rate but apparently I'm wrong. :-\
For example: 44.100Hz stereo, 100kbps, 2665472 bytes. How many samples does this file have?
Sorry for this n00by question...
But thanks for your answers!
## Post #2
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2012-01-12T00:21:20+00:00
- Post Title: calculating sample count

as the data rate isn't precise value, you can only get approximate number of samples. if you can get data rate value with single bit precision, then you can calculate exact sample count.

convert data rate from kilobits-per-second to bytes-per-second:
100 kbps = 100000 bits per sec. = 12500 bytes per sec.
calculate file length in seconds:
2665472 bytes / 12500 bytes per sec. = 213,23776 seconds
calculate approx. sample count:
213,23776 seconds * 44100 samples per sec. = 9403785,216 samples for one channel, 18807570 for both.
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-01-12T13:01:37+00:00
- Post Title: calculating sample count

The contents of this post was deleted because of possible forum rules violation.
