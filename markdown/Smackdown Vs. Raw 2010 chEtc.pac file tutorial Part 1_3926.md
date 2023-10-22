## Post #1
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-05T11:49:57+00:00
- Post Title: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

This is to explain the chEtc.pac file in SvR2010 on the Xbox 360.  The file is used when the game FIRST builds the save file.  After your save file is first created, it never accesses this file again, so for any changes to appear, you have to delete your old save.

In this first tutorial regarding the file, I'll explain the part that contains the wrestler's basic info.  You must have the data you want to change uncompressed to see what you want to change, use either the yukes.bms script or unrrbe.exe to decompress the data.  Then you must put the data back into the file, changing the offsets and sizes in the header of the file, or find a way to compress back to BPE format and then reinsert into the pac file.  The header has been reverse engineered and is easy to figure out, so you should be able to do this on your own, I did.  I have the whole file with this part of it uncompressed, but I hate publicly posting actual game files, and I really still discourage others that are doing it, I don't want another Ninja Hacker incident happening.

I'll go ahead and start the tutorial with the next post.
## Post #2
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-05T12:07:09+00:00
- Post Title: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

The first thing you want to do, is open your Hex Editor, I use Hex Workshop.  Next you want to open up your uncompressed data that you want to change, in my example, I will use Triple H and MY custom uncompressed and rebuilt chEtc.pac file.  Yours may look different depending on how you get the uncompressed data, but the 0x104 bytes you select of uncompressed data will look the same in the end.

First you select the 0x104 bytes of data of the wrestler you want, do not select the "0100 0801" part of your uncompressed file.

