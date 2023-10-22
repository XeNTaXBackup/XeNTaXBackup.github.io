## Post #1
- Username: mr rocket
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 15, 2015 4:15 am
- Post datetime: 2015-09-07T18:44:41+00:00
- Post Title: Godzilla Unleashed (Wii) - MusyX Samp and Uber files

Hello, I've been looking for a way to extract the audio from Godzilla Unleashed and, if possible, reimport new sound effects to replace the ones currently ingame. My main goal is to simply extract all the SFX, but I have a friend who would love to be able to replace each monster's SFX with movie accurate SFX as the Atari Godzilla games aren't really known for being accurate to the movies.

Here are the SFX: [http://www.mediafire.com/download/djhd5 ... UAudio.rar](http://www.mediafire.com/download/djhd5k8cd37bpv4/GUAudio.rar)

I've done a search around the internet to see if I could find anything useful and I came across a PHP script that can extract the SFX from Gamecube games using the MusyX sound engine.

Here's a link to the PHP script: [https://dl.dropboxusercontent.com/u/484 ... xtract.php](https://dl.dropboxusercontent.com/u/48454461/misc/MusyXExtract.php)

The author of the script also made a Python script: [https://dl.dropboxusercontent.com/u/484 ... Extract.py](https://dl.dropboxusercontent.com/u/48454461/misc/MusyXExtract.py)

I've tried to extract the Godzilla Unleashed SFX with the PHP script but it requires a .sdir file which is probably contained within the Uber files after looking through the file with a Hex Editor.

I was thinking either the script could be modified to extract these Uber files or the .sdir file can somehow be extracted from the Uber file.

Any help is appreciated!
## Post #2
- Username: antidote
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Apr 02, 2010 11:37 pm
- Post datetime: 2016-06-26T05:37:42+00:00
- Post Title: Godzilla Unleashed (Wii) - MusyX Samp and Uber files

I apologize for the necrobump, but just in case the OP is interested this is definitely MusyX data, looks like the proj, pool and sdir are indeed embedded in here.

On top of that we have either sample, or macro names, which is really neat! We have a MusyX re-implementation but unfortunately it doesn't directly support this format:
[https://github.com/AxioDL/amuse/releases](https://github.com/AxioDL/amuse/releases)
