## Post #1
- Username: themonkeyman
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Nov 27, 2009 8:49 am
- Post datetime: 2009-12-02T05:26:28+00:00
- Post Title: [PS2] Twisted Metal: Head-On .bdd

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-12-02T18:04:19+00:00
- Post Title: [PS2] Twisted Metal: Head-On .bdd

```
	# File entry
	GetDString NAME 0x14
	If NAME == ""
		Break
	EndIf
	GetDString EXTENSION 0x08
	Get OFFSET long
	Get SIZE long
	Get UNK1 long
	Get UNK2 long

	# Extract
	Set FULLNAME NAME
	String FULLNAME += "."
	String FULLNAME += EXTENSION
	Log FULLNAME OFFSET SIZE
While 1 == 1

```
## Post #3
- Username: themonkeyman
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Nov 27, 2009 8:49 am
- Post datetime: 2009-12-02T23:08:12+00:00
- Post Title: [PS2] Twisted Metal: Head-On .bdd

Thank you, that was very quick, but how can I compile this into a BMS?
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-02T23:20:22+00:00
- Post Title: [PS2] Twisted Metal: Head-On .bdd

- get quickbms ([http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms))
- put that script in a file giving it a bms or txt extension
- double click on quickbms.exe
- select the script just saved
- select the archive you want to extract
- select the folder where you want to extract the files
- that's all
## Post #5
- Username: themonkeyman
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Nov 27, 2009 8:49 am
- Post datetime: 2009-12-06T01:29:12+00:00
- Post Title: [PS2] Twisted Metal: Head-On .bdd

The contents of this post was deleted because of possible forum rules violation.
