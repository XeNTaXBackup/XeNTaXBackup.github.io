## Post #1
- Username: Atrov
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 14, 2015 10:49 am
- Post datetime: 2015-08-16T04:01:14+00:00
- Post Title: Rabbids Go Home (PC/Wii) (Ubisoft)

I'm having some trouble with the audio files from this game. The Wii and PC version format the audio differently. On PC, the files have a RIFF WAV header, but after that is an OGG header. After removing the WAV header the file will play in any player that supports OGG, but the audio stutters. It sounds like a timing/syncing issue, but I don't have much experience with audio files so I can't figure out what is wrong.

As for the Wii version, the audio isn't OGG. There is only a WAV header. The format ID in the header is 0x5050, so that doesn't help at all. Importing into audacity as Signed 8-bit PCM will result in recognizable music or sound effects, but distorted and with extremely heavy static.

I have already tried DecUbiSnd and vgmstream. DecUbiSnd recognizes the OGG data in the PC files, but nothing from the Wii version. The files have a .sns extension, but they aren't the type expected by vgmstream.

[http://www87.zippyshare.com/v/tWDNrwEN/file.html](http://www87.zippyshare.com/v/tWDNrwEN/file.html)
I've included a zip of the PC and Wii audio, a track from the OST referencing what one of the tracks should sound like, as well as a text file of my analysis and notes on the Wii version of the files. The first 32 bytes can be removed from each file. They are extra data left from the archive the files were in. Any help with this would be much appreciated.
## Post #2
- Username: Atrov
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 14, 2015 10:49 am
- Post datetime: 2015-08-18T00:48:50+00:00
- Post Title: Rabbids Go Home (PC/Wii) (Ubisoft)

[http://www55.zippyshare.com/v/5m9B1yta/file.html](http://www55.zippyshare.com/v/5m9B1yta/file.html)
Here's what the PC version audio sounds like when the extension is changed to ogg. It seems to stutter exactly once per second. Could it be a symptom of interleaving? If so, how could I fix it?
