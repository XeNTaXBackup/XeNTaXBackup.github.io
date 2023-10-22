## Post #1
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2017-04-19T04:58:35+00:00
- Post Title: Voodoo Vince Remaster - PC .HOT Files

Sup do0odz! the remaster for Voodoo Vince came out on the PC and it's aWESOME, i aLSO took a look at some of its files, never heard of the .HOT extension before, but maybe someone can take a gander at it c: i'm specifically looking for a possible sound extractor / sound player.

[https://www.mediafire.com/?1w1517srdcd2074](https://www.mediafire.com/?1w1517srdcd2074)

If anyone wants to go an EXTRA mile; here's also the ".HOT" extension for the models c:

[https://www.mediafire.com/?zp0w9ms24p5pb1l](https://www.mediafire.com/?zp0w9ms24p5pb1l)
## Post #2
- Username: Steve Blockhead
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 06, 2017 9:20 am
- Post datetime: 2017-05-06T01:26:08+00:00
- Post Title: Voodoo Vince Remaster - PC .HOT Files

I second this! I would love to see what can be done in terms of modding with Voodoo Vince. Such an underrated, but awesome Platformer! This gem needs mods!
## Post #3
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2017-05-06T13:55:29+00:00
- Post Title: Voodoo Vince Remaster - PC .HOT Files

```
get VERSION long
get HEADER_OFFSET long
get DATA_OFFSET long
get FILE_SIZE long
get NAME_OFFSET long
get FILES long
append
for i = 0 < FILES
	get ID long
	get DUMMY long
	get HEADER_SIZE long
	get HEADER_OFFSET long
	get DATA_SIZE long
	get DUMMY long
	get DATA_OFFSET long
	get DUMMY long
	savepos POS
	goto NAME_OFFSET
	get NAME string
	padding 4
	savepos NAME_OFFSET
	goto POS
	math DATA_SIZE -= HEADER_SIZE
	log NAME HEADER_OFFSET HEADER_SIZE
	log NAME DATA_OFFSET DATA_SIZE
next i
append
```
