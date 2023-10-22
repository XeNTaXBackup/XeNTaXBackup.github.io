## Post #1
- Username: bVictor
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 17, 2016 10:27 am
- Post datetime: 2017-02-17T13:40:26+00:00
- Post Title: [PS3] Sengoku Musou 2 HD - TRANSLATION HELP [JP->EN]

Hello everyone!

Introduction:
I finally acquired the HD remaster of one of my most favorite games, Samurai Warriors 2, but it's in Japanese...
I want to translate it in English, primarily the SUGOROKU minigame in Extreme Legends, since that's my favorite thing ever. 
And I would like to ask anyone interested to help me out to do so.

Summary:
Here is a description of "PS3_GAME/USRDIR/" content:

Folder "CMN_FILE_PS3": 
Cutscenes (../movie/*.pam)
Folders "EMP_FILE_PS3" & "EX_FILE_PS3": For Empires and Extreme Legends respectively.

Background Music (../bgm/bgm.bin)
Shader Effects (../SHADER/Effect/*.vpo|*.fpo)
 Folders "EMP_LINKDATA_PS3" & "EX_LINKDATA_PS3": For Empires and Extreme Legends respectively.

LINK_SEBANK: .BDX & .HDX
LINKDATA_ANS: .IDX & .LNK
LINKDATA_BNS: .IDX & .LNK
Folder "FILE_PS3":

"LANG_JP" Folder containing textures for the Font, Logos, Loading, Launcher and some CmnParts; and a "CmnPartsLayout.bin"
Shader Effect: "../SHADER/UI/OverwriteAlpha.fpo"
 Folder "LINKDATA_PS3":
File "LINKDATA.A"

Main data is contained in LINKDATA_[AB]NS.LNK and the "LINKDATA.A" file.

Text:
My guess is that the text is in the "LINKDATA_BNS.LNK" or "LINKDATA.A".
But I'm still clueless about how to find them.
I really need some help here!

Audio:
LINKDATA_ANS.LNK contains all the audio files (except the background music which is in "USRDIR\EX_FILE_PS3\bgm\bgm.bin"). It has ATRAC3 .wav files starting from the top, and being separated by blocks of "00" 0xX9C (about so, they vary from what I've noted from 0x19C to 0x59C) in size 'til the end including 0x19C more zeros at the bottom. WAVs are aligned with blocks of "01" at the end of files.

I was able to extract english audio from PS2 version with PSound v2.01. But they're encoded as PCM instead of ATRAC3.
I tried to convert them to ATRAC3 with Goldwave, but I couldn't set the correct "Bit Rate" and the only option was Stereo, while original Japanese audio files are mono.

I added "01" at the end of converted audio files to make them match the size of the Japanese ones. It did not affect them in any other way except the filesize. Then, I used HEX to replace the audio in the LNK and then imported it to PS3, the game played but the audio files were NOT played when they were supposed to (i.e. characters would not speak, yet the text would appear). I attached the 3 MediaInfos at the bottom and as you can see the difference is big, so that's one problem.

Also, the game checks the EXTRAS (since it copied the data files to HDD) for corruption, which triggers when the LNK size is different (since I did not find the size in the file nor the "LINKDATA_ANS.IDX" (which is in hex: "L4MS" and the rest is zeros, 0x300 in size) it might be comparing it with the file on the disk, so the sollution (and a way to test that theory) is to replace the file in both, the EXTRAS and on the disk)

Other:
The font is in "../USRDIR/FILE_PS3/LANG_JP/Font.g1t"
I opened it with TextureFinder, though distorted (probably I was doing something wrong), but I saw shapes of letters. There are english letters, for some writing in game like "PRESS START" though as of I know all the Japanese (or most) will have to be replaced. I'd need some help with editing it though.

Resources:
Japanese ATRAC3 WAVEs MediaInfo:

```
Complete name               : E:\Users\bVictor\Desktop\Samurai Warriors II\DATA\HD\Audio\LINKDATA_ANS.LNK [JAPANESE]\JAP_00000 (Yukimura Sanada returns to battle).wav
Format                      : Wave
File size                   : 24.6 KiB
Duration                    : 2 s 0 ms
Overall bit rate            : 101 kb/s

Audio
Format                      : Atrac3
Codec ID                    : FFFE / 58CB7144-23E9-BFAA-A119-FFFA01E4CE62
Duration                    : 2 s 0 ms
Bit rate                    : 96.0 kb/s
Channel(s)                  : 1 channel
Channel positions           : Front: L
Sampling rate               : 48.0 kHz
Compression mode            : Lossy
Stream size                 : 24.5 KiB (100%)

```

English PCM WAVEs MediaInfo:

```
Complete name               : E:\Users\bVictor\Desktop\Samurai Warriors II\DATA\PS2\Audio\LINKDATA.ANS\LINKDATA_00000 (Yukimura Sanada returns to battle).wav
Format                      : Wave
File size                   : 86.2 KiB
Duration                    : 2 s 0 ms
Overall bit rate mode       : Constant
Overall bit rate            : 353 kb/s
Writing application         : PSound

Audio
Format                      : PCM
Format settings, Endianness : Little
Format settings, Sign       : Signed
Codec ID                    : 1
Duration                    : 2 s 0 ms
Bit rate mode               : Constant
Bit rate                    : 352.8 kb/s
Channel(s)                  : 1 channel
Sampling rate               : 22.05 kHz
Bit depth                   : 16 bits
Stream size                 : 86.1 KiB (100%)

```

English PCM -> ATRAC3 convert attemp with GoldWave MediaInfo:

```
Complete name               : E:\Users\bVictor\Desktop\Samurai Warriors II\DATA\HD\Audio\LINKDATA_ANS.LNK [ENGLISH]\ENG_00000 (Yukimura Sanada returns to battle).wav
Format                      : Wave
File size                   : 24.6 KiB
Duration                    : 1 s 904 ms
Overall bit rate            : 106 kb/s
Writing application         : PSound
IsTruncated                 : Yes

Audio
Format                      : Atrac3
Codec ID                    : 270
Codec ID/Hint               : Sony
Duration                    : 1 s 904 ms
Bit rate                    : 66.1 kb/s
Channel(s)                  : 2 channels
Sampling rate               : 44.1 kHz
Compression mode            : Lossy
Stream size                 : 15.4 KiB (63%)

```

I created a torrent file to share all the data files here (One for each version). You may find them in the .zip archive in the attachments.

Thank you in advance.
[DATA_FILES.zip](https://xentaxbackup.github.io/file/12473_DATA_FILES.zip)
## Post #2
- Username: offering7866
- Rank: advanced
- Number of posts: 59
- Joined date: Fri Feb 24, 2017 2:16 pm
- Post datetime: 2017-02-24T06:30:55+00:00
- Post Title: [PS3] Sengoku Musou 2 HD - TRANSLATION HELP [JP->EN]

Did you at least identify the location of the game's text using Hex Workshop? Sometimes, Japanese fonts will not show up at all for some reason.
## Post #3
- Username: bVictor
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 17, 2016 10:27 am
- Post datetime: 2017-02-24T14:22:33+00:00
- Post Title: [PS3] Sengoku Musou 2 HD - TRANSLATION HELP [JP->EN]

> Reply from offering7866
>
> Did you at least identify the location of the game's text using Hex Workshop? Sometimes, Japanese fonts will not show up at all for some reason.

I couldn't find any texts, at least yet.
But, there is a separate file for the font texture and around the bottom of the "EX_LINKDATA_PS3/LINKDATA_BNS.LNK" something looking like a font map in utf8. I'm confident the text is located it the same file.

Also, I couldn't find any kind of text in english versions of the game either, so my guess is that they might be in some kind of proprietary files inside of that package.
## Post #4
- Username: offering7866
- Rank: advanced
- Number of posts: 59
- Joined date: Fri Feb 24, 2017 2:16 pm
- Post datetime: 2017-02-24T16:53:22+00:00
- Post Title: [PS3] Sengoku Musou 2 HD - TRANSLATION HELP [JP->EN]

It should be possible to see most if not all of the text from the PS2 version using Hex Workshop. By the way, are you also planning on replacing the Japanese voice banks with the English ones?
## Post #5
- Username: bVictor
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 17, 2016 10:27 am
- Post datetime: 2017-02-24T17:03:17+00:00
- Post Title: [PS3] Sengoku Musou 2 HD - TRANSLATION HELP [JP->EN]

> Reply from offering7866
>
> It should be possible to see most if not all of the text from the PS2 version using Hex Workshop. By the way, are you also planning on replacing the Japanese voice banks with the English ones?

I'll check again in a minute for the PS2 version, to be sure i didn't miss anything.

At first I thought to replace only text, but then especially since I was able to extract both English and Japanese audio files and was actually able to replace the Japanese ones, I thought, why not. 

THOUGH, I have two problems:
1. I can't seem to convert the English audio to the same format as the Japanese one, ATRAC3 FFFE. It wouldn't play the file the way I converted it with GoldWave.
2. The game won't accept the file if the size is different, so the converted file should be <= than the Japanese and then I added "01" alignment at the end to even them out. The problem here is that some English lines are longer so, to make them smaller, I had to lower the quality, which doesn't sound well. It doesn't seem to have any pointers, since audio files start from the top, first thing in the file is WAVE header.

UPDATE:

You're right! I just found the text, like: "Nobunaga... One day, your head will be mine" and "Don't worry. You haven't seen the last of me yet" in "LINKDATA.BNS" on the PS2 version using UTF8.

I used HxD before which didn't have UTF8 as an option, but after you mentioned it, I tried Hex Workshop and there it is. SO, Japanese text should be scattered the same way.
Though, I'm still not sure, even if I find it, how to align it or to change the size, since that would break all the pointers, so maybe an extraction script is necessary.
## Post #6
- Username: offering7866
- Rank: advanced
- Number of posts: 59
- Joined date: Fri Feb 24, 2017 2:16 pm
- Post datetime: 2017-02-24T19:08:28+00:00
- Post Title: [PS3] Sengoku Musou 2 HD - TRANSLATION HELP [JP->EN]

Well, that's good to hear.  Have you considered contacting some of the more experienced script writers who've worked on modding PS titles? Perhaps they can help you out with this project.
## Post #7
- Username: bVictor
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 17, 2016 10:27 am
- Post datetime: 2017-02-24T19:10:56+00:00
- Post Title: [PS3] Sengoku Musou 2 HD - TRANSLATION HELP [JP->EN]

> Reply from offering7866
>
> Well, that's good to hear.  Have you considered contacting some of the more experienced script writers who've worked on modding PS titles? Perhaps they can help you out with this project.

Do you know anyone who could help with the script?
## Post #8
- Username: offering7866
- Rank: advanced
- Number of posts: 59
- Joined date: Fri Feb 24, 2017 2:16 pm
- Post datetime: 2017-02-24T19:16:16+00:00
- Post Title: [PS3] Sengoku Musou 2 HD - TRANSLATION HELP [JP->EN]

> Reply from bVictor
>
> offering7866 wrote:Well, that's good to hear.  Have you considered contacting some of the more experienced script writers who've worked on modding PS titles? Perhaps they can help you out with this project.

Do you know anyone who could help with the script?
Unfortunately, I can't say I do since I'm recently new here, so you're better off using the search function to find those people yourself.
## Post #9
- Username: bVictor
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 17, 2016 10:27 am
- Post datetime: 2017-02-24T19:18:47+00:00
- Post Title: [PS3] Sengoku Musou 2 HD - TRANSLATION HELP [JP->EN]

> Reply from offering7866
>
> bVictor wrote:offering7866 wrote:Well, that's good to hear.  Have you considered contacting some of the more experienced script writers who've worked on modding PS titles? Perhaps they can help you out with this project.

Do you know anyone who could help with the script?
Unfortunately, I can't say I do since I'm recently new here, so you're better off using the search function to find those people yourself.

Alright, thank you.
## Post #10
- Username: EcosEstudio
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 31, 2022 1:32 pm
- Post datetime: 2023-02-10T10:17:18+00:00
- Post Title: [PS3] Sengoku Musou 2 HD - TRANSLATION HELP [JP->EN]

bVictor, were you able to edit the Japanese text into English?
