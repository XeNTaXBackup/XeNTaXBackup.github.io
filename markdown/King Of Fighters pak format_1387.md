## Post #1
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-07-09T01:21:56+00:00
- Post Title: King Of Fighters pak format

I talked with Watto about this and he said it was similar to the Simcity4 format.  I tried to understand the Sims format from this link:

[http://www.modthesims2.com/wiki/Packages](http://www.modthesims2.com/wiki/Packages)

It appears the compression is similar-- a type of RLE.  I only know that it seems an "FF" control character means to copy the next 8 bytes to the output stream.   Can you look at this file or maybe explain better than that webpage what exactly I'm looking for?  TIA
[cmdlist_txt_u.zip](https://xentaxbackup.github.io/file/342_cmdlist_txt_u.zip)
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-07-09T07:06:30+00:00
- Post Title: King Of Fighters pak format

Just a little information on this...

It is in regards to the compression method used by these files. If the archive is the same as was emailed to me, then there are 2 files in there which both look to have an in-house compression type that is commonly used for text compression, similar to an RLE scheme, or one that uses control bytes to indicate various operations like copy X bytes from a certain offset, or repeat the next character X times.

The only real expecience I have had in this ares was for the Maxis compression used in Simcity 4 and The Sims 2, which some information can be found at the website given in the post above.

Thats all - good luck!

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-09T14:39:08+00:00
- Post Title: King Of Fighters pak format

It looks like the same RLE format to me.
## Post #4
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-07-09T19:47:18+00:00
- Post Title: King Of Fighters pak format

"FF" definitely appears to copy 8 bytes to the stream file and "FD" appears to copy 6 bytes.  Can you show me how this is accomplished using the formula from the Sims page?  I am thoroughly confused.
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-09T21:00:17+00:00
- Post Title: King Of Fighters pak format

Actually, the author wrote two different formulas for the same, didn't he? That's kind of weird.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-09T23:37:47+00:00
- Post Title: King Of Fighters pak format

On inspection, it looks like bits are used to show how many characters to append. so 0xFF = 11111111 , which is all 8 of them. 
Thus, 0xFE = 11111110 , so the next 7 should be appended. 

More:

0x7F = 0111111 -> The immediate next character is a control character, but the 7 after that should be appended as is. 

0xFD = 11111101 -> The 6 upcoming should be appended as is, not the 7th (control), but the 8th again should be appended. 

Further theory:
Each time a control character is found, a series of 8 characters must be completed, regardless if other control chars are found. 

A control character is signed. When negative it will point to an area in the already decompressed part, thus -11 means: read from location - 11 of the current position and append.

Consider this example :

```
.to hold .but.n.
```
 can be found in that file. 
Let me fill in the control bytes, so you can read with me :

```
[0xFF][t][o][ ][h][o][l][d][ ][0xE1][b][u][t][-11][n]
```


Now 0xFF = 11111111
and 0xE1 = 11100001

These are primary control characters. The [-11] is a secondary control character, or a pointer in this case.

Let's start reading , the 0xFF says : take the next 8 chars 

```
 to hold 
```
 (including the spaces of course). 

Then, the oxE1 says: take the next three characters, and then follow a secondary control route for 4 characters, including the secondary control character (which presumably takes two bits), and then end with the next character in the compressed file. 

So, 

```
but
```
 is the first part, then we reach the -11. 

This is the first control character and points to a position 11 characters before the current position in the DEcompressed file. That's:

"to hold but" 

Notice how the 't' of 'to' is the 11th character upstream from right after the 't' of 'but'. We still have to read 2 control characters, according to 0xE1, so  we append from the appointed location:

to hold butto

Finally, we still have to do as told by the last bit of 0xE1, which was a 1, so read character from the compressed file. This is the 'n'.

to hold button

Makes sense?
## Post #7
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-07-10T00:32:27+00:00
- Post Title: King Of Fighters pak format

That is great!!  Thanks.  I thought the 1 bits represented a byte add but I couldn't figure out the 0 bits.  I still have a question---what would an "E5" or "11100101" represent as a control character??
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-10T07:45:37+00:00
- Post Title: King Of Fighters pak format

Well, that is what puzzles me as well, there's still a lot to be figured out. I suspect perhaps certain parts can also be tagged and used elsewhere.

What would really help is to have a decompressed part of that file, to compare with.
## Post #9
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-07-16T04:58:19+00:00
- Post Title: King Of Fighters pak format

Have you found anymore information about this format, Mr. Mouse?  I understand some of the other control bytes but still can't seem to compile a formula for them.  Any information is a plus.
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-16T07:53:18+00:00
- Post Title: King Of Fighters pak format

Well, as I said, it would help if I know some decompressed lines. 

I don't have the ability to play the game to see that, I suspect someone might play it and write down the lines here? They look like instructions to play the game, like holding down buttons etc.
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-19T22:03:19+00:00
- Post Title: King Of Fighters pak format

This is a task that needs time. So it'll be a little slow in the progress department.
## Post #12
- Username: Magus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 20, 2005 7:00 am
- Post datetime: 2005-07-19T23:01:15+00:00
- Post Title: King Of Fighters pak format

and what would allow this to go faster?
## Post #13
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2005-07-20T00:20:07+00:00
- Post Title: King Of Fighters pak format

> Reply from Mr.Mouse
>
> Well, as I said, it would help if I know some decompressed lines. 

I don't have the ability to play the game to see that, I suspect someone might play it and write down the lines here? They look like instructions to play the game, like holding down buttons etc.

Hi, in the menu this is referenced in moves list.

"(Ok to hold button down)"

hope that helps,


::Edit::
Screenshot
[](http://img130.imageshack.us/my.php?image=11218269722wv.jpg)

Also PK seems to be header (perhaps?) 20 entries (19 playable characters PS2 had 1 unlockable, don't know about xbox version)

```

BODY SLAMS

	Steel Slammer		Near Opponent. <-or-> + (P)

	Killer Krunch Toss	Near Opponent. <-or-> + (K)
	

SPECIAL MOVE

	NONEXISTENCE

DEADLY MOVES

	Fire Ball		->(down)(down diagnal right)+(p) or (P)

	427 Torment Trigger	

	R.E.D. Kick
	
	New Wave Smash

	Wicked Chew

	128 Masticate		During Wicked Chew. (followed by button sequence)

	127 Oxidate		During Wicked Chew. -> (down diag right) (down) (down diag left) <- + (p) or (P)
				     From Wicked Chew to 128 Masticate. (p) or (P)


	125 Rapids of Rage

```


I can clean this up a bit or add the rest of the moves (Stylish Move 1...17). (add some of my missing buttons   ) (p) is light punch button (P) strong punch <- (left) -> (right)..etc

first PK entry is this listing. At the End of file it lists Player name. for this KYO KUSANAGI
## Post #14
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-07-29T05:36:49+00:00
- Post Title: King Of Fighters pak format

Mr. Mouse, any updates to the possible compression method?  I have only made myself more confused!
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-29T06:13:06+00:00
- Post Title: King Of Fighters pak format

Well, all in all I haven't really gotten any further, what I don't always understand is where it gets pieces of text from when it needs it (fromalready decompressed stuff) as the method I think it uses is not always consistent with what I see. I will get back to it, but time is not on my hands.
## Post #16
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-07-29T12:58:53+00:00
- Post Title: 

Thanks for the response.  I, too, am confused with the format of the control characters.  This may just be one for the shelf.
## Post #17
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-07-30T20:38:07+00:00
- Post Title: 

Looks like I've discovered a little more.  It appears the files use an LZSS variant.  Does anyone know how to use zlib without allowing it to use the Huffman compression?  Any suggestions, Mr. Mouse?
## Post #18
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-08-09T02:57:28+00:00
- Post Title: 

This is how the KOF compression works.  (All values in LittleEndian)

The header of each section starts with 4 byte Magic "PK..", 504B 0002 in Hex.  
The next 4 bytes are the decompressed size followed by 8 bytes of NULLS(0's).
The next byte is where the compression starts.  I'll give some examples to 
illustrate.

Suppose the first compression byte you encounter is C3.  I will call this a
Main Control Byte.  It is used in binary form.  So, C3 = 11000011.  Here is 
how the binary code of the Main Control Characters are read from left to right:

1.  a)If the bit is a 1, then copy 1 byte
2.  a)If the bit is a 0, then check the next bit.
    b)If it is a 1, then use 2 bytes to get Position and Length for byte copy(more on that later*).
    c)If it is a 0, then use the next 2 bits value and Add 2.  This will be the Length.
      The Position will be the corresponding signed byte in the compressed file.
3.  a)Check if there are 3 bits or less and their binary value is less than 1.
      If it is, copy these bits to the beginning(high side) of the next Main Control Byte	      	
      and start over.

