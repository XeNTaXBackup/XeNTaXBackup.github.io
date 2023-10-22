## Post #1
- Username: Deathand
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 13, 2011 4:51 am
- Post datetime: 2017-07-12T17:52:57+00:00
- Post Title: Prisoner of Ice - Sound Effects (.KRO)

Hello there, though this is my first post, i've been reading this site quite some time ago and i love it. Perhaps any of the audio experts here can help me with this. This game has the SFX and music stored in a file called ksound.kro. The music is easy to extract since it's simply a Raw PCM Unsigned 8 Bit, 22050 Hz, Mono. Now the strange part is that the SFX (the sfx comes first then the music) is in some unknown compressed format or some thing like that because i can't find a way to play them :/ If anyone can try to make them playable, it would solve more than 20 years of mystery ^__^
[Here](https://mega.nz/#!5yQAHAST!OcF6Jaw9OIrnMrdj6zYGhZvRLbrXbTNUAIGmpoRiGh8) is the file if anyone wanna try out, thanks much!
## Post #2
- Username: cxt
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 20, 2014 10:20 pm
- Post datetime: 2017-09-25T17:06:13+00:00
- Post Title: Prisoner of Ice - Sound Effects (.KRO)

Looked at this format long time ago (in 2010 IIRC). Most of the files packed with the deflate algo.
Note that some .WAV files starts with some "EDITLS" block, so use .WAV ripping tool on top of the unpacked files to extract only .WAV part.
This is an [QuickBMS script](http://forum.xentax.com/viewtopic.php?f=13&t=4450).

krounpak.bms:

```
# (c) CTPAX-X Team 2017
# http://www.ctpax-x.org/

ImpType Standard

IDString "Burp"

Get FileCount Long

For I = 1 To FileCount
  Get FileSize Long
  Get PackSize Long
  Get ZeroData Long
  Get FileOffs Long
  Get PackType Long

  String FileName p= "%08d.dat" I

  If PackType = 0
    ComType copy
    Log FileName FileOffs PackSize
  Else
    ComType deflate
    Clog FileName FileOffs PackSize FileSize
  EndIf

Next I
```
## Post #3
- Username: Deathand
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 13, 2011 4:51 am
- Post datetime: 2018-06-24T19:46:54+00:00
- Post Title: Prisoner of Ice - Sound Effects (.KRO)

Sry for the late reply T_T Indeed it works, i really appreciate it  in fact, while digging through the files, i found some unused things that never before i found (not including one particular song that i ripped with dragon unpacker years ago) Thanks for your time
