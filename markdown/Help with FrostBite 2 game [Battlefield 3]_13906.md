## Post #1
- Username: Ryderizm
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jan 31, 2016 7:33 pm
- Post datetime: 2016-01-31T11:46:31+00:00
- Post Title: Help with FrostBite 2 game [Battlefield 3]

All i know that the audio codecs that Battlefield 3 uses is XAS Audio Codec, does not support EA Layer3 at all unlike BF4.

But there's 2 things i want to know about battlefield 3:

1- Where is the audio data exactly ? in the chunks?, because i'm confident and sure that the data is in the chunks but the EBX files are just relocating the name and offsets for the data in the chunks again.

2- How to use XAS Codecs? Decoding/Encoding aswell.. 

Any idea please post bellow. Ty ;')
## Post #2
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2016-01-31T22:01:40+00:00
- Post Title: Help with FrostBite 2 game [Battlefield 3]

The whole story is explained overthere:

[viewtopic.php?f=17&t=10347&hilit=battlefield+3](http://forum.xentax.com/viewtopic.php?f=17&t=10347&hilit=battlefield+3)

Works with PC version only.

Cordialy.
## Post #3
- Username: Ryderizm
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jan 31, 2016 7:33 pm
- Post datetime: 2016-02-01T12:50:50+00:00
- Post Title: Help with FrostBite 2 game [Battlefield 3]

> Reply from Vosvoy
>
> The whole story is explained overthere:

viewtopic.php?f=17&t=10347&hilit=battlefield+3

Works with PC version only.

Cordialy.

Well thanks, but i know the whole story. I did something that made me sure that the audio data is in the chunks. I just used one of BF4 Reflection files in BF3 and it worked. But still problematic because i don't know the chunk size of the chunk it self.

So i'm trying to seek a decoder/encoder for it. I know it's XAS dynamic lib, but the only one who can mess with these is Frank.. Who did the dumpers and decoders with his Python script.

I don't have enough info for the other post but ty for help :/ ..
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-01T16:32:48+00:00
- Post Title: Help with FrostBite 2 game [Battlefield 3]

> Reply from Ryderizm
>
> So i'm trying to seek a decoder/encoder for it. I know it's XAS dynamic lib, but the only one who can mess with these is Frank..

You are wrong. There are lots of XAS decoders, for example, you can use my decoder from this thread:

[viewtopic.php?f=10&t=13584](http://forum.xentax.com/viewtopic.php?f=10&t=13584)

You only need xas_decode.exe and no other files. You have to extract chunks before using it. You can do this with bms as i remember, but I doubt you need that without names, so better use updated python scripts provided in "the whole story" thread.
## Post #5
- Username: Ryderizm
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jan 31, 2016 7:33 pm
- Post datetime: 2016-02-01T21:26:30+00:00
- Post Title: Help with FrostBite 2 game [Battlefield 3]

> Reply from daemon1
>
> Ryderizm wrote:So i'm trying to seek a decoder/encoder for it. I know it's XAS dynamic lib, but the only one who can mess with these is Frank.. 

You are wrong. There are lots of XAS decoders, for example, you can use my decoder from this thread:

viewtopic.php?f=10&t=13584

You only need xas_decode.exe and no other files. You have to extract chunks before using it. You can do this with bms as i remember, but I doubt you need that without names, so better use updated python scripts provided in "the whole story" thread.

I know man.. I'm looking forward to encode the media files.. again..
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-02T15:57:54+00:00
- Post Title: Help with FrostBite 2 game [Battlefield 3]

> Reply from Ryderizm
>
> I know man.. I'm looking forward to encode the media files.. again..

I don't understand. First you ask where is the audio data, and how to decode it, then you say you know it.

What exactly do you want to know?
## Post #7
- Username: Ryderizm
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jan 31, 2016 7:33 pm
- Post datetime: 2016-02-02T19:45:16+00:00
- Post Title: Help with FrostBite 2 game [Battlefield 3]

> Reply from daemon1
>
> Ryderizm wrote:I know man.. I'm looking forward to encode the media files.. again..

I don't understand. First you ask where is the audio data, and how to decode it, then you say you know it.

What exactly do you want to know?

I'm currently trying to mod BF3. I changed audio file but it's truncated because it's a different xas format. I mean BF3 uses compressed XAS files 0x14, while some of BF4 files is using XAS PCM 0x12 so manged to swap one of BF3 files and it worked in a truncated way... I just need a way to encode it back. Not also for upgrading bf3 to bf4 sounds.. 

Please don't say Modding BF3 is not possible. Don't be hopeless .
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-02T20:17:45+00:00
- Post Title: Help with FrostBite 2 game [Battlefield 3]

> Reply from Ryderizm
>
> I changed audio file but it's truncated

It's truncated because audio length (and offset inside the chunk) is written inside the EBX file. If you want to modify sounds, you have to mod EBX files too.
## Post #9
- Username: Ryderizm
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jan 31, 2016 7:33 pm
- Post datetime: 2016-02-03T14:12:25+00:00
- Post Title: Help with FrostBite 2 game [Battlefield 3]

> Reply from daemon1
>
> Ryderizm wrote:I changed audio file but it's truncated

It's truncated because audio length (and offset inside the chunk) is written inside the EBX file. If you want to modify sounds, you have to mod EBX files too.

I did but the game doesn't launch.. I changed the chunk size in EBX.. so for a safer way i should convert that PCM File into XAS Compressed format.. might be bigger than the original file but not that much.
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-03T15:45:50+00:00
- Post Title: Help with FrostBite 2 game [Battlefield 3]

> Reply from Ryderizm
>
> I did but the game doesn't launch.. I changed the chunk size in EBX.. so for a safer way i should convert that PCM File into XAS Compressed format.. might be bigger than the original file but not that much.

How did you do that? Maybe you did something wrong?

Doesn't matter how much bigger the file will be. If it will be bigger, you have to correct EBX.
## Post #11
- Username: Ryderizm
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jan 31, 2016 7:33 pm
- Post datetime: 2016-02-04T12:52:57+00:00
- Post Title: Help with FrostBite 2 game [Battlefield 3]

> Reply from daemon1
>
> Ryderizm wrote:I did but the game doesn't launch.. I changed the chunk size in EBX.. so for a safer way i should convert that PCM File into XAS Compressed format.. might be bigger than the original file but not that much.

How did you do that? Maybe you did something wrong?

Doesn't matter how much bigger the file will be. If it will be bigger, you have to correct EBX.

Well, i'm going to give another try .. again.

And the chunk size is reversed in the end of the EBX file.. The raw ebx file.. 
Also should i change the chunk ID ? i'm not sure because of conflicts..
___________

+ Adding something to the game might change other game data's offsets. So i don't really know if it's dependent on the ending offset in EBX or not..

I'm affraid that i just edited the ebx file in the dumped folder not .cas one x)
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-07T17:44:12+00:00
- Post Title: Help with FrostBite 2 game [Battlefield 3]

There is an editor for BF3, but I can't find the link now. I never used it, so don't know what features it had.
## Post #13
- Username: Ryderizm
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jan 31, 2016 7:33 pm
- Post datetime: 2016-02-12T13:16:31+00:00
- Post Title: Help with FrostBite 2 game [Battlefield 3]

Nvm, thanks for the help.. I will have to make my own encoder then :/
## Post #14
- Username: elementofprgress
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Dec 10, 2015 2:48 am
- Post datetime: 2016-04-15T04:54:47+00:00
- Post Title: Help with FrostBite 2 game [Battlefield 3]

> Reply from Ryderizm
>
> Nvm, thanks for the help.. I will have to make my own encoder then :/

While saying BF3 can't be modded would be lie, the method your trying will not work. The files are locked down fairly hard when it comes to running a regular client. Ironically enough because of editor that was intended to be foundation of future mod tools. However apparently no one thought that anyone would ever figure out the Frostbite engine's files? or just wasn't thinking?  idk. so BF3 was launched with no checks or any thing to stop modders from making awesome BF mods like they always have. Assuming, obviously that modding the client wouldn't effect MP or you wouldn't be able to join a MP server with a tweaked files. ...yeah about that. not only where there no checks in place for MP.....being a "client side hit registration" game means that for the part the client deals the damage, not the server.(among other things) So all of the tweaks and changes made in the files would be in full 100% on a live MP server. No matter if you made you gun to 1 damage or 99999 damage.

Needless to say its was a disaster for both sides and DICE/EA's reaction was to lock that shit down tight. Soooooo if you playing on a normal client with origin and what not(EA core/activation iirc) modding the files just ain't gonna happen.  HOWEVER this is all YEARSSS ago, and people have gotten around that, sorta. You chould  check out the BF3 Venice project. After YEARS its almost ready. and that will finally being at least some level of modding to BF3.


Though even better is this [https://github.com/GreyDynamics/FrostBite3_Editor](https://github.com/GreyDynamics/FrostBite3_Editor) .... one day ....  one day...


also that git has a lot of documentation about how the files work which you seem to be interested in
