## Post #1
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-03-13T19:18:53+00:00
- Post Title: Hotline Miami 2: Wrong Number (*.WAD)

Rather simple format. The script is not perfect and can probably be optimized better (the main data file takes about a minute or so to start extracting), but it works.

```

for i = 0 < FILES
	get NAMESZ long
	getdstring NAME[i] NAMESZ
	get SIZE[i] longlong
	get OFFSET[i] longlong
next i

savepos BASEOFF

for i = 0 < FILES
	math TMP = OFFSET[i]
	xmath NEWOFF "BASEOFF + TMP"
	log NAME[i] NEWOFF SIZE[i]
next i
```
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-03-13T20:05:38+00:00
- Post Title: Hotline Miami 2: Wrong Number (*.WAD)

didn't know bms supported that array syntax!! always pre-allocate arrays of known size i guess
## Post #3
- Username: barti
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-03-13T23:21:06+00:00
- Post Title: Hotline Miami 2: Wrong Number (*.WAD)

A minute or so? Then try the old MexScript in MultiEx Commander. 

[https://www.youtube.com/watch?v=bDZXhD7 ... GrVNJ2kS2f](https://www.youtube.com/watch?v=bDZXhD7-Wys&index=1&list=PLP26ZYnLb5EVqqBHDgltL6oGrVNJ2kS2f)

```
Get FileNum Long 0 ;
SavePos FS 0 ;
For T = 1 To FileNum ;
Get SS Long 0 ;
SavePos J 0 ;
Math J += SS ;
Math J += 16 ;
GoTo J 0 ;
Next T ;
GoTo FS 0 ;
For K = 1 To FileNum ;
Get SS Long 0 ;
GetDString FileName SS 0 ;
Get Size Long 0 ;
Get D1 Long 0 ;
Get RelOff Long 0 ; 
Get D2 Long 0 ;
Math RelOff += J ;
Log FileName RelOff Size 0 0 ;
Next K ;

```