This is an explanation of the 2 byte Position and Length:
Say we have a 2 byte sequence of FB E4 for the Position.  Converting it to binary we get
1111101111100100 and divide it like below.  

          1st Part   2nd Part   3rd Part 
               111 / 11011111 / 00100

The Length is calculated by taking the value of the 3rd Part and adding 2 to it.  So we get a Length
of 6.  The Position is calculated by taking the 2nd Part, appending 5 1's ("11111") and then appending 
the 1st part.  This would give us 1101111111111111, which is -33 in signed short.  I know you don't need
16 bits to get -33 but, if this format is used, it saves a lot of coding.
A special case of the 2 byte Position,Length combination is if the 3rd part(Length) is all 0's.  In this case, you take the byte AFTER the 2 byte sequence and use it for the Length.  Take the decimal value of it and add 1 to it to get the Length.  Position calculation is the same as above.


Lets run an example.
F854 5854 4400 98FF FB                                      .TXTD....               

The F8 above is the start of the compression.  F8 is binary 11111000.  Using the method I described, left to right, we can see it means to copy the next 5 bytes and we will have 3 0's left over.  So, the output stream(the decompressed file) would now be:

5458 5444 00                                                TXTD.                   

We left off at the 98 in the compressed file.  This is the new Main Control Byte.  Remember the left over bits?  We have to append them to the high side of the binary form of this byte.  98 = 10011000 
Appending the leftover 0's we get 00010011000.  Using the bits left to right, they mean to 1)use the value of the next byte as Position with 3 as the Length(remember we add 2 to the "01") to perform a copy in the output stream and then 2)the following byte as Position with 5 as the Length.  There will be 3 0's("000") left over for the beginning of the next Main Control Byte.

