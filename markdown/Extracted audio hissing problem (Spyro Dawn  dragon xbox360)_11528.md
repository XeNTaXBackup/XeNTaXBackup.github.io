## Post #1
- Username: mgrandi
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 20, 2014 1:55 pm
- Post datetime: 2014-05-21T07:35:45+00:00
- Post Title: Extracted audio hissing problem (Spyro Dawn  dragon xbox360)

This is continuation of this topic here: [viewtopic.php?f=10&t=9909](http://forum.xentax.com/viewtopic.php?f=10&t=9909), since both games are made by the same developer (Étranges Libellules), and while that topic is about a different game, it seems that Étranges Libellules used the same engine / file formats between both games.

So, the game is Spyro: Dawn of the Dragon for xbox 360. This topic is covering the audio if the game, where if you have the game files, the music and sound effects are located in <RootFolder>/Data/MUSIC (duh).

The music / sound effects appear to be in this RWS format, which was described briefly in the topic i linked. RWS apparently stands for Renderware Sound, It appears to be in a lot of other games, like grand theft auto, but the 'versions' seem to differ wildly and i'm not sure if that would be any help.

Like the previous topic said, these RWS files appear to be just plain PCM audio data, 16 bit signed, little endian, stereo, 44100Hz (note: the linked topic says its big endian, which is incorrect at least for this game!). 

However, the RWS file appears to have a header (with some interesting strings like 'QBSubStream' that don't show up in any searches that i made to google) followed (or padded with) a bunch of 0xAB bytes, followed by audio data, a block of NULL bytes, then more audio data, rinse and repeat. 

----------------------------------------

Header: The data before the 0xAB bytes is 303 bytes long, the 0xABAB bytes go until byte 2036. The previously linked topic says the header goes 12 bytes past the 0xABAB, which takes it to byte 2047. Seems to end on a nice number at least (1 less then 2048).
Screenshot: [http://imgur.com/uj9RtcZ](http://imgur.com/uj9RtcZ)

Audio Data: This is where the actual stuff we care about is. After the header starting at byte 2048, it seems to be 0x801c (32796 decimal) bytes long of audio data, then 0x7e4 (2020) NULL bytes. This repeats with the same amount of audio and NULL data until the very of the file, where it ends with < 0x801c bytes of sound data and then the rest of the file is just NULL bytes (more then the usual 0x734 however)

Extracting the audio: So this is pretty simple, apparently you just get rid of the header and the NULL bytes, then you get a raw pcm file that you can do what you want with! I wrote a script to do just this, and as to run it through a program called 'sox' to convert the pcm data to a normal wav. The script is here: (requires python3 and the program 'sox' in your path) [https://gist.github.com/mgrandi/b1ce0f77d20e834de219](https://gist.github.com/mgrandi/b1ce0f77d20e834de219) . It works fine, and you can hear the sounds / music!

The problem:  However, the problem is that there is a faint 'hissing' sound throughout the track, and is very very apparent when the music/sound is at a soft spot or has a fade in / fade out. Sort of an example of the 'outputted' wav (or even pcm, its the same graph) loaded into audacity: [http://imgur.com/sVG1prF](http://imgur.com/sVG1prF) , you can see the very end, that part of the track is supposed to be pretty much silent, but there is just this hissing that is making it from being 'truly' silent

So I'm very confused on what going on here, I'm not an audio expert, and while I have tried some various sound editing tricks to try and get rid of it, I'd rather just get the 'source' audio working and not have to edit it (because editing isn't perfect, as noise gate / low pass filter only really works when its silent, but you can still tell that the hissing is there throughout the song when its not silent and you really can't rid of that). 

When playing the game in the xbox 360 the sound obviously does not have a hiss, so I'm wondering if the Xbox / game engine is doing some sort of filtering on the audio before it plays it, and its not just playing the raw audio data its loading from the disc, but that doesn't seem plausible because why would it waste cpu cycles on that when it could use it for other things, like the game itself! So its probably that I am just 'extracting' the audio wrong, but as far as I can tell no one else has tried to extract the audio from RWS files, so I have no working code to reference.

I obviously cannot post the files here as per forum rules, but I can answer any questions about it / post screenshots of hex editor if need be.

~Mark
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2014-05-23T07:31:58+00:00
- Post Title: Extracted audio hissing problem (Spyro Dawn  dragon xbox360)

Well, I would leave sox out of it just incase it does something slightly incorrectly and open the raw pcm data directly in audacity or any other audio editor supporting raw given paramters and check the audio repeatedly using various values as there is multiple pcm encoding methods besides the most common 16 bit.

As for RWS, it has a history of having contained various forms of ADPCM depending on platform even besides just PCM making it tough to support globally.
## Post #3
- Username: mgrandi
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 20, 2014 1:55 pm
- Post datetime: 2014-06-09T10:12:48+00:00
- Post Title: Extracted audio hissing problem (Spyro Dawn  dragon xbox360)

> Reply from Apollo
>
> Well, I would leave sox out of it just incase it does something slightly incorrectly and open the raw pcm data directly in audacity or any other audio editor supporting raw given paramters and check the audio repeatedly using various values as there is multiple pcm encoding methods besides the most common 16 bit.

As for RWS, it has a history of having contained various forms of ADPCM depending on platform even besides just PCM making it tough to support globally.

I actually emailed the person who worked on the RWS2WAV script, since he seemed to know the most about the format, and he seems to agree that RWS is comparable to the AVI format, where there is the container, but you don't actually know what type of data is inside it. 

I actually just solved my problem, and it was kind of stupid on what the problem actually was. the forum post that i linked to suggested skipping the first 2048 bytes, but when i did that, i got garbled audio, so on a whim i tried 2047 bytes and got 'recognizable' audio, but with the hissing. I looked on the wiki page for Broken Sword 3 which also uses the RWS format ([http://wiki.xentax.com/index.php?title= ... Dragon_RWS](http://wiki.xentax.com/index.php?title=Broken_Sword_-_The_Sleeping_Dragon_RWS)) and once i actually parsed the file how it was meant to be read, i realized that the 2048th byte is actually part of the container format, and not part of the audio.

So this left me with the data i had, but it was still garbled. On a whim i guessed maybe it was somehow not aligned correctly, so I just added a 0x00 byte to the end of the raw PCM data i extracted, and now it works perfectly! Audio data is....picky >.>

TLDR: SOLVED

Anyway,  I will be updating / creating a wiki page for this game (at least for the audio, as a start) and link my code once I cleaned it up a bit. I will probably also be creating a general 'RWS' format page to further distinguish that RWS is a container format, and the Audio data really depends on the platform its running on, and what engine they use, etc. For example, the BS3 audio is IMA ADPCM which some wonky compressed format, but then this game its just raw PCM data that I can load into audacity. 

It would also probably be good to start on the RWS wiki page (once i start it), the 'RWS chunk version' numbers, since they seem to be vastly different for every game, i'm not sure if they actually mean anything. BS3 has a version number of '0x1803ffff' (402915327) while spyro dawn of the dragon has '0x6500021C' (469893221)
