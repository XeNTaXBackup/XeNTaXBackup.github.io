## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-08-17T16:25:51+00:00
- Post Title: Quake 4 (Xbox 360) - *.xpr sound archives

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-11-11T17:14:31+00:00
- Post Title: Quake 4 (Xbox 360) - *.xpr sound archives

Finally gained enough experience to code that script myself!  The extracted XMA files have a different header. I'll write another script to convert them to decodable XMA files soon.
Here is the script, works on all the *.xpr files of Quake 4 for Xbox 360. 

```
endian big
get INFOSIZE long
get DATASIZE long 
get FILES long
set OFFCORR INFOSIZE
math OFFCORR += 0xc

for i = 1 <= FILES
	getDstring EXT 4
	get HEADER long
	get HEADERSIZE long
	get OFFSET long
	get SIZE long
	get NAMEPOS long
	math HEADER += 0xc
	math NAMEPOS += 0xc
	math OFFSET += OFFCORR
	savepos MYOFF
	goto NAMEPOS
	get NAME string
	string NAME += "."
	string NAME += EXT
	savepos NAMEPOS
	goto MYOFF
	log MEMORY_FILE 0 0
	append
	log MEMORY_FILE HEADER HEADERSIZE
	log MEMORY_FILE OFFSET SIZE
	get SIZE asize MEMORY_FILE
	log NAME 0 SIZE MEMORY_FILE
	append
next i
```
