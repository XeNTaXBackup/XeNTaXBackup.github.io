## Post #1
- Username: klitron
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 24, 2016 1:30 am
- Post datetime: 2016-06-15T21:44:29+00:00
- Post Title: Splinter Cell Blacklist .uax

Hi, guys!

I have trouble with understanding this audio format, and maybe somebody can help me.

Story starts with wanting to play Splinter Cell Blacklist on Xbox360. But, I have weird habit - play in game with original audio and localization subtitles.
So, we have US/Europe Release with English, French and Spanish audio; and few more subtitles. And Russian Release with only Russian audio and subtitle text.

First step:
I'm extract from CD Image every file in specific name folder and compare this with WinMerge.
Program show difference only in defalut.xex, Uplaybrowser.xex and loc-...umd files.

Second step:
Simply insert in US release loc-rus.umd instead of some other loc-...umd file.
In result - game have Tag-text instead of some Human-language.

Third step:
I'm install PC version for more quick modding, receive result and experimentation trys.
First of all, I'm simple get two .uax files and rename them. (English to Russian, Russian to English)
Starting game, and mission, for what I switch files, don't have voices at all.

With DecUbiSndGui and VGMToolbox i can see and extract content from .uax file. But I don't undestand how work navigation in this file.
I assume it's archive with audio streams. But navigation with offset address seems difficult.

Also, with offzip I can extract data from loc-...umd file, but it's not contains any offset address or language pointer; only HUD text.

Again, maybe somebody can help me understand where is navigation happening.

Attaching Xbox360 Files: [https://drive.google.com/open?id=0BzxWU ... Xh5VzF0YTQ](https://drive.google.com/open?id=0BzxWUfhdXXGmOXZvZXh5VzF0YTQ)
## Post #2
- Username: klitron
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 24, 2016 1:30 am
- Post datetime: 2016-06-21T16:57:46+00:00
- Post Title: Splinter Cell Blacklist .uax

For history:
After some research I found out that navigation on sound files (.uax) happened from Pec-Main.umd and Pec-ADV.umd files. These files contains addresses on header data in .uax file, which contains offsets on audio data.
So, now I can rename files English and Russian and rewrite offsets in .uax header.
But these can be troublemaking for Xbox360 version. And I just repack .uax files with needed offsets.

So, my problem solved.
## Post #3
- Username: loopypalm
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 06, 2016 8:01 am
- Post datetime: 2017-05-14T00:38:03+00:00
- Post Title: Splinter Cell Blacklist .uax

hi klitron
now i want to play Splinter Cell Blacklist on PC with Japanese audio
i have the PS3 version and the sound files but i don't know how to proceed ?
i copy them to "data\Sounds\PC" and rename eatch one to ENGLISH but there is no sound and the game crash even sometimes
what do you suggest ?
