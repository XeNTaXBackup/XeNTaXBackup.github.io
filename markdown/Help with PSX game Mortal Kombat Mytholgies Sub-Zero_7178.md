## Post #1
- Username: MusicNerd
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 14, 2011 2:48 pm
- Post datetime: 2011-08-14T07:07:50+00:00
- Post Title: Help with PSX game Mortal Kombat Mytholgies: Sub-Zero

Hi  Guys

Great forums! 

I have recently tried to extract all the music from MKM:SZ on Playstation 1. I am usally very good with finding the right tool for the job, I will download anything and try it when im on a mission to rip music. But I don't know enough about hex and offsets so I am limited to use what is only available. After much messing about I believe MKM:SZ uses some sort of custom format as if you scan with an CDXA scanner .xa format it only returns the audio from the movies. I have tried a few various other tools like PSXPlay and a shitload of BMS scripts but im stuck and need you help to rip this awesome soundtrack, as no one has ripped it and it needs to be made available to the MK fans in CD qualuty  The filetree on the disc has no XA folders at all. The music is hidden on the disc someware. If it was in a file I can scan the file, but so far I can only scan the .iso image or the original disc I have. Just to check I wasn't doing things wrong I ripped Lethal Enforcers XA folder and MK4 and both worked a treat but MKM:SZ is a mystery

breakdown of the filetree:

DOZER.BIN       - 1KB
NOXCUSES.BIN - 29,297KB
SLES_010.20    - 810KB
SYSTEM.CNF     - 1KB
WARNING.TIM   - 321KB
CHARS       - 2.13MB (.bin files)
CHARS2     - 2.61MB (.bin files)
LCDS         - 1.93MB (.lcd files) (.wav files inside)
LCDS2       - 2.72MB (.lcd files) (.wav files inside)
LEVELS      - 7.64MB (a folder for each level in the game containing .bin,.lvl,tsq,.txd and .wal files) 
LSDS         - 353KB (.lsd files 1x .wmd file)
LSDS2       - 198KB (.lsd files)
MOVIES     - 400MB (.str movies)
OVERLAYS - 226KB (.bin files demo data and .ovr files)

Also when playing in ap laystation emulator the emulator "raw envolope data streaming" so i thought the music might be on there as RAW ADPCM but I did try a few bms scripts and tools and found nothing

Thanks Guys
## Post #2
- Username: MusicNerd
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 14, 2011 2:48 pm
- Post datetime: 2011-08-14T07:44:08+00:00
- Post Title: Help with PSX game Mortal Kombat Mytholgies: Sub-Zero

Oh, if you take a look inside the .bin file with Hex Workshop you can clearly see it is uses CD-XA Format, but maybe only for the videos not the music?

Offset: 0009713 43 44 2D 58 41 30 30 31 "CD-XA001"
## Post #3
- Username: MusicNerd
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 14, 2011 2:48 pm
- Post datetime: 2011-09-28T15:06:09+00:00
- Post Title: Help with PSX game Mortal Kombat Mytholgies: Sub-Zero

Bumpn' makes me fell good...
## Post #4
- Username: MusicNerd
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 14, 2011 2:48 pm
- Post datetime: 2012-02-12T14:49:38+00:00
- Post Title: Help with PSX game Mortal Kombat Mytholgies: Sub-Zero

Really need your help with this guys, I know that someone has ripped this soundtrack since making the first post but I would love to know how. I have used every single PSX tool under the sun

VGMToolbox
PSMPlay
PSXMC
Easy CD-DA Extractor
And soooooo many more. 

No matter what, it only ever finds .xa audio for the .str movies.
There is no CD-DA tracks I can find. So where is the music coming from?
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-02-17T16:37:33+00:00
- Post Title: Help with PSX game Mortal Kombat Mytholgies: Sub-Zero

Wait some hours and I'll take a look. Ripped about 20-30 PSX games so I recognize most structures.
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-02-17T17:17:43+00:00
- Post Title: Help with PSX game Mortal Kombat Mytholgies: Sub-Zero

As I expected. The game uses the LCD/LSD music format. It's a midi format that isn't supported by anything I know. The rip had to be done via line-in recording.
## Post #7
- Username: MusicNerd
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 14, 2011 2:48 pm
- Post datetime: 2012-07-05T06:31:41+00:00
- Post Title: Help with PSX game Mortal Kombat Mytholgies: Sub-Zero

Alpha: Thanks so much for your reply. I just saw it. I found someone who said he ripped it and the quality is flawless no hiss it doesn't sound recorded, is it possible he found a way to do it somehow?
## Post #8
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-07-05T21:21:52+00:00
- Post Title: Help with PSX game Mortal Kombat Mytholgies: Sub-Zero

Send me a file and I'll tell you if it looks recorded or not.  You can't normally hear the difference, you'll have to analyze the stream.
## Post #9
- Username: MusicNerd
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 14, 2011 2:48 pm
- Post datetime: 2012-07-10T16:25:35+00:00
- Post Title: Help with PSX game Mortal Kombat Mytholgies: Sub-Zero

Sure I have attached one of the songs to this post, and here is the link to the forum where he says he ripped it - *link removed*

*link removed*
## Post #10
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-07-10T21:10:07+00:00
- Post Title: Help with PSX game Mortal Kombat Mytholgies: Sub-Zero

That source is too compressed to say if it's recorded or not. Else, please remove the link to the forum to make the admin happy.
## Post #11
- Username: MusicNerd
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 14, 2011 2:48 pm
- Post datetime: 2012-07-13T07:40:06+00:00
- Post Title: Help with PSX game Mortal Kombat Mytholgies: Sub-Zero

Links removed. All I can say is it's really very clear, it sounds to me like a direct rip. Usally when it's recorded and Asembled it sounds like ass not only that but MKM:SZ has no sound test, and he has every single track in the game, at this level of quality.
