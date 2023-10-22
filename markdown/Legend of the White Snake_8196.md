## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-06T07:06:07+00:00
- Post Title: Legend of the White Snake

白蛇传说
Homepage: [http://baishe.klgame.com/](http://baishe.klgame.com/)



Just saw this game and downloading. Will post more when I'm done. Hopefully it's not another odd archive..
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-22T04:44:52+00:00
- Post Title: Legend of the White Snake

Well this was simple enough

```

idstring "5SHEN"
getdstring skip 27
get FILES long
get TABLEOFS long

goto TABLEOFS
for i = 0 < FILES do
	getdstring NAME 260
	getdstring unk 32
	get unk long
	get OFFSET long
	get SIZE long
	get unk long
	get unk long
	log NAME OFFSET SIZE
next i

```
