## Post #1
- Username: datderecelltech
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 25, 2009 8:04 pm
- Post datetime: 2009-07-27T04:04:59+00:00
- Post Title: Monster Hunter 3 (wii) demo - bin file

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: datderecelltech
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-27T19:01:46+00:00
- Post Title: Monster Hunter 3 (wii) demo - bin file

This is the same compression used in tatsunoko vs capcom download the fpk extractor from the thread on these forums.
## Post #3
- Username: datderecelltech
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 25, 2009 8:04 pm
- Post datetime: 2009-07-29T10:42:47+00:00
- Post Title: Monster Hunter 3 (wii) demo - bin file

The fpk extractor works on the bin files?  Didn't know that.... thanks.

edit: btw, i remember reading that thread. But has anyone written a repacker?

Will Game Extractor work on that particular fpk compression?
## Post #4
- Username: tpu
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jul 09, 2009 2:42 pm
- Post datetime: 2009-08-05T01:41:14+00:00
- Post Title: Monster Hunter 3 (wii) demo - bin file

About itemdata.bin:
just reverse each byte in file, you will find the SJIS text

```
		fread (&ch, 1, 1, ifp);
		if(ch!=0x00 && ch!=0xff)
			ch = ~ch;
		fwrite(&ch, 1, 1, ofp);
	}


```
