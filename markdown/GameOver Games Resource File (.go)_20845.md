## Post #1
- Username: Nicknine
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Oct 04, 2015 3:29 am
- Post datetime: 2019-07-23T13:49:24+00:00
- Post Title: GameOver Games Resource File (.go)

Games developed by GameOver Games store their assets in GO files, I've mostly figured out the format but the files appear to be compressed. I would like to have this looked at. Here are samples from Arkanoid: The Virtual Isles: [https://www77.zippyshare.com/v/O3Sdv034/file.html](https://www77.zippyshare.com/v/O3Sdv034/file.html)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-07-23T16:16:30+00:00
- Post Title: GameOver Games Resource File (.go)

Your link doesn't work.  Can you check it?  Thanks.
## Post #3
- Username: Nicknine
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Oct 04, 2015 3:29 am
- Post datetime: 2019-07-23T20:18:35+00:00
- Post Title: GameOver Games Resource File (.go)

> Reply from DKDave ↑Wed Jul 24, 2019 12:16 am at Wed Jul 24, 2019 12:16 am
>
> 
Your link doesn't work.  Can you check it?  Thanks.

Works on my machine(TM).
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-07-23T22:45:21+00:00
- Post Title: GameOver Games Resource File (.go)

Ok, thanks.  I just get error "403 - Forbidden" every time.  Hopefully someone else can see it, or if you could upload it elsewhere?  Thanks.
## Post #5
- Username: Nicknine
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Oct 04, 2015 3:29 am
- Post datetime: 2019-07-24T06:38:40+00:00
- Post Title: GameOver Games Resource File (.go)

> Reply from DKDave ↑Wed Jul 24, 2019 6:45 am at Wed Jul 24, 2019 6:45 am
>
> 
Ok, thanks.  I just get error "403 - Forbidden" every time.  Hopefully someone else can see it, or if you could upload it elsewhere?  Thanks.

Try MEGA: [https://mega.nz/#!vdx3lSqC!x95Zo5SwNiRW ... s4lMINIi-k](https://mega.nz/#!vdx3lSqC!x95Zo5SwNiRW6aXhPoYbfpZEwb3tQynoxs4lMINIi-k)
## Post #6
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-07-24T17:42:13+00:00
- Post Title: GameOver Games Resource File (.go)

Thanks.  That one worked.

Yes, the files are compressed using ZLIB compression.  It should be easy enough to come up with a BMS script, if there isn't one already in existence.
## Post #7
- Username: Nicknine
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Oct 04, 2015 3:29 am
- Post datetime: 2019-07-24T18:18:49+00:00
- Post Title: GameOver Games Resource File (.go)

> Reply from DKDave ↑Thu Jul 25, 2019 1:42 am at Thu Jul 25, 2019 1:42 am
>
> 
Thanks.  That one worked.

Yes, the files are compressed using ZLIB compression.  It should be easy enough to come up with a BMS script, if there isn't one already in existence.

Thanks, here's a script:

```
goto 0x26
get FILES long
goto 0x100
comtype zlib

for i = 0 < FILES
	get NAME_OFF long
	get ZERO long
	get NEXT_OFF long
	get SIZE long
	get ZSIZE long
	
	goto NAME_OFF
	get NAME string
	savepos OFFSET
	
	clog NAME OFFSET ZSIZE SIZE
	goto NEXT_OFF
next i

```
## Post #8
- Username: Nicknine
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Oct 04, 2015 3:29 am
- Post datetime: 2020-03-10T23:51:14+00:00
- Post Title: GameOver Games Resource File (.go)

I have found an older version of this format and it appears to be using a different compression: [https://www95.zippyshare.com/v/0IWuM8Yc/file.html](https://www95.zippyshare.com/v/0IWuM8Yc/file.html)
Could someone identify the compression used here, please?

EDIT: Seems to be some LZW variation?
