## Post #1
- Username: AMort
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 19, 2020 1:54 am
- Post datetime: 2020-08-18T18:29:25+00:00
- Post Title: Fable Legends - Unknown Wwise .bnk files

Hello, good people of Xentax. I recently got ahold of audio files from the maligned (and now cancelled) Fable Legends, made with Unreal Engine 4, and I'm having extreme trouble getting at some of the sounds. It's contained within the Wwise .bnk file format, which from my research is normally easy to extract with programs like WW2Ogg, wwise-util, etc... except that some of the .bnks are quite small (as small as 1kb in some cases) and I cannot for the life of me open them with any of the usual programs.

Now, I can access most of the audio - the dialogue is mostly inside a "streams" folder as about 40000 .wem files, and SFX/music are in various larger .bnks in the main Audio folder (although all are unlabelled, and there seems to be no SoundBanksInfo.xml anywhere...?), but as for these particular smaller soundbank files, I just can't understand them! 

Thus, I ask for help. If anyone is experienced with wwise bnk files, and can somehow get the contents of these files to be readable, or point me in the right direction, I would greatly appreciate it. I have spent a few weeks now trying, poring over Wwise documentation and even dipping my toes into hex editing for the first time, and any progress would be amazing.

Here are three of the .bnk files I can't open, all should be similar as they're all associated with playable characters: 
[https://mega.nz/folder/KR0DCZSA#EX3p34K7qdEKU-hwBB0v4w](https://mega.nz/folder/KR0DCZSA#EX3p34K7qdEKU-hwBB0v4w)

If more files or folder structure are required, I'll happily provide them. Thanks in advance!
## Post #2
- Username: 0ther1
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Apr 30, 2020 10:56 am
- Post datetime: 2020-08-19T09:55:45+00:00
- Post Title: Fable Legends - Unknown Wwise .bnk files

Soundbanks contains various data, these ones does not include sounds, only data. As you mentioned, dialogues inside "streams" as they streamed, not embedded into soundbank.
## Post #3
- Username: AMort
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 19, 2020 1:54 am
- Post datetime: 2020-08-19T11:16:37+00:00
- Post Title: Fable Legends - Unknown Wwise .bnk files

> Reply from 0ther1 ↑Wed Aug 19, 2020 5:55 pm at Wed Aug 19, 2020 5:55 pm
>
> 
Soundbanks contains various data, these ones does not include sounds, only data. As you mentioned, dialogues inside "streams" as they streamed, not embedded into soundbank.

Ah, I assumed as much, as they look too small for any meaningful amount of audio. Do you have any idea of how to extract the data they store?
## Post #4
- Username: 0ther1
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Apr 30, 2020 10:56 am
- Post datetime: 2020-08-19T13:45:30+00:00
- Post Title: Fable Legends - Unknown Wwise .bnk files

Not sure that such tool exists, because why someone even needs wwise project settings and objects, these needed only for wwise sound engine. Though I needed them for structuring Doom Eternal sounds for easier search in thousands of number-named files, but in my case I didn't parsed whole soundbank data, only needed objects. You can see [here](https://wiki.xentax.com/index.php/Wwise_SoundBank_%28*.bnk%29) soundbank structure, it's not full and outdated though.
## Post #5
- Username: AMort
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 19, 2020 1:54 am
- Post datetime: 2020-08-19T14:52:38+00:00
- Post Title: Fable Legends - Unknown Wwise .bnk files

> Reply from 0ther1 ↑Wed Aug 19, 2020 9:45 pm at Wed Aug 19, 2020 9:45 pm
>
> 
Not sure that such tool exists, because why someone even needs wwise project settings and objects, these needed only for wwise sound engine. Though I needed them for structuring Doom Eternal sounds for easier search in thousands of number-named files, but in my case I didn't parsed whole soundbank data, only needed objects. You can see here soundbank structure, it's not full and outdated though.

Ah, yeah, I figured they were settings or something like that. I'm in much the same situation with a load of numbered sound files, so I guess I'd better learn how to parse their structure with a hex editor. I assume that's how you did it!
## Post #6
- Username: 0ther1
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Apr 30, 2020 10:56 am
- Post datetime: 2020-08-19T21:23:27+00:00
- Post Title: Fable Legends - Unknown Wwise .bnk files

It might be tough with hex editor only, much easier to automate it. With soundbanks you can group sounds by events, switches ans states (for music) using them, but these objects has only IDs. There might be some file that can help name them, in Doom Eternal there is file with event, switch and state names and their IDs from soundbanks.
## Post #7
- Username: AMort
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 19, 2020 1:54 am
- Post datetime: 2020-08-20T07:52:25+00:00
- Post Title: Fable Legends - Unknown Wwise .bnk files

> Reply from 0ther1 ↑Thu Aug 20, 2020 5:23 am at Thu Aug 20, 2020 5:23 am
>
> 
in Doom Eternal there is file with event, switch and state names and their IDs from soundbanks.

Hmm. Is that file called "soundbankinfo.xml" or something like that? I don't have anything but .bnks and .wems contained in my sound folders...
## Post #8
- Username: 0ther1
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Apr 30, 2020 10:56 am
- Post datetime: 2020-08-20T09:31:12+00:00
- Post Title: Fable Legends - Unknown Wwise .bnk files

I've never seen wwise somewhere else than new Doom games, in 2016 file is 'soundbanksinfo.events' in Eternal 'soundmetadata.bin'. Since soundbanks contains only event IDs, and events are called from game, it would be convenient to call them by names, like it does in Doom games. I assume in Unreal Engine might be something similar.
