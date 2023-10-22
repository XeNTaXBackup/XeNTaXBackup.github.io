## Post #1
- Username: 23hearts
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 29, 2017 8:07 pm
- Post datetime: 2017-12-29T12:16:01+00:00
- Post Title: Interesting .pak files in a Wii rom

Hey! I was going through a Wii ROM trying to see if there are any resources to extract when I ran into a .pak format that I couldn't find any information about.

The file has pak0.pak as name, but nothing in common with Quake, the game is My Fitness Coach 
There are several other files with same extension as well, all have the same signature: "MRQZ", some data, then list of filenames, then file contents in the same order.

I went through QuickBSM scripts but none match this signature. Would anyone be kind enough to investigate?
[pak0.zip](https://xentaxbackup.github.io/file/13744_pak0.zip)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-29T17:44:07+00:00
- Post Title: Interesting .pak files in a Wii rom

this bms script will extract your pak samples  

```

idstring "MRQZ"
get TOTAL_SZ long
goto 0xc
get FILES long
get TOTAL_DATA_SZ long
xmath BASE_OFF "(TOTAL_SZ + 8) - TOTAL_DATA_SZ"
get FOLDER basename
goto 0x88
for i = 0 < FILES
	getdstring NAME 0x40
	get OFFSET long
	math OFFSET + BASE_OFF
	get SIZE long
	get UNK long
	savepos TMP
	string NAME p= "%s\%s" FOLDER NAME
	log NAME OFFSET SIZE
	goto TMP
next i

```
## Post #3
- Username: 23hearts
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 29, 2017 8:07 pm
- Post datetime: 2017-12-29T23:36:08+00:00
- Post Title: Interesting .pak files in a Wii rom

That's amazingly fast! Thank you!

I gathered samples of .pak files from several different folders, is this enough useful samples?
[https://we.tl/6QYIRdvl5z](https://we.tl/6QYIRdvl5z)
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-30T15:40:04+00:00
- Post Title: Interesting .pak files in a Wii rom

okay i updated the previous script and now should be good
