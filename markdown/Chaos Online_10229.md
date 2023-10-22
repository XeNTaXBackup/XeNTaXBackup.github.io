## Post #1
- Username: windfury
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-03-16T20:35:46+00:00
- Post Title: Chaos Online

This game uses nif version 
Gamebryo File Format, Version 20.6.0.0
[http://chaos.playcybergames.com/en/download.php](http://chaos.playcybergames.com/en/download.php)
[http://www.youtube.com/watch?feature=pl ... EPeLPPzKm0](http://www.youtube.com/watch?feature=player_embedded&v=kEPeLPPzKm0)

i did not do the recursive directory info because i was having trouble in quickbms storing the variables.

```
get ftable long
goto ftable
getdstring null 0x16
get files long
savepos TBL1
set tsize files
math tsize * 0x15
set TBL2 TBL1
math TBL2 + tsize
math TBL2 + 0xC
set TBL3 TBL2
set tsize files
math tsize * 0x4
math TBL3 + tsize
math TBL3 + 0x12
print "%TBL3%"
goto TBL3
savepos tmp
set counter 0
get tsize asize
Do
math counter += 1
getdstring NAME 0x100
get type long
if type == 16
getdstring null 0xC
else
getdstring null 0x14
get tmp long
putarray 0 tmp NAME
endif
savepos tmp
while tmp < tsize
print "%counter%"
goto TBL1
for i = 0 < files
get unk byte
get offset long
get unk1 long
get size long
get unk1 long
get unk1 long
getarray NAME 0 i
log NAME offset size
next i

```


imports fine with the blender nif importer from mariusz szkaradek
## Post #2
- Username: windfury
- Rank: beginner
- Number of posts: 23
- Joined date: Sun May 23, 2010 2:54 pm
- Post datetime: 2013-06-17T11:32:39+00:00
- Post Title: Chaos Online

Uhm, what file do I use this with?
I tried it with the .pcl file but it doesn't seem to work.
## Post #3
- Username: glcat
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Feb 15, 2012 12:31 pm
- Post datetime: 2013-06-25T02:25:24+00:00
- Post Title: Chaos Online

oh it does not work ,PL fixed,thank you very much
## Post #4
- Username: darlandk
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 15, 2011 8:58 pm
- Post datetime: 2013-07-20T04:34:10+00:00
- Post Title: Chaos Online

> Reply from glcat
>
> oh it does not work ,PL fixed,thank you very much
## Post #5
- Username: Larss
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Aug 13, 2012 6:54 am
- Post datetime: 2013-07-27T03:17:55+00:00
- Post Title: Chaos Online

What does the script extract?
## Post #6
- Username: Larss
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-07-28T17:54:11+00:00
- Post Title: Chaos Online

putvar seems broken here is a script with folders that does not use it.

```
get ftable long
goto ftable
getdstring null 0x16
get files long
append
for i = 0 < files
get unk byte
savepos tmp
log MEMORY_FILE tmp 4
get offset long
get unk1 long
savepos tmp
log MEMORY_FILE2 tmp 4
get size long
get unk1 long
get unk1 long
next i
append
getdstring null 0xC
set tsize files
math tsize * 0x4
math tsize + 0x12
getdstring null tsize
savepos tmp
get tsize asize
Do
getdstring NAME 0x100
get type long
if type == 16
getdstring null 0xC
set DIR NAME
else
getdstring null 0x14
get num long
set NAME2 DIR
string NAME2 + NAME
math num * 4
#print "%num%"
get size asize MEMORY_FILE
#print "%size%"
goto num MEMORY_FILE
goto num MEMORY_FILE2
get offset long MEMORY_FILE
get size long MEMORY_FILE2
log NAME2 offset size
endif
savepos tmp
while tmp < tsize

```
## Post #7
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2013-09-10T07:18:21+00:00
- Post Title: Chaos Online

Error: [myfseek] the offset 0x0000000134200000 in the file -1 can't be reached
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-10T11:20:07+00:00
- Post Title: Chaos Online

> Reply from mappy2012
>
> Error: [myfseek] the offset 0x0000000134200000 in the file -1 can't be reached
You need latest QuickBMS 0.5.24b
## Post #9
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2013-09-21T20:12:12+00:00
- Post Title: Chaos Online

> Reply from Ekey
>
> mappy2012 wrote:Error: [myfseek] the offset 0x0000000134200000 in the file -1 can't be reached
You need latest QuickBMS 0.5.24b

Getting the same error even with that version...
## Post #10
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2013-10-12T07:24:47+00:00
- Post Title: Chaos Online

> Reply from Ekey
>
> mappy2012 wrote:Error: [myfseek] the offset 0x0000000134200000 in the file -1 can't be reached
You need latest QuickBMS 0.5.24b

hi~ekey,
i use latest QuickBMS 0.5.26,get Error: [myfseek] the offset 0x0000000221500000 in the file -1 can't be reached
Script does not support the new version of the client？？？
## Post #11
- Username: axeladsmith
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Sep 01, 2013 12:12 pm
- Post datetime: 2014-05-18T13:03:45+00:00
- Post Title: Chaos Online

for script need use quickbms for 4gb files
## Post #12
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-09-07T08:01:46+00:00
- Post Title: Chaos Online

well many thanks for that chrox, but after try use them, I got same error as @mappy2012 so I think files was change a bit, maybe is possible update script? here some samples, many thanks.

[http://puu.sh/bp1No/9df6dd6ade.7z](http://puu.sh/bp1No/9df6dd6ade.7z)
