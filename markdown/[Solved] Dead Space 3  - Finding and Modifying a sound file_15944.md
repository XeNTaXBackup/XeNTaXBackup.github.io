## Post #1
- Username: monochrony
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 04, 2017 5:21 pm
- Post datetime: 2017-03-04T10:59:09+00:00
- Post Title: [Solved] Dead Space 3  - Finding and Modifying a sound file

hi there,

i'm on a journey that has already cost me quite some hours to figure out. dead space 3 has a very annoying audio bug, that causes ALL kinetic doors ingame to make a constant loud stuttering sound. examples as follows:
[https://youtu.be/XYIYcjbVJFI](https://youtu.be/XYIYcjbVJFI)
[https://youtu.be/KaMFFmIl3U0](https://youtu.be/KaMFFmIl3U0)
[https://youtu.be/t-yI-GQn4WM](https://youtu.be/t-yI-GQn4WM)

1. the actual bug

especially in the first video, you can hear that the stuttering is somtimes interrupted by a fully played sound. my guess is that this sound file is the one that's causing the stutter by being played too fast and repeatedly in a loop. i further think that it's not the actual opening/closing sound of the door, but the turning sound of the valve/handle.

this bug is the bane of my existence and is the sole reason i was never able to finish the game. it doesn't happen in the console version and an ea community manager in the official forums made clear, that they would never fix it. 
so, what i intend to do is finding the specific audio file and muting it.


2. the approach

by stumbling through the forums, i've already managed to find the (rick) tools to unpack the game's bigfiles and to extract the sound files. problem is, i'm yet to find the correct file. it's like finding the needle in the haystack.

there are 6 bigfiles in the installation folder. my approach to this is to delete or replace bulks of audio assets to see if this file is within one of them, while further narrowing down the file's location. for this to work, i have to start and test the game every time i modified and repacked a bigfile. the sound files are are either placed within an .exa.snu format, which are located in bigfile0.viv or within .str packages, of which there are hundreds of them scattered in all bigfiles.

another approach would be to extract virtually every sound file into mp3's, and find a way to compare these to an audio snippet from the youtube video; acoustic fingerprinting. but i have yet to find a tool suitable for that.

3. the problem(s)

i've already found out, that the file is not one of the .exa.snu files in bigfile0.viv\audiostreams\. i've deleted all of them and the annoying sound is still present. as far as i can tell, there are no other snu files. so it has to be within one of the .str packages. i've made some screenshots to show how these are structured:









i'm now in the process of looking at how the .sbk files are named, trying to find all of which that contain "door", "valve" or "open" and "close" and testing them. but it's perfectly possible, that the problematic file is not properly named or is part of another big asset file. for example, i've found one .sbk that contains 744 small audio files, numerically named. i'm not in the mood to listen through all of that, so i'm planning on using my narrowing approach here aswell. but here's another problem: i have yet to find a tool that can repack a bunch of .exa files into the original .sbk file. i can't just rename or replace bigger .sbk files, or they won't repack back into .str properly. small ones can be replaced, though. for extracting, user daemon1 made the tool [ds3_sbk](http://forum.xentax.com/viewtopic.php?f=10&t=12716&hilit=dead+space+3). i now need a way to do the opposite.


for testing purposes, i've already managed to find and mute the sounds of the line gun, by replacing smaller .sbk files with empty ones. so once i've managed to find the file, this should work. if someone is willing to help me solving this bug, i'd very much appreciate that. i've been digging so deep, i can't just stop now. ^^"


EDIT1: i may or may not have found the specific file within the global assets, specifically in \bigfile2.viv\global_assets.str\SBK\0015_global_assets.sbk
that package contains the said 744 audio files. i've uploaded the snippet i took from the youtube video and the sound file to soundcloud, for you to hear: [https://soundcloud.com/monochrony/sets/ ... g-snippets](https://soundcloud.com/monochrony/sets/dead-space-3-door-sound-bug-snippets)

but the initial problem remains. i need to repack all of these files back into an .sbk and i don't know how.

EDIT2: I FUCKING DID IT! YEAH!

turns out, that was indeed the right file. i found it by comparing the file size of the snippet i made from the youtube video to all the .exa sound files in roughly the same size range, then listening through the bunch. after that, i simply hex edited the .str and replaced all strings matching the ones from this .exa with zeroes. simply deleting the segment would change the file size and cause a crash. finally, sweet, sweet silence. no annoying sound bug. 

now, to create a batch patch for all the other poor souls out there, that ea abandoned...

EDIT3: made a small patcher. just download, extract into the installation directory and follow instructions.
download [https://drive.google.com/open?id=0B3Jv9 ... GxVNE5YNjQ](https://drive.google.com/open?id=0B3Jv9BvjwGHtUWNDcGxVNE5YNjQ)
mirror on ModDB: [http://www.moddb.com/games/dead-space-3 ... tutter-fix](http://www.moddb.com/games/dead-space-3/downloads/kinesis-door-audio-stutter-fix)

EDIT4: thanks to user daemon1, i've managed to make a far simpler patch. download link stays the same.
## Post #2
- Username: Krovosos
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 31, 2010 12:28 am
- Post datetime: 2017-04-17T19:47:58+00:00
- Post Title: [Solved] Dead Space 3  - Finding and Modifying a sound file

Thanks so much, that was a problem that has annoyed me a lot!!

I am curious, how did you rip and convert the audio files?
I never quite figured it out.
## Post #3
- Username: monochrony
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 04, 2017 5:21 pm
- Post datetime: 2017-04-18T13:43:44+00:00
- Post Title: [Solved] Dead Space 3  - Finding and Modifying a sound file

i ripped the audio files with a tool (ealayer3) from this thread: [http://zenhax.com/viewtopic.php?f=9&t=437](http://zenhax.com/viewtopic.php?f=9&t=437)
yet the problem was not ripping the audio files, but to apply the edit. when i finally found the correct audio file, i still had no means to repack the .str package, that contained it. so i hex-edited the .str, looking for the specific string that would match the extracted audio. luckily, i found it and replaced the section with zeroes. that's basically like deleting the sound file without messing up the file size of the package. my knowledge on this topic is very basic, and i guess that would have not worked, were the files encrypted or compressed.
