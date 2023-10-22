## Post #1
- Username: MisterLeroy
- Rank: n00b
- Number of posts: 11
- Joined date: Sat May 02, 2015 6:43 pm
- Post datetime: 2015-05-02T10:55:30+00:00
- Post Title: Audio File Confusion

Hey folks,

Absolute beginner here. 

I've followed the GUI guides for QuickBMS generic files extractor and reimporter 0.6.3 with comtype_scan2.bms + comtype_scan2.bat plugins but it fails immediately whatever I do. 

The file types the audio are found in are AUX, and I think there are OVL files which do all the pointing.

I'd dropped some of the files in to drop box (I skipped the music files, I think, I am only seeking the ship voice itself)

I'm really at a loss, but this seems like the kind of place which might be able to point me in the right direction I hope. 

I am a beginner at this, but i am a competent user and keen learner/researcher but have little knowledge of scripting. My research isn't helping here though. 

Thanks for any insight you can offer,  Xentax

(I did search also and find this thread, which put me on the path I am on above, but here my findings end [viewtopic.php?f=21&t=12572](http://forum.xentax.com/viewtopic.php?f=21&t=12572))

Update:

using this guide I've managed to sort out getting the audio out of the product, but now to work out how to get my own back in

[https://www.youtube.com/watch?v=wDNsDRfcWNs](https://www.youtube.com/watch?v=wDNsDRfcWNs)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-04T14:04:22+00:00
- Post Title: Audio File Confusion

Can you please put this huge screenshot under spoiler? 

Do you still need help using ww2ogg?
## Post #3
- Username: MisterLeroy
- Rank: n00b
- Number of posts: 11
- Joined date: Sat May 02, 2015 6:43 pm
- Post datetime: 2015-05-04T18:58:36+00:00
- Post Title: Audio File Confusion

> Reply from daemon1
>
> Can you please put this huge screenshot under spoiler?Apologies -- I tried, the code isn't listed on the options and trying it anyway didn't work. 

> Reply from daemon1
>
> Do you still need help using ww2ogg?So far I have managed to land myself with a bunch of playable .wwise files. my ultimate hope is to somehow wiggle my own audio files in place of those. I have the audio but my guess is I'd need to somehow wwise it and then repack it. I'm fairly new to this.
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-04T19:52:31+00:00
- Post Title: Audio File Confusion

Sorry, I forgot this forum doesn't have a spoiler feature.

About the audio: .aux files are wwise audio packages, and .ovl files are wwise banks. These banks contain links to packages, and/or audio itself. There's no easy way to change and pack it back. Usually you have to write your own set of tools for each game.
## Post #5
- Username: MisterLeroy
- Rank: n00b
- Number of posts: 11
- Joined date: Sat May 02, 2015 6:43 pm
- Post datetime: 2015-05-04T20:08:30+00:00
- Post Title: Audio File Confusion

Is Ravioli a one-way thing?
## Post #6
- Username: MisterLeroy
- Rank: n00b
- Number of posts: 11
- Joined date: Sat May 02, 2015 6:43 pm
- Post datetime: 2015-05-05T08:25:15+00:00
- Post Title: Audio File Confusion

Would Audiokinetic Wwise be the licence I am after to repack my audio files in to a Soundbank?
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-05T16:35:47+00:00
- Post Title: Audio File Confusion

If you find wwise version they were using while making the game, you can probably convert files to wwise format. But I really doubt you can build soundbanks. They have uids and lots of properties (attenuation, mixers, modifiers e.t.c.)

Which sounds (.aux or .ovl) would you like to replace and how many?
## Post #8
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-05-05T17:13:19+00:00
- Post Title: Audio File Confusion

Daemon Is there a way to locate original filenames for WWise audio files? or do the developers leave them out? i find sometimes in gams they leave the .txt or xml files with the anmes but sometimes they leave them out but dunno if it can be found like in the exe or .xex or some other files?
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-05T18:15:10+00:00
- Post Title: Audio File Confusion

In most cases you can find names inside of unreal packages, in very different places. Because this is convenient for the developers themselves. But sometimes there's nothing left. In such case we only have a location name, dialog name, speaker name, and phrase number inside of a dialogue. But anyway, this is really all we need to identify a file.
## Post #10
- Username: MisterLeroy
- Rank: n00b
- Number of posts: 11
- Joined date: Sat May 02, 2015 6:43 pm
- Post datetime: 2015-05-05T20:52:14+00:00
- Post Title: Audio File Confusion

> Reply from daemon1
>
> If you find wwise version they were using while making the game, you can probably convert files to wwise format. But I really doubt you can build soundbanks. They have uids and lots of properties (attenuation, mixers, modifiers e.t.c.)right yes. This is what terrified me in Audiowise. It looked like something far to comprehensive and tailored.

> Reply from daemon1
>
> Which sounds (.aux or .ovl) would you like to replace and how many?

So i will confirm when home. Please disregard those I included in the current Dropbox as they aren't actually the right ones.

Thanks for your input thus far. hope I'm not chasing ghosts.
## Post #11
- Username: MisterLeroy
- Rank: n00b
- Number of posts: 11
- Joined date: Sat May 02, 2015 6:43 pm
- Post datetime: 2015-05-05T21:10:15+00:00
- Post Title: Audio File Confusion

So it's one OVL [file](https://www.dropbox.com/s/g065xatu2r03nym/Data.ovl?dl=0) with 102 files. The end number to replace is less than 100 (or can be all 102 if required).
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-06T16:32:30+00:00
- Post Title: Audio File Confusion

This is bad. It's a bank. Rebuilding a bank can be tricky. Are you sure if you change the files the game will not ban you? You said you have permission from the developers, maybe this means you can send them your WAVs and they will pack this bank for you?
## Post #13
- Username: MisterLeroy
- Rank: n00b
- Number of posts: 11
- Joined date: Sat May 02, 2015 6:43 pm
- Post datetime: 2015-05-06T17:50:39+00:00
- Post Title: Audio File Confusion

> Reply from daemon1
>
> This is bad. It's a bank. Rebuilding a bank can be tricky. Are you sure if you change the files the game will not ban you? You said you have permission from the developers, maybe this means you can send them your WAVs and they will pack this bank for you?

So their stance is this:

> Hi <snip>,
>
> 
>
> I understand your concern with anti-hacking and other issues going on in <snip> and other similar games. I'm aware users in other games are often banned for modifying files for simple changes that are purely aesthetic so it's always concerned me too.
>
> 
>
> As for an official stance on the matter, I believe we don't tell people to go ahead and do it but I also don't believe we'll actively seek you out and ban you for it. So my response is this:
>
> 
>
> Go for it, make sure to back your hard work up somewhere in case a patch wipes it clean, but have fun with the game and experiment a little. If you're found actually gaining an unfair advantage then we're likely to take action, if you're just making changes to help you enjoy the game more then you should be fine.
>
> 
>
> As an additional safety net for you, if you're banned for this edit (which I am 99% sure you won't be) you can start a new ticket with us and refer back to this one and we'll be able to help you with that without a problem.

It's not perfect but I am happy they even gave this much of a response to what is frankly a rediculous query I raised. I worked for Blizzard nearly a decade and they'd certainly never give this level of freedom.

So is this worthwhile pursuing or are banks really that unpleasant to work with?
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-06T18:06:50+00:00
- Post Title: Audio File Confusion

> Reply from MisterLeroy
>
> So is this worthwhile pursuing or are banks really that unpleasant to work with?

Well, we can try.
## Post #15
- Username: MisterLeroy
- Rank: n00b
- Number of posts: 11
- Joined date: Sat May 02, 2015 6:43 pm
- Post datetime: 2015-05-06T18:16:17+00:00
- Post Title: Audio File Confusion

I'm fairly clueless as to where to go from here basically. Don't get me wrong I'm really more than happy to approach this as a research based experience for me. I think I just need some steering and perhaps some freedom to ask what may be to you (and the forum in general) some pretty naive questions.
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-06T18:38:31+00:00
- Post Title: Re: Audio File Confusion

While I'm thinking how we can replace the sounds, can you tell me, which particular sound of those 120 we can use for quick testing? So you can check it in game.
## Post #17
- Username: MisterLeroy
- Rank: n00b
- Number of posts: 11
- Joined date: Sat May 02, 2015 6:43 pm
- Post datetime: 2015-05-06T19:23:49+00:00
- Post Title: Re: Audio File Confusion

This one perhaps. 

If you wish to try with some of the [audio](https://www.dropbox.com/s/d9nqfzdaql320u4/Landing%20gear%20deployed.wav?dl=0) I have on hand.
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-06T20:31:30+00:00
- Post Title: Re: Audio File Confusion

ok, we also need to choose another file, that is not in a bank. It must be some sound from .aux file.

I think tomorrow we can make some tests.
## Post #19
- Username: MisterLeroy
- Rank: n00b
- Number of posts: 11
- Joined date: Sat May 02, 2015 6:43 pm
- Post datetime: 2015-05-06T21:12:26+00:00
- Post Title: Re: Audio File Confusion

I've no idea what I am doing with an Aux file I'm afraid but I have placed one [here](https://www.dropbox.com/s/nscj0bmm3fna6ya/audioframeshiftdrive_frameshiftdrive_bnk_s.zip?dl=0) I believe to contain something reproducible if you perhaps know how to extract one of these, or prod me in the right direction
## Post #20
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-11T11:33:02+00:00
- Post Title: Re: Audio File Confusion

Good news. I was able to repack the audio bank with some original sounds swapped. Now we need a suitable Wwise version to convert our own sound.
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-11T12:17:22+00:00
- Post Title: Re: Audio File Confusion

Very good news. Although i have wwise 2011 installed, and it's for sure not the version they used, your phrase works in game. Maybe it's backwards compatible, I don't know. Expect a tool soon.
## Post #22
- Username: MisterLeroy
- Rank: n00b
- Number of posts: 11
- Joined date: Sat May 02, 2015 6:43 pm
- Post datetime: 2015-05-11T15:57:06+00:00
- Post Title: Re: Audio File Confusion

:O my my that's amazing, I honestly didn't know what to expect. Incredible.
## Post #23
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-11T17:04:17+00:00
- Post Title: Re: Audio File Confusion

I didn't know either. You can always stuck on something they have in custom format.
