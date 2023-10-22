## Post #1
- Username: DesBurak
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Jun 19, 2011 5:55 pm
- Post datetime: 2014-01-01T18:57:18+00:00
- Post Title: Max Payne 3 PS3 RPF(4?)

Here is the header of decrypted common.rpf(from common.sdat)



after many zeros this



or you can check the file here (105 mb, 55 mb compressed)

[https://mega.co.nz/#!HdMRRT4Q!eKQNYAxVM ... FeAeu48MdM](https://mega.co.nz/#!HdMRRT4Q!eKQNYAxVMeLujgrxroMAXSLu9D5oNmNU8FeAeu48MdM)

None of current RPF programs (OpenIV as always on consoles, RPFTool as it doesn't support PS3..) worked. Can anyone help me to extract texts and localize this game
## Post #2
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2014-01-01T22:03:11+00:00
- Post Title: Max Payne 3 PS3 RPF(4?)

I released my rpftool code a while ago, I think the ps3 version uses a different key but if you can find that it should be fairly trivial to add support for the ps3 version - [https://code.google.com/p/rpftool/](https://code.google.com/p/rpftool/)
## Post #3
- Username: DesBurak
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Jun 19, 2011 5:55 pm
- Post datetime: 2014-01-03T13:35:11+00:00
- Post Title: Max Payne 3 PS3 RPF(4?)

I've been working on it since you said but how can I realize that i found the real key 

I mean, it's same in PS3 and Xbox till MP3(MC:LA, Red Dead Redemption, GTA IV...). In GTA V, it includes similar(copy, load, right byte or data) but different instructions in IDA. I don't know what I'll look for. I read your tutorial but none of PS3 elfs include "archive" commands like XBox
## Post #4
- Username: DesBurak
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Jun 19, 2011 5:55 pm
- Post datetime: 2014-01-04T22:09:20+00:00
- Post Title: Max Payne 3 PS3 RPF(4?)

Sorry I sent you pm I just saw it.
## Post #5
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2014-01-07T22:13:13+00:00
- Post Title: Max Payne 3 PS3 RPF(4?)

Key can be found at 0x014C6CA4 after dropping the original elf into IDA, for those interested in a version of RPFTool for MP3 on PS3 contact DesBurak.
## Post #6
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2018-09-12T15:47:40+00:00
- Post Title: Max Payne 3 PS3 RPF(4?)

Hello. I am late for this party, but as DesBurak said, current RPF tools doesn't support the PS3 version of the game.
From this posts, it seems that this guy was in the right direction, but he got the key from where?
