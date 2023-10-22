## Post #1
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2018-05-01T10:03:03+00:00
- Post Title: New tool to extract audio from Civ 6 (and maybe other games)

I have written a tool to help with extracting audio (e.g. the awesome music) from Civilization 6.
The Windows binary is attached to this post and the source code can be found at [https://github.com/jonwil/soundextract](https://github.com/jonwil/soundextract)
Other than the win32 UI stuff, the rest of the code is all standard C++ (or at least it should be) so it should be possible to make the core code work on Linux or Mac if you want to and you have the programming skills to do so (I dont use Linux or Mac so I wont be doing it). Note also that its only tested on the data files from the Windows version of Civilization 6 (it may not work on the other platform data files since I dont have those). Oh and it may work on other games if the files are the same (same format, same xml files, same layout etc) but I have no other games to test it on.

To use it, start the program and press the "open" button. Under the Civ 6 install folder navigate into base or into one of the folders under DLC and look for a "platforms" folder. Then go into that folder then into "windows" then "audio" (if there is no "audio" folder, that DLC has no audio). Under the "audio" folder (and the language specific folders within that, if they exist) there will be 1 or more xml files. Open one of these.

You will then see a list of all the audio within that particular sound bank (either stored loose as wem files or stored inside the bnk file). Select one and press "extract" and then save it to the location you want. Right now it extracts it as a wem file (to be converted via ww2ogg if its using Vorbis audio or via other tools if its using ADPCM or PCM audio) but I am planning to add proper conversion for all 3 codecs (so my tool will do the same thing as ww2ogg does for example) in a future version.

The advantage of this new tool is that it gives all the audio files within the bank a proper name (no more need to use a bnk extraction tool to extract the sounds embedded in the bank and no more need to try and guess which .wem file (loose or extracted) is the one you want by looking at the xml or txt files, soundextract will take care of giving the sound files a proper name and extracting the data from the bnk file if need be.
[soundextract.zip](https://xentaxbackup.github.io/file/14304_soundextract.zip)
## Post #2
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2018-05-03T13:14:43+00:00
- Post Title: New tool to extract audio from Civ 6 (and maybe other games)

Now soundextract converts the wem file properly to an ogg file or wav file (depending on the codec).
Source code is updated as well.

Much easier way to do this stuff than to try and figure out what wem file you need, use a bank extraction tool to extract it if its in a bank then run ww2ogg/revorb if its using ogg, an adpcm tool if its using adpcm or a pcm tool if its using pcm. Soundextract incorporates the bank extraction tool, ww2ogg, revorb, adpcm stuff and pcm stuff plus automatically giving useful names to the sounds rather than numbers.
[soundextract.zip](https://xentaxbackup.github.io/file/14311_soundextract.zip)
