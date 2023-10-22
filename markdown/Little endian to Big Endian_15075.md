## Post #1
- Username: dvoika
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Nov 08, 2014 4:19 am
- Post datetime: 2016-09-22T13:49:14+00:00
- Post Title: Little endian to Big Endian

Hello my friends 
I need to edit the file in a sequence of bits
ABCD on DCBA 


there is a program or script on this one ? my english is sux sorry
tnx for reply

progress:

get SIZE asize
math OFFSET = 4
math SIZE -= OFFSET
goto OFFSET
math SIZE /= 4
for i = 0 < SIZE
    get TMP long
next i
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-09-25T09:46:38+00:00
- Post Title: Little endian to Big Endian

If the whole file is just 32-bit integers (unlikely). You could probably open the file in Winhex then perform a 32-bit byte-swap on the whole file.

Cheers.
## Post #3
- Username: bekir007
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Aug 02, 2012 8:52 pm
- Post datetime: 2016-10-28T20:21:42+00:00
- Post Title: Little endian to Big Endian

You can use 010 editor. 

"Tools > Hex Operations > Swap"
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-11-05T11:35:57+00:00
- Post Title: Little endian to Big Endian

from the quickbms manual:
MATH TMP s 4
swaps a long

using it with a (little endian) binary file: 12 34 56 78
(insert print "%TMP%" for logging the variable)
result:
before
- SCRIPT's MESSAGE:
  2018915346 (-> 0x78563412)
after
- SCRIPT's MESSAGE:
  305419896 (-> 0x12345678)
