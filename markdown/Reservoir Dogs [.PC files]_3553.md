## Post #1
- Username: prysm
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 15, 2009 6:38 am
- Post datetime: 2009-06-25T22:46:49+00:00
- Post Title: Reservoir Dogs [.PC files]

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-06-27T19:25:35+00:00
- Post Title: Reservoir Dogs [.PC files]

The audio are raw pcm, no headers found or Id's   
In the botton of the 1rst file (s_0_training.pc)  you can see some information

```

```
## Post #3
- Username: prysm
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 15, 2009 6:38 am
- Post datetime: 2009-06-27T22:48:45+00:00
- Post Title: Reservoir Dogs [.PC files]

Savage, if I understood your words correctly - the audio can't be extracted, right?   Do all 5 files can't be extracted or some of them?
## Post #4
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2009-06-27T22:58:09+00:00
- Post Title: Reservoir Dogs [.PC files]

Only downloaded the first part (s_0_training.pc) - it simple pcm 16bit little endian - you dont need headers - try a simple audio editor like goldwave
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-28T04:06:51+00:00
- Post Title: Reservoir Dogs [.PC files]

the following BMS script extracts all the files from the PC archive:

*edit* use the script of mr.mouse some posts below

from what I have seen some files are in raw pcm mode and have a minimal header at their beginning (samples, frequency, channels and so on) while the others are all in the PS2 VAG ADPCM and almost all have an interleave value of 8000 (in blue_tutorial_radiobackupgeneral_2.wav.str I don't know what's the right value).
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-28T05:41:11+00:00
- Post Title: Reservoir Dogs [.PC files]

bugtest, nice work! I'd appreciate it greatly if you'd also post the structure of a file, besides a BMS script. This will help everyone understand the format.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-28T07:12:07+00:00
- Post Title: Reservoir Dogs [.PC files]

eh eh eh I'm so lazy that I created a new tool for making my work quicker and you ask me to do additional work? :)

usually the BMS scripts are very basic and easy to understand so I guess it's useless to document the file format in other additional forms spending more time for doing it than doing the reversing+bms job.

in this case the only particular thing was in the offsets which are all divided by 16.
in the playstation stuff is enough normal to use sectors as reference for offsets and sometimes sizes but it's ever set to 2048 bytes (size of mode1 CD-ROM sectors) while in this case it's set to 16 for some unknown reason (probably it was 2048 on PS2 and then was changed to 16 in the PC port)... it's only a hypothesis.
## Post #8
- Username: prysm
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-28T20:52:38+00:00
- Post Title: Reservoir Dogs [.PC files]

Unfortunately, bugtest, the format of these .pc files is a little different. 

Here's my MexScript that will extract the resources and match them with the correct filename. 

```
Get FILES Long 0;
Get INFO_OFF Long 0;
Get SBNK_OFF Long 0;
GoTo 40 0;
Get NAMES_OFF Long 0;
Math INFO_OFF *= 16;
Math SBNK_OFF *= 16;
Math NAMES_OFF *= 16;
For i = 1 To FILES;
GoTo INFO_OFF 0;
Get OFFSET Long 0;
Get DUMMY Long 0;
Get SIZE Long 0;
Get NAMEOffset Long 0;
Get DUMMY Long 0;
Get DUMMY Long 0;
Get DUMMY Long 0;
Get DUMMY Long 0;
SavePos INFO_OFF 0;
Math NAMEOffset += NAMES_OFF ;
GoTo NAMEOffset 0;
Get NAME String 0;
Math OFFSET *= 16;
Log NAME OFFSET SIZE 0 0;
Next i;

```


Here's the .BMS to add to your MultiEx Commander using the BMS-->Add BMS to MRF... option so you can open any .PC file with MultiEx Commander the normal way. 


 pc.zip
(320 Bytes) Downloaded 52 times



The QuickBMS script assumed that the files were saved in chronological order in the archive, which they are not exactly. The FileName table lists the names, but in a different order than the INFO_OFF table. In fact, the variable that comes after the SIZE variable in the INFO_OFF table is not a trivial one: it is the pointer to the correct filename in the NAMES_OFF table.  

All of these .pc files have the 'FileNameTable.pak.sys' resource entry. It was natural to assume that the INFO_OFF table would match the actual offset and size of this entry.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-28T21:39:08+00:00
- Post Title: Reservoir Dogs [.PC files]

ops the names offsets, I should pay more attention when I do this stuff... but I'm lazy :)
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-28T22:01:41+00:00
- Post Title: Reservoir Dogs [.PC files]

I would not call you lazy at all, looking at your energy to create a lot of tools. 

Perhaps a little 'careless', then...  (Just like : you have been thanked a lot by people, but were to careless to thank others   ) 

Anyway, I've had my own share of mistakes in format demystification, it's only human. eh eh
## Post #11
- Username: prysm
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 15, 2009 6:38 am
- Post datetime: 2009-06-30T09:50:13+00:00
- Post Title: Reservoir Dogs [.PC files]

Thanks for Your help, guys! Appreciate it!   

I'll try the script you've made, Mr.Mouse
