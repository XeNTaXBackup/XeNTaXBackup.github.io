## Post #1
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-06-10T14:33:09+00:00
- Post Title: Bomberman Series Sound Effects

Greetings all. I've been posting here a bit about Bomberman and it's an ongoing hobby of mine. I figured it would be best to just make a general thread since I plan on popping in and out frequently with questions, if that's all right. Please feel free to help in any way possible as we go.

Currently I'm looking into Saturn Bomberman and Saturn Bomberman Fight!!. I used PowerISO and was able to find the voice files in Saturn as .AIF files but it seems the sound effects are still lurking deeper. Anyone have any idea how to investigate further?
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-10T17:06:14+00:00
- Post Title: Bomberman Series Sound Effects

From what I can see in Saturn Bomberman:

In the BOMSS folder - .CPK are the video files (with some dialogue), .AIF are voice files.
In the NETLINK folder - the .WAV files are sound effects.

There doesn't appear to be any other sounds than those above.
## Post #3
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-06-11T03:32:23+00:00
- Post Title: Bomberman Series Sound Effects

This is where I got stuck. The .WAV files in the Netlink folder are for the Netlink capabilities and not the game itself. Do you think they could be in the .bin files in the BOMSS folder? I'm unable to extract anything from those files with PowerISO.
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-11T16:54:30+00:00
- Post Title: Bomberman Series Sound Effects

I think you're right.  The PROGRAM.BIN file is an archive of lots of files,  I can hear some 8-bit signed audio data in there, which is all the sound effects and in-game voices.  I can't see a way to easily extract them at the moment.  I'm thinking there must be a table somewhere to reference this, so I'll have a look.
## Post #5
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-06-25T08:43:16+00:00
- Post Title: Bomberman Series Sound Effects

I showed this to a friend and he was able to find a few things of interest. Using Audacity, he was able to locate some of the sounds in the PROGRAM.BIN file. 

