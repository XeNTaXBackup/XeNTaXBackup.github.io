## Post #1
- Username: tomysshadow
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 28, 2016 4:44 pm
- Post datetime: 2017-03-07T06:07:47+00:00
- Post Title: Groove Media Audio codec (WAV container)

Hi, this is my first post here! I've written a couple of converters for some formats before so I'm not a completely incompetent n00b (I would hope, anyway,) specifically the Acme3D IMG texture format, 3D Game Machine 3GM Model File format, Torque DIF format (what a nightmare) and the WBD archive format - I may post these converters here later. In fact I'm surprised I hadn't signed up to this forum earlier. That's besides what this topic is about, however, which is 3D Groove's proprietary Groove Media Audio or GMA format.

I have the benefit of having created a couple 3D models before so I know what to look for when it comes to converting them (position of vertices etc.) but when it comes to audio, I have no idea where to start. I feel kind of bad asking for help converting it when I haven't made much progress myself but I can't find any tutorials or help to describe what I should be looking for when it comes to audio file conversion (as opposed to archive formats which have plenty of such tutorials.)

GMA is clearly a compressed format - when importing it as if it were a raw PCM stream, the clip is way shorter than expected (and is just a bunch of noise that sounds nothing like how it's supposed to regardless of codec, bits, sample rate etc. to import.) The file extension is WAV, but there is no RIFF header - instead it seems to begin with the magic key GMA0. There is a short header, which seems to vary from game to game but doesn't seem to contain any easily recognizable numbers (such as 44100 etc.) and I can't even really tell if it's little or big endian - I'm guessing it's little endian but it's really hard to tell since there aren't a lot of null bytes anywhere.

By looking at the strings in the game engine I was able to deduce some interesting facts about the format. There are error messages in the 3D Groove game engine code along the lines of "ERROR: Unsupported 8-bit sample size: This sound file must have a 16-bit sample size to be compressed as a GMA file. Please use a sound editting tool to upsample the sound file from 8-bits to 16-bits" and "ERROR: Unsupported number of channels: This sound has more than 2 channels of sound." It can definitely have a sample rate of 11kHz, 16kHz, 22kHz, and I'm guessing based on the code the maximum sample rate is 44100Hz. I'm probably not going to be skilled enough to actually see what the disassembled code is doing and write a converter around that though.

I've linked a couple examples (since it won't let me attach a WAV or a ZIP file) as well as what I believe they should sound like in a FLAC format (but don't take that data as gospel because I only accomplished this by recording the sound from my computer speakers, so the volume and any number of other minor things may be off.) One is taken from the game Penguin Racers and the other is taken from the game Battle of the Planets - Zoltars Revenge, both of which were free online games. If more examples are needed please say so.

[http://k003.kiwi6.com/hotlink/wxdckwfuq ... _Files.zip](http://k003.kiwi6.com/hotlink/wxdckwfuqf/GMA_Audio_Files.zip)

I'd really like help to be able to convert these but I realize compression may make this difficult. I'm genuinely interested in learning how to do this, even just a point in the right direction to get started. Thanks in advance.
## Post #2
- Username: tomysshadow
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 28, 2016 4:44 pm
- Post datetime: 2019-06-17T11:31:10+00:00
- Post Title: Groove Media Audio codec (WAV container)

This is a big necropost, to say the least, but, I have finally figured this out by myself and wrote a converter, as a C++ command line application.

[https://github.com/tomysshadow/Groove-M ... -Converter](https://github.com/tomysshadow/Groove-Media-Audio-Converter)
