## Post #1
- Username: alientech
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Apr 03, 2010 8:23 pm
- Post datetime: 2013-05-24T12:58:20+00:00
- Post Title: Kamen Rider Battride war EMD model. (PS3)

Hi everyone. Now, I'm trying to research about the model engine from this game. I read all around the forum about emd file (Resident Evil 1 and 2).
I tried some tools for emd files but won't work for this game. So, Someone can help me learn about this file?

Here a model from the game : [https://docs.google.com/file/d/0Bx4rRNA ... sp=sharing](https://docs.google.com/file/d/0Bx4rRNAZOeSYdFVyT1FqWGhPMGs/edit?usp=sharing)

Thank you.
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-05-24T15:01:15+00:00
- Post Title: Kamen Rider Battride war EMD model. (PS3)

Just briefly looked at sample file, there will be a little problem with uvs I guess.
[bike.jpg](https://xentaxbackup.github.io/file/6426_bike.jpg)
## Post #3
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2013-05-24T17:47:04+00:00
- Post Title: Kamen Rider Battride war EMD model. (PS3)

Funny that someone else was looking into the format at the same time, considering I started last night. And have got to [more or less the same point](http://img.photobucket.com/albums/v336/RandomTalkingBush/KRBW-WizardBikeModelPiece.png). I've gotten an understanding of reading bones (not pictured), vertex points and polygons, but no UV mapping or bone weights yet.

So yeah, I support this, as I know a couple of friends of mine who would love to have these models.
## Post #4
- Username: alientech
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Apr 03, 2010 8:23 pm
- Post datetime: 2013-05-24T17:47:59+00:00
- Post Title: Kamen Rider Battride war EMD model. (PS3)

> Reply from zaramot
>
> Just briefly looked at sample file, there will be a little problem with uvs I guess.

Oh wow, How can I read EMD files?
Hmmm.... Texture files isn't include in an EMD file. It seperate to dds files.

Here texture files for this model : [https://docs.google.com/file/d/0Bx4rRNA ... sp=sharing](https://docs.google.com/file/d/0Bx4rRNAZOeSYNFE1M0dhXzAyRVk/edit?usp=sharing)
## Post #5
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2013-05-24T17:58:36+00:00
- Post Title: Kamen Rider Battride war EMD model. (PS3)

Also if it helps with setting up the UV mapping, the models are for the most part the exact same as the ones from any of the Climax Heroes Wii games.
## Post #6
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-05-24T21:24:41+00:00
- Post Title: Kamen Rider Battride war EMD model. (PS3)

No, UV's are there. I mean, it could be a little problematic to parse them for each mesh part.
[bike_2.jpg](https://xentaxbackup.github.io/file/6427_bike_2.jpg)
## Post #7
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2013-05-24T21:36:40+00:00
- Post Title: Kamen Rider Battride war EMD model. (PS3)

Wait, why did I say that earlier? What I meant to say was "If it helps with finding the UV mapping". Eh, doesn't matter.

Where in particular are the UV offsets stored in the file, so I can learn about the format some more? I'm still kinda new at this, after all.
## Post #8
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-05-24T21:47:49+00:00
- Post Title: Kamen Rider Battride war EMD model. (PS3)

UV's stored at the end of the file, it's a big section of data you can't miss it - it starts with ffff then 4 bytes of uv's values (uv's stored as half-floats) Here's pic there's offset to UV's stored in this sample file, the only file I have:)
[offset.jpg](https://xentaxbackup.github.io/file/6429_offset.jpg)
## Post #9
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2013-05-24T21:50:17+00:00
- Post Title: Kamen Rider Battride war EMD model. (PS3)

Aaaah, I see now. Didn't think they'd be stored as half-float values, no wonder I didn't spot them. Thanks!
## Post #10
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-05-24T21:58:52+00:00
- Post Title: Kamen Rider Battride war EMD model. (PS3)

You're welcome. I'm glad to help, if I can
## Post #11
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2013-05-25T04:22:43+00:00
- Post Title: Kamen Rider Battride war EMD model. (PS3)

Yeah, I see what you mean about the UV mapping. Still, it's a learning experience figuring it out.
## Post #12
- Username: alientech
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Apr 03, 2010 8:23 pm
- Post datetime: 2013-05-26T16:47:53+00:00
- Post Title: Kamen Rider Battride war EMD model. (PS3)

Anything update?
## Post #13
- Username: alientech
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Apr 03, 2010 8:23 pm
- Post datetime: 2013-07-22T09:18:42+00:00
- Post Title: Kamen Rider Battride war EMD model. (PS3)

Nothing update? No one can help?
## Post #14
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2013-07-23T04:44:15+00:00
- Post Title: Kamen Rider Battride war EMD model. (PS3)

I ended up getting caught up in other things, so no progress was made from me at least.
## Post #15
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2013-07-25T00:31:43+00:00
- Post Title: Kamen Rider Battride war EMD model. (PS3)

> Reply from RandomTBush
>
> Also if it helps with setting up the UV mapping, the models are for the most part the exact same as the ones from any of the Climax Heroes Wii games.

Only a Few are UV Wise (like OOO and Eternal)
(they are actually more closer to the Gambaride Arcade game (Witch i hope get dumped one day)


But sadly Wizard is not complete in Super Climax Heroes (Missing Water and Land Dragon Plus All-dragon) and Beast is included to the Roster(I have the Infinity Style & Hyper Beast files too if anyone wants them)

I'd Really like to have the Models form this!
## Post #16
- Username: aaiki14
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 09, 2011 5:05 pm
- Post datetime: 2013-07-25T01:20:39+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

what tools needed ?
how to export them to 3ds max or other 3d modelling program?
## Post #17
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2013-07-25T01:55:38+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

Is there a MaxScript? if so i'd like to see it :O INFINITY! Pleaze?

[http://www.mediafire.com/?fqjjuv9hdmnlbhq](http://www.mediafire.com/?fqjjuv9hdmnlbhq)

Here is Wizard (Infinity Style) "DLC" With Textures (DDS)

..._W00_... is his "Axcalibur" Weapon
## Post #18
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2013-08-08T21:39:52+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

Anything Yet :V?

I'd Really like a way to get the models Please ):
## Post #19
- Username: alientech
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Apr 03, 2010 8:23 pm
- Post datetime: 2013-12-29T13:43:38+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

Nothing update?
No one can help me?
## Post #20
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-02-28T14:11:57+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

Worthwhile bump ahoy!



I've written a MAXScript that gets the models from this game now -- polygons, vertex points, UV mapping and bone structures. Only thing it's missing is importing the bone IDs. I've located what I think are the bone weights (four bytes that equal 255 when added together, just like No More Heroes: Heroes' Paradise had), I just haven't located the bone IDs. That, and the materials, but it's easy enough to apply textures to models.

Once it's finished, I'll upload it for others to use, even if it is a little messy/clumsy in spots.
## Post #21
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-02-28T20:43:34+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

bone ids? you mean parent ids? usually a game doesn't have bone ids, it's just an array of joints from 0 to N - 1 joints and there is another array somewhere that contains parenting info. or do you mean joint mapping data?

EDIT:
oh nevermind, i think i get what you mean now: u meant blend indices. blend indices are typically single bytes as well, though i remember RE6 PS3 had half-float blendindices. also, dynasty warriors games use blend indices that must be divided by three (for god knows what odd reason lmao), so sometimes it's not obvious, but 90% of the time they are simple bytes. also, remember that a lot of times the blend indices direct from the vertex buffer won't make sense because of joint mapping.
## Post #22
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-03-01T21:20:27+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

> Reply from howfie
>
> also, dynasty warriors games use blend indices that must be divided by three (for god knows what odd reason lmao), so sometimes it's not obvious, but 90% of the time they are simple bytes.Sounds just like the way Telltale stores 'em in their games.

Either way, it seems to be stored as weight percentage 1/index 1/weight percentage 2/index 2/etc. (one byte each), but the IDs probably have a cross-reference to 'em, as moving one bone moves a different part for each polygon group. Similarly to how the one Virtua Fighter 5 script / Project Diva from elsewhere on this forum is set up.
## Post #23
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2014-03-14T22:20:33+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

Ahhhh Den-Bird Would it be possible to get a version of the Script that just imports the meshes? what i need ATM dose not require Rigging 

I hope the format is the Same in the Sequel comming out in June :V
## Post #24
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-06-27T14:15:27+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

I'm still working on trying to fix up the last few things with the MaxScript (need to figure out where the UV size is read from, and where the proper node IDs are stored), but the model format in Battride War II's the exact same as the first game's.



(Don't mind the missing shoulder pad piece, I've already fixed that since I took this pic).

(EDIT: Fixed the UV mapping problem. Once I figure out how to fix the rigging, I'll be releasing the script here!)
## Post #25
- Username: Maspayno
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 16, 2009 6:13 pm
- Post datetime: 2014-06-29T04:54:25+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

> Reply from RandomTBush
>
> 
Once I figure out how to fix the rigging, I'll be releasing the script here!)
how if you can't fix the rigging ? 
i hope the script still  will be released
## Post #26
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-06-29T20:35:27+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

> Reply from Maspayno
>
> RandomTBush wrote:
Once I figure out how to fix the rigging, I'll be releasing the script here!)
how if you can't fix the rigging ? 
i hope the script still  will be releasedI'll figure it out soon enough. I found what I believe are the proper node IDs, but for whatever reason any polygon group with more than two bones attributed to it is still broken. But that's the last thing I need to fix now.
## Post #27
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-07-03T03:32:42+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

My model-importing script for both Kamen Rider: Battride War games has finally been finished! Just to keep everything in one place, here's the file-exporting QuickBMS script for Battride War II's NativePS.NCAT, instead of being in the previous post:

```
get FILES long
get UNKNOWN long
get UNKNOWN long
get UNKNOWN long

for i = 0 < FILES

   get OFFSET long
   get BLOCKSIZE long
   get FILESIZE long
   getdstring NAME 0x74
   log NAME OFFSET FILESIZE

next i

endfunction
```


And here's a link to the MaxScript:
[Download MaxScript](https://mega.nz/#!zoIFgTQT!y0X5Zl2Q3gQKSE7gYgxUhqTxpMrZyEnu2z_va4ZCrtU)
[Download NativePS.ncat QuickBMS Script](https://mega.nz/#!OlwHxRzZ!83cc74YCkBELq_1-YBbtAjAMtRwcdvwfDJ2odDX4gTU)

Please inform me if there are any rigging or texture problems with this script, and if you use it, I wouldn't mind some thanks for going through all this effort to write it up. Especially the node ID crap, that took me way too long to figure out... Anyhoo, enjoy! Just don't say I never do anything for anyone. 

(EDIT 08/27/14: Added an alternative version for 3DS Max 2012+.)
## Post #28
- Username: Maspayno
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 16, 2009 6:13 pm
- Post datetime: 2014-07-03T10:58:33+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

> Reply from RandomTBush
>
> 
And here's a link to the MaxScript:
http://www.mediafire.com/?vtw85p1haf2h0hl

Please inform me if there are any rigging or texture problems with this script, and if you use it, I wouldn't mind some thanks for going through all this effort to write it up. Especially the node ID crap, that took me way too long to figure out... Anyhoo, enjoy! Just don't say I never do anything for anyone.

thank you very much ...
will try out soon
## Post #29
- Username: Misawa Hajime
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Aug 23, 2014 3:23 pm
- Post datetime: 2014-08-26T01:21:21+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

> Reply from RandomTBush
>
> My model-importing script for both Kamen Rider: Battride War games has finally been finished! Just to keep everything in one place, here's the file-exporting QuickBMS script for Battride War II's NativePS.NCAT, instead of being in the previous post:



And here's a link to the MaxScript:
http://www.mediafire.com/?vtw85p1haf2h0hl

Please inform me if there are any rigging or texture problems with this script, and if you use it, I wouldn't mind some thanks for going through all this effort to write it up. Especially the node ID crap, that took me way too long to figure out... Anyhoo, enjoy! Just don't say I never do anything for anyone. 

(EDIT 07/04/14: Added a fix to prevent crashing when material has no texture applied to it.)

thanks...
## Post #30
- Username: Misawa Hajime
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Aug 23, 2014 3:23 pm
- Post datetime: 2014-08-27T02:26:42+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

> Reply from RandomTBush
>
> Please inform me if there are any rigging or texture problems with this script, and if you use it, I wouldn't mind some thanks for going through all this effort to write it up. Especially the node ID crap, that took me way too long to figure out... Anyhoo, enjoy! Just don't say I never do anything for anyone.
[rigproblem.png](https://xentaxbackup.github.io/file/7745_rigproblem.png)
## Post #31
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2014-08-27T02:32:31+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

I didn't have that rigging Problem at all...
## Post #32
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-08-27T16:25:14+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

[https://dl.dropboxusercontent.com/u/278 ... MD_2012.ms](https://dl.dropboxusercontent.com/u/27874399/KamenRiderBattrideWar_EMD_2012.ms)

The guys who updated 3DS Max to 2012 and onwards must be drunk. The reason why the script was glitching up on you is 3DS MAX 2012+ CAN'T COUNT. It thinks 10 comes immediately after 1 (and 2 comes after 19 -- I'm not kidding!), and it paid absolutely no attention to the ordering I set up in the MaxScripts. So I added a three-digit number to the beginnings of the bone names. And that fixed it. That is seriously the only change I made. And my other scripts have the same issues.

Be right back, I'm gonna find the nearest manatee to plunge my fist into the schnoz of.
## Post #33
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2014-08-27T17:08:56+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

It's like Windows' Sorting feature.
(Is this something some one thought was cool?)
It's thinks that:
1
10
100
1000
2
20
ect,
are the sane numbers where as
001
002
003
004
ect.
009
010
It's Treating Numbers Alphanumarical 8V
## Post #34
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-08-27T17:12:11+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

That's exactly it, yep.

(EDIT: Only... Thinking about it now, it's been alphabetizing everything while paying no attention to the order the bones are created, which would explain why inserting the three-digit number at the beginning fixed it.)
## Post #35
- Username: LarsMasters
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Aug 25, 2014 10:30 am
- Post datetime: 2014-08-29T07:48:19+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

Will this new script fix the stage too?
## Post #36
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-08-31T18:42:18+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

> Reply from LarsMasters
>
> Will this new script fix the stage too?I thought I already fixed that? Which models in particular are you trying to import?
## Post #37
- Username: LarsMasters
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Aug 25, 2014 10:30 am
- Post datetime: 2014-09-04T15:51:35+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

Like Mark XVII (was it name?), BW1 Final, BW2 Final, School, Snow Mountain, Underground, & Futo Tower stage parts for example? It has an error while i try to port it to MAX & some of the stage are in a wrong textures
## Post #38
- Username: Fileking
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Aug 05, 2015 7:41 am
- Post datetime: 2015-08-04T23:49:00+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

So im a noob at this .. every  time i try  to get the files  with  quick bms and the script  you  gave... it  says error
## Post #39
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-08-05T04:35:30+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

The input file shouldn't be the script file, it should be the game's NativePS.NCAT file.
## Post #40
- Username: Fileking
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Aug 05, 2015 7:41 am
- Post datetime: 2015-08-07T10:20:01+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

> Reply from RandomTBush
>
> The input file shouldn't be the script file, it should be the game's NativePS.NCAT file.
 ok im so lost  please help me explain this
## Post #41
- Username: LarsMasters
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Aug 25, 2014 10:30 am
- Post datetime: 2016-03-07T03:46:12+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

Okay the PS3 Iso is out
## Post #42
- Username: franada
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jun 07, 2018 2:13 pm
- Post datetime: 2018-06-29T11:16:51+00:00
- Post Title: Re: Kamen Rider Battride war EMD model. (PS3)

Why 3ds max script have error when I try to import a stage map emd?

I got those error

-unknown system exception
-vertex index in face out of range
-undefined to type: point3

And why the texture are like more grey that it should be ?
