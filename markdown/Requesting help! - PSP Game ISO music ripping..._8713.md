## Post #1
- Username: becomingthebeast
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 08, 2012 10:10 am
- Post datetime: 2012-04-08T02:24:59+00:00
- Post Title: Requesting help! - PSP Game ISO music ripping...

Hello!

I'm Victor, from Mexico.

Thanks for taking the time to read these words.

I hope somebody here can point me into the right direction...as I've been researching for 2 days with no success.

I've been always interested in ripping games soundtracks...
So, when I found that it was possible to rip out the audio files from a PSP iso DUMP... I got really interested and started my research for this task.

I got a bunch of tools that enable me to do this, such as: Dragon unpacker, HIMDRenderer, ATRAC3 codecs...

So well, I managed to successfully rip the music from a couple of games ( Rengoku and Rengoku 2 ) 

Then...since I love the retro gaming, I tried to rip music from the SNK Arcade Classics PSP game.
I dumped the ISO, and started the extraction...

In this case I found ".POD" files for each of the games.

I went straight for "LASTRESORT.POD"... and started the file analysis.
Dragon Unpacker reported 19 "WAV" files.

Of these 19 files...4 were ready to play straight out from the box...(FOO BAR player reported them as "Atrac3" files ??).
However the rest of the files are not recognized by almost ANY software I have tried: Goldwave, Audacity, most media players....?

When I open those files in hex editors, I see the following:

     1. The playable files header look like:
         RIFF XXX WAVEfmt

     2. The ones that won't play look like:
         RIFF XXX WAVEfmt 4 <- this 4 is different...? what is that "4"
telling?

     3. I can also see that the distance between "fact" and "data" words vary between the playable and unplayable files.

I have read something about the Atrac3 format...it appears that there also exists an "Atrac3Plus" encoding which is uncommon.
I have also read some cases of "bad headers", but I'm quite lazy to study the RIFF WAVE file format...(at least for now).

So, I kindly as for your advice, if you have any...do you have a clue about how to convert or interpret these files correctly...or if you can explain what is going on?

I tried to attach a file, but the forum won't let me.
If you are interested please PM me with your email.

Thank you!
## Post #2
- Username: becomingthebeast
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 08, 2012 10:10 am
- Post datetime: 2012-04-08T05:24:08+00:00
- Post Title: Requesting help! - PSP Game ISO music ripping...

I uploaded one of the unplayable files... here's the link:

[http://becomingthebeast.com/h3ll/LRESORT_00002.wav](http://becomingthebeast.com/h3ll/LRESORT_00002.wav)

Please, help relief my frustration 

Thanks!
## Post #3
- Username: becomingthebeast
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 08, 2012 10:10 am
- Post datetime: 2012-04-08T08:12:05+00:00
- Post Title: Requesting help! - PSP Game ISO music ripping...

Finally!

Got it working!

Steps:

1. Download SonicStage App from Sony...

[http://forums.sonyinsider.com/files/fil ... e-edition/](http://forums.sonyinsider.com/files/file/95-sonicstage-43-ultimate-edition/)

You have to register in the forums.

2. The extracted "unknown-raw-ugly-unplayable" files should be converted to SFaa3 - Sound Forge AA3 format, using:

Atrac3Plus Tool

...provided here by Cozy:
[viewtopic.php?f=17&t=6591](http://forum.xentax.com/viewtopic.php?f=17&t=6591)

Thanks for that tool Cozy!

3. Once those files are converted, you gotta import them to SonicStage app...you should be able to play them.

4. Once imported in SonicStage...you can convert them to a more friendly format, such as the big, common, plain, WAV...!

...and that's it!!!

 

I spent like 24 continue hours of research, reading, try and learn, installed LOTS of different tools...but finally...got it work...
however, I don't really understand much about the Atrac3 formats and what is the first format I am getting.

It's very misleading, because some of the extracted audio files are already playable, while others are immediately not.

So I hope this helps another newbie.

Thanks to all those who posted useful tools to make this happen
