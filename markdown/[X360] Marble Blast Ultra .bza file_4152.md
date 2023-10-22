## Post #1
- Username: GXavs
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Feb 19, 2010 6:19 pm
- Post datetime: 2010-02-19T12:03:08+00:00
- Post Title: [X360] Marble Blast Ultra .bza file

It's a small XBLA game so this file is the only archive it comes with. I took a 2MB rip of it, the full file is 23MB. Let me know if you want the full thing.
[http://rapidshare.com/files/352808636/marble.bza.zip](http://rapidshare.com/files/352808636/marble.bza.zip)

You can see the filenames near the start with a hex editor but that's as much as I can help you.
Thanks in advance.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-02-19T15:21:50+00:00
- Post Title: [X360] Marble Blast Ultra .bza file

```
get END_OF_INDEX long

for i = 0 < FILE_COUNT

	get OFFSET long
	get ZSIZE long
	get SIZE long

	get NULL char
	get NAMESIZE char
	getdstring NAME NAMESIZE
	
	if ZSIZE == SIZE
		log NAME OFFSET SIZE
	else
		clog NAME OFFSET ZSIZE SIZE
	endif
	
next i

```


note that there are some file duplicates when you run this script
## Post #3
- Username: GXavs
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Feb 19, 2010 6:19 pm
- Post datetime: 2010-02-19T17:31:38+00:00
- Post Title: [X360] Marble Blast Ultra .bza file

Thanks, it works pretty well. How can I rebuild the archive if I edit one of the files?
Also, is there any way to avoid the first 1-2 letters getting cut off file/folder names sometimes?
## Post #4
- Username: marterik231
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 27, 2012 7:00 am
- Post datetime: 2012-04-26T23:01:38+00:00
- Post Title: [X360] Marble Blast Ultra .bza file

can i have the full file  please email = [marterik231@live.ca](mailto:marterik231@live.ca)
