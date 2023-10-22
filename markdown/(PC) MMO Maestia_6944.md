## Post #1
- Username: joqqy
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-09T18:50:53+00:00
- Post Title: (PC) MMO Maestia

[http://maestia.bigpoint.com/](http://maestia.bigpoint.com/)

Quickbms extractor

```
findloc start string "\x01\x92\x28\x9C"
print "%start%"
goto start
get type1 long
get totalsize long
get type2 long
get nsize long
math nsize - 8
getdstring uname nsize
set NAME unicode uname
get type3 long
get type3size long
math type3size - 8
getdstring null type3size
get type4 long
get type4size long
math type4size - 8
getdstring null type4size
get type5 long
get type5size long
math type5size - 8
getdstring null type5size
get type6 long
get type6size long
math type6size - 8
savepos offset
log name offset type6size
math offset + type6size
goto offset
next

```
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-09T19:18:48+00:00
- Post Title: (PC) MMO Maestia

Nice, looks like I will have another download tonight  
Edit
lol it seems like non-EU people can't DL the client from bigpoint, though it looks like there's a CB client available on MMORPG. lol it seems like non-EU people can't DL the client from bigpoint, though it looks like there's a CB client available on MMORPG.
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-16T02:24:27+00:00
- Post Title: (PC) MMO Maestia

> Reply from finale00
>
> Nice, looks like I will have another download tonight  
Edit
lol it seems like non-EU people can't DL the client from bigpoint, though it looks like there's a CB client available on MMORPG. lol it seems like non-EU people can't DL the client from bigpoint, though it looks like there's a CB client available on MMORPG.is really easy get client anyway, here you have downloader client enjoy.

[Maestia Client Downloader](http://filekeen.com/4ulr8v2m5474/Maestia-Downloader.exe.html)

The transfer is very good 
[Maestia Updater.png](https://xentaxbackup.github.io/file/4495_Maestia Updater.png)
