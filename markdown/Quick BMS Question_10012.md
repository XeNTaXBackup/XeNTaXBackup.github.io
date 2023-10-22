## Post #1
- Username: Romsstar
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 03, 2012 6:30 pm
- Post datetime: 2013-01-06T10:08:14+00:00
- Post Title: Quick BMS Question

if I have an occurence of two lines of zeros after every header of a file,
is there a nicer way of writing this in quickBMS than?
get ZERO long
get ZERO2 long
get ZERO3 long
get ZERO4 long

This just looks stupid. I mean it doesn't slow down or anything. But I'm sure there must be a faster and nicer way of doing it?
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-01-07T09:56:57+00:00
- Post Title: Quick BMS Question

getdstring ZERO 16
## Post #3
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2013-01-07T11:05:36+00:00
- Post Title: Quick BMS Question

Is it even necessary to get them? Can you simply skip them?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-07T11:24:23+00:00
- Post Title: Quick BMS Question

there is a goto command if its only in the header you can say like 
goto 0x20
but if its in a loop and say you read 5 int values but only the first or last 2 are usefull its faster to do 
getdstring null 0xXX
otherwise you would have to do 
savepos tmp
math tmp + XX
goto tmp
## Post #5
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-01-08T19:10:12+00:00
- Post Title: Quick BMS Question

aluigi

It's real add reimport for COMP_DK2 compression? Really need to

Or maybe exist other compression tool. I'm dont need repack, only compress
