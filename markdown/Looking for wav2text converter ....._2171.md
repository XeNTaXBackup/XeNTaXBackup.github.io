## Post #1
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-10-25T14:58:31+00:00
- Post Title: Looking for wav2text converter .....

We all know programs which convert text to speech. Are there any to convert the other way around   Freeware, if I may add and most importantly .... really working
## Post #2
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-04-16T04:02:18+00:00
- Post Title: Looking for wav2text converter .....

The only one I can think of is in the retail side of the software industry: Dragon Naturally Speaking.  I know Various games have implemented Speech to Text but it's usually implemented directly into the game's installation (pc's) or directly into the game engine (consoles).
## Post #3
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2008-04-19T23:52:54+00:00
- Post Title: Looking for wav2text converter .....

You can't take a audio file and have a program write the words to a text file or any other file.  Each byte in the file represents a specific tone, which gets played through your speackers. So some ones voice could be any tone in the world. But im sure you could do it if there wasn't any background noise.
## Post #4
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-04-20T21:24:44+00:00
- Post Title: Looking for wav2text converter .....

> Reply from grimdoomer
>
> You can't take a audio file and have a program write the words to a text file or any other file.  Each byte in the file represents a specific tone, which gets played through your speackers. So some ones voice could be any tone in the world. But im sure you could do it if there wasn't any background noise.

Not true.  To be technical, there are two important things to consider with an audio file (waveform) the bit depth, and the sampling frequency.  Today's standard is based on the Nyquist theorum: sampling frequency = double the range of human hearing which is ballparked at 20hz to 20,000 hz (hertz = cycles per second aka frequency) bit depth determins how many bits it takes to define a singular sample.  multiply this by the number of samples per second you're recording at (usually the standard today would be 44,100 samples per second) and then again by the length of the audio file to get the actual file size.  It takes multiple samples to create a cycle for any complex waveform.  Speech recognition software is pretty complex but it definitely exists.  Like I said above, Dragon Naturally speaking is the only software I can think of that does it, and it's expensive.

[http://www.nuance.com/naturallyspeaking/](http://www.nuance.com/naturallyspeaking/)

The reason it gets that expensive is because they make the software interface with other applications like Outlook, Word, and more advanced features might include recognizing functions to do actions by voice in Access or Excel.  If this is what you're looking at doing, I'd recommend it.  However, it only works via live interaction.
If you're looking at doing some advanced archiving like taking audio files from a game, and saving a text file next to each one with the dialog, or even just saving a text file with the dialog from each wave file, you could cue up all the audio files into a media player, and change the input of the Naturally Speaking software to listen to all audio input from the OS.  It's definitely possible, I've had to do this for several mods in the past.
