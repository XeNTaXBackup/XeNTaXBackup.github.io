## Post #1
- Username: Bioscope
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Mar 26, 2007 9:43 pm
- Post datetime: 2009-08-06T15:16:09+00:00
- Post Title: Baldurs Gate Dark Alliance  PS2 extracted .vag

Help!!! I manage to extract music, sounds and dialogs from the .VAT files in the folder named DATA\BG using Cube or ADPCM player, and calculate the interleave using MFAUDIO. When I play the adpcm music file, it plays clearly, but with an irritating popping sound in the background. Now I know that all the old SCE games have been succesfully ripped before, BGDA, BGDAII, CHAMPIONS OF NORRATH etc. So what am I doing wrong here? Is it copy protection perhaps?

I hope I wont have to use hex editor here, cause I'm still a noob in that respect. Are there other tools out there that extract vags?

BTW, I can't line in, cause the sound menu doesn't take the ambient sounds away....
## Post #2
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2009-08-07T12:02:42+00:00
- Post Title: Baldurs Gate Dark Alliance  PS2 extracted .vag

Okay i guess -  its a hdd error or maybe your videocard...

Bioscope we need an "EXAMPLE" uplaod a file
## Post #3
- Username: Bioscope
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Mar 26, 2007 9:43 pm
- Post datetime: 2009-09-11T04:05:19+00:00
- Post Title: Baldurs Gate Dark Alliance  PS2 extracted .vag

sorry i meant that the ps2 audio options menu doesnt fully remove the ambience when dialed down.
## Post #4
- Username: Bioscope
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Mar 26, 2007 9:43 pm
- Post datetime: 2009-10-28T03:27:03+00:00
- Post Title: Baldurs Gate Dark Alliance  PS2 extracted .vag

At last!

Sorry, guys... I got it to work, thanks to Luigi Auriema's VAGGUESS. I extracted a bunch 32000 .ss2 files from each of the .vat archives, converted with MFAUDIO then it was a case of matching up the frequency with gameplay audio (24000) and upsampling to 44100. No more popping sounds. So now I have a rip with no sfx or background ambience.