[https://imgur.com/Kl0cZ5X](https://imgur.com/Kl0cZ5X)
## Post #6
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-11-17T07:46:29+00:00
- Post Title: Bomberman Series Sound Effects

Hey all. Lately I shifted gears and have been working on Super Bomberman R on Steam. I have located where the sound files are but Windows can't seem to identify what they are. I turned off the "Hide extensions for known file types" and got nothing. It won't open with Foobar either. Any thoughts?

[https://imgur.com/HXVPm0O](https://imgur.com/HXVPm0O)
## Post #7
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-11-17T12:00:47+00:00
- Post Title: Bomberman Series Sound Effects

Hello again!

I'm guessing it's an archive.  Can you upload one of them so we can check?
## Post #8
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-11-18T09:59:33+00:00
- Post Title: Bomberman Series Sound Effects

Hello again Dave! Here's that file: [https://mega.nz/#!soZjRCRB!h0_uEuo4Qlv8 ... oE6X2FErwQ](https://mega.nz/#!soZjRCRB!h0_uEuo4Qlv8vRyn2X-TOF3dFIxLOKOrkoE6X2FErwQ)
## Post #9
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-11-19T18:32:13+00:00
- Post Title: Bomberman Series Sound Effects

There's nothing obvious in the file, so it's either compressed or encrypted.  I looked at various compression methods and couldn't find anything, so it's more likely encrypted.  I don't know much about decryption, so hopefully someone else might.
## Post #10
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-11-19T19:07:49+00:00
- Post Title: Bomberman Series Sound Effects

Thanks for trying Dave.
## Post #11
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2020-04-03T08:40:34+00:00
- Post Title: Bomberman Series Sound Effects

Hello all. I've switched my tune and have been looking at Bomberman Blast for Wii, the Japanese version. I've been trying to rip the music/sound effects from the game. I used Dolphin and extracted a .brsar file but can't seem to get much done with it. BrawlBox only plays like 5 sounds of the entire thing, brsar unpacker won't open when I try to run it, and I even tried a .brsar extractor. Anyone out there have experience with these files?

The brsar file: [https://mega.nz/file/c0YgzaqL#eqkqW01v2 ... Yk0O3LNkTA](https://mega.nz/file/c0YgzaqL#eqkqW01v2BnwprO706BF5t-H5W0kRIrfDYk0O3LNkTA)
## Post #12
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-04-03T17:05:47+00:00
- Post Title: Bomberman Series Sound Effects

The brsar file follows the same format as the Nintendo DS .sdat files.  In this case, each file seems to start with "RWAV"

Should be possible to write an extractor if there isn't already one!
## Post #13
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2021-05-31T14:40:43+00:00
- Post Title: Bomberman Series Sound Effects

Do you know if one exists Dave? I'm not familiar with writing things like this. I had read that these sounds/music are sequenced and not easily obtainable.
## Post #14
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-06-01T01:05:01+00:00
- Post Title: Bomberman Series Sound Effects

I've recently discovered that VGMTrans can play the sequenced music from these files.

[https://github.com/magcius/vgmtrans/releases](https://github.com/magcius/vgmtrans/releases)

When you load the .brsar file, you get a load of instruments, sequences, etc.  I saved the instrument set as Soundfont2 and the Sequences as MIDI, and use a MIDI plugin for Foobar and it seems to work quite well.
## Post #15
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2021-06-01T02:57:55+00:00
- Post Title: Bomberman Series Sound Effects

Well I'll be dern. Thank you Dave! That version of VGMTrans worked! The bass is pretty strong in these clips but I can tweak that. I've also been looking for the music so this is a double bonus really.

Out of curiosity, do you make anything of that file from the Steam version of Super Bomberman R? There's a few exclusive characters to that version who have voices in it.
## Post #16
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-06-02T01:00:39+00:00
- Post Title: Re: Bomberman Series Sound Effects

I did a script not long ago for those Super Bomberman R files (although any FSB extractor should also work):



 FSB5.zip
(435 Bytes) Downloaded 21 times
## Post #17
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2021-06-02T04:26:33+00:00
- Post Title: Re: Bomberman Series Sound Effects

I appreciate the script Dave. It seems the sound archive for SBR on steam doesn't like it though. It turned up 0 files. =/
## Post #18
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-06-02T10:24:27+00:00
- Post Title: Re: Bomberman Series Sound Effects

They must be in a different format to the other sound files then.  Might be useful if you could post a sample of the sound archive.
## Post #19
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2021-06-02T15:40:28+00:00
- Post Title: Re: Bomberman Series Sound Effects

How do I get a sample? Sorry I'm not familiar with this.
## Post #20
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-06-02T19:23:02+00:00
- Post Title: Re: Bomberman Series Sound Effects

You can either use a file cutter to get a small sample, if it's a large file, or you can upload it to some online hosting place like Mega, etc.
## Post #21
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2021-06-03T01:52:48+00:00
- Post Title: Re: Bomberman Series Sound Effects

Will do. What program do you recommend?
## Post #22
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-06-03T16:19:57+00:00
- Post Title: Re: Bomberman Series Sound Effects

You use something like VGMToolbox, but any file cutter will do.
## Post #23
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2021-06-04T15:43:17+00:00
- Post Title: Re: Bomberman Series Sound Effects

Gotcha. I'll work on that this weekend. 

You wouldn't happen to know anything about .dig files would you? [https://mega.nz/file/zhICgBIY#I9u6Be5Wm ... VjY57VlJxs](https://mega.nz/file/zhICgBIY#I9u6Be5WmOYCR9EZ-v2OHcaFdzSnPNuDyVjY57VlJxs)
## Post #24
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-06-04T16:18:52+00:00
- Post Title: Re: Bomberman Series Sound Effects

I've seen a few different .dig files over the years, but it looks familiar.  Which game is it from?
## Post #25
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2021-06-04T19:05:17+00:00
- Post Title: Re: Bomberman Series Sound Effects

Bomberman Land 2 on gamecube. The PS2 version has already been ripped but the Gamecube version is something I get a lot of requests for. Never really got past finding this file.
## Post #26
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2021-06-25T01:40:45+00:00
- Post Title: Re: Bomberman Series Sound Effects

Hey dave. Do you have an email I could contact you at? I'm at [steamyjimmy@protonmail.com](mailto:steamyjimmy@protonmail.com) I wanted to ask you about something with the .dig file.
## Post #27
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-06-25T11:34:32+00:00
- Post Title: Re: Bomberman Series Sound Effects

I've enabled PMs on here for now, so you can use that if you like.
