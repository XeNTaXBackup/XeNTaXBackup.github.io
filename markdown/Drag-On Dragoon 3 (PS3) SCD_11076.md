## Post #1
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2013-12-25T08:50:06+00:00
- Post Title: Drag-On Dragoon 3 (PS3) *SCD

All music files end with SCD.XXX extension and apparently this SCD extension was used in earlier Square Enix games such as FFXIII and FFXIII-2. There's also a mention that vgmstream was eventually made to support FFXIII's SCD files, so I tried that but vgmstream failed to open scd. 

I hope this isn't some new encrypted variation of a previously used format, but who knows.
Maybe this is cake for someone, please have a look, here's a sample: 
MUSIC_BOSS_B01A_A_SCD.XXX (2 MB)
[https://mega.co.nz/#!hgMFlQ5B!M1zve3ECJ ... V9tdi-YPkc](https://mega.co.nz/#!hgMFlQ5B!M1zve3ECJgP5oYDWa-JCojofH1w7wqT7-V9tdi-YPkc)
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2013-12-30T04:04:17+00:00
- Post Title: Drag-On Dragoon 3 (PS3) *SCD

Funky, this has 48 kHz MP3 but the scd header says 47999 Hz. vgmstream checks for agreement here before going off and decoding, I've added a special case for this situation in r1019. Still needs to be renamed .scd to be recognized.

btw I assume this is a really weird track, silent until almost 1 minute in and then some weird vox, but it seems to loop properly and all.
## Post #3
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2013-12-30T11:01:21+00:00
- Post Title: Drag-On Dragoon 3 (PS3) *SCD

Thank you for adding support to this, hcs, your work is very much appreciated. 
Indeed this track is strange, but it's not the only one. Pretty much all boss battle themes have side A and B, and A is always this kind of distorted vox that starts after 1 min in. They look like this: 


My guess is that it's a dialog that plays out during each boss battle. Apparently it goes simultaneously with the music and has the same length as the bgm track.
For some reason it must've been encoded in a different way compared to the rest of the voice tracks in the game, as I checked and was able to convert regular VO tracks with r1019 just fine. The important thing is that the actual bgm tracks (part B) also convert just fine.

Here a couple more samples if you want to take a look. Added youtube links of gameplay to demonstrate how those boss battle tracks and dialogs sound in action.

MUSIC_BOSS_B02A_A_SCD.scd
MUSIC_BOSS_B02A_B_SCD.scd
[https://mega.co.nz/#!59VwXZwb!Ez5zJ2llR ... vr8WrSNri4](https://mega.co.nz/#!59VwXZwb!Ez5zJ2llReDTMvds5DnrRDasmHkYpn9a1vr8WrSNri4)
[http://www.youtube.com/watch?v=t5T_blOBPMg](http://www.youtube.com/watch?v=t5T_blOBPMg)

MUSIC_BOSS_B04A_A_SCD.scd
MUSIC_BOSS_B04A_B_SCD.scd
[https://mega.co.nz/#!thNmzahK!dnEaPgHS_ ... 0hi4fmKrtY](https://mega.co.nz/#!thNmzahK!dnEaPgHS_n9zvao87lMPhFDjb1Rqbi5zE0hi4fmKrtY)
[http://www.youtube.com/watch?v=vjhFSFge7QY](http://www.youtube.com/watch?v=vjhFSFge7QY)
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2013-12-30T18:03:21+00:00
- Post Title: Drag-On Dragoon 3 (PS3) *SCD

I assume it comes into play with some kind of powerup, though I didn't notice it in the videos you linked. Since the battles are themed around a cry/song that phases into the battle music, it makes some sense for this to be a babble.
[edit]
Ah yeah, kicks in around 6:30 in this video:

[http://www.youtube.com/watch?v=BsNmMePuM1c#t=6m26s](http://www.youtube.com/watch?v=BsNmMePuM1c#t=6m26s)
## Post #5
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2013-12-30T20:15:55+00:00
- Post Title: Drag-On Dragoon 3 (PS3) *SCD

Oh wow you right it does kick in in that distorted form. Must be some powerup indeed. Good catch, it means all files are converted properly.
