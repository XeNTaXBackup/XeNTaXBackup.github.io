## Post #1
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2014-08-30T04:02:50+00:00
- Post Title: [PS2] Death by Degrees UV extraction (500$ compensation)

Hi,
over at [http://ps23dformat.wikispaces.com/share/view/55330192](http://ps23dformat.wikispaces.com/share/view/55330192) we've been looking into extracting models from the PS2 game Death by Degrees.
The creator of the wiki has written a quickbms script to extract 3D models from Tekken 5 which also works on Death by Degrees. Both games are Namco games that were released in 2005 for the PlayStation2 and are similar in their model format. (Link to the script: [http://ps23dformat.wikispaces.com/Tekken+5](http://ps23dformat.wikispaces.com/Tekken+5))
Here's a screenshot of a look at an extracted model in Noesis.



This is were we hit a wall. Apart from the messy meshes (which can be easily cleaned up manually) we don't know how to extract the meshes with UV's.

I figured I might try and take this here and see if anybody can help and/or share some advice.

Here are 2 in-game PCSX2 savestates.



[http://www.mediafire.com/download/2k1iz ... te_007.rar](http://www.mediafire.com/download/2k1izk9b79i3521/DbD_sstate_007.rar)



[http://www.mediafire.com/download/hr1xi ... te_003.rar](http://www.mediafire.com/download/hr1xi95i4z5g7wn/DbD_sstate_003.rar)
## Post #2
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2015-02-21T19:32:09+00:00
- Post Title: [PS2] Death by Degrees UV extraction (500$ compensation)

Bump, just in hopes someone capable might see this.
## Post #3
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2015-03-14T01:37:19+00:00
- Post Title: [PS2] Death by Degrees UV extraction (500$ compensation)

500$ (PayPal) for anyone who finds a way to extract UV information.
I know this is generally frowned upon, but maybe somebody knowledgeable would like to earn a buck or two (or 500) instead of being asked to look into a game they might not be interested in for free.
## Post #4
- Username: IvoryCutter
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-03-14T23:21:18+00:00
- Post Title: [PS2] Death by Degrees UV extraction (500$ compensation)

With voice acting like this you can't go wrong.
[https://www.sendspace.com/file/mmphbi](https://www.sendspace.com/file/mmphbi)
## Post #5
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2015-03-15T09:39:35+00:00
- Post Title: [PS2] Death by Degrees UV extraction (500$ compensation)

I'm trying to get the faces to read correctly, without it the UV data is useless. :\

so far I've tested the vertex def for bit masking for the termination of the face strip, 
but results in game don't lead me to think that there is any bitmasking in the vertex def

after the vertex def however there is a small table which might have a correlation to the face strips
But I haven't figured anything out yet 

I'm studying this simple hexagon shaped mesh


there are a total of 13 vertices, and some vertices overlap that suggest that there is a new face strip started there
based off these clues I can assemble the below face indices list

```
02)	2,3,4
[03]	3,4,5
------------------
04)	6,7,8
[05]	7,8,9
------------------ (polygons on backface)
06)	10,11,12
07)	11,12,[13]
```


the Mystery Table provides the following data

```
0x 70 0b 80 1a	(112,	11,	128,	26)
0x 70 0b 80 2e	(112,	11,	128,	56)
```


taking the 4th byte and converting it to binary we gets this

```
0x1A: 00011 01 0	3	1	0
0x2E: 00101 11 0	5	3	0
```


Notice that in the first column 3 and 5 appear and there is a correlation to the indexes of the faces I assembled

I haven't implemented it into my code yet, being its 5:00 AM and I'm about to pass out.
## Post #6
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2015-03-15T14:53:53+00:00
- Post Title: [PS2] Death by Degrees UV extraction (500$ compensation)

> Reply from chrrox
>
> With voice acting like this you can't go wrong.
https://www.sendspace.com/file/mmphbi

Hahaha, Wow, I have never heard these! I've played through this game too many times for me to be comfortable saying it here, but I've never come across any of these lines. Some of them are hilarious. How did you come across this blooper reel? Is there more?



> Reply from mariokart64n
>
> I'm trying to get the faces to read correctly, without it the UV data is useless. :\

so far I've tested the vertex def for bit masking for the termination of the face strip, 
but results in game don't lead me to think that there is any bitmasking in the vertex def

after the vertex def however there is a small table which might have a correlation to the face strips
But I haven't figured anything out yet 

I'm studying this simple hexagon shaped mesh


there are a total of 13 vertices, and some vertices overlap that suggest that there is a new face strip started there
based off these clues I can assemble the below face indices list
Code: Select all01)	1,2,3
02)	2,3,4
[03]	3,4,5
------------------
04)	6,7,8
[05]	7,8,9
------------------ (polygons on backface)
06)	10,11,12
07)	11,12,[13]

the Mystery Table provides the following data
Code: Select all0x 70 06 80 01	(112,	06,	128,	01)
0x 70 0b 80 1a	(112,	11,	128,	26)
0x 70 0b 80 2e	(112,	11,	128,	56)

taking the 4th byte and converting it to binary we gets this
Code: Select all0x01: 00000 00 1	0	0	1
0x1A: 00011 01 0	3	1	0
0x2E: 00101 11 0	5	3	0

Notice that in the first column 3 and 5 appear and there is a correlation to the indexes of the faces I assembled

I haven't implemented it into my code yet, being its 5:00 AM and I'm about to pass out.

Holy....! I don't think anyone has ever looked that deep into this game.
This is so over my head, I almost feel bad for only being able to compensate your effort and time with a meagre 500 for this rocket science. 
Would you mind posting/documenting your findings here just like you did in this post? Even though I personally am not yet able to wrap my head around most of it, it's still so very interesting, and it might be of help for anyone else trying to learn or doing some research.

Regarding the UV data being useless without getting the faces to read correctly, I feared as much.  So I take it the quickBMS script is of no use to you really, is it?

So looking forward to your future findings.
## Post #7
- Username: IvoryCutter
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-03-15T15:36:49+00:00
- Post Title: [PS2] Death by Degrees UV extraction (500$ compensation)

I took a look at this as well. The meshes seem to be some viftag-like format. Face indices do seem complex and I'm pleased that mariokart64n has looked into it. Hopefully his solution will work, very nice work mariokart64n  

I think the models are stored within the .obj files.

The .obj files look to be a container for multiple nupd mesh files? Possibly at multiple lod levels.

Format:

```
{
unsigned int uiUnk00;
unsigned int uiUnk01;
unsigned int uiNumNupdFiles;
unsigned int uiUnk02;

unsigned int uiOffsetNupdPtrs; //Offset to Nupd Pointers
unsigned int uiNupdStart; //Start offset of first Nupd?
unsigned int uiOffsetNupdNames; //Offset to Nupd Names
unsigned int uiUnk03;
};

```


The rest of it is pretty simple for the .obj. uiOffsetNupdNames points to an offset which holds more pointers to the name of each nupd file (i think). This is enough info to to begin reading the singular mesh files but yeah, face indices got me on this one  so I'll leave it to mariokart64n
## Post #8
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2015-03-15T17:26:49+00:00
- Post Title: [PS2] Death by Degrees UV extraction (500$ compensation)

Thank you so much for your input, Gh0stBlade! I wish it was only the complexity of face indices posing a challenge for me :-/ As I said, the way you guys look at code is rocket science level stuff and then some. Kudos!
## Post #9
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2015-03-16T02:57:32+00:00
- Post Title: [PS2] Death by Degrees UV extraction (500$ compensation)

ok another update  

I said last that I had a mystery table and I thought it correlated to the face strips
I wanted to confirm that without a doubt...

So I imported the vertices from her model and isolated the heel of her shoe



I wanted to do some testing in PCSX2, and null the data in the face strip table.

but that resulted in a game crash, so instead I duplicated the first entry in the table
over the rest of the table entries. 



The results confirms that when we modify the table in the game we get the same
result as we do in 3dsmax when we generate our strips without knowing the strip terminations.


After I made my confirmation I went to scratching my head for hours.

Since I don't know anything about disassembly or anything like that, I was
basically pissing in the dark. lol I didnt know how to further approach the problem.. :\

So lets look at the table data together and I'll share what I know so far

the stuff here highlighted in red is the face strip info from that object above.

> 00 05 00 01 00 00 00 20  7F FF FF FF 01 80 06 70
>
> 29 80 06 70 42 80 0B 70 5B 80 06 70 6F 80 06 70
>
> 83 80 06 70 00 00 00 00  01 01 00 01 00 00 00 20
>
> 00 00 00 00 00 00 00 14  00 00 00 00 00 00 00 00
there also seems to be other command calls here in the block,
but... I don't think thats important at the moment...

It would appear that column 1 and 3 impact where the strip is started from

```
2)        29 80   06 70      ->hex2dec:   41  128     6  112
3)        42 80   0B 70      ->hex2dec:   66  128    11  112
4)        5B 80   06 70      ->hex2dec:   91  128    06  112
5)        6F 80   06 70      ->hex2dec:  111  128    06  112
6)        83 80   06 70      ->hex2dec:  131  128    06  112
```

I believe the 3rd column is bit masked, I'm going to extract bits 1,2

```
6              000001 | 10      1 | 2
 6              000001 | 10      1 | 2
11             000010 | 11      2 | 3
 6              000001 | 10      1 | 2
 6              000001 | 10      1 | 2
 6              000001 | 10      1 | 2
```

Great now lets have a look at this incredibly confusing picture that I drew
I reconstructed the faces based on logical observations of how the model should look

and also confirmed by poking in PCSX2 while the game was running

Note that there are 6 strips, I've coloured each stripped surface with a different colour
and labelled it with a face index


Let me break this down:
based on my face list I know that there are 6 elements.
and as it soo happens there are 6 entries in the strip table. 

we need info for starting and stopping the strip somewhere in here and I've
tried to lay it out visually, and in the text representation its divided into columns.
I try to make a connection with my face list and the info provided to us in the strip table

```
         02,04,03                       10,12,11                       16,18,17                       20,22,21                       24,26,25                       28,30,29
         03,04,05                       11,12,13
         04,06,05
         05,06,07
         06,08,07

         ( 6)=1,2                       ( 6)=1,2                       (11)=2,3                      ( 6)=1,2                       ( 6)=1,2                       ( 6)=1,2


missing ->               7,8                          12,13,14                        17,18                         21,22                          25,26
```


example face 1
01 80   06 70

lets name these into variables
a = 1 (1st byte)
b = 1 (3rd byte[0x06], bits 3-8)
c = 2 (3rd byte[0x06], bits 1-2)

and I've come up with this formula;
((a-1)/5)+b = face_pos

so lets plugin the numbers
((1-1)/5)+1 = 1

lets do the rest of them
((41-1)/5)+1 = 9
((66-1)/5)+2 = 15
((91-1)/5)+1 = 19
((111-1)/5)+1 = 23
((131-1)/5)+1 = 27

Note these match the starting face index in each element shown above
and the number of missing indices seems to somehow be indicated
in the next strip info ??

I imagine I got this all wrong, when you stare are a number for soo long
your mind will start to imagine logical ways to make it relevant, but in fact could be entirely false

anyway we will have to see when I code this up and test it out, but until then..
I think I'll call it a night and get some rest
## Post #10
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2015-03-16T09:04:26+00:00
- Post Title: [PS2] Death by Degrees UV extraction (500$ compensation)

Whatever Namco were cooking up back in 2004, you're totally on to it! Your conclusion even makes sense to me (just how you got there is still a blur) 
Incredible work, mariokart!
Thanks for the insightful documentation! You certainly left on a cliff hanger
## Post #11
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2015-03-17T05:11:04+00:00
- Post Title: [PS2] Death by Degrees UV extraction (500$ compensation)

coded it up and it failed on the first strip lol

there are different values in the table and I can adapt the formula but
more study is needed to understand how this works... its annoying cause the numbers fit but shift

strip info
01 80 04 70
1F 80 04 70
2E 80 07 70
40 80 07 70
4F 80 04 70
5B 80 04 70
64 80 07 70

hex > dec
[1,128,4,112]   :: 0 / 3 = 0 + 1 = 1
[31,128,4,112]   :: 30 / 3 = 10 + 1 = 11
[46,128,7,112]  :: 45 / 3 = 15 + 2 = 17
[64,128,7,112]	:: 64 / 3 = 21 + 2 = 23
[79,128,4,112]   :: 78 / 3 = 26 + 1 = 27
[91,128,4,112]   :: 90 / 3 = 30 + 1 = 31
[100,128,7,112] :: 99 / 3 = 33 + 2 = 35

dec > bin
4 = 10 0 (2|0)
7 = 11 1 (3|1)

required face list

> 1,2,3
>
> 2,3,4
>
> 3,4,5
>
> 4,5,6
>
> 5,6,7
>
> 6,8,7
>
> 7,8,9
>
> 8,10,9
>
> ----------------------> 2  (9,10)
>
> 11,12,13
>
> 12,14,13
>
> 13,14,15
>
> ----------------------> 3  (14,15,16)
>
> 17,18,19
>
> 18,20,19
>
> 19,20,21
>
> ----------------------> 3  (20,21,22)
>
> 23,24,25
>
> 24,26,25
>
> ----------------------> 2  (25,26)
>
> 27,28,29
>
> 28,30,29
>
> ----------------------> 2  (29,20)
>
> 31,32,33
>
> ----------------------> 3  (32,33,34)
>
> 35,36,37

EDIT

doh` ! >_<

> Reply from mariokart64n
>
> 
00 05 00 01 00 00 00 20  7F FF FF FF 01 80 06 70
29 80 06 70 42 80 0B 70 5B 80 06 70 6F 80 06 70
83 80 06 70 00 00 00 00  01 01 00 01 00 00 00 20
00 00 00 00 00 00 00 14  00 00 00 00 00 00 00 00
there also seems to be other command calls here in the block,
but... I don't think thats important at the moment...
I'm an idiot that divisor is supplied before the table
00 05 00 01 00 
5 is the divisor, in the example above 00 03 00 01 was included 

.. that explains that magical 5 I had before, and why I needed to use 3 this time..


EDIT2
## Post #12
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2015-03-17T07:30:46+00:00
- Post Title: [PS2] Death by Degrees UV extraction (500$ compensation)

You've done it! Impressive work! 
What's the next step?
## Post #13
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2015-03-18T03:44:58+00:00
- Post Title: [PS2] Death by Degrees UV extraction (500$ compensation)


## Post #14
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2015-03-18T06:52:04+00:00
- Post Title: [PS2] Death by Degrees UV extraction (500$ compensation)


## Post #15
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2015-03-18T07:20:58+00:00
- Post Title: [PS2] Death by Degrees UV extraction (500$ compensation)


## Post #16
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2015-03-18T11:30:20+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

Magnificent! I love the art direction in this game. Finally there's a way to really appreciate it.

Can I try?
Also, looks like it's time you PM me your paypal info
## Post #17
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2015-03-19T00:09:50+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

Cool I'll PM you my info, I still need to prepare an explanation on how to get everything together
## Post #18
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-03-19T00:30:40+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

That is an awfully roundabout way of interpreting stcycl/stmask-driven unpacks.  It should Just Work if pushed through the Noesis VIF unpacker.
## Post #19
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-03-22T18:51:33+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

Yeah, I had a chance to plug this into Noesis and verify today. All it's doing is using those stcycl and stmask commands to affect the subsequent unpacks, which run through and write R3 into the position w's, then you can conveniently use those position w's as strip resets. All the work is done for you if you just VIF-unpack the data. You were manually interpreting the CYCLE and MASK values to figure out strip offsets. 

Did this guy ever pay up? Because this format will probably be in the next Noesis.
## Post #20
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2015-03-22T19:53:59+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

nope haven't got any money for this project yet, OP says he will next month.

also have you looked into Tekken5's format? the mesh table is driving me crazy. 
I had to manually assign the materials such a pain



[http://www46.zippyshare.com/v/oXIZY6Ym/file.html](http://www46.zippyshare.com/v/oXIZY6Ym/file.html)
## Post #21
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-03-22T22:05:39+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

I'd suspect he's a terrible liar, then. I'm tempted to just start banning people who broadcast financial offers. Even the ones that come through tend to end up being pieces of crap in one way or another. People shouldn't make offers if they don't have the money to follow through, either way.

Nope, I haven't looked at Tekken 5 yet. Planning to do that soonish. I'm assuming that in these Death by Degrees models, texture id's are stored in those blocks after the draw structures, which are referenced from the draw structures, and those blocks themselves probably represent a simple material structure. Haven't gotten to verifying that yet either. I just went as far as getting them up and drawing using the VIF-unpacked strip signals. I never would've gotten involved with this thread if that hex block you pasted hadn't looked like it started off with VIF cycle and mask commands, but I figure I might as well jam support for this thing in now that I've already half-implemented it.
## Post #22
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2015-03-23T02:44:37+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

yeah haven't had luck with money offers, I remember the last time I did it and I got chewed down from the original 15$ offer down to 5$. 
They said I could have the other 10$ if I completed a list of features which was not apart of the original agreement. lol only 15 dollars!!!


Anyways thank you for having a look into DBD and giving your insight into the format. 
I don't have any career in computers, I just do it as a hobby. So of course it is a great honor to be here on xentax and learn from you and all the other great members.

PS. I couldnt extract files from tekken5's file archive, so I used PCSX2 to make a save state. then wrote a BMS to scan and dump the models and tm2 textures

essentially the tekken5 models are the exact same format, however its like the addresses in the files are overwritten, probably cause I took them from ram.

BMS for grabbing crap from save state (thanks to chrrox for helping)

```

get FSIZE asize
set COUNT_G long 1
set COUNT_T long 1
set NAME string ""
SavePos POS 0
Do
	get DATA long 0
	If DATA == 0x00745865
		goto 0x0C 0 SEEK_CUR
		get DATA long 0
		If DATA == 0x58444947
			goto -0x44 0 SEEK_CUR
			SavePos OFFSET 0
			get SIZE long
			goto OFFSET 0 SEEK_SET
			goto SIZE 0 SEEK_CUR
			string NAME p= "%08d" COUNT_T
			string NAME += ".tm2"
			math COUNT_T += 1
			set MEMORY_FILE binary "\x54\x49\x4D\x32\x04\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00"
			append
				log MEMORY_FILE OFFSET SIZE 0
			append
			get SIZE asize MEMORY_FILE
			log NAME 0 SIZE MEMORY_FILE
		endif
	elif DATA == 0x5044554E
		goto 0x04 0 SEEK_CUR
		get DATA byte 0
		if DATA == 0x03
			goto 0x05 0 SEEK_CUR
			get DATA short 0
			if DATA == 0x00
				goto -0x0C 0 SEEK_CUR
				get SIZE long 0
				goto -0x08 0 SEEK_CUR
				SavePos OFFSET 0
				goto SIZE 0 SEEK_CUR
				string NAME p= "%08d" COUNT_G
				string NAME += ".nud"
				math COUNT_G += 1
				log NAME OFFSET SIZE 0
			else
				goto -0x02 0 SEEK_CUR
			endif
		else
			goto -0x05 0 SEEK_CUR
		endif
	Endif
	SavePos POS 0
While POS < FSIZE
```
## Post #23
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2015-03-23T09:01:15+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

Now now guys, calm down. Before talking about banning people maybe take into consideration that not every person on the Internet is a cheap lying bastard.
The only reason Mr mariokart hasn't been compensated YET is that I didn't expect anyone to jump on board and look into this so quickly and efficiently. I told him in several mails that I get paid on the 5th and that's when he'll get the compensation. I also suggested he'd keep his scripts and not release them until then. Again, I just didn't expect anyone to reply on this topic so quickly as it has been sitting here for a while. I'm glad he did, though, and I had the impression he does not mind waiting a couple of days to have the payment transferred to his PayPal account.

I don't care if noesis could have easily done the same trick or any of the things the scripts by chroxx and mariokart do, as I wouldn't have known how to get it to work that way. I asked for help, I offered a fair compensation, and mariokart delivered so brilliantly (I've tried both scripts and they work fantastic) he deserves every bit of those 500$ and then some. Unfortunately 500 is as much as I can offer right now, otherwise I would happily give him more, as I value other people's time and effort just as high as I value my own.
Sad to see you guys jump to conclusions, especially after I feel like my honest intentions were made pretty clear in the PM's I sent mariokart.
But I guess it was my fault for putting up the offer without having the funds yet. In that case I apologize to mariokart (again) for having to wait until the 5th of next month.

edit: 

> Reply from MrAdults
>
> I'd suspect he's a terrible liar, then. I'm tempted to just start banning people who broadcast financial offers. Even the ones that come through tend to end up being pieces of crap in one way or another.

Holy..., only just read that now. Wow! How rude of you! 
Well, even though I don't have to prove anything to you I'll be very happy to prove you wrong. 
My sincerest apologies if offering a financial compensation was against the rules, but I would never ask a stranger to do anything like this for free. But if it's against the rules I understand and I will have to think of a different way to approach people and still be able to pay them for their effort.
No need for unfounded accusations and name calling, though.

On a more cheerful note, I'm so glad you guys are looking into Tekken 5!
## Post #24
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2015-03-23T20:53:31+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

Personally for me, I put faith in the honor system.

I gave you the tools and I trust that you will repay the favor in kind 

Of course im not calling foul here but you have to understand mr adults critisms and support for programers in such situations.

Anyways ... The script i sent you supports death by degrees and tekken5. It's wriitten in the scripts change log
## Post #25
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-03-24T00:04:48+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

Yeah, people are ridiculous about things like that these days. Thanking someone for their time by negotiating petty amounts is more offensive than useful. This isn't the god damn App Store. Anyway, thanks for the script, hopefully I can get back to this on the weekend.

As for my rudeness... you obviously don't have much experience with the human race. People are usually shitwads when they're operating (pseudo) anonymously. Congratulations if you're a beacon of hope, but I wouldn't put money on it, nor would it make the next guy to come along any less likely to be a liar. Quite the contrary, in fact.
## Post #26
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2015-03-24T12:08:03+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

If you feel like that attitude makes life easier for you, go for it. Maybe I just run in kinder circles. But I feel it's pretty obvious that a person looking to compensate any coding job with a pathetic 15$ does neither value nor respect other people's time. Should be fairly easy to avoid such people.

Anyway, what a welcome surprise your scripts will work with Tekken 5 as well! I've been sorting and naming models in my spare time the past couple of days and didn't even check the change log. 
The scripts run flawlessly and finally handling these models in 3DSM is not a pain anymore. Can't wait to work with the textures.

Let me thank you for your great youtube video guide. I've already downloaded and saved it for future reference. I'm also quite the fan of your dulcet tones Hahah Great voice!

Also very much looking forward to the noesis implementation. Will make things that much more easy, and I love using noesis. So happy how this turned out, I honestly didn't expect anything and I feel like I got everything haha 

Please keep us posted about the noesis implementation, mrAdults
## Post #27
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-03-25T03:59:51+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

Life, no. Internet forums where demented monsters with severe Asperger's go to embrace their lack of humanity, yes. Oh yes.

I'll probably get around to doing a build on the weekend, unless a contract thing comes up.
## Post #28
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2015-03-25T11:40:31+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

Haha, OK, you've got a point there!

> Reply from MrAdults
>
> 
I'll probably get around to doing a build on the weekend, unless a contract thing comes up.

Very much looking forward to it!
## Post #29
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-03-25T12:21:35+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

Hey mario, did you find the mirrored vertex flag? Looking at one of the skeleton bits in one of those nina models, there are two draws referencing the same VIF segment, and I know one of them has to be the mirrored draw. I thought for sure it was bit 0x200 of the value 12 bytes into the draw structure, but apparently it isn't. That bit and the first bit of the structure are the only bits that change between those two draws, but they also change for geometry that doesn't seem like it should be mirrored. Did I miss a separate lookup table for mirrored geo or something? I figure either that or there's a pointer to the microcode that's gonna be run for the thing which is implicitly dictating whether the draw will be mirrored. That's the less appealing option, since it requires sifting through all the models to find the mirroring microcode variants.

Edit: Oh, and I noticed the texture is just the first 4 bytes of the draw struct, referencing it by global index. Dunno if you figured that out already or if it points you in the right direction for Tekken.
## Post #30
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-03-25T19:20:20+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

All this talk about vif commands urges me to ask a question.
I've been working on a vif style model format for ages (in maxscript) but the way weighted vertices are stored (overlapping several masked vertex arrays) drives me crazy.
So I might just want to learn noesis for this but before I do, what kind of output does the noesis' vif unpack give you?
## Post #31
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2015-03-25T20:38:30+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

> Reply from MrAdults
>
> Hey mario, did you find the mirrored vertex flag? Looking at one of the skeleton bits in one of those nina models, there are two draws referencing the same VIF segment, and I know one of them has to be the mirrored draw. I thought for sure it was bit 0x200 of the value 12 bytes into the draw structure, but apparently it isn't. That bit and the first bit of the structure are the only bits that change between those two draws, but they also change for geometry that doesn't seem like it should be mirrored. Did I miss a separate lookup table for mirrored geo or something? I figure either that or there's a pointer to the microcode that's gonna be run for the thing which is implicitly dictating whether the draw will be mirrored. That's the less appealing option, since it requires sifting through all the models to find the mirroring microcode variants.

Edit: Oh, and I noticed the texture is just the first 4 bytes of the draw struct, referencing it by global index. Dunno if you figured that out already or if it points you in the right direction for Tekken.

yeah I tried mirroring that skeleton mesh in 3dsmax and the vertices are not along the origin of the X axis.. so it doesnt even mirror correctly in 3dsmax. there was something odd going there Im not sure what.

also the first 4 bytes, they are global offset or global index? i got large values when i was looking at tekken5. Silly I never considered that they might be offsets into the texture resource file though?
## Post #32
- Username: TGE
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-03-25T22:02:01+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

You mean the fact that the verts are all offset a little bit from the origin? Yeah, I noticed that too. I also noticed that the bone reference table for each draw is the same, which means there's probably a "base" joint index for that table somewhere, could be packed where that 0x200 bit value is changing. Then you might end up having to reskin the verts based on the relative transforms of those joints or something from some bind pose matrix that would be identical for each VIF seg since the bind pose has no mirroring in it. Unfortunately that probably means having to dig skeletal poses out of the motion data as well to transform against, cause there's no non-bind-space transform in the obj files that I saw. That might be further than I'm willing to go, although that motion data looked to be lacking any difficult compression beyond basic quantization. But anyway, yeah, it seems like it isn't as simple as a mirror bit.

I meant global index - you'll notice that each of those tim2 entries has extension data containing GIDX entries. Those global indices are unique across all loaded resources, so you'll rightfully get some pretty big values there. Funny enough they stuck with this same scheme for the next-gen Tekken/Soul Calibur/etc. titles, so I bet it's the same in Tekken 5 as well. You just match the global index of the texture resource with the first 32 bits of the draw struct.

It's possible, though, that because you're dumping Tekken 5 models out of memory, that they remap those indices at runtime so matching them to the offline cooked texture data could prove more problematic. But maybe not, at least in DBD it looks like they generate unique ID's at cook time so no runtime remapping would be necessary.

> Reply from TGE
>
> All this talk about vif commands urges me to ask a question.
I've been working on a vif style model format for ages (in maxscript) but the way weighted vertices are stored (overlapping several masked vertex arrays) drives me crazy.
So I might just want to learn noesis for this but before I do, what kind of output does the noesis' vif unpack give you?
Noesis has a couple of different unpacking modes, but only the dumb one is exposed in Python at the moment. I neglected it, because no one has been using it. The dumb one is the one that just parses through the VIF data and hands you back raw structures for each unpack detailing the size and type of the source data, so you get to handle actually interpreting it yourself.

It should be easy for me to hook the authentic mode up to Python for the next build too. It does the full-on unpacking according to all of the hardware specs and obeys all of the relevant registers (and allows you to emulate both VIF0 and VIF1 in a single context), so you end up with what you'd really end up with on hardware. All of your writes will be expanded out to 32 bits at 4 elements each in VU memory, and you get back a list of structures telling you where the unpacks took place with the relevant type info and start/end addresses in VU memory. Then you typically just do some rpgBind calls for the vertex buffers right over the emulated VU memory and you're good to go. This would probably instantly put an end to that Dirge of Cerberus thread that's been going on for years here.  I did write it from my own interpreted spec from the docs (didn't pull it from an emulator or anything), so there could be problems lurking, but... at least it's worked on all of the games I've encountered so far. Having more people using it would be good to discover any bugs or flat-out-broken things that I interpreted wrongly. I still need to get back to trying it on the MGS games too. revelation was kind enough to dump a bunch of info about them on me a long time ago, and... well, life.
## Post #33
- Username: mariokart64n
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-03-29T04:51:48+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

I'll be putting a build of Noesis up in a little bit that supports this. It also supports the dumped Tekken 5 models by scanning through for the seemingly-reliable initial VIF commands to set the cycle and write out the element count, then using that offset to find the address fixup for every other pointer in the file.

Skeleton, weights, and materials are supported. If you just load something up it'll throw everything at you like this:



That's because it doesn't know which skeleton to use (outside of any models within the file that might have embedded pose data), so I've added the ability to specify a _dbdinfo.txt file that lets you fill that stuff in and end up with something like this instead:



For this case you just make a file next to chr_nina1.obj named chr_nina1_dbdinfo.txt and fill it with this:

```
;FixWindings 1

;create a named skeleton from translation and rotation data
AddDataToNamedSkeleton "nina_main_pose" "chr_common.mop" "01_nin_Mid_INITIAL_TRANS.mot"
AddDataToNamedSkeleton "nina_main_pose" "chr_common.mop" "01_nin_Mid_INITIAL_ROT.mot"

;apply named skeleton to body, head, and hands
SetObjectNamedSkeleton "chr_ni1_b1.obj" "nina_main_pose"
SetObjectNamedSkeleton "chr_ni1_h1.obj" "nina_main_pose"
SetObjectNamedSkeleton "chr_ni1_t1l.obj" "nina_main_pose"
SetObjectNamedSkeleton "chr_ni1_t1r.obj" "nina_main_pose"

;transform hair onto the head (the head bone index is 11)
;this will also transform and reparent any sub-skeletons associated with the object.
;can be used to perform transforms to multiple bones in order.
TransformAndReparentObject "chr_ni1_dk1.obj" "nina_main_pose" 11
TransformAndReparentObject "chr_ni1_dk2.obj" "nina_main_pose" 11
TransformAndReparentObject "chr_ni1_dk3.obj" "nina_main_pose" 11

;skip over shadow mesh
SkipByObjectName "chr_nin_s1.obj" 1
;skip over effect shell by material
SkipByMaterialName "material1000139f" 1

;skip over additional head targets
SkipByObjectName "chr_ni1_ha.obj" 1
SkipByObjectName "chr_ni1_h2.obj" 1
SkipByObjectName "chr_ni1_h3.obj" 1

;skip over additional hand targets
SkipByObjectName "chr_ni1_t2l.obj" 1
SkipByObjectName "chr_ni1_t2r.obj" 1
SkipByObjectName "chr_ni1_t3l.obj" 1
SkipByObjectName "chr_ni1_t3r.obj" 1
SkipByObjectName "chr_ni1_t4l.obj" 1
SkipByObjectName "chr_ni1_t4r.obj" 1
SkipByObjectName "chr_ni1_t5l.obj" 1
SkipByObjectName "chr_ni1_t5r.obj" 1
SkipByObjectName "chr_ni1_t6l.obj" 1
SkipByObjectName "chr_ni1_t6r.obj" 1
SkipByObjectName "chr_ni1_t8r.obj" 1

;skip over alternate hair by material
SkipByMaterialName "material1000139a" 1
SkipByMaterialName "material1000139d" 1

```


The idea is the same for all of the other models. For figuring out material names and object names, just look at the data viewer in Noesis.

It'll also auto-load paired .nut files for the raw memory-dumped Tekken 5 files and auto-assign materials from the global indices, but you'll have to manage to find the right TIM2 list with global indices intact for that to work. I have no idea if that's easy or not, I haven't looked at Tekken 5 or any dumps from it, I just looked at and tested with the file mario put up in this thread.

I'm sorry, I didn't end up getting to the improved Python VIF support, cause sorting out the skeleton nonsense with this took longer than expected. But it's fully exposed in native plugin land if you're feeling adventurous. Otherwise, it's on the short-order todo list.
## Post #34
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2015-03-30T00:19:52+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

> Reply from MrAdults
>
> I'll be putting a build of Noesis up in a little bit that supports this. It also supports the dumped Tekken 5 models by scanning through for the seemingly-reliable initial VIF commands to set the cycle and write out the element count, then using that offset to find the address fixup for every other pointer in the file.

Skeleton, weights, and materials are supported. If you just load something up it'll throw everything at you like this:
 ...  
===============
What's New
===============
Version 4.1-4.148:
 -4.148 - Added import support for Death by Degrees.

Wow. That's major!
Just downloaded and tried it. Works like a charm.
You just saved me hours/days/weeks. Incredible.
Thank you so much! So glad you got involved in this thread. Also, many thanks for the detailed description/guide in your above post!
Do you by any chance also have a PayPal account that I could donate to? If you do, please PM me the info.

OMG.
## Post #35
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2015-03-30T01:29:41+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

great works
but...obj...?
where would obj come out...?

sorry noob question
## Post #36
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-03-30T01:52:03+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

Sure, by no means expected, but if you still have something to spare after giving mario the 500.  There's a paypal direct link here: [http://www.richwhitehouse.com/index.php ... _about.php](http://www.richwhitehouse.com/index.php?content=inc_about.php)

> Reply from porimac
>
> but...obj...? You can extract the archives with Noesis as well, just browse to and export them from the list view.
## Post #37
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2015-03-31T03:42:35+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

thank you for the information
Tekken 5 is different archive type...perhaps, i think there are same format
## Post #38
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2015-04-03T02:52:22+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

I tried noesis with TEKKEN 5 and it worked with most of the models, but the program crashes when i tried to open the .nud file of Steve Fox, if you need a sample of the file just tell me.
## Post #39
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2015-04-03T11:32:17+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

> Reply from MrAdults
>
> Sure, by no means expected, but if you still have something to spare after giving mario the 500.  There's a paypal direct link here: http://www.richwhitehouse.com/index.php ... _about.php

So it is you! I wasn't sure. I'll use that Paypal link then. Probably not his month, as I will compensate mario for his efforts first, but I'll make sure to show my gratitude to you next month 
The worst part in all of this is I currently have friends visiting that I need to entertain, so I have all these incredible tools you guys built and no time to get any work done with them atm First world problems I guess. Considering I'll be working with mario's script and your tools on Death by Degrees for the next couple of months, it's not too bad, though.
## Post #40
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-04-03T15:07:39+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

Yeah, the unholy trinity of identities can be confusing. I started Noesis to be a silly one-off project and figured I'd drop it after a little while. Then I ended up working on it for years. That's probably why I hate the codebase so much now.

> Reply from Casedey
>
> I tried noesis with TEKKEN 5 and it worked with most of the models, but the program crashes when i tried to open the .nud file of Steve Fox, if you need a sample of the file just tell me.Sure, send it over. There's probably a false positive for the first VIF segment that's throwing off the address fixup.
## Post #41
- Username: IvoryCutter
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-04-03T19:29:11+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

I had to add ReparentObjectSkeletonAndRebaseWeights for the cinematic models, cause they reference a bunch of different poses.



I'll put a build up later with that change. Once I do, stuff like this will work (for s2000.obj):

```
;FixWindings 1

;create a named skeleton from translation and rotation data
AddDataToNamedSkeleton "nina_main_pose" "../DATA0_files/chr_common.mop" "01_nin_Mid_INITIAL_TRANS.mot"
AddDataToNamedSkeleton "nina_main_pose" "../DATA0_files/chr_common.mop" "01_nin_Mid_INITIAL_ROT.mot"
AddDataToNamedSkeleton "nina_facial_pose" "../DATA0_files/chr_common.mop" "01_nin_facial_INITIAL_TRANS.mot"
AddDataToNamedSkeleton "nina_facial_pose" "../DATA0_files/chr_common.mop" "01_nin_facial_INITIAL_ROT.mot"
AddDataToNamedSkeleton "nina_lhand_pose" "../DATA0_files/chr_common.mop" "01_nin_Lhand_INITIAL_TRANS.mot"
AddDataToNamedSkeleton "nina_lhand_pose" "../DATA0_files/chr_common.mop" "01_nin_Lhand_INITIAL_ROT.mot"
AddDataToNamedSkeleton "nina_rhand_pose" "../DATA0_files/chr_common.mop" "01_nin_Rhand_INITIAL_TRANS.mot"
AddDataToNamedSkeleton "nina_rhand_pose" "../DATA0_files/chr_common.mop" "01_nin_Rhand_INITIAL_ROT.mot"

;apply named skeletons to body, face, and hands
SetObjectNamedSkeleton "chr_ni3_b1_mid.obj" "nina_main_pose"
SetObjectNamedSkeleton "chr_ni2_hf1_mid.obj" "nina_facial_pose"
SetObjectNamedSkeleton "chr_ni2_tfl_mid.obj" "nina_lhand_pose"
SetObjectNamedSkeleton "chr_ni2_tfr_mid.obj" "nina_rhand_pose"

;transform hair onto the head (the head bone index is 11)
;this will also transform and reparent any sub-skeletons associated with the object.
;can be used to perform transforms to multiple bones in order.
TransformAndReparentObject "chr_ni2_dk1_mid.obj" "nina_main_pose" 11
TransformAndReparentObject "chr_ni2_dk2_mid.obj" "nina_main_pose" 11
TransformAndReparentObject "chr_ni2_dk3_mid.obj" "nina_main_pose" 11
;just reparent the skeletons for the hands and face, geo is already in the right place.
;the last parameter here is the number of bones which influence weights in front of the
;base joint for the object's local skeleton. so 11 3 means reparent to joint 11 (head),
;while bone weight indices 0-2 reference joints 9-11.
ReparentObjectSkeletonAndRebaseWeights "chr_ni2_hf1_mid.obj" "nina_main_pose" 11 3
ReparentObjectSkeletonAndRebaseWeights "chr_ni2_tfl_mid.obj" "nina_main_pose" 15 2
ReparentObjectSkeletonAndRebaseWeights "chr_ni2_tfr_mid.obj" "nina_main_pose" 19 2

;skip over shadow mesh
SkipByObjectName "chr_nin_s1.obj" 1
;skip over alternate hair by material
SkipByMaterialName "material10001719" 1
SkipByMaterialName "material10001717" 1
SkipByMaterialName "material1000171b" 1

```
## Post #42
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2015-04-04T15:46:23+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

> Reply from MrAdults
>
> Sure, send it over. There's probably a false positive for the first VIF segment that's throwing off the address fixup.

Noesis crashes with these 3 files:

[http://www.mediafire.com/download/uyit9 ... rashes.rar](http://www.mediafire.com/download/uyit9x41caqo51a/TK5+Crashes.rar)

And these 3 files loads incomplete:

[http://www.mediafire.com/download/d9m6b ... +Parts.zip](http://www.mediafire.com/download/d9m6bn8d984j7r4/Missing+Parts.zip)
## Post #43
- Username: Casedey
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-04-05T21:15:08+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

Thanks, they're fixed in 4.149.
## Post #44
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2015-04-08T14:10:57+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

> Reply from MrAdults
>
> I had to add ReparentObjectSkeletonAndRebaseWeights for the cinematic models, cause they reference a bunch of different poses.

Bloody Hell. Thank you so much! I noticed that the in-game skeleton was being used for the cutscene models with the older script, but since I'm still sorting stuff and applying different versions of your base script to get different things I just ignored it for now... and then I come back here and see that in the meantime you've already fixed the issue... You're bloody brilliant! 

One question; do you think it'd be possible to apply a character model's pose data from the game directly in noesis? Like a specific pose from a certain frame of a cutscene?
## Post #45
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2015-04-08T23:42:10+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

Hey just wanted to take a moment to say thankyou to IvoryCutter for coming through on the payment for the work I did.
DBD was very hard for me to figure out but with hard work I was able to get it, and the reward makes it that much sweeter.

Also thanks to Chrrox for the DBD BMS, and of course MrAdult for getting involved and adding support into noesis for DBD and TK5
I'm no where close to the level that MrAdult is at, so I appreciate it very much that I wasn't forgotten about.
## Post #46
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-04-09T01:05:46+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

Good job coming through for mario there, IvoryCutter. Sorry I was a dick by default.

I could probably add the ability to apply different poses by name on top of the initial poses pretty easily. I didn't look to see if that pose data is a delta to or if it replaces the initial pose data for the supplied bones. If it replaces it, it'd actually work as-is, if you just add more AddDataToNamedSkeleton commands below the initial pose entries, and have those reference the character poses in the character mop file. That's just for initial anim poses though, not actual sequences. The way actual animation sequence deltas are stored may or may not be easy to figure out. I can probably look into that sometime in the next weekend or two. I also never looked around to see if there's already a file that ties the objects and animations and everything together, I'm sure that data is somewhere, although it could be in the elf.
## Post #47
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2015-04-09T20:51:43+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

> Reply from mariokart64n
>
> 
I'm no where close to the level that MrAdult is at, so I appreciate it very much that I wasn't forgotten about.

Ha! Mariokart, as MrAdults said himslef, he "never would've gotten involved with this thread if that hex block you pasted hadn't looked like it started off with VIF cycle and mask commands"  So thanks for posting that hex block that starts off with VIF cycle and mask commands (I have no idea what any of this means).

I'm using your MaxScript for all the static objects. Mainly to put together the enormous and intricate cruise liner. I just wanna texture these parts manually (b/c I later want to have it 3D printed and I feel much more comfortable doing so if I know the model inside out), and the colour coding your script provides is just such a brilliant and convenient way to do that.

For models with an armature I use Noesis, obviously. So happy to see the format supported so flawlessly in the newest releases.

> Reply from MrAdults
>
> Good job coming through for mario there, IvoryCutter. Sorry I was a dick by default.

Ha! Don't be! After our little back and forth I went ahead and had a look at how a lot of these financial offers go, both here and on a few other forums. Let's just say, I can absolutely see where the skepticism came from. 

> Reply from MrAdults
>
> I could probably add the ability to apply different poses by name on top of the initial poses pretty easily. I didn't look to see if that pose data is a delta to or if it replaces the initial pose data for the supplied bones. If it replaces it, it'd actually work as-is, if you just add more AddDataToNamedSkeleton commands below the initial pose entries, and have those reference the character poses in the character mop file. That's just for initial anim poses though, not actual sequences. The way actual animation sequence deltas are stored may or may not be easy to figure out. I can probably look into that sometime in the next weekend or two. I also never looked around to see if there's already a file that ties the objects and animations and everything together, I'm sure that data is somewhere, although it could be in the elf.

Many thanks for the explanation. Didn't know applying the in-game animation poses would be that easy. At least you make it sound easy. Looking forward to play around with that later. If you ever get a chance to look into what you call animation sequence deltas, that would be the icing on the cake. With mario's  brilliant maxscript and the complete and flawless noesis implementation this game has already received so much more attention and support than I ever anticipated. To think that, originally, I was just looking for UV data... Bloody hell, you guys!!!
## Post #48
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2015-04-14T21:23:04+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

Death by Degrees and Tekken 5 models can be ripped now - it's really GREAT news!!!
And what about Tekken 4 - this game have different models format?
## Post #49
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2015-04-19T12:57:13+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

MrAdults, are there commands to let you skip over armatures/bones that are included by default? 
I've tried the obvious suspects like SkipBySkeletonName, SkipByBoneName etc but to no avail.

edit: pictures
eg. Armature for Anna's hair even though the txt file with the correct code was used to only have Heihachi's meshes and armature loaded.



or here, where armature for Lana's dress and Nina's hair show up even though the code only references Enrique's meshes and armature.



There's probably a very obvious command that I'm just missing...


> Reply from Doronetty
>
> Death by Degrees and Tekken 5 models can be ripped now - it's really GREAT news!!!
And what about Tekken 4 - this game have different models format?

I suppose so.
## Post #50
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-04-21T03:09:51+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

I guess those skeletons are embedded in the file you're loading. I might not be ignoring object skeletons along with object meshes, which it's probably always appropriate to do. If you send over the dbdinfo's you're using, I'll take a look next time I get a chance.
## Post #51
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2015-04-25T09:08:58+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

Thank you!

This is the code I've used on Enrique's files (As a side note, he's referenced as "ben" in the character files, which finally confirmed my suspicion he was designed after the likeness of Benicio del Toro. Ha!:

```
AddDataToNamedSkeleton "ben_rhand_pose" "chr_common.mop" "02_ben_Rhand_INITIAL_ROT.mot"
AddDataToNamedSkeleton "ben_facial_pose" "chr_common.mop" "02_ben_facial_INITIAL_TRANS.mot"
AddDataToNamedSkeleton "ben_facial_pose" "chr_common.mop" "02_ben_facial_INITIAL_ROT.mot"

;apply named skeleton to body, head, and hands
SetObjectNamedSkeleton "chr_ben_b1_mid.obj" "ben_main_pose"
SetObjectNamedSkeleton "chr_ben_tfl_mid.obj" "ben_lhand_pose"
SetObjectNamedSkeleton "chr_ben_tfr_mid.obj" "ben_rhand_pose"
SetObjectNamedSkeleton "chr_ben_hf_mid.obj" "ben_facial_pose"

;just reparent the skeletons for the hands and face, geo is already in the right place.
;the last parameter here is the number of bones which influence weights in front of the
;base joint for the object's local skeleton. so 11 3 means reparent to joint 11 (head),
;while bone weight indices 0-2 reference joints 9-11.
ReparentObjectSkeletonAndRebaseWeights "chr_ben_hf_mid.obj" "ben_main_pose" 11 3
ReparentObjectSkeletonAndRebaseWeights "chr_ben_tfl_mid.obj" "ben_main_pose" 15 2
ReparentObjectSkeletonAndRebaseWeights "chr_ben_tfr_mid.obj" "ben_main_pose" 19 2

;skip over shadow mesh
;skip over effect shell by material
SkipByMaterialName "material1000139f" 1
SkipByObjectName "chr_nin_s1.obj" 1
SkipByObjectName "chr_fer_s1.obj" 1
SkipByObjectName "chr_ben_s1.obj" 1
SkipByObjectName "chr_stv_s1.obj" 1
SkipByObjectName "chr_k1d1sn0n.obj" 1

;skip over additional character models
SkipByObjectName "chr_fer_dk1_mid.obj" 1
SkipByObjectName "chr_fer_dk2_mid.obj" 1
SkipByObjectName "chr_fer_dk3_mid.obj" 1
SkipByObjectName "chr_fer_dk4_mid.obj" 1
SkipByObjectName "chr_fer_dk5_mid.obj" 1
SkipByObjectName "chr_fer_dk6_mid.obj" 1
SkipByObjectName "chr_fer_dk7_mid.obj" 1
SkipByObjectName "chr_fer_b1_mid.obj" 1
SkipByObjectName "chr_fer_hf_mid.obj" 1
SkipByObjectName "chr_fer_tfl_mid.obj" 1
SkipByObjectName "chr_fer_tfr_mid.obj" 1
SkipByObjectName "chr_stv_b1_mid.obj" 1
SkipByObjectName "chr_stv_it1_mid.obj" 1
SkipByObjectName "chr_stv_it2_mid.obj" 1
SkipByObjectName "chr_stv_hf_mid.obj" 1
SkipByObjectName "chr_stv_tfl_mid.obj" 1
SkipByObjectName "chr_stv_tfr_mid.obj" 1
SkipByObjectName "chr_ni2_b1_mid.obj" 1
SkipByObjectName "chr_ni2_hf1_mid.obj" 1
SkipByObjectName "chr_ni2_tfl_mid.obj" 1
SkipByObjectName "chr_ni2_tfr_mid.obj" 1
SkipByObjectName "chr_ni2_dk1_mid.obj" 1
SkipByObjectName "chr_ni2_dk2_mid.obj" 1
SkipByObjectName "chr_ni2_dk3_mid.obj" 1
SkipByObjectName "chr_skn_b.obj" 1
SkipByObjectName "chr_skn_h3.obj" 1
SkipByObjectName "chr_skn_h2.obj" 1
SkipByObjectName "chr_skn_h4.obj" 1
SkipByObjectName "chr_skn_h1.obj" 1
SkipByObjectName "chr_skn_t3l.obj" 1
SkipByObjectName "chr_skn_t3r.obj" 1
SkipByObjectName "chr_skn_dk1.obj" 1

;skip over additional weapon models
SkipByObjectName "sub_brg_1.obj" 1
SkipByObjectName "sub_ebs_1.obj" 1
SkipByObjectName "sub_hdg_1.obj" 1
SkipByObjectName "sub_tsc_1.obj" 1

```


In case you need them, here are his files: [http://www.mediafire.com/download/pl0u5 ... nrique.rar](http://www.mediafire.com/download/pl0u5i2gypkdtib/Enrique.rar)


edit:

> Reply from MrAdults
>
> I had to add ReparentObjectSkeletonAndRebaseWeights for the cinematic models, cause they reference a bunch of different poses.



I'll put a build up later with that change. Once I do, stuff like this will work (for s2000.obj):
Code: Select all;uncomment if you want to force recalculation of triangle windings instead of relying on ps2 draw kicks with strip order
;FixWindings 1

;create a named skeleton from translation and rotation data
AddDataToNamedSkeleton "nina_main_pose" "../DATA0_files/chr_common.mop" "01_nin_Mid_INITIAL_TRANS.mot"
AddDataToNamedSkeleton "nina_main_pose" "../DATA0_files/chr_common.mop" "01_nin_Mid_INITIAL_ROT.mot"
AddDataToNamedSkeleton "nina_facial_pose" "../DATA0_files/chr_common.mop" "01_nin_facial_INITIAL_TRANS.mot"
AddDataToNamedSkeleton "nina_facial_pose" "../DATA0_files/chr_common.mop" "01_nin_facial_INITIAL_ROT.mot"
AddDataToNamedSkeleton "nina_lhand_pose" "../DATA0_files/chr_common.mop" "01_nin_Lhand_INITIAL_TRANS.mot"
AddDataToNamedSkeleton "nina_lhand_pose" "../DATA0_files/chr_common.mop" "01_nin_Lhand_INITIAL_ROT.mot"
AddDataToNamedSkeleton "nina_rhand_pose" "../DATA0_files/chr_common.mop" "01_nin_Rhand_INITIAL_TRANS.mot"
AddDataToNamedSkeleton "nina_rhand_pose" "../DATA0_files/chr_common.mop" "01_nin_Rhand_INITIAL_ROT.mot"

;apply named skeletons to body, face, and hands
SetObjectNamedSkeleton "chr_ni3_b1_mid.obj" "nina_main_pose"
SetObjectNamedSkeleton "chr_ni2_hf1_mid.obj" "nina_facial_pose"
SetObjectNamedSkeleton "chr_ni2_tfl_mid.obj" "nina_lhand_pose"
SetObjectNamedSkeleton "chr_ni2_tfr_mid.obj" "nina_rhand_pose"

;transform hair onto the head (the head bone index is 11)
;this will also transform and reparent any sub-skeletons associated with the object.
;can be used to perform transforms to multiple bones in order.
TransformAndReparentObject "chr_ni2_dk1_mid.obj" "nina_main_pose" 11
TransformAndReparentObject "chr_ni2_dk2_mid.obj" "nina_main_pose" 11
TransformAndReparentObject "chr_ni2_dk3_mid.obj" "nina_main_pose" 11
;just reparent the skeletons for the hands and face, geo is already in the right place.
;the last parameter here is the number of bones which influence weights in front of the
;base joint for the object's local skeleton. so 11 3 means reparent to joint 11 (head),
;while bone weight indices 0-2 reference joints 9-11.
ReparentObjectSkeletonAndRebaseWeights "chr_ni2_hf1_mid.obj" "nina_main_pose" 11 3
ReparentObjectSkeletonAndRebaseWeights "chr_ni2_tfl_mid.obj" "nina_main_pose" 15 2
ReparentObjectSkeletonAndRebaseWeights "chr_ni2_tfr_mid.obj" "nina_main_pose" 19 2

;skip over shadow mesh
SkipByObjectName "chr_nin_s1.obj" 1
;skip over alternate hair by material
SkipByMaterialName "material10001719" 1
SkipByMaterialName "material10001717" 1
SkipByMaterialName "material1000171b" 1

Also, for anyone using MrAdults' example script (quoted above) for s2000.obj (I've already seen it on deviantart lol), go for the code below instead, which references another one of Nina's skeletons that includes armature for the lower part of her dress:

```
;FixWindings 1

;create a named skeleton from translation and rotation data
AddDataToNamedSkeleton "nina_main_pose" "chr_common.mop" "01_nin_Sk_Mid_INITIAL_TRANS.mot"
AddDataToNamedSkeleton "nina_main_pose" "chr_common.mop" "01_nin_Sk_Mid_INITIAL_ROT.mot"
AddDataToNamedSkeleton "nina_facial_pose" "chr_common.mop" "01_nin_facial_INITIAL_TRANS.mot"
AddDataToNamedSkeleton "nina_facial_pose" "chr_common.mop" "01_nin_facial_INITIAL_ROT.mot"
AddDataToNamedSkeleton "nina_lhand_pose" "chr_common.mop" "01_nin_Lhand_INITIAL_TRANS.mot"
AddDataToNamedSkeleton "nina_lhand_pose" "chr_common.mop" "01_nin_Lhand_INITIAL_ROT.mot"
AddDataToNamedSkeleton "nina_rhand_pose" "chr_common.mop" "01_nin_Rhand_INITIAL_TRANS.mot"
AddDataToNamedSkeleton "nina_rhand_pose" "chr_common.mop" "01_nin_Rhand_INITIAL_ROT.mot"

;apply named skeletons to body, face, and hands
SetObjectNamedSkeleton "chr_ni3_b1_mid.obj" "nina_main_pose"
SetObjectNamedSkeleton "chr_ni2_hf1_mid.obj" "nina_facial_pose"
SetObjectNamedSkeleton "chr_ni2_tfl_mid.obj" "nina_lhand_pose"
SetObjectNamedSkeleton "chr_ni2_tfr_mid.obj" "nina_rhand_pose"

;transform hair onto the head (the head bone index is 11)
;this will also transform and reparent any sub-skeletons associated with the object.
;can be used to perform transforms to multiple bones in order.
TransformAndReparentObject "chr_ni2_dk1_mid.obj" "nina_main_pose" 11
TransformAndReparentObject "chr_ni2_dk2_mid.obj" "nina_main_pose" 11
TransformAndReparentObject "chr_ni2_dk3_mid.obj" "nina_main_pose" 11
;just reparent the skeletons for the hands and face, geo is already in the right place.
;the last parameter here is the number of bones which influence weights in front of the
;base joint for the object's local skeleton. so 11 3 means reparent to joint 11 (head),
;while bone weight indices 0-2 reference joints 9-11.
ReparentObjectSkeletonAndRebaseWeights "chr_ni2_hf1_mid.obj" "nina_main_pose" 11 3
ReparentObjectSkeletonAndRebaseWeights "chr_ni2_tfl_mid.obj" "nina_main_pose" 15 2
ReparentObjectSkeletonAndRebaseWeights "chr_ni2_tfr_mid.obj" "nina_main_pose" 19 2

;skip over shadow mesh
SkipByObjectName "chr_nin_s1.obj" 1
;skip over alternate hair by material
SkipByMaterialName "material10001719" 1
SkipByMaterialName "material10001717" 1
SkipByMaterialName "material1000171b" 1
```
## Post #52
- Username: IvoryCutter
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-04-26T02:05:13+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

Yeah, looks like it just needs to skip the skeletons associated with the objects too. Will be fixed whenever I get a new build up.
## Post #53
- Username: gledson999
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Mar 18, 2012 10:59 am
- Post datetime: 2015-11-29T04:29:18+00:00
- Post Title: Re: [PS2] Death by Degrees UV extraction (500$ compensation)

anyone had a plugin or tool to import this model for ps2?
