## Post #1
- Username: Esidor
- Rank: beginner
- Number of posts: 21
- Joined date: Thu May 14, 2009 12:53 pm
- Post datetime: 2009-05-19T12:26:54+00:00
- Post Title: Need help with Adventures of Robinson Crusoe .pak

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-19T12:40:53+00:00
- Post Title: Need help with Adventures of Robinson Crusoe .pak

Might indeed be xored. What game is it?
## Post #3
- Username: Esidor
- Rank: beginner
- Number of posts: 21
- Joined date: Thu May 14, 2009 12:53 pm
- Post datetime: 2009-05-19T13:11:10+00:00
- Post Title: Need help with Adventures of Robinson Crusoe .pak

Its "Adventures of Robinson Crusoe" a Hidden Object Casual Game.
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-19T13:21:03+00:00
- Post Title: Need help with Adventures of Robinson Crusoe .pak

Could you upload the exe and dlls?
## Post #5
- Username: Esidor
- Rank: beginner
- Number of posts: 21
- Joined date: Thu May 14, 2009 12:53 pm
- Post datetime: 2009-05-19T13:23:36+00:00
- Post Title: Need help with Adventures of Robinson Crusoe .pak

Here is a download link

[http://www.reflexive.com/AdventuresofRo ... related=13](http://www.reflexive.com/AdventuresofRobinsonCrusoe.html?related=13)

Maybe you can install it
## Post #6
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-05-19T14:05:37+00:00
- Post Title: Need help with Adventures of Robinson Crusoe .pak

Hi!

Can't help you alot here but just wanted to inform about forum rules regarding naming your thread. "help with .pak" is not enough  you should mention what game and such to make things easier  Good luck with the topic though
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-19T14:27:38+00:00
- Post Title: Need help with Adventures of Robinson Crusoe .pak

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "MIS"
goto 12
get FILES long
get BYTE byte
if BYTE == 0
    set ROT13 long 0x100
    get BYTE byte
    math ROT13 -= BYTE
else
    get ROT13 byte
endif
math ROT13 *= -1
filerot13 ROT13

goto 0x20
for i = 0 < FILES
    getdstring NAME 30
    get DUMMY short
    get SIZE long
    get OFFSET long
    get DUMMY long

    log NAME OFFSET SIZE
next i
```
*ps*: I agree with pixellegolas, the title of the thread sux so please change it to something more humanly comprehensible like "Adventures of Robinson Crusoe PAK"
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-19T14:48:43+00:00
- Post Title: Need help with Adventures of Robinson Crusoe .pak

Good job.
Ah those devs are so unimaginative. Where are the good old encryptions occupying you for weeks  Still remember the Settlers 2 encryption, that was fun
## Post #9
- Username: Esidor
- Rank: beginner
- Number of posts: 21
- Joined date: Thu May 14, 2009 12:53 pm
- Post datetime: 2009-05-19T17:08:28+00:00
- Post Title: Need help with Adventures of Robinson Crusoe .pak

Thank you sooo much 

And sorry for the wrong Topic, i did already edit it !
## Post #10
- Username: DrAcid
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 10, 2009 1:22 pm
- Post datetime: 2009-06-11T00:51:51+00:00
- Post Title: Need help with Adventures of Robinson Crusoe .pak

wow! Great job guys, really helped me out!

I just had one more question - how do I pack the files back into game archive?
Algorithm is found, so, I guess, there will be no problem writing a simple, cmdline tool? 

I would really appreciate that!

Thank You!

P.S.(I'm a n00b in whole "cracking archives", so please, go easy on me  )
