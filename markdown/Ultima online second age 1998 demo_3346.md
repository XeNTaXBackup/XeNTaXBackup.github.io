## Post #1
- Username: Darius Terrance
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 07, 2009 12:00 am
- Post datetime: 2009-02-06T16:12:24+00:00
- Post Title: Ultima online second age 1998 demo

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-02-08T00:13:13+00:00
- Post Title: Ultima online second age 1998 demo

Wrong forum
## Post #3
- Username: Darius Terrance
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 07, 2009 12:00 am
- Post datetime: 2009-02-08T13:14:37+00:00
- Post Title: Ultima online second age 1998 demo

> Reply from Rheini
>
> Wrong forum

Sorry, i'm a new one.
The data has been correctly decrypted but know I have another couple of files that seem sub-encrypted.

Rheini, i've sent you an e-mail.

^^
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-02-08T17:30:18+00:00
- Post Title: Ultima online second age 1998 demo

Well no similarities among the files, no identifiable header. You probably have to debug the exe.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-02-08T17:51:22+00:00
- Post Title: Ultima online second age 1998 demo

just for reference in case someone else was interested, the tool for decrypting uodemo.dat is [http://aluigi.org/papers/uodemoext.zip](http://aluigi.org/papers/uodemoext.zip)

now about the m scripts.
I have rechecked the executable and I see no traces of encryption or compression, just because there are no functions which perform an input->output operations on these files.

the only thing I see is a "strange" (very strange) set of operations which do some things without converting the input data in something else.
for example at rva 00610B40 there is a fixed 16bit table used to perform some comparisons with each 16 bit value of these files and at rva 00426EC1 there is the beginning of all the operations on the content of these .m files of the scripts folder.

the only hypothesis I have is that uodemo interpretes these files which so are something like "compiled" scripts, but nothing of "easily" readable (imho)
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-02-08T23:46:27+00:00
- Post Title: Ultima online second age 1998 demo

> Reply from Bugtest
>
> the only hypothesis I have is that uodemo interpretes these files which so are something like "compiled" scripts, but nothing of "easily" readable (imho)
Indeed possible. If that's the case there's not much you could do. Even if you had a disassembler, making some changes would be difficult. Precompiled scripts is the best "protection" I can think of ^^
