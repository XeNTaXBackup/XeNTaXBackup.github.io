## Post #1
- Username: WSSDude
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 26, 2015 6:49 pm
- Post datetime: 2023-04-05T21:29:23+00:00
- Post Title: Glacier 1 Audio Tool

Glacier 1 Audio Tool

Supported for import:
Hitman: Codename 47 (IDX/BIN pairs)
Hitman: Silent Assassin (WHD/WAV pairs + streams.wav)
Hitman: Contracts (WHD/WAV pairs + streams.wav)
Supported for export:
Hitman: Codename 47 (IDX/BIN pairs)
Hitman: Silent Assassin (WHD/WAV pairs + streams.wav)
Hitman: Contracts (WHD/WAV pairs + streams.wav)
Hitman: Blood Money (WHD/WAV pairs + STR)
Features:
Supports multiple Glacier 1 games (see list of supported formats and games above)
Automatically converts data to desired format on import
Ability to show modified entries in archives thanks to original records caching
Currently 2 supported languages - English and Czech
Read about features in more detail in README.md
Requires VS2022 Visual C++ Redistributable (x64) to work!
[https://aka.ms/vs/17/release/vc_redist.x64.exe](https://aka.ms/vs/17/release/vc_redist.x64.exe)

Source [https://github.com/WSSDude/Glacier1AudioTool](https://github.com/WSSDude/Glacier1AudioTool)
Version 1.2.1 [https://github.com/WSSDude/Glacier1Audi ... /tag/1.2.1](https://github.com/WSSDude/Glacier1AudioTool/releases/tag/1.2.1)
## Post #2
- Username: WSSDude
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 26, 2015 6:49 pm
- Post datetime: 2023-04-10T08:26:15+00:00
- Post Title: Glacier 1 Audio Tool

I wanted to update wiki pages about the formats this tool works with (*.whd/*.wav), but I cant register (error says new users are not allowed to register atm...)

Would there be a chance for an exception? Feel like it is a shame it has incomplete info when I believe I know a lot about the format and differences between other Glacier 1 games.
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-04-10T11:29:19+00:00
- Post Title: Glacier 1 Audio Tool

Wiki is currently broken (missing styles, broken registration etc.), so you can send me info by PM or paste it in this topic and I will update the wiki article for you.
## Post #4
- Username: helendam
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 15, 2023 3:17 pm
- Post datetime: 2023-04-15T07:24:45+00:00
- Post Title: Glacier 1 Audio Tool

thank you for share
## Post #5
- Username: WSSDude
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 26, 2015 6:49 pm
- Post datetime: 2023-07-17T12:13:50+00:00
- Post Title: Glacier 1 Audio Tool

Updated to new version and rebranded from Hitman Audio Tool to Glacier 1 Audio Tool. 

Latest release has some bugfixes, new layout, a lot of QoL improvements and most of all - fully working export for Hitman Blood Money!
Exports should be as perfect as they get and should be the best results from all the tools and scripts currently available.

Exports respect boundaries of data (many of the scripts and existing tools did not), should properly handle WAV data prepended with LIPs (practically everything ignored this aspect of the files), should properly handle aliased WAV data offsets (another pitfall no tool exported properly) and more.

It also performs conversion to more easily playable PCM S16 format, as game uses odd sample rates as form of compression (verified all of the data is correct, many players have issues with such data though hence the conversion). Conversion can be turned off in options. By default, only WAV files with odd sample rates are converted, as OGG seems to have better support for these. OGG files can also be automatically converted though if user selects appropriate setting.

It also has support for any import format libsndfile is able to import (everything gets converted on the background to PCM S16 stream game understands in case of unknown format to game).

Overall, huge release with tons of changes.

I also included some basic docs in the repository documenting the formats. They are very barebones, I plan to rewrite them to nicer format. They should be used as reference when someone wants to make their own decoders/encoders.
## Post #6
- Username: WSSDude
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 26, 2015 6:49 pm
- Post datetime: 2023-07-17T18:25:28+00:00
- Post Title: Glacier 1 Audio Tool

> Reply from ikskoks ↑Mon Apr 10, 2023 7:29 pm at Mon Apr 10, 2023 7:29 pm
>
> 
Wiki is currently broken (missing styles, broken registration etc.), so you can send me info by PM or paste it in this topic and I will update the wiki article for you.

Format docs for STR and WHD+WAV pair specifically for Hitman Blood Money primarily for export purposes (along with some writeup on format details and parsing algorithm I used and verified works as intended) can be found here:
[STR](https://github.com/WSSDude/Glacier1AudioTool/blob/main/docs/HitmanBloodMoney/Formats/STR.h) 
[WHD+WAV pairs](https://github.com/WSSDude/Glacier1AudioTool/blob/main/docs/HitmanBloodMoney/Formats/WHD%2BWAV.h)

I'm planning on slowly writing the rest as I once mentioned, already have bits-and-pieces of some other formats written in the repo.
## Post #7
- Username: WSSDude
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 26, 2015 6:49 pm
- Post datetime: 2023-07-30T16:19:51+00:00
- Post Title: Glacier 1 Audio Tool

Thanks to some feedback on ReHitman Discord, I found and fix some issues with exported Hitman: Blood Money data. Updated the tool, I hope it should now correctly export everything.

[https://github.com/WSSDude/Glacier1Audi ... /tag/1.2.1](https://github.com/WSSDude/Glacier1AudioTool/releases/tag/1.2.1)

Updated links also in OP.
