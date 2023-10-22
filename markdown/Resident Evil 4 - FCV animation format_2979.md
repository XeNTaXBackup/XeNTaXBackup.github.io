## Post #1
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-03-22T07:14:43+00:00
- Post Title: Resident Evil 4 - FCV animation format

if this is the wrong place for this, i apologize. Please move it somewhere else if this is true.

Well, let's just dive in to this.

```

-------------------------------------------------------------------------
Short = 2byte (4digit) hex number with lowest value first ie: CD AB is read as AB CD

uint = 4byte(8digit) unsigned hex number with lowest value first ie: 78 56 34 12 is read as 12 34 56 78

float = IEEE-754 float, 4 bytes read in binary as 1= sign 00000000=exponent  (1.)0000000000=radiant
(note this float is -0, which is non existent... NAN (not a number))

-------------------------------------------------------------------
known stuff

0xB0 bytes	header   #0x4C (uint) is always the length of the file

#positioning data
for amount of bones moving at different times: #undetermined as to how this is known
	uint		how many bones

	for bone index in how many bones:
		short		index of bone in PMD file currently being used

	for bone position in how many bones:
		float   	new x coordinate
		float   	new y coordinate
		float   	new z coordinate
#end this point in time

uint		time flag?	#all is judged on the truth in this statement
uint		current time
uint * 6	0		#definitely padding

refer to positioning data

--------------------------------------------------------------------------
notes: 

-Sometimes x,y,z floats aren't floats, but i think this is just hexworkshop interpreting the floats backwards (3f 80 00 00 is NAN to them)

-I think the 0x00 to 0x4c values are just importing the PMD info
	-very repetitive
	-always similar with small variations

-0x4c - 0xB0 lists a bunch of pointers that point to SOME of the positioning data (refer to "known stuff")
```


Anyone with Animation savy tell me what to do D:
Also here's the infamous header that i talk about:

```
50 02 50 A0 45 02 00 04 00 02 50 A0 45 02 00 04 
00 02 50 20 54 02 50 04 00 02 50 20 54 02 40 04 
00 02 50 00 00 00 01 02 03 04 05 07 0A 0A 0B 0D 
10 10 11 12 14 14 15 16 18 18 19 00 E0 32 00 00 
18 23 00 00 1A 1E 00 00 48 23 00 00 8C 1F 00 00 
5A 21 00 00 52 28 00 00 18 14 00 00 4E 0D 00 00 
44 0F 00 00 30 07 00 00 2A 0A 00 00 1A 12 00 00 
70 25 00 00 B0 00 00 00 0C 04 00 00 44 1C 00 00 
20 2A 00 00 F4 2D 00 00 42 2F 00 00 D6 15 00 00 
06 2C 00 00 A4 16 00 00 4A 19 00 00 2E 32 00 00
```


and here's an fcv file

 fcv file.rar
-what was posted here-2 fcv files (20.2 KiB) Downloaded 134 times
