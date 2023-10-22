## Post #1
- Username: godmode
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 21, 2007 4:06 am
- Post datetime: 2007-06-20T20:39:39+00:00
- Post Title: Ragnarok Online 2 .utx encrypted

So, RO2 is in Korean beta right now. The engine is a modified Unreal2 engine.
The texture files in it are encrypted .utx files. Is there any way to make these readable with UnrealEd or UTPT? 

Example: [http://www.zshare.net/download/2357465298990d/](http://www.zshare.net/download/2357465298990d/)
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-06-28T12:21:20+00:00
- Post Title: Ragnarok Online 2 .utx encrypted

It seems that they also changed the package format.
## Post #3
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-06-28T20:59:54+00:00
- Post Title: Ragnarok Online 2 .utx encrypted

I think they just encrypted the header info.
So you have to locate where the import table and export tables are.

Say like the files sample about, tables location of system_t.utx @ 0x1D018D and tables location of Rag2_shipzone_t.utx @ 0x200E8F.
(Just Export table, no import table?)
Note also the table format maybe extened since the UE2 verision is 129!
But I can't found any different on a quick peek.


That's what I know ATM!
## Post #4
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-06-28T22:22:37+00:00
- Post Title: Ragnarok Online 2 .utx encrypted

Here is a quick hacked file if anyone interested to see!
You can open it in UTPT but no image will be displayed since the import table is missing so UTPT didn't know which one is texture image!

[http://www.zshare.net/download/24758055297fbe/](http://www.zshare.net/download/24758055297fbe/)
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-06-28T22:45:39+00:00
- Post Title: Ragnarok Online 2 .utx encrypted

If it really is encrypted, debugging the exe would help.
But I don't have the beta files.
## Post #6
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-07-03T10:31:09+00:00
- Post Title: Ragnarok Online 2 .utx encrypted

I'm bored today so I have another look at the files. I'm sure to tell you that ONLY Header is encrypted!
I hacked the header manually and get all standard UE2 infos.



[Here is the hacked utx](http://www.zshare.net/download/2541315927a94b/)
## Post #7
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-03T13:04:13+00:00
- Post Title: Ragnarok Online 2 .utx encrypted

> Reply from fatduck
>
> I'm sure to tell you that ONLY Header is encrypted!
Quiet common approach.
Would need the exe and dll files to have a closer look.
## Post #8
- Username: godmode
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 21, 2007 4:06 am
- Post datetime: 2007-07-04T09:25:43+00:00
- Post Title: Ragnarok Online 2 .utx encrypted

heres the exe if it helps:

[http://download.yousendit.com/D5D7EFE536A964C8](http://download.yousendit.com/D5D7EFE536A964C8)
## Post #9
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-04T14:46:08+00:00
- Post Title: Ragnarok Online 2 .utx encrypted

As I already said, I also need the dll files.
## Post #10
- Username: godmode
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 21, 2007 4:06 am
- Post datetime: 2007-07-05T22:01:55+00:00
- Post Title: Ragnarok Online 2 .utx encrypted

ok, here is the system directory with the .exe and all the .dll files
[http://zenixstudios.com/f.php?f=uhkxnjs](http://zenixstudios.com/f.php?f=uhkxnjs)
## Post #11
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-06T08:16:49+00:00
- Post Title: Ragnarok Online 2 .utx encrypted

ProtectionID tells that it is protected with XProtector (now called Themida afaik). XProtStripper doesn't work.
