## Post #1
- Username: cjraven
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 14, 2022 5:04 am
- Post datetime: 2023-09-11T20:11:03+00:00
- Post Title: Help with PS2 Armored Core fsliblzs files

Hello, i have been trying to learn how to properly use QuickBMS by figuring out how to extract from this BND file.
i wanted something that's more than just "log name offset size", after messing around with clog and changing compression types and also just log with encryption types i decided to actually ask for help.

the file is 520MB so i won't be able to send it, but i can send images of what i've found so far and see if anyone else in here can get it.

The first image is of the very start of the file, it goes on like that for every file and there is nothing else at the end of the big file list.


I'll show a few images of the first 3 files and what i found in them as well...

This is the first file:
I don't know what the number in the red actually is, i just thought it looked important, the rest of the file just looks like a mess. At one point it stops hugging the left side and becomes a block of FF, then FF FE and then a load of other stuff.





The second file:
This one has nothing at the start, and then a bunch of blocks all the way 'till the end

A better view of the blocks



The third and last file i'll show to save the post from getting even longer:
This file is very similar to the second but it's blocks are smaller and use a different number at the start 

and yes. All of the lines pointing at the description are absolutely necessary.

The other files in the archive look like they're more similar to the first file, using the file size as the first 4 bytes.
## Post #2
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-09-12T14:55:34+00:00
- Post Title: Help with PS2 Armored Core fsliblzs files

I planned to look to at Armored Core after I was done with Front Mission. I guess I'll have to work with savestates.
## Post #3
- Username: cjraven
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 14, 2022 5:04 am
- Post datetime: 2023-09-12T16:33:09+00:00
- Post Title: Help with PS2 Armored Core fsliblzs files

Yeah would love any help on getting these files open.

If it helps there's another bnd file with the same format, but without any compression in the files, well at least i think they're uncompressed because they actually have headers (SShd).

I can send some images of that if anyone thinks it'll help, still can't attach the file because it's 300MB
## Post #4
- Username: cjraven
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 14, 2022 5:04 am
- Post datetime: 2023-09-12T19:53:46+00:00
- Post Title: Help with PS2 Armored Core fsliblzs files

i've done some more digging through the files in the archive and i've come to the idea that it's actaully not compressed at all, it's just simply not all generic files but more just random blocks of hex that the game reads from.

sometimes theres completely random hex and stuff i don't understand like in the images i sent in the frist post,

sometimes it looks like values the game would read to display text in game, like item descriptions.


and sometimes it does look like it is just files,


Now i'm going to try and found out what these fsliblzs files are.
## Post #5
- Username: cjraven
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 14, 2022 5:04 am
- Post datetime: 2023-09-12T20:33:01+00:00
- Post Title: Help with PS2 Armored Core fsliblzs files

I wasn't sure when first going through them, but i think the fsliblzs may also be some sort of file storage as i've found a few now that also have what looks like another BND file inside them.

and from the looks of it, from offset 10, the first 4 bytes are the archive size, and the next 4 bytes are the number of files (1 in this case)

Also the data in the BND is not following the normal BND format that the other files do so i think this fsliblzs may actually be compressed or encrypted this time?
or it could also just be a whole different format to the usual BNDs
## Post #6
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-09-12T21:33:09+00:00
- Post Title: Help with PS2 Armored Core fsliblzs files

Oh, you must be poking around Nexus/NineBreaker/Last Raven. I remember seeing those headers in the later entries.
## Post #7
- Username: cjraven
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 14, 2022 5:04 am
- Post datetime: 2023-09-12T21:56:30+00:00
- Post Title: Help with PS2 Armored Core fsliblzs files

Yeah, good to know you've also been doing the same.

No idea how to deal with the fsliblzs right now, but i did just find another bnd file with a bunch of the in game descriptions which is pretty cool, just reading through them and looking through the other bnd files inside of the big main one because i can actually open those, saw one earlier that had some emblem.tm2 files that i want to look at.
I've found a few names through the parts of the fsliblzs that are readable and saw some stuff talking about debug generator/booster parts as well

Edit: just found out most of the bnd files actually do have filenames at the end of the big file offset list, just the main one doesn't
Main one:


Others:

And the numbers to the right of the filesize column is the filename offset.
So i'm going to update my qbms script to get filenames if there are ones set and then be able to use them instead of just using file number as the name
## Post #8
- Username: cjraven
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 14, 2022 5:04 am
- Post datetime: 2023-09-12T22:28:52+00:00
- Post Title: Help with PS2 Armored Core fsliblzs files

It works, i'll leave my qbms script here for anyone else that wants to try it.

```

IDString "BND\x00"
get FF long
get unknown1 long # Normally equals 202 or 211
get archiveSize long
get FileCount long
get zeroes long
get unknown2 long # No clue what this is.
goto 0x20

for i = 0 < fileCount
	get number long
	get Offset long
	get Size long
	get fileNameOffset long
	
	# If there is a filename associated with the file
	if fileNameOffset != 0
		goto fileNameOffset
		get Name string
		
	Else # In the case of no filenames, use file number + header of file as an extension.
		goto Offset
		get Name string
		
		if Name == BND
			string number + ".bnd"
			
		Elif Name == fsliblzs
			string number + ".fsliblzs"
			
		Else
			string number + ".bin"
			
		endif

		# "string number" overwrites the number variable, set Name to use new filename
		set Name number

	endif
	
	# Calculate where in the file list it should be and go back to that point.
	set Offset2 0
	set start 32
	Xmath Offset2 "start + ((i+1) * 16)"
	goto Offset2
	
	log Name Offset Size 
next i


```


But now i still have a problem with the fsliblzs files, guess i'll change the name of the thread to that now.

Also any feedback on how i can improve the quickbms script is very appreciated, if there's maybe a more efficient way i should be doing this let me know.
## Post #9
- Username: cjraven
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 14, 2022 5:04 am
- Post datetime: 2023-09-16T14:11:22+00:00
- Post Title: Help with PS2 Armored Core fsliblzs files

Finally got around to looking at the fsliblzs files, not entirely sure what's going on in these files.

I can't see anything that points to the start of the file either, but in other fsliblzs there are some that look like they start a byte earlier.

I didn't colour the bottom 2 sets of bytes i was pointing at because i can't tell if they start 1 byte to the right or not
## Post #10
- Username: cjraven
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 14, 2022 5:04 am
- Post datetime: 2023-09-16T20:46:57+00:00
- Post Title: Help with PS2 Armored Core fsliblzs files

QuickBMS has a liblzs decompression type, but i can't get it to work properly, all the files it outputs are tiny.
going to keep trying stuff but i think i'm basically out of ideas now, can't see anything in the file that might help me open it. I still haven't done anything with the random 256 (00 01 00 00) at offset 0x20
## Post #11
- Username: cjraven
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 14, 2022 5:04 am
- Post datetime: 2023-09-17T13:17:48+00:00
- Post Title: Help with PS2 Armored Core fsliblzs files

just realised the fsliblzs are small enough to send as an attachment, here's a zip of a few fsliblzs files for anyone who wants to see if they can open it.


 fsliblzs.zip
(84.74 KiB) Downloaded 13 times