Click to Enlarge
[](http://brienj.home.insightbb.com/chEtc1.jpg)

Next, you paste the selected data into a new file.

Click to Enlarge
[](http://brienj.home.insightbb.com/chEtc2.jpg)

This is to set it up so you can follow along with the offsets I will be giving in the next step.
## Post #3
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-05T12:19:36+00:00
- Post Title: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

List of all known values, if you find any new ones, please let us know, thanks.

------------------------------------------------------------------------------------------

0x000 = All 8 attributes listed twice in a row (Byte values)

0x010 = Raw 0x00
	Smackdown 0x01
	ECW 0x02
	Legend 0x04
	WCW 0x05
	Free Agent 0x06

0x015 = Cheer 0x00
	Boo 0x01

0x01C = Height (Short Value)
Comments:
To determine what value to use for an height, this value will be approxiamtely (54.75 * height in inches) or (2,156 * height in meters).  It was difficult to get a really accurate number here, because there are differences in billed height, actual height, and so on, but  I believe they are using actual heights of wrestlers, not billed height.  Regardless, the values I gave you will get you very close to the actual height that you want.

0x01E = Second Height Value ??? (Some wrestlers have slightly different number here)

0x020 = Wrestler's Number (Short Value)

0x022 = Wrestler's Full Name

0x066 = Wrestler's Nickname (if used)

0x0AA = Wrestler's Short Name

0x0D4 = Man 0x00
	Diva 0x01

0x0D2 = Wrestler's Number w/ 1 added to end of it (Short Value) (Example: Wrestler 123 would have value 1231 here)

0x0D4 = Wrestler's Number w/ 2 added to end of it (Short Value) (Example: Wrestler 123 would have value 1232 here)

0x0D6 = Wrestler's Number w/ 3 added to end of it (Short Value) (Example: Wrestler 123 would have value 1233 here)

0x0D8 = Wrestler's Number w/ 4 added to end of it (Short Value) (Example: Wrestler 123 would have value 1234 here)

0x0DA = Wrestler's Number again

0x0DD = Not-Playable 0x00
	Playable 0x01

0x0E2 = Number in Selection List Menu (Short Value)
Comments:
Must be careful with this number, if two wrestlers have the same number, one of them will not show up on the selection menu, as well as making one wrestler next to them in the list not show up as well.

0x0E6 = Wrestler's Number again

0x0EA = The 6 Abillities listed in a row (Byte Values) 

------------------------------------------------------------------------------------------

The values in the game file are little endian.  The values in the game save, which uses this game file, are big endian.  This is helpful if you check changes in the save file after making changes within the game.  This is how I found out some of the values, others were by conjecture.  You can also use this method to get the value of each of the abillities.
## Post #4
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2009-12-08T07:35:10+00:00
- Post Title: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

So Brienj with this info can I just add wrestler pac files from other svr games as long as I assign a select screen number that isnt used and make sure theyre not npc's? If so whats the highest superstar number on the default roster so i can just use numbers above that. Also the height how does that translate into hex for example what value is 6'4"? Sorry for sounding like an idiot.
## Post #5
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-08T09:28:45+00:00
- Post Title: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

I have the tools but when I use them on the chEtc.pac I get 5 folders ABD, CTRL, DAT, PMLH, PRO
if i dont use the tools and open the chetc in hex editor I get the below pic

Please Can you tell me were I'm going wrong?
[svr10.jpg](https://xentaxbackup.github.io/file/2602_svr10.jpg)
## Post #6
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-08T15:07:40+00:00
- Post Title: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

> Reply from snyperstyle
>
> So Brienj with this info can I just add wrestler pac files from other svr games as long as I assign a select screen number that isnt used and make sure theyre not npc's? If so whats the highest superstar number on the default roster so i can just use numbers above that. Also the height how does that translate into hex for example what value is 6'4"? Sorry for sounding like an idiot.
William Regal is the highest number on the select screen, and his number is 0x59, so I've been adding wrestlers starting at 0x60.

Like I mentioned in the tutorial:

> 0x01C = Height (Short Value)
>
> Comments:
>
> To determine what value to use for an height, this value will be approxiamtely (54.75 * height in inches) or (2,156 * height in meters). It was difficult to get a really accurate number here, because there are differences in billed height, actual height, and so on, but I believe they are using actual heights of wrestlers, not billed height. Regardless, the values I gave you will get you very close to the actual height that you want.

So for the example I used, Triple H has a value of 0x1040 (Hex) or 4,160 (decimal), so you take 4,160 and divide it by 54.75 and you get 75.98 or rounded to 76 inches, which is the 6' 4" that you wanted.
## Post #7
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-08T15:13:38+00:00
- Post Title: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

> Reply from DRAVEN
>
> I have the tools but when I use them on the chEtc.pac I get 5 folders ABD, CTRL, DAT, PMLH, PRO
if i dont use the tools and open the chetc in hex editor I get the below pic

Please Can you tell me were I'm going wrong?
In my example I have a rebuilt chEtc.pac file.  

Use the yukes.bms script on it, then go in the folder DAT and open 102.POF0 and see if it looks the same then.  Remember the offsets will be based on if you remove the first four bytes which are 0x01000801

I edited my post above in the tutorial to explain it better, I hope.
## Post #8
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-08T19:23:49+00:00
- Post Title: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

Ok thanks m8 I have it now will wait on your release.. its just good a thing to know... I would like to get into editing the textures for the game as I has already started in the hope that away to reimport them and have them work is found..
## Post #9
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-11T02:57:22+00:00
- Post Title: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

Love the work you're doing on this!

> Reply from brienj
>
> Use the yukes.bms script on it, then go in the folder DAT and open 102.POF0 and see if it looks the same then.  Remember the offsets will be based on if you remove the first four bytes which are 0x01000801
I was really confused until I read this part and tried looking at the 102.POF0 file.  Now I'm only a medium amount of confused (heh).

If I look at my chEtc.pac file, it seems like Triple H only takes up 0x083 spaces, not 0x104.  But if I run the quickBMS on the chEtc.pac and look at 102.POF0 in the DAT folder, I see that my positions in that file's Triple H all seem to match yours.

How do I reconcile that I have two versions of Triple H here, and only the one in the 102.POF0 file matches your offsets?  Can I copy the 102.POF0's Triple H block and insert that directly into my chEtc.pac?  Or should I be altering the chEtc.pac's version of Triple H, which is slightly shorter and the offset positions do not match what you've provided?

I'd also like to echo Draven's sentiments about being able to compile a new PAC file with images.  If we can do that, we can replace rings, belts, model skins....*drool*
## Post #10
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-11T03:55:37+00:00
- Post Title: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

One more question - once you're done adding wrestlers to the chEtc.pac, how do you add the extra wrestlers' .pacs to the game?  I've been using XBox Backup Creator to Extract and Replace .pacs, but there's no option for Adding one.

You'll probably answer that in the tutorial at some point, I know
## Post #11
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-11T17:14:29+00:00
- Post Title: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

> Reply from FatalArms
>
> Love the work you're doing on this!
brienj wrote:Use the yukes.bms script on it, then go in the folder DAT and open 102.POF0 and see if it looks the same then.  Remember the offsets will be based on if you remove the first four bytes which are 0x01000801

I was really confused until I read this part and tried looking at the 102.POF0 file.  Now I'm only a medium amount of confused (heh).

If I look at my chEtc.pac file, it seems like Triple H only takes up 0x083 spaces, not 0x104.  But if I run the quickBMS on the chEtc.pac and look at 102.POF0 in the DAT folder, I see that my positions in that file's Triple H all seem to match yours.

How do I reconcile that I have two versions of Triple H here, and only the one in the 102.POF0 file matches your offsets?  Can I copy the 102.POF0's Triple H block and insert that directly into my chEtc.pac?  Or should I be altering the chEtc.pac's version of Triple H, which is slightly shorter and the offset positions do not match what you've provided?

I'd also like to echo Draven's sentiments about being able to compile a new PAC file with images.  If we can do that, we can replace rings, belts, model skins....*drool*
That's because everything in the chEtc.pac file is compressed.  As I've said several times now, I have a custom chEtc.pac file where almost everything is uncompressed in it.

> Reply from FatalArms
>
> One more question - once you're done adding wrestlers to the chEtc.pac, how do you add the extra wrestlers' .pacs to the game?  I've been using XBox Backup Creator to Extract and Replace .pacs, but there's no option for Adding one.

You'll probably answer that in the tutorial at some point, I know
You have to rebuild a totally new iso file.
## Post #12
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2009-12-11T18:01:09+00:00
- Post Title: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

brienj quick question did you figure out how to add music to the game or were those just playlists from your pc in the video?
## Post #13
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-11T18:36:28+00:00
- Post Title: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

> Reply from brienj
>
> That's because everything in the chEtc.pac file is compressed.  As I've said several times now, I have a custom chEtc.pac file where almost everything is uncompressed in it.
Ah, so you did!  Gotcha.  I was confusing "uncompressed" with "extracted" in my stupid brain.  Makes sense now.  Where would I find this unrrbe.exe?  A Google search only turns up this thread, as does a forum search.

Also, what program would you (or anyone) recommend for building a new ISO?

(Sorry for being a clueless noob!)
## Post #14
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-12T08:27:16+00:00
- Post Title: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

> Reply from snyperstyle
>
> brienj quick question did you figure out how to add music to the game or were those just playlists from your pc in the video?
I didn't add music to the game, each wrestler I add will play a playlist named after them, so for example, Hulk Hogan will play the playlist named "Hulk Hogan" on your 360, if you have a playlist named that, if not, you make one.  I did that so people will not have to go into Create-An-Entrance, you can, but if you change anything and save it, you will lose the titantron.  I'll have full instructions on how to make custom entrances if you don't like the ones I make, and it will still let you keep the titantron, it just requires copying some info from the save file after you save the entrance the way you want it.
## Post #15
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2009-12-12T12:19:42+00:00
- Post Title: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

I figured that but thats an awesome idea to have them set up already.
## Post #16
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-12T22:08:48+00:00
- Post Title: Re: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

> Reply from snyperstyle
>
> I figured that but thats an awesome idea to have them set up already.
I would like to have all the movesets setup too, but that is a big chore, but I am doing it for wrestlers that have their movesets in the game, like The Boogeyman, Ric Flair, Lance Cade, etc.
## Post #17
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-14T09:41:05+00:00
- Post Title: Re: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

What would you need mate? someone to make them and send you the save file to use the data?
## Post #18
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-14T16:26:52+00:00
- Post Title: Re: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

> Reply from DRAVEN
>
> What would you need mate? someone to make them and send you the save file to use the data?
If you want to make some custom movesets to help out, that would be very helpful.  You wouldn't have to worry about any wrestlers that already have movesets for them in the game, there are 30 premade ones in the game:
Moveset 1: Hurricane/Gregory Helms 
Moveset 2: Charlie Haas 
Moveset 3: Jamie Noble 
Moveset 4: Shane McMahon 
Moveset 5: RVD 
Moveset 6: Paul London 
Moveset 7: Lance Cade 
Moveset 8: Trevor Murdoch 
Moveset 9: Viscera or Big Daddy V 
Moveset 10: Elijah Burke 
Moveset 11: Boogeyman 
Moveset 12: Bob Holly 
Moveset 13: Val Venis 
Moveset 14: Kung Fu Naki 
Moveset 15: Tajiri 
Moveset 16: Brock Lesnar 
Moveset 17: Goldberg 
Moveset 18: Floyd Mayweather 
Moveset 19: Kurt Angle 
Moveset 20: Booker T 
Moveset 21: Rhino 
Moveset 22: Bubba Ray 
Moveset 23: D-Von 
Moveset 24: Samoa Joe 
Moveset 25: AJ Styles 
Moveset 26: Ric Flair 
Moveset 27: Mick Foley 
Moveset 28: Eddie Guerrero 
Moveset 29: Roddy Piper 
Moveset 30: Bret Hart

Just make movesets for any wrestlers that are in SvR2009 and LOW and do not have a premade moveset.  You don't need to put them on CAWs, in fact it would be easier if you didn't, and just tell me which wrestlers have which moveset, then I can convert the save data from big endian to little endian and transfer over to the chEtc.pac file.

Another thing that would help me out, is if everyone could make a list of good stats for the wrestlers in LOW, I don't need them for SvR2009 wrestlers, as they have them already.  I've been giving stats from some examples I can find on CAW sites as well as my own feelings, but if anyone wants to add their input, they are more than welcome.

Don't worry, all stats, and all movesets can be changed by anyone with the roster hack, you won't be stuck with what I give you, but the more stuff I can have premade, the less stuff anyone will have to change.
## Post #19
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-14T17:41:45+00:00
- Post Title: Re: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

Ok mate I will have a look
## Post #20
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-16T21:15:27+00:00
- Post Title: Re: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

any chance someone can help with this as I've had abit of bad news and have to have treatment for 6 weeks then maybe another operation
## Post #21
- Username: coroner
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Dec 06, 2009 9:12 am
- Post datetime: 2009-12-17T04:04:00+00:00
- Post Title: Re: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

What exactly did you need?
## Post #22
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-17T08:22:26+00:00
- Post Title: Re: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

> Reply from brienj
>
> DRAVEN wrote:What would you need mate? someone to make them and send you the save file to use the data?
If you want to make some custom movesets to help out, that would be very helpful.  You wouldn't have to worry about any wrestlers that already have movesets for them in the game, there are 30 premade ones in the game:
Moveset 1: Hurricane/Gregory Helms 
Moveset 2: Charlie Haas 
Moveset 3: Jamie Noble 
Moveset 4: Shane McMahon 
Moveset 5: RVD 
Moveset 6: Paul London 
Moveset 7: Lance Cade 
Moveset 8: Trevor Murdoch 
Moveset 9: Viscera or Big Daddy V 
Moveset 10: Elijah Burke 
Moveset 11: Boogeyman 
Moveset 12: Bob Holly 
Moveset 13: Val Venis 
Moveset 14: Kung Fu Naki 
Moveset 15: Tajiri 
Moveset 16: Brock Lesnar 
Moveset 17: Goldberg 
Moveset 18: Floyd Mayweather 
Moveset 19: Kurt Angle 
Moveset 20: Booker T 
Moveset 21: Rhino 
Moveset 22: Bubba Ray 
Moveset 23: D-Von 
Moveset 24: Samoa Joe 
Moveset 25: AJ Styles 
Moveset 26: Ric Flair 
Moveset 27: Mick Foley 
Moveset 28: Eddie Guerrero 
Moveset 29: Roddy Piper 
Moveset 30: Bret Hart

Just make movesets for any wrestlers that are in SvR2009 and LOW and do not have a premade moveset.  You don't need to put them on CAWs, in fact it would be easier if you didn't, and just tell me which wrestlers have which moveset, then I can convert the save data from big endian to little endian and transfer over to the chEtc.pac file.

Another thing that would help me out, is if everyone could make a list of good stats for the wrestlers in LOW, I don't need them for SvR2009 wrestlers, as they have them already.  I've been giving stats from some examples I can find on CAW sites as well as my own feelings, but if anyone wants to add their input, they are more than welcome.

Don't worry, all stats, and all movesets can be changed by anyone with the roster hack, you won't be stuck with what I give you, but the more stuff I can have premade, the less stuff anyone will have to change.

He needs the above mate
## Post #23
- Username: coroner
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Dec 06, 2009 9:12 am
- Post datetime: 2009-12-20T08:32:10+00:00
- Post Title: Re: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

deleted
## Post #24
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2010-01-14T11:07:18+00:00
- Post Title: Re: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

any chance to add the name anouncement ?
## Post #25
- Username: BxNight
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Dec 18, 2009 11:52 am
- Post datetime: 2010-02-19T03:36:10+00:00
- Post Title: Re: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

i figured out how to use hex workshop i am able to edit the stats height show etc but i cant load the model once i select them i made a small list of model numbers for those who need wrestler numbers(the hex values for the chXXX.pac files) 

Edit: Figured out the selection screen also posted hex values up to CH303.pac. Still having a hard time getting the models to show up but I think I'm on the right track I'm gonna try to put the superstars in there original slot.


Roster Values
---------------
HEX  ChXXX.pac
64 - 100
65 - 101
66 - 102
67 - 103
68 - 104
69 - 105
6A - 106
6B - 107
6C - 108
6D - 109
6E - 110
6F - 111
70 - 112
71 - 113
72 - 114
73 - 115
74 - 116
75 - 117
76 - 118
77 - 119
78 - 120
79 - 121
7A - 122
7B - 123
7C - 124
7D - 125
7E - 126
7F - 127
80 - 128
81 - 129
82 - 130
83 - 131
84 - 132
85 - 133
86 - 134
87 - 135
88 - 136
89 - 137
8A - 138
8B - 139
8C - 140
8D - 141
8E - 142
8F - 143
90 - 144
91 - 145
92 - 146
93 - 147
94 - 148
95 - 149
96 - 150
97 - 151
98 - 152
99 - 153
9A - 154
9B - 155
9C - 156
9E - 157
9F - 158
A0 - 159
A1 - 160
A2 - 161
A3 - 162
A4 - 163
A5 - 164
A6 - 165
A7 - 166
A8 - 167
A9 - 168
AA - 169
AB - 170
AC - 171
AD - 172
AE - 173
AF - 174
B0 - 175
B1 - 176
B2 - 177
B3 - 178
B4 - 179
B5 - 180
B6 - 181
B7 - 182
B8 - 183
B9 - 184
BA - 185
BB - 186
BC - 187
BD - 188
BE - 189
BF - 190
C0 - 191
C1 - 192
C2 - 193
C3 - 194
C4 - 195
C5 - 196
C6 - 197
C7 - 198
C8 - 199
C9 - 200
CA - 201
CB - 202
CC - 203
CD - 203
CE - 204
CF - 205
D0 - 206
D1 - 207
D2 - 208
D3 - 209
D4 - 210
D5 - 211
D6 - 212
D7 - 213
D8 - 214
D9 - 215
DA - 216
DB - 217
DC - 218
DD - 219
DE - 220
DF - 221
E0 - 222
E1 - 223
E2 - 224
E3 - 225
E4 - 226
E5 - 227
E6 - 228
E7 - 229
E8 - 230
E9 - 231
EA - 232
EB - 233
EC - 234
EE - 235
EF - 236
F0 - 237
F1 - 238
F2 - 239
F3 - 240
F4 - 241
F5 - 242
F6 - 243
F7 - 244
F8 - 245
F9 - 246
FA - 247
FB - 248
FC - 249
FE - 250
FF - 251
0101 - 252
0201 - 253
0301 - 254
0401 - 255
0501 - 256
0601 - 257
0701 - 258
0801 - 259
0901 - 260
0A01 - 261
0B01 - 262
0C01 - 263
0D01 - 264
0E01 - 265
0F01 - 266
1001 - 267
1101 - 268
1201 - 269
1301 - 270
1401 - 271
1501 - 272
1601 - 273
1701 - 274
1801 - 275
1901 - 276
1A01 - 277
1B01 - 278
1C01 - 279
1D01 - 280
1E01 - 281
1F01 - 282
2001 - 283
2101 - 284
2201 - 285
2301 - 286
2401 - 287
2501 - 288
2601 - 289
2701 - 290
2801 - 291
2901 - 292
2A01 - 293
2B01 - 294
2C01 - 295
2D01 - 296
2E01 - 297
2F01 - 298
3001 - 299
3101 - 300
3201 - 301
3301 - 302
3401 - 303
## Post #26
- Username: BxNight
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Dec 18, 2009 11:52 am
- Post datetime: 2010-02-19T21:33:56+00:00
- Post Title: Re: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

I will also be posting values for other things in this section to help other users get the hang of this. Here are the letter values used for the Wrestlers names.

Letter Values
-----------------------
HEX  Letter

20 = space
41 = A
42 = B
43 = C
44 = D
45 = E
46 = F
47 = G
48 = H
49 = I
4A = J
4B = K
4C = L
4D = M
4E = N
4F = O
50 = P
51 = Q
52 = R
53 = S
54 = T
55 = U
56 = V
57 = W
58 = X
59 = Y
5A = Z
61 = a
62 = b
63 = c
64 = d
65 = e
66 = f
67 = g
68 = h
69 = i
6A = j
6B = k
6C = l
6D = m
6E = n
6F = o
70 = p
71 = q
72 = r
73 = s
74 = t
75 = u
76 = v
77 = w
78 = x
79 = y
7A = z
80 = À
81 = Á
82 = Â
83 = Ã
84 = Ä
85 = Å
86 = Æ
87 = Ç
88 = È
89 = É
8A = Ê
8B = Ë
8C = Ì
8D = Í
8E = Î
8F = Ï
90 = Ð
91 = Ñ
92 = Ò
93 = Ó
94 = Ô
95 = Õ
96 = Ö
97 = Š
98 = Ø
99 = Ù
9A = Ú
9B = Û
9C = Ü
9D = Ý
9E = Þ
E0 = à
E1 = á
E2 = â
E4 = â
F0 = ì
ED = í
EF = î
F6 = ö
FC = ù
FA = ú
FB = û
30 = 0
31 = 1
32 = 2
33 = 3
34 = 4
35 = 5
36 = 6
37 = 7
38 = 8
39 = 9
21 = !
22 = "
23 = #
24 = $
25 = %
26 = &
27 = '
28 = (
29 = )
2A = *
2B = +
2C = ,
2D = -
2E = .
2F = /
3A = :
3B = ;
3C = <
3D = =
3E = >
3F = ?
40 = @
5B = [
5C = ¥
5D = ]
5E = ^
5F = _
60 = ®
7B = {
7C = |
7D = }
7E = ~
01 = †
02 = ‡
03 = Œ
04 = œ
05 = ¡
06 = ¿
07 = ¤
08 = §
09 = ¶
0A = ª
0B = ‰
0C = ¥
0D = €
0E = ¢
10 = µ
10 = µ
11 = °
12 = ß
## Post #27
- Username: nikethebike
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 24, 2010 1:57 pm
- Post datetime: 2010-05-08T12:30:49+00:00
- Post Title: Re: Smackdown Vs. Raw 2010 chEtc.pac file tutorial Part 1

A little note:
Show at 0x010 must be repeated four times after eachother. Atleast on the PS2.
Thanks for the tutorial!