The first byte AFTER the 98 is FF which has a signed value of -1.  This is our Position and we already have a length of 3 from the bits.  So, we go back 1 byte in the output stream and copy 3 bytes.  3 bytes??  How the hell do we copy 3 bytes if we only go back one?  In the case that the Length goes past the end of the file, you just copy the same byte over.  This means we will copy the "00" 3 times on the end of the output stream.  We now have as the output stream:

5458 5444 0000 0000                                         TXTD....    

The next byte in the compressed file is FB, which is -5 in signed form.  We already have 5 as the Length so we have Position = -5, Length = 5.  We go back 5 bytes in the output stream and copy the next 5 bytes to the end of it.  We now have:

5458 5444 0000 0000 4400 0000 00                            TXTD....D....           


I'm sure there are better ways of decompressing this file, but I couldn't find one.  The file uses a variant LZSS compression, so if anyone figures out what type please post it.  Hopefully, someone can write that "re-compressor" because I don't think I have the skills necessary.  Thanks to Intruder for the initial PK extractor.
## Post #19
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-08-09T03:05:33+00:00
- Post Title: 

looks like a ZIP file
## Post #20
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-08-09T12:34:00+00:00
- Post Title: 

Excellent work thus far  - it is obvious that you have much for free time than we seem to have. I'm not sure what Mr Mouse is doing but he hasn't posted much recently - I have been busy with University starting back and stuff like that. 

Good work on the analysis of the compression

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #21
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-09T14:17:03+00:00
- Post Title: 

Actually, I am very busy indeed. Even this post I do from the university I'm taking an advanced statistical course at, so I'm away for a few weeks. 

Meanwhile, if I have time, I'm working on the new version of MultiEx Commander (4.2) that should rock, and getting Rahly's pluginmanager fully implemented. 

Not to mention the most important event upcoming: birth of my first child (due 31st of august). So you'll understand I'm with my wife.
