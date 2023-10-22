## Post #1
- Username: JasteRogue
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 22, 2018 8:06 am
- Post datetime: 2018-10-22T00:08:23+00:00
- Post Title: Resident Evil 4 Xbox 360 - RIFFP Wave

Hi, I recently extract the ".xwb" files in the Resident Evil 4 Xbox 360 and inside them have many wav files, but I cant listen. I open through Hex Edit, the compress is: RIFFP seek. 
Anyone can convert the audio to normal Wav?

In UHD Version of Steam, the format is the same, but the compress is very different.

EDIT:

.Wav of UHD PC Version (5MB):  [https://www.mediafire.com/file/sm6t1q72 ... f.wav/file](https://www.mediafire.com/file/sm6t1q727ddo2qb/000000af.wav/file)
The same .Wav of XBOX 360 Version (800KB):  [https://www.mediafire.com/file/7989xnna ... f.wav/file](https://www.mediafire.com/file/7989xnna75h9f3d/000000af.wav/file)
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2018-10-22T08:52:07+00:00
- Post Title: Resident Evil 4 Xbox 360 - RIFFP Wave

I find it really odd that you say the 5MB file is from the Xbox 360 version. Because that's just standard PCM WAV and can be played with any audio player. That format isn't that common on Xbox 360. The second file (800KB) is however as it's encoded with XMA which is the Xbox 360's native audio format and is found across most of the platforms titles. Are you sure you didn't accidently mix them up?


Anyway...

[vgmstream](https://github.com/bnnm/vgmstream-builds/raw/master/bin/vgmstream-latest-test-u.zip) can play back the 800kb file but it does not play the full track, it only plays the first second of it.

However, when I manually stripped away the old XMA header and added a new XMA header, it did playback the full track of 0:39 with vgmstream.

[Submit this example and a few more examples if you could to bnnm over on HCS](https://hcs64.com/mboard/forum.php?showthread=8687&lastpage).

He might be able to fix that up for you within vgmstream so you don't have to manually remove and then add an XMA header to the files.
## Post #3
- Username: JasteRogue
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 22, 2018 8:06 am
- Post datetime: 2018-10-22T20:38:23+00:00
- Post Title: Resident Evil 4 Xbox 360 - RIFFP Wave

Thanks for reply
Sorry, I inverted, i fixed now the post

Actually I need to find some way to edit these Wav to reinsert in the game.

I have a brazilian fandub project of the game (already it was released for PS2, PC Ubisoft and UHD STEAM) and now I intend to release also for Xbox 360. Do you know how to re-create the same files (with this same XMA compression)?

Example of Fandub: (PS2 and UHD Version):

[https://www.youtube.com/watch?v=oWbDS4YFG7M&t=2s](https://www.youtube.com/watch?v=oWbDS4YFG7M&t=2s)

[https://www.youtube.com/watch?v=0-nZtQBGf8g&t=7s](https://www.youtube.com/watch?v=0-nZtQBGf8g&t=7s)
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2018-10-22T21:12:56+00:00
- Post Title: Resident Evil 4 Xbox 360 - RIFFP Wave

[XMA2 Encode](https://mega.nz/#!JRdnnSoJ!a87sMn41pPe2it7nEiVXnA9NTGe_8zAyTwUr3z3xNn0)

Here is three different versions of XMA2 Encode, the encoder from the Xbox 360 SDK. These can convert PCM WAV files into XMA files.
## Post #5
- Username: JasteRogue
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 22, 2018 8:06 am
- Post datetime: 2018-10-25T20:48:55+00:00
- Post Title: Resident Evil 4 Xbox 360 - RIFFP Wave

Thanks a lot for the help
