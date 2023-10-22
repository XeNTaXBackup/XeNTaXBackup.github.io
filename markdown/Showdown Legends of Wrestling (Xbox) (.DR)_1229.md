## Post #1
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-05-10T12:54:50+00:00
- Post Title: Showdown: Legends of Wrestling (Xbox) (.DR)

Lots of people @ NMZ have been begging me 2 ask you about LoW textures so I figure we could give it a shot. Hopefully you guys can whip up another .bms script like you did with wm21  
[WRESTHED.zip](https://xentaxbackup.github.io/file/218_WRESTHED.zip)
## Post #2
- Username: Online_Dude
- Rank: beginner
- Number of posts: 20
- Joined date: Wed May 11, 2005 5:16 am
- Post datetime: 2005-05-11T21:01:31+00:00
- Post Title: Showdown: Legends of Wrestling (Xbox) (.DR)

Hey I know you guys banned the dude that wanted these low files but I wouldnt mind messing with these files myself. So if anyone could extract files from this format and possible import back in the game. No rush or anything Im just curious about this since my brother has this game.

~Thanx Dudes xentax rocks I extracted a bunch of images from some of my pc games!
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-12T07:47:18+00:00
- Post Title: Showdown: Legends of Wrestling (Xbox) (.DR)

Well, the file containes chunks of 4096 sized .map files, saved one after the other. 

```
uint32{4}	Dimension2 (64)
uint32{4}	Unknown (0xFFFFFF)
uint32{4}	Length of filename string (FL) 
string{FL}	null-terminated string, padded with 0xCC to fill up to FL bytes
uint32{4}	Unknown
uint32{4}	Unknown
uint32{4}	Unknown (0x8008)
uint32{4}	Unknown (0x0)
uint16{2}	Unknown (0x0c01)
string{4}	null-terminated string ("PAD")
Data		file data

```


If you multiply Dimension1 * Dimension2 you get the file size of the whole file (4096). Coincidence?
## Post #4
- Username: Online_Dude
- Rank: beginner
- Number of posts: 20
- Joined date: Wed May 11, 2005 5:16 am
- Post datetime: 2005-05-12T10:12:40+00:00
- Post Title: Showdown: Legends of Wrestling (Xbox) (.DR)

Thanks for checking it out I'm not sure what you mean. I guess you were saying you couldnt do anything with that file so I decided 2 dig up this game and try another file if you feel like looking at it. If I can figure out how to transfer files over from my xbox that is...
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-12T12:55:55+00:00
- Post Title: Showdown: Legends of Wrestling (Xbox) (.DR)

Oh yes, I could create a script, no problem. Just did not have the time yet.   

But an additional file would be handy, yes.
## Post #6
- Username: Online_Dude
- Rank: beginner
- Number of posts: 20
- Joined date: Wed May 11, 2005 5:16 am
- Post datetime: 2005-05-12T13:49:52+00:00
- Post Title: Showdown: Legends of Wrestling (Xbox) (.DR)

Really!? You guys are the best I think I will tell all my friends about this place once again thanks! I took a pic of one of the directorys. I dunno maybe it could be some help

I would love to get my hands on these costumes *drools over classic wrestling attires*

---------
I zipped up 3 .DR files  I hope I did this right

[http://s26.yousendit.com/d.aspx?id=3NJB ... DGLA41CB5O](http://s26.yousendit.com/d.aspx?id=3NJBS7JF650342YLDGLA41CB5O)
## Post #7
- Username: Online_Dude
- Rank: beginner
- Number of posts: 20
- Joined date: Wed May 11, 2005 5:16 am
- Post datetime: 2005-05-18T18:35:58+00:00
- Post Title: Showdown: Legends of Wrestling (Xbox) (.DR)

Couldnt figure out a script? Thats ok I guess
## Post #8
- Username: XTC
- Rank: Banned
- Number of posts: 23
- Joined date: Wed Apr 27, 2005 10:21 am
- Post datetime: 2005-05-20T22:46:04+00:00
- Post Title: Showdown: Legends of Wrestling (Xbox) (.DR)

come on guy's me and my mate are desperate for these.
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-21T00:04:45+00:00
- Post Title: Showdown: Legends of Wrestling (Xbox) (.DR)

> Reply from Online_Dude
>
> Couldnt figure out a script? Thats ok I guess

I have just been too busy with other stuff...
## Post #10
- Username: Online_Dude
- Rank: beginner
- Number of posts: 20
- Joined date: Wed May 11, 2005 5:16 am
- Post datetime: 2005-05-21T04:41:10+00:00
- Post Title: Showdown: Legends of Wrestling (Xbox) (.DR)

Thats cool dude Whenever you feel like it is fine with me I can wait
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-21T09:16:38+00:00
- Post Title: Showdown: Legends of Wrestling (Xbox) (.DR)

Okay here's the script. This will extract all the .MAP files (I assume they are single files, with headers that also include their own name). 

```
GoTo EOF 0 ;
SavePos END 0 ;
GoTo CP 0 ;
Do ;
Set Offset Long CP ;
Get Width Long 0 ;
Get Heigth Long 0 ;
Set FileSize Long Heigth ;
Math FileSize *= Width ;
Get Unknown Long 0 ;
Get NameSize Long 0 ;
Get IDName String 0 ;
Get FileName String 0 ;
Log FileName Offset FileSize 0 0 ;
Math CP += FileSize ;
GoTo CP 0 ;
While CP < END ;

```


I also pre-compiled the script for you.
[dr.zip](https://xentaxbackup.github.io/file/241_dr.zip)
## Post #12
- Username: mel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 18, 2007 9:41 am
- Post datetime: 2007-07-20T02:20:27+00:00
- Post Title: Showdown: Legends of Wrestling (Xbox) (.DR)

I know its old but can someone reup them 3 dr files.
## Post #13
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2007-08-09T12:02:56+00:00
- Post Title: Showdown: Legends of Wrestling (Xbox) (.DR)

does this script work with the ps2 version of the game also?
