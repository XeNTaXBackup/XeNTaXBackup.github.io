## Post #1
- Username: MertKilic
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Apr 27, 2012 1:26 am
- Post datetime: 2014-06-01T13:05:17+00:00
- Post Title: SpongeBob SquarePants - Light Camera Pants (.SBT File)

Hi guys! I want to translate SpongeBob SquarePants - Light Camera Pants (PC) game to my language.
But I can't open .sbt file. I don't know how can I unpack and pack again.

I've added a file as an attachment.
I'm waiting for you guys. Help me please. 
[Dialogue.rar](https://xentaxbackup.github.io/file/7408_Dialogue.rar)
## Post #2
- Username: MertKilic
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Apr 27, 2012 1:26 am
- Post datetime: 2014-06-01T15:04:14+00:00
- Post Title: SpongeBob SquarePants - Light Camera Pants (.SBT File)

Okay, I don't know it's important or not, but I just want to share it.
I opened game file (sb_lcp.exe) with Resource Hacker. And I just found something like this.
But still I don't know how can I unpack text, or see that box for real.

Picture:
[http://s7.directupload.net/images/140601/7engm6gd.png](http://s7.directupload.net/images/140601/7engm6gd.png)
## Post #3
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2014-06-01T18:31:04+00:00
- Post Title: SpongeBob SquarePants - Light Camera Pants (.SBT File)

it's just xored with 0x30, for unpack you can use this quickbms script

```
get name basename
get strings short
for i = 0 < strings
	get str_size short
	for j = 0 < str_size
		get data byte
		math data ^ 0x30
		put data byte MEMORY_FILE
	next j
	put 0x0a0d short MEMORY_FILE
next i

string name + ".txt"
get size asize MEMORY_FILE
log name 0x00 size MEMORY_FILE
```
## Post #4
- Username: MertKilic
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Apr 27, 2012 1:26 am
- Post datetime: 2014-06-01T21:46:27+00:00
- Post Title: SpongeBob SquarePants - Light Camera Pants (.SBT File)

Thank you so much! It worked!
I know I asked a lot of questions but how can I pack the file?
## Post #5
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2014-06-02T07:08:28+00:00
- Post Title: SpongeBob SquarePants - Light Camera Pants (.SBT File)

need to do script for pack, i do it some of these days
## Post #6
- Username: MertKilic
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Apr 27, 2012 1:26 am
- Post datetime: 2014-06-02T19:02:25+00:00
- Post Title: SpongeBob SquarePants - Light Camera Pants (.SBT File)

> Reply from Thief1987
>
> need to do script for pack, i do it some of these days

I'm waiting. Thank you.
## Post #7
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2014-06-05T20:48:20+00:00
- Post Title: SpongeBob SquarePants - Light Camera Pants (.SBT File)

sorry for delaying, i'm forgot about it 

```
get name basename
put 0x00 short MEMORY_FILE
get size asize
set i = 0
for i
	savepos TMP
	getct str string 0x0D
	strlen str_size str
	goto TMP
	put str_size short MEMORY_FILE
	for j = 0 < str_size
		get data byte
		math data ^ 0x30
		put data byte MEMORY_FILE
	next j
	get dummy short
	savepos offset
	if offset = size
		break 
	endif
	
next i
goto 0x00 MEMORY_FILE
math i + 1
put i short MEMORY_FILE

string name + ".sbt"
get size2 asize MEMORY_FILE
log name 0x00 size2 MEMORY_FILE 
```

Apply to txt file
## Post #8
- Username: MertKilic
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Apr 27, 2012 1:26 am
- Post datetime: 2014-06-05T21:56:50+00:00
- Post Title: SpongeBob SquarePants - Light Camera Pants (.SBT File)

It worked! Thank you so so much!
