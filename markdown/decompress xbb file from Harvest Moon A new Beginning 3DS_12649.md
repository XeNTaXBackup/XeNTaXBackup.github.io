## Post #1
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-02-26T14:19:47+00:00
- Post Title: decompress xbb file from "Harvest Moon A new Beginning 3DS"?

Hey Guys, 

today I decrypted a Nintendo 3DS Game and found MAAAAAANY scripts and code-related stuff as plain text in it.
The Game I've decrypted was "Harvest Moon A new Beginning" for 3DS.
But the Game contains some xbb-files which are encrypted or compressed and I don't know how to decrypt/decompress them.

I've uploaded some and hope, that someone could help me with it.
I want do decrypt/decompress them. I think, they're compressed/encrypted on the same way.

Would be great if you can help me with it 
[GameData.rar](https://xentaxbackup.github.io/file/8762_GameData.rar)
## Post #2
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-02-28T10:40:12+00:00
- Post Title: decompress xbb file from "Harvest Moon A new Beginning 3DS"?

Is someone able to help me with this? :/

Someone sent me a txt-file with informations about xbb files from an older Harvest Moon Game.
[https://www.dropbox.com/s/56ertxekzzkqw ... n.txt?dl=0](https://www.dropbox.com/s/56ertxekzzkqwdn/xbb_documentation.txt?dl=0)

Another documentation
[https://gist.github.com/andibadra/2632d ... xbb_3ds-md](https://gist.github.com/andibadra/2632d06a7066224ae08d#file-9_format_xbb_3ds-md)




I really want to unpack and repack this files
## Post #3
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-02-28T13:15:00+00:00
- Post Title: decompress xbb file from "Harvest Moon A new Beginning 3DS"?

Using the links that you gave me, i wrote this algorithm to extract xbb files:

```

IDString 0 XBB;
GoTo 4 0;
Get NFiles Long 0;
GoTo 32 0;

For T = 1 To NFiles;
Get FileOffset Long 0;
Get FileSize Long 0;
Get FileNameOffset Long 0;
Get FileID Long 0;

SavePos HeaderOffset 0;
GoTo FileNameOffset 0;

Get FileName String 0;

Log FileName FileOffset FileSize 0 0;
GoTo HeaderOffset 0;
Next T;

```


The extracted files have the header PAPA and I developed this code to extract them.

```

IDString 0 PAPA;

GoTo 8 0;

Get HeaderOffset Long 0;
Get HeaderSize Long 0;
Get NFiles Long 0;

Math NFiles -= 1;

For T = 1 To NFiles;

Get FileOffset Long 0;
SavePos HeaderCurOffset 0;

Get NextFileOffset Long 0;

Set FileSize Long NextFileOffset;
Math FileSize -= FileOffset;

GoTo HeaderCurOffset 0;

Log T FileOffset FileSize 0 0;

Next T;

```


From what I've seen, this is probably a file with information that only the game knows. The extracted files seem to have a pattern, but it depends on the file. If you are interested we can analyze the extracted files.
## Post #4
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-02-28T22:19:34+00:00
- Post Title: decompress xbb file from "Harvest Moon A new Beginning 3DS"?

Oh nice! I will try it! 
I need quickbms for this, i guess?

Yea, would be great if you could help me with analyzing the extracted files.
It would be VERY helpful
## Post #5
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-03-01T00:44:11+00:00
- Post Title: decompress xbb file from "Harvest Moon A new Beginning 3DS"?

I used multiex commander to extract the files. May i ask for what purpose do you want to extract the files? Do you want to repack them?
## Post #6
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-01T01:39:54+00:00
- Post Title: decompress xbb file from "Harvest Moon A new Beginning 3DS"?

> Reply from ekanspt
>
> I used multiex commander to extract the files. May i ask for what purpose do you want to extract the files? Do you want to repack them?

I want to edit and repack them, yes.
And If possible, add NEW FILES to the xbb-files!

Uploaded the Msg.xbb which should contain all Strings etc. Could you make the files "editable"?

[http://filehorst.de/d/bBFxHsvs](http://filehorst.de/d/bBFxHsvs)
## Post #7
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-01T11:19:33+00:00
- Post Title: decompress xbb file from "Harvest Moon A new Beginning 3DS"?

btw. I was able to modify some script-related things and to compile it back to the Game!  It works!
[http://abload.de/img/modixmuwz.jpg](http://abload.de/img/modixmuwz.jpg)
## Post #8
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-03-01T15:35:07+00:00
- Post Title: decompress xbb file from "Harvest Moon A new Beginning 3DS"?

So the xxb files you can extract with multiex commander. Do you know how to do that?

For the extracted files, i developed a simple program to extract them. Please note that I only take in consideration the Msg.xxb file, wich contains strings. Maybe the PAPA files have a standard format, but I don't have figured it out.

To extract the files, just drag and drop the PAPA file in the executable, or on the command line write 3ds.exe <inputFile>.

[https://mega.co.nz/#!iZ5yBZyY!MjgGLb8ii ... T8eHRR6qv4](https://mega.co.nz/#!iZ5yBZyY!MjgGLb8iiTsFfEHtsXN0E2VfFl07YeYYAT8eHRR6qv4)
## Post #9
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-01T16:03:13+00:00
- Post Title: decompress xbb file from "Harvest Moon A new Beginning 3DS"?

> Reply from ekanspt
>
> So the xxb files you can extract with multiex commander. Do you know how to do that?

For the extracted files, i developed a simple program to extract them. Please note that I only take in consideration the Msg.xxb file, wich contains strings. Maybe the PAPA files have a standard format, but I don't have figured it out.

To extract the files, just drag and drop the PAPA file in the executable, or on the command line write 3ds.exe <inputFile>.

https://mega.co.nz/#!iZ5yBZyY!MjgGLb8ii ... T8eHRR6qv4

Yes, I know how to extract the xbb-files with multiex commander 
Did it already and tried your 3ds.exe for decrypting "PlayerAvatarData.xbb/PlayerBodyData/" and got a clean txt!
it seems to work for all the papa-files.
[https://hackpad.com/PlayerBodyData.papa-XYdnMUGrVrv](https://hackpad.com/PlayerBodyData.papa-XYdnMUGrVrv)

This is really great!  

Are you able to make a papa-repacker and xbb-repacker to add new things to the game?
Want to add a new AvatarBody (Character Outfit INgame) to the game. I have to add new lines to the papa-files like this one

> PlayerBody
>
> CUSTOM_OUTFIT
>
> b_999


EDIT: For some pp-files, it seems that the 3ds.exe don't decrypt all needed infos. 
In AvatarBodyData, it forgets the Object Name
## Post #10
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-03-01T16:19:53+00:00
- Post Title: decompress xbb file from "Harvest Moon A new Beginning 3DS"?

It may work for all PAPA files but some have additional data that isn't considered in extraction. 

For instance in FlowerList.xxb/FlowerData extracts (i think):

```
FLOWER_GROUP_00
ITEM_TULIP

```


But it has some more information:
ITEM_RED_ROSE
ITEM_GARBERA

So as I said, I think that it extracts all the information from Msg.xbb PAPA files, but not from others. If you want I can help you, but you have to take a look with me to this files.

I think that yes, I can make the repackers, I will start with the xbb repacker.
## Post #11
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-01T16:22:09+00:00
- Post Title: decompress xbb file from "Harvest Moon A new Beginning 3DS"?

> Reply from ekanspt
>
> It may work for all PAPA files but some have additional data that isn't considered in extraction. 

For instance in FlowerList.xxb/FlowerData extracts (i think):
Code: Select allFlowerGroup
FLOWER_GROUP_00
ITEM_TULIP


But it has some more information:
ITEM_RED_ROSE
ITEM_GARBERA

So as I said, I think that it extracts all the information from Msg.xbb PAPA files, but not from others. If you want I can help you, but you have to take a look with me to this files.

I think that yes, I can make the repackers, I will start with the xbb repacker.

Yes, I tried this with AvatarBodyData already and it doesn't extract all the informations.
Sure, tell me what I have to do
## Post #12
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-03-01T16:32:35+00:00
- Post Title: decompress xbb file from "Harvest Moon A new Beginning 3DS"?

So from the image that you posted, there are some script files associated with xbb/papa files? I don't know anything from 3DS file format, so I need the much information that I can get.

If you can post one of the scripts and the corresponding xbb file it would be a great help.
## Post #13
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-01T16:34:12+00:00
- Post Title: decompress xbb file from "Harvest Moon A new Beginning 3DS"?

> Reply from ekanspt
>
> So from the image that you posted, there are some script files associated with xbb/papa files? I don't know anything from 3DS file format, so I need the much information that I can get.

If you can post one of the scripts and the corresponding xbb file it would be a great help.

Yes, some Scripts are associated with this files.

I uploaded a example 

The Game is written in Squirrel Language with uncompiled scripts (.nut)
[SceneGameInitSetting.rar](https://xentaxbackup.github.io/file/8780_SceneGameInitSetting.rar)
## Post #14
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-03-01T16:37:57+00:00
- Post Title: decompress xbb file from "Harvest Moon A new Beginning 3DS"?

Can you post here the AvatarBodyData file?
## Post #15
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-01T17:09:35+00:00
- Post Title: decompress xbb file from "Harvest Moon A new Beginning 3DS"?

> Reply from ekanspt
>
> Can you post here the AvatarBodyData file?
Could you upload the source, too? want to see how this works :3
[PlayerBodyData.rar](https://xentaxbackup.github.io/file/8781_PlayerBodyData.rar)
## Post #16
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-02T19:08:15+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

There's anothe Fileformat that I want to unpack/repack.
[http://3dbrew.org/wiki/ARC](http://3dbrew.org/wiki/ARC)
I've uploaded such a file

I also uploaded a Screenshot with much informations about this uploaded file.
[http://abload.de/img/exp27owr.jpg](http://abload.de/img/exp27owr.jpg)
Right now, there's only this viewer+exporter available for this file format, but not a unpacker/repacker or editor :/
It would be VERY useful if you can help me with this :>
[BustUp_WITCH.rar](https://xentaxbackup.github.io/file/8783_BustUp_WITCH.rar)
## Post #17
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-03-07T12:11:25+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

I was a little busy in this week, but i made an extractor for xbb files and i'm working on a repacker.

[https://mega.co.nz/#!bBxUEQYQ!3yuo36RtD ... saxSawXJoU](https://mega.co.nz/#!bBxUEQYQ!3yuo36RtDFJI3xxyoirMlk97YVrWX8b98saxSawXJoU)
## Post #18
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-07T13:04:48+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

> Reply from ekanspt
>
> I was a little busy in this week, but i made an extractor for xbb files and i'm working on a repacker.

https://mega.co.nz/#!bBxUEQYQ!3yuo36RtD ... saxSawXJoU

thank you :>
Would be cool if you can work on a repacker 
And for papa-files, We need to find a way to export ALL strings of every papa-file and a reencrypter or something to use the modified files.

EDIT: Extracting files works GREAT!
## Post #19
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-03-07T18:11:34+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

Here it is, i think that it does the trick.

Just drag and drop the extracted folder in the executable. Please note that it needs the _loading order file to exist and you can't change the number of files. Please take care with your original xbb file.

If you have the time, please confirm if it's all ok.

[https://mega.co.nz/#!nQJGWAzY!Pgz_zJtQs ... FNzXmj2ync](https://mega.co.nz/#!nQJGWAzY!Pgz_zJtQstcI346f5CVcmi52bO8-6MT9jFNzXmj2ync)
## Post #20
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-07T19:24:48+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

> Reply from ekanspt
>
> Here it is, i think that it does the trick.

Just drag and drop the extracted folder in the executable. Please note that it needs the _loading order file to exist and you can't change the number of files. Please take care with your original xbb file.

If you have the time, please confirm if it's all ok.

https://mega.co.nz/#!nQJGWAzY!Pgz_zJtQs ... FNzXmj2ync

Exported all files of Msg.xbb, changed something with Hex-Editor in one pp-file, repacked Msg.xbb.

All works! Changed things are visible ingame 
Now I need a pp-encrypter (decrypter that works on all files, not only msg)
## Post #21
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2015-03-08T11:28:56+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

Ok so I think I might have to respond:

ChrisX contacted me for making a XBB tool, PAPA tool and DARC tool.
I finished the XBB tool(just a lil' bug fix to do), currently working on PAPA and the DARC tool should be easy enough.

all those tools will support extraction, repacking and adding of new files also.

Just for lettin' ya know
-GY
## Post #22
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-03-08T13:59:27+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

Wonderful! 

Good luck
## Post #23
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-08T14:15:19+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

Can't wait for it °^° really want to recreate a 3DS Game :>
## Post #24
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-26T06:37:17+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

GovanifY said he is busy for the next three weeks and is possibly not able to help me with this tools :/
Could someone else help me with this, please?
## Post #25
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-04-11T23:05:29+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

/bumpitup
## Post #26
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-05-03T07:10:23+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

/bump again 

We really want to edit this files and without your help, we're not able to x_x
## Post #27
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2015-05-06T17:42:46+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

YES YES I KNOW I AM BUSY RIADUEOZDPOZPDUPZ8DË
Nah seriously I sended you sources of my tools as y'saw and still fucking busy SOOOOOOOOOOOOOOOOOOOOOOOOO
Sorry T_T
-GY
## Post #28
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-05-26T09:54:35+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

Still need help with this x_X
## Post #29
- Username: Katai
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 05, 2015 3:28 pm
- Post datetime: 2015-06-05T07:36:42+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

Thanks a whole ton for the XBB extractor.  It's been a huge boon in trying to modify Harvest Moon DS: Sunshine Islands.  Unfortunately, I'm not sure if the repacking is working as designed.  The rom itself seems to not like the replaced XBB file at all.  It's a pack of sprites, and the game simply doesn't render them (as if the files were missing).  I haven't even modified any of the files in the folder, and the rom won't take it.

Basically all I did was unpack the xbb, immediately repack the xbb, then copy the file into the rom data.  It looks like some of the headers before the data is different in the new xbb compared to the original, but I'll have to look up the xbb specifications to see what specifically got changed.
## Post #30
- Username: ubergeek77
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jun 11, 2015 11:04 am
- Post datetime: 2015-06-12T04:52:47+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

> Reply from GovanifY
>
> YES YES I KNOW I AM BUSY RIADUEOZDPOZPDUPZ8DË
Nah seriously I sended you sources of my tools as y'saw and still fucking busy SOOOOOOOOOOOOOOOOOOOOOOOOO
Sorry T_T
-GY

> Reply from ChrisX930
>
> Still need help with this x_X
Alright guys, where are we at on this?

GovanifY, surely school (at least that was my assumption) can't have you that busy anymore now that the summer has started, no? Hopefully you can lend a hand now. right!?   

Hmm.... What else could make this go by faster? Do you want me to pay you? I can totally pay you. Donations always make magic happen
## Post #31
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-06-21T09:19:34+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

I still need help with this files (extractor AND repacker) 
I've uploaded a XBB-File from another Game (should be the same format?)
The only difference: This game is japanese.
Title: Dragon Quest Monsters 2


please help us with this x-x

I've uploaded some of the xbb-files (they're a bit different than the Harvest Moon -xbb files.
[http://puu.sh/ix5ZX/e1411f8444.rar](http://puu.sh/ix5ZX/e1411f8444.rar)
## Post #32
- Username: ubergeek77
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jun 11, 2015 11:04 am
- Post datetime: 2015-09-03T05:34:00+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

So is this dead now? Is there nothing else we can do go figure this format out? From my testing, so long as you don't change the file size of the contents of the archive, everything works fine and nothing is broken. This must mean that the beginning and end offsets for each individual file are contained somewhere. And if we can find it and modify it, I think we should be able to get this working.

Sorry Chris. I remember trying to help with this months back and neither one of us had any luck. I hope you haven't given up yet, because there's a lot I'd like to do with this game.
## Post #33
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-09-05T17:06:41+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

> Reply from ubergeek77
>
> So is this dead now? Is there nothing else we can do go figure this format out? From my testing, so long as you don't change the file size of the contents of the archive, everything works fine and nothing is broken. This must mean that the beginning and end offsets for each individual file are contained somewhere. And if we can find it and modify it, I think we should be able to get this working.

Sorry Chris. I remember trying to help with this months back and neither one of us had any luck. I hope you haven't given up yet, because there's a lot I'd like to do with this game.

It isn't "dead", but I'm focusing a game translation at the moment.
I still need help with the xbb-format because GovanifY never finished it.
## Post #34
- Username: Z6n4
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 11, 2015 11:59 am
- Post datetime: 2015-09-11T04:07:36+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

Looks like you guys are working on Dragon Quest Monsters 2 3DS?  I think we should talk.
I dont use this forum often (at all, I signed up just to speak with you 2).

Check this out, post and we'll go from there.
Trying to keep this on the DL.
[https://gbatemp.net/threads/partial-tra ... nd.393956/](https://gbatemp.net/threads/partial-translation-project-dqm3d-terrys-wonderland.393956/)
## Post #35
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-09-11T21:14:24+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

> Reply from Z6n4
>
> Looks like you guys are working on Dragon Quest Monsters 2 3DS?  I think we should talk.
I dont use this forum often (at all, I signed up just to speak with you 2).

Check this out, post and we'll go from there.
Trying to keep this on the DL.
https://gbatemp.net/threads/partial-tra ... nd.393956/
nope, 
at the moment, we're working on Fire Emblem If
## Post #36
- Username: Z6n4
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 11, 2015 11:59 am
- Post datetime: 2015-09-14T22:18:53+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

Well we basically have it all done except repack in the SRC Files and im struggling.  Help would be greatly appreciated
## Post #37
- Username: NewZealandSolid
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 27, 2015 4:47 am
- Post datetime: 2015-09-16T09:05:38+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

> Reply from Katai
>
> Thanks a whole ton for the XBB extractor.  It's been a huge boon in trying to modify Harvest Moon DS: Sunshine Islands.  Unfortunately, I'm not sure if the repacking is working as designed.  The rom itself seems to not like the replaced XBB file at all.  It's a pack of sprites, and the game simply doesn't render them (as if the files were missing).  I haven't even modified any of the files in the folder, and the rom won't take it.

Basically all I did was unpack the xbb, immediately repack the xbb, then copy the file into the rom data.  It looks like some of the headers before the data is different in the new xbb compared to the original, but I'll have to look up the xbb specifications to see what specifically got changed.

Did you find out how to repack the files into Sunshine Islands again ? If so, please share.

I really need help with this, because the game just wont take the .xbb files again after extracting and repacking.
## Post #38
- Username: ubergeek77
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jun 11, 2015 11:04 am
- Post datetime: 2015-09-21T22:07:30+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

This post got pretty lengthy (we REALLY need spoiler tags, admins!!!), soooo:

TL;DR: The XBB extractor and repacker created by ekanspt both work well, you can change the file sizes of any of the resulting files so long as you don't add new ones. As for the PAPA files, I have the format fully figured out and I've attached example ones that I've created from scratch. At this time, we basically have everything we need to add/remove game text as we please, but a PAPA editor is almost necessary due to the sheer size of the default game ones. I hope someone can use my example files to create something like that.

My original post, plus edits:

As soon as we can repack .xbb files, we should all be on our way, as I've gained an understanding of PAPA (pp) files such that I can create my own from scratch rather easily without ruining the format of it. The last hurdle is the .xbb archive itself, and while it is somewhat similar in structure to the PAPA files it contains, it's more complicated, and there are checksums in place which is something I haven't completely figured out yet. As far as adding new text strings to a PAPA file, or a new PAPA file to an XBB, it isn't as simple as tacking something new at the end; both formats have offsets of where each file/string is located. So if you add something to the end, you'd need to add an offset for it, which will shift the location of each file by 4 bytes, which means you would need to add 4 bytes to every offset in the archive. Same goes for just modifying existing text string PAPA files - the offsets would have to be updated to reflect that change. Because archives can contain hundreds/thousands of files, this isn't an easy task to do by hand in a hex editor. A program could probably do it simply enough, but creating one is out of my skillset.

Here is documentation (it's been posted on this thread before as a link, but I'll include it for good measure), roughly Google Translated from Indonesian: [http://pastebin.com/kw5En1Tt](http://pastebin.com/kw5En1Tt)
I've added some of my own notes to it so that  it is easier to understand. I also forgot to note in the pastebin that filesizes are in little-endian (so 14 01 -> 01 14 -> 0x0140), offsets are not.

(I would have posted it inline, but for some strange reason Xentax doesn't support the spoiler tag).

Here are two example PAPA files that I made from scratch, using the documentation, that contain a single "Hello World"-like text string. There are two because the format between Harvest Moon ANB and Story of Seasons differs ever so slightly. In ANB, the variable name for the text string comes after the text string itself, whereas in Story of Seasons, it comes before the string, which is more logical. Note that I have no way to test these in game, so I have no way of knowing if I've made any errors, but I believe I've followed the documentation well enough to get these right:

[https://mega.nz/#!Kc4E0RIB!AM4UV-Ums2Dh ... pIJSZsWH18](https://mega.nz/#!Kc4E0RIB!AM4UV-Ums2DhakgNVTKQKlK_U83JjpSaTpIJSZsWH18)

I hope this helps, especially the documentation - it's very informative. I'll take a look at the format of an xbb archive when I have more free time, but for now this is all I've got.

EDIT:
It seems we already have an extractor:

> Reply from ekanspt
>
> I was a little busy in this week, but i made an extractor for xbb files and i'm working on a repacker.

https://mega.co.nz/#!bBxUEQYQ!3yuo36RtD ... saxSawXJoU

As well as a repacker:

> Reply from ekanspt
>
> Here it is, i think that it does the trick.

Just drag and drop the extracted folder in the executable. Please note that it needs the _loading order file to exist and you can't change the number of files. Please take care with your original xbb file.

If you have the time, please confirm if it's all ok.

https://mega.co.nz/#!nQJGWAzY!Pgz_zJtQs ... FNzXmj2ync

And ChrisX930 confirms repacking is functional:

> Reply from ChrisX930
>
> ekanspt wrote:Here it is, i think that it does the trick.

Just drag and drop the extracted folder in the executable. Please note that it needs the _loading order file to exist and you can't change the number of files. Please take care with your original xbb file.

If you have the time, please confirm if it's all ok.

https://mega.co.nz/#!nQJGWAzY!Pgz_zJtQs ... FNzXmj2ync

Exported all files of Msg.xbb, changed something with Hex-Editor in one pp-file, repacked Msg.xbb.

All works! Changed things are visible ingame 
Now I need a pp-encrypter (decrypter that works on all files, not only msg)

So now the question is - even if I don't change the number of files in the .xbb (which isn't necessary, because you can add text strings to the individual PAPA files), is changing the filesize by a significant amount alright so long as you modify the offsets/filesize information in the PAPA file accordingly? I'll try and test this myself, but that may be a very daunting task, as changing the offsets for each string won't be easy. I might need to find the smallest PAPA file and add a new string to that, and then modify a .nut script and call it from there.

If all that works, and I have a good feeling about it, then all we're really missing is a utility that will automate the process of creating PAPA files by changing the offsets of each file depending on how much you add/remove. Because the structure of a PAPA file isn't all that complex, I don't think making such a utility will be all that complicated.

EDIT2: I have great news! The xbb repacker seems to be working fine with files that are larger than the original, as I was able to overwrite a basically useless PAPA file (Event_SYSTEM_ITEMNAME, from Story of Seasons) with a copy of the intro story PAPA file, with some modifications so that I know it was actually changed, and then I changed the reference to the PAPA file in the .nut script accordingly. This is a relatively significant change in file size, as the new Msg.xbb is about 18kb larger than the original, and it still functions in-game. The next step is seeing if we can get it working with even bigger PAPA files, but since this is plenty large enough of a size increase to knock a pointer or two out of the way if the tool were hardcoded to a specific size, I'm pretty confident the .xbb repacker is working properly.

I did try throwing in my example PAPA file for good measure, but oddly I couldn't get it to load correctly. The text became an odd ".......○" when called from the .nut script. It may be because it doesn't have all/as many variables that the story script needs, but I'll keep working on making an example PAPA file that I can call in game.
I fixed this. I've updated the link above with fully working from-scratch PAPA files. (I made the text tiny because Xentax doesn't have strikethrough tags, either. They should really fix that)

At least for now, so long as we can create valid PAPA files, it's great to know that we can add stuff to Msg.xbb as we please!

EDIT3:
There was an issue with my original example PAPA files. Turns out that, even if you have only 1 file, you need to specify that you have TWO files inside the PAPA, and then point to an 8-byte block at the end with all zeroes. I think this is so that the game knows where the string ends. Anyway, my new, made-from-scratch example PAPA file works in Story of Seasons, so I'll update the original link to the archive. I'll make the same change to the A New Beginning PAPA file, but I'm not set up to test it yet, so someone else will have to do that.
## Post #39
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-09-30T11:01:25+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

Finally I got my Internet back 
Will try to rebuild AND use the pp-file creator the next few days
## Post #40
- Username: ubergeek77
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jun 11, 2015 11:04 am
- Post datetime: 2015-10-01T20:57:16+00:00
- Post Title: Re: decompress xbb file from "Harvest Moon A new Beginning 3

> Reply from ChrisX930
>
> Finally I got my Internet back 
Will try to rebuild AND use the pp-file creator the next few days

Just a quick note - I've been working on something too, and if you take a look at the examples I posted, I think there is an extra set of zeroes (0x00000000) that don't need to be there. They were there on the Story of Seasons one, but I can't remember if they were on the ANB one. Don't let that trip you up.
