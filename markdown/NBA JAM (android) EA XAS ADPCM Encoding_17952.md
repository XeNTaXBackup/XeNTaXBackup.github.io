## Post #1
- Username: TheBirchman
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 07, 2018 4:21 am
- Post datetime: 2018-04-09T16:16:57+00:00
- Post Title: NBA JAM (android) EA XAS ADPCM Encoding

Hi all. 

I've been lurking this board and trawling the internet for a couple of weeks looking for answers to my problem and while I've gotten close, I haven't quite cracked it yet. So I figured I'd reach out to the helpful people here. 

Long story short, I'm working on a roster update for the android version of NBA JAM (the game hasn't been updated officially in years). I've figured out how to extract and replace textures and now I'm working on commentary audio. 

Thanks to daemon1 and others, I've been able to successfully identify and decode the audio -- it has a .caf extension, but is actually the EA XAS ADPCM codec. I can now import the audio into an editor like Audacity and edit the files. However, I'm not sure how to encode the audio so that I can re-insert the edited files back into the game. Anytime I've tried, the game crashes when the audio file triggers. 

Any thoughts or suggestions? Any help would be greatly appreciated. 

Let me know if there's anything else that I should provide.

Thanks!
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2018-04-10T06:10:35+00:00
- Post Title: NBA JAM (android) EA XAS ADPCM Encoding

As far as I am aware, I don't believe anyone has actually made an encoder for EA XAS ADPCM, only decoders.
## Post #3
- Username: TheBirchman
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 07, 2018 4:21 am
- Post datetime: 2018-04-10T14:50:17+00:00
- Post Title: NBA JAM (android) EA XAS ADPCM Encoding

Bummer -- that's what I was afraid of. Thanks for the reply, though.

I'm gonna spend some time figuring out if there's a way to use the XAS decoding resources out there to create an encoder (even though I'm still not exactly sure how I'm gonna do that yet). 

I've also just discovered that players added in the most "recent" (like 3 years ago) roster update have uncompressed commentary audio (byte 0 = 2), so I might try messing around with those files first since I wouldn't have to do any codec work, I think. I can import the raw data into audacity as a S16PCM big-endian with a 22050 sample rate and everything sounds good. The problem I've noticed initially is that when I export it as a raw, headerless audio file and compare the hex values to the original, it seems like all the 2byte block values are reversed (which I think means the endianess is backwards?).

Unfortunately, when I try and import the raw audio into Audacity again but this time as little-endian, it's just static noise. 

This is all a bit over my head, so sorry if any of this is incoherent. I'll keep messing around with it, but if anyone has any ideas, let me know -- i'm sure you're all much smarter than me
## Post #4
- Username: jeter17
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 26, 2016 4:34 am
- Post datetime: 2018-07-13T02:16:45+00:00
- Post Title: NBA JAM (android) EA XAS ADPCM Encoding

I got the same problem.. [roll]Do you find the way to solve it?
