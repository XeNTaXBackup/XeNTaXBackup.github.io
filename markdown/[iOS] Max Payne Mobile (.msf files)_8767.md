## Post #1
- Username: toebi1987
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 30, 2010 3:39 pm
- Post datetime: 2012-04-13T17:24:07+00:00
- Post Title: [iOS] Max Payne Mobile (.msf files)

hi, i need the german sound files from max payne.
they are in a single msf file. but i have no idea how to extract it?
please help  

the file:
<link removed due forum rules violation>
## Post #2
- Username: gui679
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 15, 2012 12:00 am
- Post datetime: 2012-04-14T16:03:49+00:00
- Post Title: [iOS] Max Payne Mobile (.msf files)

I want it too.

I've downloaded the Brazilian Portuguese version of Max Payne for PC and I want to change the sounds of English Archive to PT-BR (if it's possible).
It will help us all of brazil :s

but I don't know how to open it too... :/

Any lights?

--
if helps, I've discovered how to open .RAS files of Max Payne 1... in the disc image of the game have archives named "MAX-FX", there has a program named "RASMaker".
## Post #3
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2012-04-18T07:26:17+00:00
- Post Title: [iOS] Max Payne Mobile (.msf files)

here, mate:

```
idstring \x00\x00\x03\xE7\x00\x00\x00\x02
get FILES long

for i = 0 < FILES
	get OFFSET long
	get SIZE long
	get NSIZE byte
	getdstring NAME NSIZE
	
	log NAME OFFET SIZE
next i

```

(for quickbms)
## Post #4
- Username: toebi1987
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 30, 2010 3:39 pm
- Post datetime: 2012-04-18T15:20:04+00:00
- Post Title: [iOS] Max Payne Mobile (.msf files)

Big Thanks RENIKRILL, 
but 506 mp3-files are not playable and the other 224 files have the same sound?
can you fix it?
## Post #5
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2012-04-18T15:56:18+00:00
- Post Title: [iOS] Max Payne Mobile (.msf files)

W00ps! I made a stupid typo. Sorry, buddy.
Here's a correct one:

```
idstring \x00\x00\x03\xE7\x00\x00\x00\x02
get FILES long

for i = 0 < FILES
   get OFFSET long
   get SIZE long
   get NSIZE byte
   getdstring NAME NSIZE
   
   log NAME OFFSET SIZE
next i
```
## Post #6
- Username: toebi1987
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 30, 2010 3:39 pm
- Post datetime: 2012-04-18T18:42:36+00:00
- Post Title: [iOS] Max Payne Mobile (.msf files)

nice work
THX
## Post #7
- Username: gui679
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 15, 2012 12:00 am
- Post datetime: 2012-04-19T18:00:37+00:00
- Post Title: [iOS] Max Payne Mobile (.msf files)

a big thank you from the brazilian people
## Post #8
- Username: sabinex
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 03, 2012 12:11 am
- Post datetime: 2012-05-02T16:14:21+00:00
- Post Title: [iOS] Max Payne Mobile (.msf files)

hi

new here...

i just want to know how to repack this sounds into a msf again
does it need a repacker? or can it be done with quickbms?

thanks!
