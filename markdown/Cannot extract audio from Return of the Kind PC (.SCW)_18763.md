## Post #1
- Username: fudge
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Sep 01, 2018 11:40 pm
- Post datetime: 2018-09-01T15:44:30+00:00
- Post Title: Cannot extract audio from Return of the Kind PC (.SCW)

Afternoon,

I am trying desperately to extract the audio from the Return of the King on PC. Game extractor can open the games .scw files but the files are a scrambled mess of .sono and .shoc files. Running MFAudio on the .scw files allows me to hear the grunts of the characters perfectly clear, but actual dialogue and music is so hideously compressed that you can only just about make it out.

If anybody has any advice on how I can go about getting the audio out of this game I would be very appreciative! As it stands a similar thread on VGR has yielded no real advice so you're my last hope!

I have included a link to one .scw file (for the Black gate) for reference - [https://1drv.ms/u/s!ArXMmzOtC8DfiVHuuJD_hs4uMemb](https://1drv.ms/u/s!ArXMmzOtC8DfiVHuuJD_hs4uMemb)

Cheers,
Fudge
## Post #2
- Username: fudge
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Sep 01, 2018 11:40 pm
- Post datetime: 2018-09-04T21:30:15+00:00
- Post Title: Cannot extract audio from Return of the Kind PC (.SCW)

I'll name my first child after anybody who can assist me.
## Post #3
- Username: fudge
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Sep 01, 2018 11:40 pm
- Post datetime: 2018-09-08T20:50:57+00:00
- Post Title: Cannot extract audio from Return of the Kind PC (.SCW)

What about a nice picture of a goose? That sway anybody?
## Post #4
- Username: fudge
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Sep 01, 2018 11:40 pm
- Post datetime: 2019-01-21T14:26:22+00:00
- Post Title: Cannot extract audio from Return of the Kind PC (.SCW)

Maybe a hug will convince somebody?
## Post #5
- Username: fudge
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Sep 01, 2018 11:40 pm
- Post datetime: 2019-01-25T11:35:31+00:00
- Post Title: Cannot extract audio from Return of the Kind PC (.SCW)

A short poem depicting their heroic nature in helping me decode this?

There are also some .cbx files if those are easier for anyone.
## Post #6
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-03-05T05:09:05+00:00
- Post Title: Cannot extract audio from Return of the Kind PC (.SCW)

Just noticed this, if you're still around, can you re-upload the sample?
## Post #7
- Username: fudge
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Sep 01, 2018 11:40 pm
- Post datetime: 2019-07-07T13:04:07+00:00
- Post Title: Cannot extract audio from Return of the Kind PC (.SCW)

> Reply from Pingu ↑Tue Mar 05, 2019 1:09 pm at Tue Mar 05, 2019 1:09 pm
>
> 
Just noticed this, if you're still around, can you re-upload the sample?

Hello! Thank you for attempting to help me with this thing. I have re-uploaded one of the scw files here - [https://1drv.ms/u/s!ArXMmzOtC8Dfij3vSOq ... d?e=OrgCN3](https://1drv.ms/u/s!ArXMmzOtC8Dfij3vSOqbcLC6Iovd?e=OrgCN3)

I cannot seem to find anything on these weird files.

Cheers,
Fudge
## Post #8
- Username: fudge
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Sep 01, 2018 11:40 pm
- Post datetime: 2019-08-13T19:13:13+00:00
- Post Title: Cannot extract audio from Return of the Kind PC (.SCW)

Captain's log. Almost a year has passed. Still no contact from the people who can solve this audio problem. My assumption is my petty rewards are not significant enough. I am searching for a suitable gift..I have settled on either a ripe melon or a slightly wonky pebble.
## Post #9
- Username: fudge
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Sep 01, 2018 11:40 pm
- Post datetime: 2019-12-18T15:00:56+00:00
- Post Title: Cannot extract audio from Return of the Kind PC (.SCW)

Today I awoke from a crazed dream where somebody had solved this weird file problem. In my dazed weariness I was reminded of my futility of my quest.

Therefore I have upgraded the reward further to a rather nice compliment either from myself or from whomever I can pull in off the sreet.
## Post #10
- Username: Imthefuture
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 18, 2020 4:16 pm
- Post datetime: 2020-04-18T08:28:38+00:00
- Post Title: Cannot extract audio from Return of the Kind PC (.SCW)

> Reply from fudge ↑Sat Sep 01, 2018 11:44 pm at Sat Sep 01, 2018 11:44 pm
>
> 
 of .sono and .shoc files. Running MFAudio on the .scw files
Hi 
.scw file most likely it is a structure in which large files are fragmented at 8 kb. But MFAdion reproduces some fragments quite well on the settings - frequency 22100, channel 1, RAW uncompressed. A few observations about scw - each block starts with a .PADD file in which information about fragments.

PS the entire scw file went through at a frequency of 22100 channel 1, offset 0 - at the very beginning after the hissing sounds appeared

Good luck
## Post #11
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-04-19T18:32:22+00:00
- Post Title: Cannot extract audio from Return of the Kind PC (.SCW)

I've been messing with this format for a while and I've almost cracked it.  It's very covoluted the way the data is organised, but there is a method to the madness of it.

The sound effects are 16 bit PCM, which are the easiest to extract.  The other sounds - music etc. - is a bit more tricky as that seems to be in a different format.
## Post #12
- Username: fudge
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Sep 01, 2018 11:40 pm
- Post datetime: 2020-04-23T11:25:11+00:00
- Post Title: Cannot extract audio from Return of the Kind PC (.SCW)

> Reply from DKDave ↑Mon Apr 20, 2020 2:32 am at Mon Apr 20, 2020 2:32 am
>
> 
I've been messing with this format for a while and I've almost cracked it.  It's very covoluted the way the data is organised, but there is a method to the madness of it.

The sound effects are 16 bit PCM, which are the easiest to extract.  The other sounds - music etc. - is a bit more tricky as that seems to be in a different format.

Whoa people replied! I'mg going to have to start on getting these rewards under way.

In all seriousness this is unbelievable. I've asked everywhere to try and find somebody who could help us extract the audio from this game. Its for a mod we work on for the BFME series - [https://www.moddb.com/mods/the-horse-lo ... n-for-bfme](https://www.moddb.com/mods/the-horse-lords-a-total-modification-for-bfme).

If either of you manage to actually crack this it would be incredible. We'll take anything, ideally though we'd love to get the dialogue out of the game?

Kind regards,
Fudge
## Post #13
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-04-23T12:02:24+00:00
- Post Title: Cannot extract audio from Return of the Kind PC (.SCW)

Here's what I've got so far.

Once the files are extracted from the .scw file, the file "initial_load" contains the audio info.

The "initial_load" file is based around chunks.  The audio info is stored in the "ONOS" chunks.  There are 2 types of blocks - header and data.  There are also 2 types of data blocks - file table info and sample data.

You have to join together all of the file table blocks and all of the sample data blocks.  This will give you a complete file table and an "internal" sample data block.  This internal sample data is for sound effects and seems to be all standard 16-bit PCM.  The "external" audio data, for cutscenes, etc. is stored at the end of the file after all of the various chunks.  This audio seems to be EA ADPCM.

In the file table, there seem to be separate tables for internal and external audio, so it's just a case of working out the full format of these.  The table for the "internal" sound effects is fairly straightforward, but the other is a bit trickier.

So at the moment I'm trying to work out the format to get the dialogue/cutscene audio.  It's a bit tricky as the entries for these seem to be variable length.  At least it's a start ...
## Post #14
- Username: fudge
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Sep 01, 2018 11:40 pm
- Post datetime: 2020-04-23T13:03:06+00:00
- Post Title: Cannot extract audio from Return of the Kind PC (.SCW)

Hi,


Well it certainly seems like a rather complicated process? I'm fully rooting for you though! It'd be the first time since the game came out in 2004 that anybody has solved it. The fact you've got some sound effects out is really impressive. I can't say I fully understand what all of that means, but I appreciate you taking the time to explain it.

You'll certainly be in my good books for a very long time!

Cheers,
Fudge
## Post #15
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-04-28T23:17:03+00:00
- Post Title: Cannot extract audio from Return of the Kind PC (.SCW)

Just thought you might like a progress update.

I've sorted out the format of most of the sound tables and can extract the data for the dialogue and cutscene audio.  It's in some sort of 4-bit IMA format, not sure yet exactly which (possibly some EA ADPCM).  Here's an example as standard IMA converted to a playable mp3, which you can hear isn't exactly right, but at least you can hear what it's meant to be!
[bla01_8.zip](https://xentaxbackup.github.io/file/18055_bla01_8.zip)
## Post #16
- Username: fudge
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Sep 01, 2018 11:40 pm
- Post datetime: 2020-05-08T13:51:15+00:00
- Post Title: Re: Cannot extract audio from Return of the Kind PC (.SCW)

Well that's fantastic progress. Certainly its a bit distorted but clearly you can here what it is meant to be. Do you reckon you'll be able to get it sounding a little clearer?

Cheers,
Fudge
## Post #17
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-05-08T22:07:06+00:00
- Post Title: Re: Cannot extract audio from Return of the Kind PC (.SCW)

I've tried a few options, but the standard ones using GENH don't seem to be right.  So, if someone can work out what the right codec should be, then it'll be easier.

Here's a few raw files extracted from bla01.scw to see if anyone can get them to play correctly (maybe I have start offset wrong, but I think they're right).
[raw.zip](https://xentaxbackup.github.io/file/18109_raw.zip)
## Post #18
- Username: fudge
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Sep 01, 2018 11:40 pm
- Post datetime: 2020-05-14T11:58:28+00:00
- Post Title: Re: Cannot extract audio from Return of the Kind PC (.SCW)

Hello again,

Ah right. Thanks so much for what you have done. Its tantalising close though! Fingers crossed some clever clogs comes along and manages to finish off the last part to get these audio clips in their original quality.

Cheers,
Fudge
## Post #19
- Username: Imthefuture
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 18, 2020 4:16 pm
- Post datetime: 2020-06-08T17:26:35+00:00
- Post Title: Re: Cannot extract audio from Return of the Kind PC (.SCW)

> Reply from DKDave ↑Sat May 09, 2020 6:07 am at Sat May 09, 2020 6:07 am
>
> 
I've tried a few options, but the standard ones using GENH don't seem to be right.  So, if someone can work out what the right codec should be, then it'll be easier.

Here's a few raw files extracted from bla01.scw to see if anyone can get them to play correctly (maybe I have start offset wrong, but I think they're right).

Really very interesting format. And most likely coded by developers. I think you can look for the unpacked version in the dump of the game after launch.

In the dump, I managed to find the unpacked textures when, as in all files except fro03.scw, they are packed.
## Post #20
- Username: fudge
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Sep 01, 2018 11:40 pm
- Post datetime: 2020-06-13T19:02:19+00:00
- Post Title: Re: Cannot extract audio from Return of the Kind PC (.SCW)

So this dump may help decode the audio files potentially?
## Post #21
- Username: fudge
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Sep 01, 2018 11:40 pm
- Post datetime: 2020-07-22T20:29:25+00:00
- Post Title: Re: Cannot extract audio from Return of the Kind PC (.SCW)

Hello again,

I just wanted to bump this just in case some clever bugger fancies taking this one on for me. I would but my brain is too small.

Cheers,
## Post #22
- Username: fudge
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Sep 01, 2018 11:40 pm
- Post datetime: 2021-03-16T10:31:49+00:00
- Post Title: Re: Cannot extract audio from Return of the Kind PC (.SCW)

Even older Fudge here,

Again if any kind soul thinks they can finally put me out of my misery with this damn game I'd be hugely grateful!

Emoticon as a reward   

Cheers,
Fudge
## Post #23
- Username: fudge
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Sep 01, 2018 11:40 pm
- Post datetime: 2022-10-18T19:14:15+00:00
- Post Title: Re: Cannot extract audio from Return of the Kind PC (.SCW)

Hi me from the past,

Good news, we got somewhere! We don't have all of it, but we got all the dialogue, SFX, music and ambience that plays on each mission. General audio, so most SFX including character grunts/deaths, are still buried in the files so its not complete!

For anybody else looking to do this the process isn't super clean!

You can do this on the PS2 ISO, not the bloody PC copy! You need to extract the modules/data from the game using any old PS2 ISO extractor, I used Apache3, and then you need can use "ADPCM Player v1.44h" to scan the .SCO files for each mission and it will pull out all of the SFX, Music and Dialogue - for cutscenes these are premixed so you won't be able to pull anything cleanly out of these!

These are all in stereo so on ADPCM you will need to set the interleave to 4000, set the frequency to 23000 and set the number of channels to 2.

Now here's the awkward bit! For most character dialogue these settings will miss the last .5s of 75% of the files. I have played with the settings on ADPCM but I cannot resolve this. The only solution is to extract these cut-off files as 1 channel files (Mono). This will give you the full audio file, BUT, the audio will loop. Most files will loop once however long files can loop 2-3 times. The only way to fix this is to open these files in Audacity and manually delete the looping segments.

This is a labour intensive process but even at its worst it'll only take a day or so - its mostly just boring!

In terms of the files there isn't much new stuff in here, but there's definitely a few nice bits of dialogue that don't play in game.

This eluded me for years so I hope it is of some use to others! One day hopefully we'll be able to extract everything else buried in this old game, but for now we've at least got something!

P.S If any clever clogs manage to break into the other files in this damn game they will have my thanks!

Cheers,
