## Post #1
- Username: Surestsafe
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 25, 2023 6:12 pm
- Post datetime: 2023-02-25T10:42:34+00:00
- Post Title: Star Wars: First Assault Audio

Hello, ive been trying to extract the sound from Star Wars: First Assault but its very strange, its an Unreal Engine 3 xbox 360 game and the audio is in .gap format (its a non-standard format, I think its upk in disguise but im not sure) Wwise Unpacker can get all of the voice line audio, but it cant get weapon sounds, music, foley, things like that, I noticed that when the audio file is renamed to .xxx (the format the rest of the game uses) its able to rip Explosion sounds, and can *detect* more sounds but is giving the error "Parse error: expected 0x42 fmt if vorb missing" 

This is the audio file: [https://drive.google.com/file/d/19L_Jmz ... share_link](https://drive.google.com/file/d/19L_JmzLcgVzCy0L9ghb7-fHpLuiP6zWv/view?usp=share_link)

Ive been messing with this for hours and it seems like the solution is right in front of my face, but I think it is beyond me.
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2023-02-26T23:01:08+00:00
- Post Title: Star Wars: First Assault Audio

It's a WWise audio archive.  If you delete the AKPK segment (i.e. everything from the start up to "BKHD"), rename the file to *.bnk, and then it'll load into Foobar/vgmstream.  At least, I couldn't get it to play with the AKPK section intact.
