## Post #1
- Username: anakinator
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 01, 2023 7:41 pm
- Post datetime: 2023-08-01T12:21:43+00:00
- Post Title: Sound format *.sfx

Hello, I'm a beginner and I'm writing to you through a translator. Sorry if my question is unclear, I will try to clarify.
I am analyzing the game "Pirates of the Caribbean: At World's End". Initially, in the game directory, files with dialogs (voice acting) are packed into archives with the extension "*.000"
With the help of game extractor, I extracted files in the format "*.sfx". I found out that this is a sound, that is what I need.
However, it does not work to convert to ".wav" or ".mp3" and it cannot even listen to more than one player. Either it doesn't open, or it hisses.
After studying the forum a bit, I came across the "VGMstream" plugin for "foobar," the file opens, but it plays very very quickly, like a cartoon voice. If you slow down through "audacity", then you can hear speech, but of terrible quality.
Can you tell me how to solve this problem? Maybe I'm doing something wrong?
I attach a couple of files "*.sfx".  
[https://dropmefiles.com/LQZiS](https://dropmefiles.com/LQZiS)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-08-01T15:30:13+00:00
- Post Title: Sound format *.sfx

You can use this tool [https://github.com/eurotools/eurosound-explorer](https://github.com/eurotools/eurosound-explorer)

It doesn't have native support for your samples (file version 10 is not supported apparently),
but if you go to File > Decode Audio File and you'll select Eurocom ADPCM format from the list,
you'll be able to convert your samples to proper WAV files.

By the way, format is described here [http://wiki.xentax.com/index.php/EngineX_SFX](http://wiki.xentax.com/index.php/EngineX_SFX)
## Post #3
- Username: anakinator
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 01, 2023 7:41 pm
- Post datetime: 2023-08-01T15:56:27+00:00
- Post Title: Sound format *.sfx

Thank you, I downloaded it, but I can't figure out how to run it? I don 't see the file .exe to run... Is the launch done through some other program?
## Post #4
- Username: jmarti856
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-08-01T15:58:05+00:00
- Post Title: Sound format *.sfx

You should download a latest release from this link
[https://github.com/eurotools/eurosound- ... oSound.zip](https://github.com/eurotools/eurosound-explorer/releases/download/2.0.6/EuroSound.zip)
## Post #5
- Username: anakinator
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 01, 2023 7:41 pm
- Post datetime: 2023-08-01T16:36:54+00:00
- Post Title: Sound format *.sfx

I do not know what to tell you or how to tell you. But you're just a genius! I ran the *.sfx file through EuroSound, it switched to the *wav format. You are simply the best, insanely grateful!
So far, there are no questions left, I hope there will be no new ones
## Post #6
- Username: jmarti856
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Aug 29, 2015 8:45 pm
- Post datetime: 2023-09-03T10:18:12+00:00
- Post Title: Sound format *.sfx

Hello!

I'm the author of the EuroSound Explorer tool, glad that you find it usefully. 

Unfortunately I've only been able to add support until version 6, Pirates of the Caribbean: At World's End if I'm not wrong uses the version 8 of the MusX file format. 

I will try to add support to it in a near future, I hope.
## Post #7
- Username: anakinator
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 01, 2023 7:41 pm
- Post datetime: 2023-09-04T22:56:15+00:00
- Post Title: Sound format *.sfx

In any case, my goal was achieved. Thank you for your program!
