## Post #1
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-08T11:10:15+00:00
- Post Title: Toy Story 3 ZIP help please

Hello all,

I have a small problem. I'm trying to repack this zip file for a long time. I can unpack it and so on, But once i do repack it always crashed, because it countaints MD5 hash for all file in the zip, pls see below. Can anyone help me out please ?? That MD5 seems to be crypted or something.....



```
http://warimagehost.net/files/startup_ORIG.zip
```
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-08T13:10:19+00:00
- Post Title: Toy Story 3 ZIP help please

extract using winrar its a normal zip.
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-08T13:24:38+00:00
- Post Title: Toy Story 3 ZIP help please

> Reply from chrrox
>
> extract using winrar its a normal zip.

I know it is ! But when i do repack or change anything in the file. Game is crashing coz each file got MD5 check writen in the zip file....
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-08T19:12:27+00:00
- Post Title: Toy Story 3 ZIP help please

anyone pls ?
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-12-08T21:10:22+00:00
- Post Title: Toy Story 3 ZIP help please

this is a standard zip format with a custom comment field for the raw MD5 hash of the file.

when you repack the zip you need to add the comment field:

```
KF\x13\x00MD5
```
 followed by the 16-byte md5 hash

i'm not sure if any zip programs allow you to do this automatically though
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-09T07:50:57+00:00
- Post Title: Toy Story 3 ZIP help please

> Reply from WRS
>
> this is a standard zip format with a custom comment field for the raw MD5 hash of the file.

when you repack the zip you need to add the comment field:
Code: Select allKF\x13\x00MD5 followed by the 16-byte md5 hash

i'm not sure if any zip programs allow you to do this automatically though

Thank you. Did know this but that number got only 21 bytes and standart MD5 hash got 32 bytes, so i 'm confused 
Is there any tool or any way to conver that 32 byte hash to that their format please ? I have no problem to insert it manually but i need to know what to insert  ?

Thank you
## Post #7
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-12-09T12:45:23+00:00
- Post Title: Toy Story 3 ZIP help please

You can use [http://www.pc-tools.net/win32/md5sums/](http://www.pc-tools.net/win32/md5sums/) in Base64 mode

ex.

```
md5sums -B -u text.tfx > text.md5.txt
```


and it will make a base64 encoded string, which after decoding will be 16-byte long sequence, which is written in that zip file.

It's not so comfortable solution, but maybe someone else knows better way how to do it
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-09T13:15:48+00:00
- Post Title: Toy Story 3 ZIP help please

> Reply from merlinsvk
>
> You can use http://www.pc-tools.net/win32/md5sums/ in Base64 mode

ex.
Code: Select allmd5sums -B -u text.tfx > text.md5.txt

and it will make a base64 encoded string, which after decoding will be 16-byte long sequence, which is written in that zip file.

It's not so comfortable solution, but maybe someone else knows better way how to do it

That is perfect if works , gonna try now  thx


EDIT: It it something else it generate some Unix format MD5 hash, not what i needed
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-09T16:03:27+00:00
- Post Title: Toy Story 3 ZIP help please

I guess that is is : 

Write simple application to do it : 

```
http://warimagehost.net/files/MD5Hash Check.exe
```
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-09T18:15:35+00:00
- Post Title: Toy Story 3 ZIP help please

I don't see problems or difficult things, it's just like WRS said:
"KF\x13\x00MD5" followed by the md5 in binary form (so 16 bytes).
if you want I can write a script for doing the job automatically but if you must modify only one or two files is better if you do it by hand :)
## Post #11
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-09T19:24:58+00:00
- Post Title: Toy Story 3 ZIP help please

> Reply from aluigi
>
> I don't see problems or difficult things, it's just like WRS said:
"KF\x13\x00MD5" followed by the md5 in binary form (so 16 bytes).
if you want I can write a script for doing the job automatically but if you must modify only one or two files is better if you do it by hand

You mean pack back into ZIp with this format? That would be great  Pls if you can...
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-09T20:54:36+00:00
- Post Title: Toy Story 3 ZIP help please

forget what I said about the "possible" script, I was thinking to other things in general.
## Post #13
- Username: TKFRvision
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Oct 28, 2021 6:07 am
- Post datetime: 2021-10-28T15:48:03+00:00
- Post Title: Toy Story 3 ZIP help please

It should be possible using my [script](https://github.com/TKFRvisionOfficial/Cars2TheVideoGameModding/blob/main/why.py) for cars 2: the video game.
Same dev, same engine so it should work...
